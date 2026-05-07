---

copyright:
  years: 2025
lastupdated: "2026-05-07"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Data integration
{: #solution-data-integration}

## Overview
{: #solution-data-integration-overview}

This guide presents three integration patterns for consuming SAP data in IBM Cloud environments while maintaining compliance with SAP's usage terms and conditions. Each pattern is optimized for specific use cases—from real-time queries to complex analytics and ML workloads.

### Key Principles
{: #solution-data-integration-overview-key-principles}

All patterns follow these core principles:

* **Compliance-First**: Use SAP-approved APIs and methods (e.g., OData, SAP BDC Connect); avoid unauthorized database access or permanent replication of original SAP data
* **Zero-Copy Preferred**: Minimize data movement to reduce costs and complexity where possible
* **Consume and Materialize**: SAP data can be consumed via approved connectors and temporarily materialized in third-party systems (like watsonx.data) for performance optimization—caching data to speed up queries without constantly accessing SAP sources
* **Enrich and Transform**: Materialized data can be enriched through joins, AI processing, ML predictions, and integration with external data sources; enriched/transformed data can be stored indefinitely as it becomes distinct from original SAP Data Products
* **No Downstream Distribution**: Data cannot be distributed to subsequent systems outside the approved ecosystem; third-party systems serve as processing endpoints, not pass-through pipelines
* **Flexible Architecture**: Support diverse use cases from agentic AI to business intelligence while maintaining SAP compliance

## SAP Data Integration Patterns
{: #solution-data-integration-patterns}

This guide presents three complementary patterns for SAP data integration:

### Pattern 1: API-Based Integration (OData)
{: #solution-data-integration-patterns-pattern1}

- **Description**: Direct, real-time API access to SAP data
- **Data Movement**: None—consume on-demand
- **Complexity**: Low
- **Cost**: Low
- **Best For**: Real-time queries, agentic AI, conversational queries, low-volume access
- **Example**: Customer service chatbot querying order status

### Pattern 2: Zero-Copy Data Access via watsonx.data
{: #solution-data-integration-patterns-pattern2}

- **Description**: Federated queries without physical data movement; access SAP data where it lives using open standards
- **Data Movement**: Minimal/None
- **Complexity**: Medium-High
- **Cost**: Medium
- **Best For**: Large-scale analytics, federated queries, multi-source integration, cost-sensitive scenarios
- **Example**: Cross-system financial consolidation
- **Three sub-patterns:**
    - **2A - Native Connectors**: Standard federated queries using built-in watsonx.data connectors
    - **2B - Streaming Integration**: Near-real-time analytics with event-driven architectures using Kafka/Confluent Cloud streaming SAP CDC events to Iceberg tables (e.g., TableFlow, custom Kafka consumers)
    - **2C - Delta Sharing**: True zero-copy access using SAP Datasphere and Delta Sharing protocol
  
- For streaming integration (Pattern 2B), SAP systems require partner add-ons to be able to send events to Kafka brokers like Confluent or IBM Event Streams.
- The Delta Sharing protocol integration is currently under development by the watsonx.data team. Please refer to [watsonx.data documentation](https://cloud.ibm.com/docs/watsonxdata) for the latest availability information.
{: note}

### Pattern 3: Data Enrichment in watsonx.data Fabric
{: #solution-data-integration-patterns-pattern3}

- **Description**: Selective data extraction with temporary materialization; enrich with ML predictions, external data, and derived metrics
- **Data Movement**: Selective
- **Complexity**: High
- **Cost**: High
- **Best For**: ML/AI training, complex transformations, multi-source integration, predictive analytics
- **Example**: Customer churn prediction with enriched features

In practice, some clients replicate SAP data to a staging database before performing enrichment or running ETL scripts. This approach can provide additional flexibility for data transformation workflows and reduce load on the SAP system during complex processing operations.
{: note}

**Selecting the Right Pattern:**

Choose your pattern based on your primary use case and requirements:

- **Pattern 1 (API-Based)** is ideal when you need real-time data access for conversational AI, chatbots, or low-volume queries where data freshness is critical and you want to avoid any data storage.

- **Pattern 2 (Zero-Copy)** is best for large-scale analytics where you want to minimize data movement and storage costs. Choose the sub-pattern based on your specific needs:
    - Use **2A (Native Connectors)** for standard batch analytics with built-in watsonx.data connectors
    - Use **2B (Streaming)** for near-real-time or event-driven analytics requiring continuous data updates
    - Use **2C (Delta Sharing)** when you have SAP Datasphere and want true zero-copy access with SAP-native governance

- **Pattern 3 (Enrichment)** is the right choice when you need to combine SAP data with ML predictions, external data sources, or complex transformations that justify temporary data materialization and storage.

Many organizations use multiple patterns simultaneously—for example, Pattern 1 for real-time queries, Pattern 2 for analytics, and Pattern 3 for ML model training.

---

## Pattern 1: API-Based Integration (OData)
{: #solution-data-integration-pattern1}

### Overview
{: #solution-data-integration-pattern1-overview}

Direct API access to SAP data for real-time queries. Data is consumed on-demand without storage, making it ideal for agentic AI and low-volume access scenarios.

**When to Use This Pattern:**
- ✅ Real-time data freshness is critical
- ✅ Low-volume access (< 1000 queries/day)
- ✅ Agentic AI conversational queries
- ✅ Minimal infrastructure preferred
- ❌ Avoid for high-volume analytics or complex joins

### Use Cases
{: #solution-data-integration-pattern1-usecases}

**Real-World Examples:**
- **Customer Service Chatbots**: Query order status, delivery information, or customer details in real-time
- **Sales Agent Tools**: Check inventory availability, pricing, or customer credit limits during sales calls
- **Executive Dashboards**: Display live KPIs and metrics without data replication
- **On-Demand Reports**: Generate financial or operational reports with current data

### Architecture
{: #solution-data-integration-pattern1-architecture}

**Architecture Diagram:**

![SAP Data Integration Pattern 1](../images/data/SAP-data-integration-pattern-1.svg){: caption="SAP Data Integration Pattern 1" caption-side="bottom"}

**Architecture Components:**

**Supporting IBM Cloud Services:**
- **watsonx.ai / watsonx.orchestrate**: AI runtime for agentic workflows and LLM processing
- **Code Engine**: Serverless compute for API integration layer and custom logic
- **API Connect** (optional): API management, rate limiting, and security policies
- **Databases for Redis** (optional): Caching layer for improved performance
- **Secrets Manager**: Secure storage for SAP credentials and API keys

**Network Connectivity:**

For detailed network connectivity options, see [Integration Overview](../integration/integration-overview.md).

- **Public Internet**: Simple setup for non-production or low-security requirements
- **Direct Link**: Dedicated, high-bandwidth connection for production workloads
- **VPN**: Encrypted tunnel over internet for secure connectivity
- **SAP Private Link**: SAP's private connectivity service for secure, private connections between SAP BTP and hyperscaler services without internet exposure

**Authentication Methods:**
- **OAuth 2.1** (recommended): Modern, token-based authentication with enhanced security
- **Basic Auth**: Simple username/password authentication (use only for development)
- **Certificate-based**: Mutual TLS authentication for highest security requirements

### Considerations
{: #solution-data-integration-pattern1-considerations}

**Advantages:**
- ✅ **SAP Compliant**: No data storage, fully compliant with SAP usage terms
- ✅ **Real-Time Access**: Always queries live data from SAP
- ✅ **Low Cost**: Minimal infrastructure and storage costs
- ✅ **Simple Architecture**: Easy to implement and maintain

**Limitations:**
- ⚠️ **Network Latency**: Each query requires a round-trip to SAP
- ⚠️ **API Rate Limits**: Subject to SAP API throttling and quotas
- ⚠️ **Limited Analytics**: Not suitable for complex joins or aggregations
- ⚠️ **Availability Dependency**: Requires SAP system to be available

**Best Practices:**
- **Security**: Use OAuth 2.1 for authentication; store credentials in Secrets Manager
- **Performance**: Cache reference data intelligently; optimize queries with OData options
- **Resilience**: Implement retry logic with exponential backoff; add circuit breakers
- **Monitoring**: Track response times, error rates, and API quota usage
- **Error Handling**: Provide graceful degradation when SAP is unavailable

---

## Pattern 2: Zero-Copy Data Access via watsonx.data
{: #solution-data-integration-pattern2}

### Overview
{: #solution-data-integration-pattern2-overview}

Access SAP data without physical movement using watsonx.data and open standards (Iceberg, Delta Sharing). Data stays in SAP while enabling federated queries, making it ideal for large-scale analytics and multi-source integration.

**When to Use This Pattern:**
- ✅ Large-scale analytics workloads
- ✅ Multi-source data integration (SAP + non-SAP)
- ✅ Cost-sensitive scenarios (minimize storage)
- ✅ Need to combine data from multiple sources
- ❌ Avoid for simple queries or extensive transformations

**Three Sub-Patterns:**
- **2A - Native Connectors**: Standard federated queries with built-in watsonx.data connectors
- **2B - Streaming Integration**: Near-real-time analytics with event-driven architectures
- **2C - Delta Sharing**: True zero-copy access using SAP Datasphere and Delta Sharing protocol

### Use Cases
{: #solution-data-integration-pattern2-usecases}

**Real-World Examples:**
- **Cross-System Financial Consolidation**: Combine financial data from multiple SAP instances and external systems for enterprise-wide reporting
- **Customer 360 Views**: Integrate SAP customer data with CRM, social media, and support systems for complete customer intelligence
- **Supply Chain Analytics**: Analyze supply chain data across multiple SAP instances, IoT sensors, and external logistics providers
- **Multi-Cloud Analytics**: Federate queries across SAP on IBM Cloud and data in other cloud platforms

### Architecture
{: #solution-data-integration-pattern2-architecture}

**Architecture Diagram:**

![SAP Data Integration Pattern 2](../images/data/SAP-data-integration-pattern-2.svg){: caption="SAP Data Integration Pattern 2" caption-side="bottom"}



**Architecture Components:**

**Supporting IBM Cloud Services:**
- **watsonx.data**: Lakehouse platform with Presto query engine for federated queries
- **watsonx.ai**: AI/ML workloads and model training on federated data
- **Cloud Object Storage**: Storage for query results and metadata caching
- **Event Streams** (for 2B): Managed Apache Kafka for streaming SAP CDC events
- **VPC**: Secure network isolation for data access

**Network Connectivity:**

For detailed network connectivity options, see [Integration Overview](../integration/integration-overview.md).

- **Direct Link** (recommended): Dedicated, high-bandwidth connection for production workloads
- **VPN**: Encrypted tunnel for secure connectivity
- **SAP Private Link**: SAP's private connectivity service for secure, private connections between SAP BTP and hyperscaler services without internet exposure

**Authentication Methods:**
- **OAuth 2.1**: Token-based authentication for SAP APIs
- **Certificate-based**: Mutual TLS for highest security
- **RBAC**: Role-based access control in watsonx.data

### Considerations
{: #solution-data-integration-pattern2-considerations}

**Advantages:**
- ✅ **Zero-Copy Access**: Especially with Delta Sharing, no data duplication
- ✅ **Scalable**: Handle large-scale analytics workloads efficiently
- ✅ **Multi-Source**: Combine SAP and non-SAP data in single queries
- ✅ **Cost-Effective**: Minimize storage costs with open standards

**Limitations:**
- ⚠️ **Complex Setup**: Requires watsonx.data infrastructure and configuration
- ⚠️ **Network Dependency**: Query performance depends on network latency
- ⚠️ **Infrastructure Required**: Need watsonx.data platform

**Best Practices:**
- **Sub-Pattern Selection**: Choose 2A for simplicity, 2B for real-time needs, 2C for true zero-copy with Datasphere
- **Network**: Use Direct Link for production workloads to minimize latency
- **Caching**: Implement intelligent caching for frequently accessed data
- **Security**: Use least privilege access controls and comprehensive audit logging
- **Monitoring**: Track query performance, network latency, and resource utilization

---

## Pattern 3: Data Enrichment in watsonx.data Fabric
{: #solution-data-integration-pattern3}

### Overview
{: #solution-data-integration-pattern3-overview}

Selective data movement from SAP to watsonx.data for enrichment with ML predictions, external data, and derived metrics. Data is temporarily materialized for processing, making it ideal for AI/ML workloads and complex transformations.

**When to Use This Pattern:**
- ✅ ML/AI model training and inference
- ✅ Complex data transformations
- ✅ Multi-source data blending
- ✅ Derived metrics and KPIs
- ❌ Avoid for simple queries or strict data residency requirements

**Key Considerations:**
- Requires data lifecycle management with retention policies (e.g., 7 days for temporary SAP data)
- Higher storage costs than Pattern 2, but justified by enrichment value
- Enriched/transformed data can be stored indefinitely per SAP usage terms

### Use Cases
{: #solution-data-integration-pattern3-usecases}

**Real-World Examples:**
- **Customer Churn Prediction**: Extract customer data, enrich with usage patterns, social sentiment, and support interactions; train ML models to predict churn risk
- **Supply Chain Optimization**: Combine SAP logistics data with IoT sensor data, weather forecasts, and traffic patterns for predictive delivery optimization
- **Financial Forecasting**: Blend SAP financial data with market indicators, economic data, and news sentiment for advanced forecasting models
- **Product Recommendation Engines**: Enrich SAP sales and customer data with browsing behavior, social media activity, and demographic data for personalized recommendations

### Architecture
{: #solution-data-integration-pattern3-architecture}

**Architecture Diagram:**

![SAP Data Integration Pattern 3](../images/data/SAP-data-integration-pattern-3.svg){: caption="SAP Data Integration Pattern 3" caption-side="bottom"}


**Architecture Components:**

**Supporting IBM Cloud Services:**
- **watsonx.data**: Lakehouse platform for data management and query processing
- **watsonx.ai**: AI/ML model training and inference for data enrichment
- **Cloud Object Storage**: Scalable object storage for data lake (Iceberg tables)
- **DataStage** (optional): Enterprise ETL/ELT for complex data transformations
- **Event Streams** (optional): Managed Apache Kafka for real-time data streaming
- **Code Engine**: Serverless compute for custom data processing logic
- **Cloud Databases**: Metadata storage and catalog management

**Network Connectivity:**

For detailed network connectivity options, see [Integration Overview](../integration/integration-overview.md).

- **Direct Link** (recommended): Dedicated connection for high-volume data extraction
- **VPN**: Encrypted tunnel for secure data transfer
- **Public Internet**: For non-sensitive or low-volume extractions

**Authentication Methods:**
- **OAuth 2.1**: Token-based authentication for SAP APIs
- **Certificate-based**: Mutual TLS for secure data extraction

### Considerations
{: #solution-data-integration-pattern3-considerations}

**Advantages:**
- ✅ **Rich Enrichment**: Combine SAP data with ML predictions, external data, and derived metrics
- ✅ **Multi-Source Integration**: Blend data from multiple sources seamlessly
- ✅ **ML/AI Ready**: Optimized for training and inference workloads
- ✅ **Complex Analytics**: Support advanced transformations and aggregations

**Limitations:**
- ⚠️ **Data Movement**: Requires extracting data from SAP (selective, not full replication)
- ⚠️ **Storage Costs**: Higher than Pattern 2 due to data materialization
- ⚠️ **Governance Complexity**: Requires data lineage tracking and lifecycle management
- ⚠️ **Lifecycle Management**: Must implement retention policies for temporary SAP data

**Best Practices:**
- **Lifecycle Management**: Implement retention policies (e.g., 7 days for temporary SAP data); enriched data can be kept indefinitely
- **Data Quality**: Monitor data quality with automated checks and alerts
- **Lineage Tracking**: Track data lineage for governance and compliance
- **Storage Optimization**: Use Iceberg compaction and partitioning to optimize storage costs
- **Security**: Encrypt sensitive data at rest and in transit; implement fine-grained access controls
- **Monitoring**: Track extraction jobs, enrichment pipelines, and storage usage

---

## Pattern Comparison
{: #solution-data-integration-pattern-comparison}

This table provides a side-by-side comparison of the three integration patterns to help you select the right approach for your requirements:

| Criteria | Pattern 1: API | Pattern 2: Zero-Copy | Pattern 3: Enrichment |
|----------|----------------|----------------------|-----------------------|
| **Data Movement** | None - data consumed on-demand | Minimal/None - queries federated to source | Selective - only needed data extracted |
| **Latency** | High - each query requires SAP round-trip | Medium - network-dependent federated queries | Low - data cached locally for fast access |
| **Complexity** | Low - simple API integration | Medium-High - requires watsonx.data setup | High - full data pipeline with enrichment |
| **Cost** | Low - minimal infrastructure | Medium - watsonx.data platform costs | High - storage + compute + enrichment |
| **Use Cases** | Ad-hoc queries, agentic AI, real-time lookups | Large-scale analytics, multi-source queries | ML/AI training, complex transformations |
| **SAP Compliance** | ✅ Excellent - no data storage | ✅ Excellent - zero-copy access | ✅ Good - temporary materialization allowed |
| **Scalability** | Limited - constrained by API limits | High - scales with query engine | Very High - scales with data platform |
| **Data Freshness** | Real-time - always current | Near real-time - depends on sub-pattern | Batch/streaming - scheduled or continuous |
| **Setup Time** | Quick - hours to days | Medium - days to weeks | Long - weeks to months |
{: caption="Pattern comparison" caption-side="top"}

**Key Takeaways:**
- **Pattern 1** is best for simplicity and real-time access with low volume
- **Pattern 2** balances cost and capability for large-scale analytics
- **Pattern 3** provides maximum flexibility for AI/ML workloads with data enrichment

---

## Agentic AI Integration
{: #solution-data-integration-ai-integration}

These patterns enable MCP (Model Context Protocol) tools and AI agents to access SAP data. Each pattern supports different agent use cases:

| Pattern | Agent Use Case | Implementation | Benefit |
|---------|---------------|----------------|---------|
| **1: API-Based** | Real-time conversational agents | MCP server with OData tools | Immediate SAP data access |
| **2: Zero-Copy** | Analytics agents | MCP server with watsonx.data | Federated queries across sources |
| **3: Enrichment** | ML-powered agents | MCP server with enriched data | Pre-computed features and predictions |
{: caption="Pattern use cases" caption-side="top"}

### Agent Examples
{: #solution-data-integration-ai-integration-examples}

**Pattern 1 - Conversational:**
```text
User: "What's the status of order 12345?"
Agent: [get_order_status tool] → Real-time SAP data
```
{: codeblock}

**Pattern 2 - Analytics:**
```text
User: "Show me trends for premium customers in Q1"
Agent: [analyze_customer_trends tool] → Federated query across SAP + CRM
```
{: codeblock}

**Pattern 3 - Predictive:**
```text
User: "Is customer ABC123 at risk of churning?"
Agent: [predict_customer_churn tool] → ML prediction from enriched data
```
{: codeblock}

### Multi-Pattern Agents
{: #solution-data-integration-ai-integration-multi-pattern-agents}

Complex agents combine patterns:
- Pattern 1: Real-time order status
- Pattern 2: Historical pattern analysis
- Pattern 3: Delivery issue predictions

### Best Practices
{: #solution-data-integration-ai-integration-best-practices}

**Pattern Selection:**
- Pattern 1: Real-time, transactional queries
- Pattern 2: Analytics, cross-system correlation
- Pattern 3: ML predictions, complex enrichment

**MCP Tool Design:**
- Keep tools focused and single-purpose
- Provide clear descriptions for agent reasoning
- Include error handling and caching
- Implement fine-grained access control

**Security:**
- Audit all agent-initiated data access
- Use OAuth 2.1 for SAP authentication
- Encrypt data in transit and at rest

For complete agentic AI patterns, see [Building Agentic AI Solutions in IBM Cloud: Integration with RISE with SAP](solution-guide-agentic-ai.md)
{: note}

---

## Additional Resources
{: #solution-data-integration-additional-resources}

**IBM Cloud:**
- [watsonx.data](https://cloud.ibm.com/docs/watsonxdata)
- [watsonx.ai](https://cloud.ibm.com/docs/watsonx-ai)
- [Code Engine](https://cloud.ibm.com/docs/codeengine)
- [Event Streams](https://cloud.ibm.com/docs/EventStreams)
- [IBM Cloud Compliance](https://www.ibm.com/cloud/compliance)

**SAP:**
- [SAP API Business Hub](https://api.sap.com/)
- [SAP Datasphere Documentation](https://help.sap.com/docs/SAP_DATASPHERE)

**Integration Technologies:**
- [Apache Iceberg](https://iceberg.apache.org/)
- [Delta Sharing](https://delta.io/sharing/)
- [Confluent TableFlow](https://docs.confluent.io/cloud/current/connectors/cc-iceberg-sink.html)

**Tutorials and Articles:**
- [Building an Event-Driven Agentic AI System with Apache Kafka on Confluent Cloud and watsonx Orchestrate](https://developer.ibm.com/tutorials/event-driven-agentic-ai-system-confluent-watsonx-orchestrate/)
- [AI-Ready Data with Open Standards: Using Confluent TableFlow and IBM watsonx.data](https://community.ibm.com/community/user/blogs/william-accetta/2026/03/17/aiready-data-with-open-standards-using-confluent)

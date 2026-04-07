---

copyright:
  years: 2025
lastupdated: "2026-04-07"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Data integration
{: #solution-data-integration}

## Overview

This guide presents three integration patterns for consuming SAP data in IBM Cloud environments while maintaining compliance with SAP's usage terms and conditions. Each pattern is optimized for specific use cases—from real-time queries to complex analytics and ML workloads.

### Key Principles

All patterns follow these core principles:

1. **Compliance-First**: Use SAP-approved APIs and methods; avoid unauthorized database access or long-term replication
2. **Zero-Copy Preferred**: Minimize data movement to reduce costs and complexity
3. **Temporary Materialization**: SAP data can be temporarily stored for processing, analytics, and enrichment
4. **Data Enrichment**: Extracted data can be combined with external sources, ML predictions, and derived metrics
5. **Flexible Architecture**: Support diverse use cases from agentic AI to business intelligence


## Pattern Selection Guide

Choose the right pattern based on your requirements:

| Pattern | Best For | Data Movement | Complexity | Cost |
|---------|----------|---------------|------------|------|
| **1. API-Based** | Real-time queries, agentic AI, low-volume access | None | Low | Low |
| **2. Zero-Copy** | Large-scale analytics, federated queries, cost-sensitive | Minimal/None | Medium-High | Medium |
| **3. Enrichment** | ML/AI training, complex transformations, multi-source integration | Selective | High | High |

### Quick Decision Tree

```
Need real-time data? → Pattern 1 (API)
Need ML enrichment? → Pattern 3 (Enrichment)
Have SAP Datasphere? → Pattern 2C (Delta Sharing)
Need near-real-time analytics? → Pattern 2B (TableFlow)
Large-scale analytics? → Pattern 2A (Connectors)
```

---

## Pattern 1: API-Based Integration (OData)

### Overview

Direct API access to SAP data for real-time queries. Data is consumed on-demand without storage, ideal for agentic AI and low-volume access.

**Use When:**
- ✅ Real-time data freshness required
- ✅ Low-volume access (< 1000 queries/day)
- ✅ Agentic AI conversational queries
- ✅ Minimal infrastructure preferred
- ❌ Avoid for high-volume analytics or complex joins

**Example Use Cases:**
- Customer service chatbots querying order status
- Sales agents checking inventory
- On-demand financial reports
- Executive dashboards with live data

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                        IBM Cloud                            │
│                                                             │
│  ┌──────────────────────────────────────────────────────┐   │
│  │         Agentic AI / Analytics Application           │   │
│  │  ┌────────────────────────────────────────────────┐  │   │
│  │  │  watsonx.ai / watsonx.orchestrate              │  │   │
│  │  │  - AI Agents                                   │  │   │
│  │  │  - LLM Processing                              │  │   │
│  │  │  - Orchestration Logic                         │  │   │
│  │  └────────────────────────────────────────────────┘  │   │
│  │                        ↓                             │   │
│  │  ┌────────────────────────────────────────────────┐  │   │
│  │  │  API Integration Layer                         │  │   │
│  │  │  - IBM Cloud Code Engine / OpenShift           │  │   │
│  │  │  - API Gateway / API Connect                   │  │   │
│  │  │  - Caching Layer (Redis)                       │  │   │
│  │  └────────────────────────────────────────────────┘  │   │
│  └──────────────────────────────────────────────────────┘   │
│                        ↓ OData/REST API                     │
└────────────────────────┼────────────────────────────────────┘
                         ↓
              ┌──────────────────────┐
              │   SAP S/4HANA        │
              │   - OData Services   │
              │   - REST APIs        │
              └──────────────────────┘
```

### Architecture & Services

**IBM Cloud Services:**
- watsonx.ai/orchestrate (AI runtime)
- Code Engine (serverless compute)
- API Connect (optional, API management)
- Databases for Redis (optional, caching)
- Secrets Manager (credential storage)

**Network Options:** Public Internet, Direct Link, VPN, SAP Private Link

**Authentication:** OAuth 2.1 (recommended), Basic Auth, Certificate-based

### Implementation Details

**Performance Optimization:**
- Cache reference data with appropriate TTL
- Use OData query options ($select, $filter, $top, $skip)
- Implement rate limiting and circuit breakers
- Connection pooling for efficiency

**Sample Implementation Flow:**
```
User Query → AI Agent → OData API Call → SAP S/4HANA
                ↓
         Process & Format
                ↓
         Return Response
                ↓
         Discard Data
```

**Example:** Customer service agent queries order status
1. Parse: "What is the status of order 12345?"
2. Call: `/sap/opu/odata/sap/API_SALES_ORDER_SRV/A_SalesOrder('12345')`
3. Process and format response
4. Discard temporary data

### Key Considerations

**Advantages:**
- ✅ SAP compliant (no data storage)
- ✅ Real-time data access
- ✅ Low cost and complexity
- ✅ Simple architecture

**Limitations:**
- ❌ Network latency per query
- ❌ API rate limits
- ❌ Limited for complex analytics
- ❌ Dependent on SAP availability

**Best Practices:**
- Cache reference data intelligently
- Optimize with OData query options
- Monitor response times and errors
- Use OAuth 2.1 authentication
- Implement retry logic with exponential backoff

---

## Pattern 2: Zero-Copy Data Access via watsonx.data

### Overview

Access SAP data without physical movement using watsonx.data and open standards (Iceberg, Delta Sharing). Data stays in SAP while enabling federated queries.

**Use When:**
- ✅ Large-scale analytics workloads
- ✅ Multi-source data integration (SAP + non-SAP)
- ✅ Cost-sensitive (minimize storage)
- ✅ SAP Datasphere available (Delta Sharing)
- ❌ Avoid for simple queries or extensive transformations

**Sub-Patterns:**
- **2A (Native Connectors)**: Standard federated queries, simple setup
- **2B (TableFlow)**: Near-real-time analytics with CDC
- **2C (Delta Sharing)**: True zero-copy with SAP Datasphere

**Example Use Cases:**
- Cross-system financial consolidation
- Customer 360 views (SAP + CRM)
- Supply chain analytics across multiple SAP instances

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                           IBM Cloud                                 │
│                                                                     │
│  ┌────────────────────────────────────────────────────────────────┐ │
│  │                    watsonx.data                                │ │
│  │  ┌──────────────────────────────────────────────────────────┐  │ │
│  │  │      Query Engine (Presto/Trino)                         │  │ │
│  │  │  - Federated Query Processing                            │  │ │
│  │  │  - Query Optimization                                    │  │ │
│  │  └──────────────────────────────────────────────────────────┘  │ │
│  │                           ↓                                    │ │
│  │  ┌──────────────────────────────────────────────────────────┐  │ │
│  │  │        Zero-Copy Data Access Layer                       │  │ │
│  │  │  ┌─────────────┐  ┌──────────────┐  ┌─────────────────┐  │  │ │
│  │  │  │ watsonx.data│  │  Confluent   │  │  Delta Sharing  │  │  │ │
│  │  │  │ Connectors  │  │  TableFlow   │  │    Protocol     │  │  │ │
│  │  │  └─────────────┘  └──────────────┘  └─────────────────┘  │  │ │
│  │  └──────────────────────────────────────────────────────────┘  │ │
│  └────────────────────────────────────────────────────────────────┘ │
│                           ↓                                         │
│  ┌────────────────────────────────────────────────────────────────┐ │
│  │              AI/Analytics Applications                         │ │
│  │  - watsonx.ai (AI/ML workloads)                                │ │
│  │  - watsonx.orchestrate (Agentic workflows)                     │ │
│  └────────────────────────────────────────────────────────────────┘ │
└──────────────────────────────┼──────────────────────────────────────┘
                               ↓ Zero-Copy Access
                    ┌──────────────────────┐
                    │   SAP Data Sources   │
                    │  - SAP Datasphere    │
                    │  - SAP S/4HANA       │
                    └──────────────────────┘
```

### Sub-Pattern Details

**2A: Native Connectors**
- Built-in watsonx.data connectors for standard protocols
- Services: watsonx.data, watsonx.ai, Cloud Object Storage, VPC
- ✅ Native integration, standard SQL
- ❌ Limited SAP version support, network latency

**2B: TableFlow Integration** ([Reference](https://community.ibm.com/community/user/blogs/william-accetta/2026/03/17/aiready-data-with-open-standards-using-confluent))
- Stream SAP CDC → Kafka → TableFlow → Iceberg → watsonx.data
- Services: watsonx.data, Event Streams, Confluent Cloud, Cloud Object Storage
- ✅ Near-real-time, incremental updates, time travel
- ❌ Requires Confluent, some data movement, complexity

**2C: Delta Sharing** ([Reference](https://architecture.learning.sap.com/docs/ref-arch/f5b6b597a6/1))
- True zero-copy with SAP Datasphere
- Services: watsonx.data (Delta Sharing client), watsonx.ai, Cloud Object Storage
- ✅ True zero-copy, SAP-native, open standard, audit trail
- ❌ Requires SAP Datasphere, network latency

### Implementation Details

**Network & Security:**
- Use Direct Link for dedicated connection
- Deploy watsonx.data in region closest to SAP
- TLS 1.3, OAuth 2.1 or certificate-based auth
- RBAC and comprehensive audit logging

**Performance Optimization:**
- Cache query results and table metadata
- Leverage partition pruning and predicate pushdown
- Monitor and tune query performance

**Sample Implementation:**
```
Supply Chain Analytics:
SQL Query → watsonx.data → Federated Query → SAP + Weather API
Result: Real-time supply risk scores

Customer 360:
Delta Sharing → SAP Customer Data + Social Sentiment + Credit Rating
Result: Unified customer intelligence
```

### Key Considerations

**Advantages:**
- ✅ Zero-copy access (especially Delta Sharing)
- ✅ Scalable for large analytics
- ✅ Combine SAP and non-SAP data
- ✅ Open standards, cost-effective

**Limitations:**
- ❌ Complex setup
- ❌ Requires watsonx.data infrastructure
- ❌ Network-dependent performance

**Best Practices:**
- Choose sub-pattern based on requirements
- Optimize network with Direct Link
- Implement intelligent caching
- Use least privilege access controls

---

## Pattern 3: Data Enrichment in watsonx.data Fabric

### Overview

Selective data movement from SAP to watsonx.data for enrichment with ML predictions, external data, and derived metrics. Data is temporarily materialized for processing.

**Use When:**
- ✅ ML/AI model training and inference
- ✅ Complex data transformations
- ✅ Multi-source data blending
- ✅ Derived metrics and KPIs
- ❌ Avoid for simple queries or strict data residency requirements

**Key Considerations:**
- Requires data lifecycle management (retention policies)
- Higher storage costs than Pattern 2
- Best when enrichment value justifies data movement

**Example Use Cases:**
- Customer churn prediction with enriched features
- Supply chain optimization with IoT and weather data
- Financial forecasting with market indicators
- Product recommendation engines

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                           IBM Cloud                                 │
│                                                                     │
│  ┌────────────────────────────────────────────────────────────────┐ │
│  │                    watsonx.data Fabric                         │ │
│  │                                                                │ │
│  │  ┌──────────────────────────────────────────────────────────┐  │ │
│  │  │              Enrichment Layer                            │  │ │
│  │  │  ┌────────────┐  ┌────────────┐  ┌──────────────────┐    │  │ │
│  │  │  │ ML Models  │  │ External   │  │  Transformation  │    │  │ │
│  │  │  │(watsonx.ai)│  │ Data APIs  │  │     Logic        │    │  │ │
│  │  │  └────────────┘  └────────────┘  └──────────────────┘    │  │ │
│  │  └──────────────────────────────────────────────────────────┘  │ │
│  │                           ↓                                    │ │
│  │  ┌──────────────────────────────────────────────────────────┐  │ │
│  │  │         Enriched Data Storage (Iceberg)                  │  │ │
│  │  │  - SAP Data (Temporary Materialization)                  │  │ │
│  │  │  - Enriched Attributes                                   │  │ │
│  │  │  - Derived Metrics                                       │  │ │
│  │  │  - ML Predictions                                        │  │ │
│  │  └──────────────────────────────────────────────────────────┘  │ │
│  │                           ↑                                    │ │
│  │  ┌──────────────────────────────────────────────────────────┐  │ │
│  │  │           Data Ingestion Layer                           │  │ │
│  │  │  - Batch ETL (Spark)                                     │  │ │
│  │  │  - Streaming (Kafka)                                     │  │ │
│  │  │  - API-based extraction                                  │  │ │
│  │  └──────────────────────────────────────────────────────────┘  │ │
│  └────────────────────────────────────────────────────────────────┘ │
│                           ↑                                         │
└───────────────────────────┼─────────────────────────────────────────┘
                            ↓ Data Extraction
                 ┌──────────────────────┐
                 │   SAP Data Sources   │
                 │  - SAP S/4HANA       │
                 │  - SAP BW/4HANA      │
                 └──────────────────────┘
```

### Architecture & Services

**IBM Cloud Services:**
- watsonx.data (lakehouse platform)
- watsonx.ai (AI/ML enrichment)
- Cloud Object Storage (data lake storage)
- DataStage (optional, ETL/ELT)
- Event Streams (optional, streaming)
- Code Engine (serverless compute)
- Cloud Databases (metadata)

### Implementation Details

**Data Extraction:**
- Batch: OData API with date filters → Iceberg tables
- Streaming: SAP CDC → Kafka → Iceberg tables (real-time)

**Enrichment Strategies:**
1. **ML-Based**: Add churn predictions, LTV scores via watsonx.ai
2. **External Data**: Combine with market intelligence, social sentiment, IoT data
3. **Derived Metrics**: Calculate KPIs, RFM scores, aggregations

**Lifecycle Management:**
- Set retention policies (e.g., 7 days for temporary SAP data)
- Expire old snapshots to manage costs
- Implement data quality checks and lineage tracking

**Sample Implementation Flow:**
```
Extract SAP Data → Enrich with ML/External Data → Store in Iceberg
                                ↓
                    Customer Intelligence Platform
                    - Churn predictions
                    - Social sentiment
                    - RFM scores
                    - Expose via API
```

### Key Considerations

**Advantages:**
- ✅ Rich enrichment capabilities
- ✅ Combine multiple data sources
- ✅ ML/AI integration
- ✅ Complex analytics support

**Limitations:**
- ❌ Data movement required
- ❌ Higher storage costs
- ❌ Complex governance
- ❌ Requires lifecycle management

**Best Practices:**
- Implement retention and expiration policies
- Monitor data quality with automated checks
- Track data lineage for governance
- Optimize storage with compaction
- Secure sensitive data with encryption

---

## Pattern Comparison

| Criteria | Pattern 1: API | Pattern 2: Zero-Copy | Pattern 3: Enrichment |
|----------|----------------|----------------------|-----------------------|
| **Data Movement** | None | Minimal/None | Selective |
| **Latency** | High (per query) | Medium | Low (cached) |
| **Complexity** | Low | Medium-High | High |
| **Cost** | Low | Medium | High |
| **Use Cases** | Ad-hoc queries, agentic AI | Large-scale analytics | ML/AI, complex transformations |
| **SAP Compliance** | ✅ Excellent | ✅ Excellent | ✅ Good (temporary) |
| **Scalability** | Limited | High | Very High |
| **Data Freshness** | Real-time | Near real-time | Batch/streaming |
| **Setup Time** | Quick | Medium | Long |

---

## Agentic AI Integration

These patterns enable MCP (Model Context Protocol) tools and AI agents to access SAP data. Each pattern supports different agent use cases:

| Pattern | Agent Use Case | Implementation | Benefit |
|---------|---------------|----------------|---------|
| **1: API-Based** | Real-time conversational agents | MCP server with OData tools | Immediate SAP data access |
| **2: Zero-Copy** | Analytics agents | MCP server with watsonx.data | Federated queries across sources |
| **3: Enrichment** | ML-powered agents | MCP server with enriched data | Pre-computed features and predictions |

### Agent Examples

**Pattern 1 - Conversational:**
```
User: "What's the status of order 12345?"
Agent: [get_order_status tool] → Real-time SAP data
```

**Pattern 2 - Analytics:**
```
User: "Show me trends for premium customers in Q1"
Agent: [analyze_customer_trends tool] → Federated query across SAP + CRM
```

**Pattern 3 - Predictive:**
```
User: "Is customer ABC123 at risk of churning?"
Agent: [predict_customer_churn tool] → ML prediction from enriched data
```

### Multi-Pattern Agents

Complex agents combine patterns:
- Pattern 1: Real-time order status
- Pattern 2: Historical pattern analysis
- Pattern 3: Delivery issue predictions

### Best Practices

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

**IBM Cloud:**
- [watsonx.data](https://cloud.ibm.com/docs/watsonxdata) | [watsonx.ai](https://cloud.ibm.com/docs/watsonx-ai)
- [Code Engine](https://cloud.ibm.com/docs/codeengine) | [Event Streams](https://cloud.ibm.com/docs/EventStreams)
- [IBM Cloud Compliance](https://www.ibm.com/cloud/compliance)

**SAP:**
- [SAP API Business Hub](https://api.sap.com/)
- [SAP Datasphere Documentation](https://help.sap.com/docs/SAP_DATASPHERE)

**Integration Technologies:**
- [Apache Iceberg](https://iceberg.apache.org/) | [Delta Sharing](https://delta.io/sharing/)
- [Confluent TableFlow](https://docs.confluent.io/cloud/current/connectors/cc-iceberg-sink.html)

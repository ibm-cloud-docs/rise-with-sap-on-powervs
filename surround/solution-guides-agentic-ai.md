---

copyright:
  years: 2025
lastupdated: "2026-04-17"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Agentic AI
{: #solution-agentic-ai}

## Introduction

This guide covers building Agentic AI solutions on IBM Cloud that integrate with SAP data and resources as surround workloads. These solutions leverage autonomous agents that can reason, plan, and execute tasks using tools and data sources. By connecting to RISE with SAP environments, Agentic AI enables automation of complex SAP business processes and provides intelligent enterprise assistance.

---

## Agentic AI Architecture Layers
{: #solution-agentic-ai-architecture-layers}

Agentic AI solutions are built on multiple interconnected layers, each serving a specific purpose in the overall architecture:

![IBM Cloud Agentic AI Architecture Layers](../images/ai/Agentic_AI_layers.svg)

### 1. Resource Layer
{: #solution-agentic-ai-architecture-layers-resource}

The Resource Layer represents all enterprise resources including data, APIs, and services across the landscape. This foundational layer provides the information and capabilities that agents access and process, supporting diverse locations and formats to meet enterprise requirements.

**Location Flexibility:**
- **On-Premises**: Legacy systems, SAP ERP, databases
- **Cloud**: IBM Cloud Object Storage, Cloud Databases, watsonx.data
- **Multi-Cloud**: AWS S3, Azure Blob Storage, Google Cloud Storage
- **Hybrid**: Combination of on-premises and cloud data sources

**Key Characteristics:**
- Data can reside anywhere in the enterprise landscape
- Supports structured, semi-structured, and unstructured data
- Enables real-time and batch data access patterns
- Maintains data sovereignty and compliance requirements

### 2. Tools Layer
{: #solution-agentic-ai-architecture-layers-tool}

The Tools Layer provides the interface that exposes enterprise capabilities and services to agents through standardized protocols. Tools abstract complex operations into simple, reusable functions that agents can invoke.

**Integration Capabilities:**
- **Data Integration**: Connect to databases, data lakes, and data warehouses
- **API Integration**: REST APIs, GraphQL, SOAP services
- **Service Integration**: SAP APIs, IBM Cloud services, third-party services
- **Custom Tools**: Business-specific functions and utilities

**Tool Characteristics:**
- Tools abstract complex operations into simple, reusable functions
- Can be local (embedded) or remote (via MCP servers)
- Support synchronous and asynchronous operations
- Enable secure access to enterprise resources

### 3. Agent Layer
{: #solution-agentic-ai-architecture-layers-agent}

The Agent Layer consists of intelligent orchestrators powered by Large Language Models (LLMs) that use tools to accomplish tasks autonomously. Agents can reason, maintain context, and coordinate with other agents to solve complex business problems.

**Agent Capabilities:**
- **Tool Utilization**: Agents use tools from local or remote MCP (Model Context Protocol) servers
- **Reasoning**: LLM-powered decision making and planning
- **Memory**: Maintain context and conversation history
- **Orchestration**: Coordinate multiple tools and sub-agents

**Agent Communication:**
- **Local MCP Servers**: Direct integration with tools in the same environment
- **Remote MCP Servers**: Distributed tool access across network boundaries
- **Agent-to-Agent (A2A) Protocol**: Inter-agent communication for complex workflows
- **Multi-Agent Systems**: Collaborative problem-solving with specialized agents

### 4. Application Layer
{: #solution-agentic-ai-architecture-layers-app}

The Application Layer represents user-facing interfaces and backend services that interact with agents to deliver AI-powered experiences. This layer enables various integration patterns to connect applications with agent capabilities.

**Integration Patterns:**
- **Direct Integration**: Applications embed agents directly
- **API-based Integration**: Applications communicate with agents via REST APIs/WebSocket
- **Remote Agents**: Applications integrate with external agents via APIs (agents use A2A internally)
- **API Gateway**: Centralized access to agent capabilities with authentication and routing

**Application Types:**
- Web applications (React, Angular, Vue.js)
- Mobile applications (iOS, Android)
- Enterprise applications (SAP Fiori, custom portals)
- Backend services and microservices

---

## SAP Integration Patterns
{: #solution-agentic-ai-sap-integration-patterns}

Four primary patterns connect Agentic AI solutions with RISE with SAP. Each addresses different integration needs and can be combined for comprehensive solutions.

![IBM Cloud Agentic AI Architecture Layers](../images/ai/SAP_Surround_agent_integration_patterns.svg)

### Pattern 1: MCP Server Integration with SAP
{: #solution-agentic-ai-sap-integration-patterns-1}

**Overview:**
MCP (Model Context Protocol) servers provide the integration layer between agents and SAP systems, exposing tools that abstract SAP operations for agent consumption.

**Key Characteristics:**
- Direct SAP API connections (OData, REST, BAPI, RFC)
- Tool-based abstraction of SAP operations
- Reusable across multiple agents
- Centralized SAP connectivity

**Key Use Cases:**

1. **Real-time Inventory Management**
   - E-commerce platforms checking product availability across SAP warehouses
   - MCP server exposes `check_inventory` tool querying SAP S/4HANA
   - Example: Customer adds item → Agent calls MCP → Returns SAP inventory status

2. **Automated Purchase Order Processing**
   - Procurement automation based on inventory thresholds
   - MCP server provides `create_purchase_order` tool invoking SAP BAPI
   - Example: Low inventory detected → Agent creates PO via MCP → Routes for approval

**Architecture:**
Agents → MCP Server (IBM Cloud) → SAP APIs → SAP systems

Agents invoke tools on the MCP server, which translates requests into SAP API calls to access SAP systems. This pattern centralizes SAP connectivity through MCP servers deployed on IBM Cloud, providing reusable tools for multiple agents.

**Supporting IBM Cloud Services:**
- **Code Engine / OpenShift**: Host MCP servers with auto-scaling and container orchestration
- **VPC**: Provide isolated network environment for secure SAP connectivity
- **Secrets Manager**: Store and manage SAP credentials and API keys securely
- **Direct Link**: Enable low-latency, dedicated connection to on-premises SAP systems

---

### Pattern 2: Agent Integration with SAP MCP Servers
{: #solution-agentic-ai-sap-integration-patterns-2}

**Overview:**
Agents on watsonx.orchestrate consume MCP server tools to interact with SAP, enabling reasoning about SAP data and executing operations.

**Key Use Cases:**

1. **Intelligent Order Processing**
   - Customer service agent handles complex order inquiries with natural language understanding
   - Multi-step reasoning: check inventory → verify pricing → update order
   - Example: "Change order #12345 to expedited shipping" → Agent processes → Updates SAP → Confirms

2. **Financial Reconciliation**
   - Automated invoice matching and payment processing with exception handling
   - Example: Payment received → Matches invoices → Identifies discrepancies → Creates follow-up tasks

**Architecture:**
watsonx.orchestrate Agents → MCP Server Registry → SAP MCP Servers → SAP APIs → SAP systems

Agents on watsonx.orchestrate discover and invoke tools through the MCP Server Registry, which routes requests to appropriate SAP MCP Servers. These servers translate agent requests into SAP API calls, enabling intelligent reasoning and multi-step operations across SAP systems.

**Supporting IBM Cloud Services:**
- **watsonx.orchestrate**: Provide agent platform with pre-built templates and workflow automation
- **watsonx.ai**: Supply foundation models for agent reasoning and natural language understanding
- **VPC**: Ensure secure, isolated network for agent and MCP server communication
- **App ID**: Manage user authentication and authorization for agent access
- **Secrets Manager**: Securely store SAP credentials used by MCP servers

---

### Pattern 3: Agent-to-Agent Communication (A2A)
{: #solution-agentic-ai-sap-integration-patterns-3}

**Overview:**
Agents use A2A protocol to collaborate on complex multi-domain tasks, enabling task delegation and result aggregation across specialized agents.

**Key Characteristics:**
- Distributed architecture with specialized agents
- Asynchronous communication
- Task decomposition and delegation

**Key Use Cases:**

1. **End-to-End Order Fulfillment**
   - Orchestrator coordinates sales, inventory, logistics, and finance agents
   - Flow: Order placed → Orchestrator delegates → Agents execute → Results aggregated → Order confirmed
   - Benefits: Parallel processing, specialized expertise, fault tolerance

2. **Intelligent Procurement with External Suppliers**
   - Internal procurement agent collaborates with external supplier agents
   - Flow: Low inventory → Request quotes → Evaluate options → Create PO
   - Benefits: Real-time negotiation, competitive pricing, automation

**Architecture:**
Orchestrator Agent → Internal Agents (A2A) → External Partner Agents (A2A)

An orchestrator agent coordinates specialized agents using the A2A protocol for task delegation and result aggregation. Internal agents communicate with each other and external partner agents to execute complex multi-domain workflows across multiple domains and systems.

**Supporting IBM Cloud Services:**
- **Code Engine / OpenShift**: Deploy and scale multiple specialized agents with container orchestration
- **VPC**: Create secure network boundaries for internal and external agent communication
- **Event Streams**: Enable asynchronous messaging and event-driven agent coordination
- **API Connect**: Manage and secure A2A protocol endpoints with rate limiting and monitoring
- **Secrets Manager**: Store credentials for inter-agent authentication and system access

**Security:** Mutual TLS, OAuth 2.1, end-to-end encryption, rate limiting, audit logging

---

### Pattern 4: Application Integration with SAP Agents
{: #solution-agentic-ai-sap-integration-patterns-4}

**Overview:**
Applications (web, mobile, enterprise) integrate with SAP-enabled agents for intelligent, conversational SAP interfaces.

**Key Use Cases:**

1. **Conversational E-commerce**
   - AI-powered shopping assistant with SAP inventory integration
   - Example: "Show blue running shoes size 10" → Agent searches SAP → Returns results

2. **Mobile Field Service**
   - Field technicians access SAP work orders via mobile app with offline capability
   - Example: "What's my next appointment?" → Agent retrieves SAP schedule

3. **SAP Fiori AI Copilot**
   - Embedded AI assistant in SAP Fiori apps
   - Example: "Summarize customer order history" → Copilot analyzes → Provides insights

**Architecture:**
User Applications → API Gateway → Application Backend → SAP Agents → SAP MCP Servers → SAP systems

Applications interact with SAP-enabled agents through an API Gateway that provides authentication, routing, and rate limiting. The application backend manages business logic and coordinates agent requests, while agents use MCP servers to access SAP systems and provide intelligent, conversational interfaces.

**Supporting IBM Cloud Services:**
- **Code Engine / OpenShift**: Host application backends and agent services with scalability
- **API Connect**: Provide API gateway for authentication, routing, and rate limiting
- **VPC**: Ensure secure communication between application layers
- **App ID**: Manage end-user authentication and single sign-on
- **Object Storage**: Store application data, logs, and agent conversation history
- **Cloud Databases**: Provide persistent storage for application state and user data

---

### Enhanced Integration Capabilities
{: #solution-agentic-ai-sap-integration-patterns-enhanced}

The four primary patterns can be enhanced with advanced data and event integration capabilities.

#### Data-Centric Integration via watsonx.data

**Overview:**
watsonx.data provides unified data access for SAP and enterprise data sources, essential for data-intensive MCP tools.

**Three Data Integration Patterns:**

For detailed guidance, see **[SAP Data Integration Patterns for IBM Cloud](solution-guides-data-integration.md)**:

1. **API-Based Integration (OData)** - Real-time queries, low latency
2. **Zero-Copy Data Access** - Federated queries without data movement
3. **Data Enrichment** - Selective data movement for ML and analytics

**Pattern Selection:**

| Scenario | Pattern | Rationale |
|----------|---------|-----------|
| Real-time queries (chatbots) | API-Based | Low latency, always current |
| Analytics (cross-system reports) | Zero-Copy | Federated queries, no duplication |
| ML predictions | Enrichment | Feature engineering, model training |

**Supporting IBM Cloud Services:** watsonx.data, Object Storage, Cloud Databases, Event Streams

#### Event-Driven Integration

**Overview:**
SAP events trigger real-time agent actions for reactive automation.

**Use Cases:** Order processing, inventory alerts, customer service automation, transaction monitoring

**Supporting IBM Cloud Services:** Event Streams, Code Engine, Cloud Functions

---

## Integration Pattern Comparison

| Pattern | Design Effort | Response Time | Scalability | Best For |
|---------|--------------|---------------|-------------|----------|
| **MCP-SAP** | Low | Low (ms) | High | Direct SAP operations, CRUD |
| **Agent-MCP** | Medium | Medium (seconds) | High | Conversational interfaces |
| **A2A** | Medium | Medium-High (seconds) | Very High | Complex workflows |
| **App-Agent** | Medium | Low-Medium | High | End-user applications |
| **Data-Centric** | Low-Medium | Low-High* | Very High | Analytics, ML |
| **Event-Driven** | Low | Very Low (ms) | Very High | Real-time automation |

*Response time varies: Lakehouse (pre-loaded data) is faster than virtualization (real-time federation)

**Metric Definitions:**

- **Design Effort**
  - **Low**: Minimal custom code, leverage existing services and templates
  - **Low-Medium**: Some custom integration logic, configuration required
  - **Medium**: Moderate development, custom agent logic and integration
  - **High**: Significant custom development, complex architecture design

- **Response Time**
  - **Very Low (ms)**: < 100ms - Event-driven triggers, direct API calls
  - **Low (ms)**: 100ms - 1s - Simple operations without LLM reasoning
  - **Low-Medium**: 1-3s - API operations with light processing
  - **Medium (seconds)**: 2-10s - Single agent with LLM reasoning
  - **Medium-High (seconds)**: 5-15s - Multi-agent coordination, complex workflows
  - **Low-High***: Variable - Depends on data source (API: low, federation: high)

- **Scalability**
  - **High**: Supports 100s-1,000s of concurrent operations
  - **Very High**: Supports 10,000+ concurrent operations with horizontal scaling

**Selection Guidance:** Choose based on requirements; patterns can be combined (e.g., Event-Driven + Agent-MCP)

---

## Deployment & Decision Factors
{: #solution-agentic-ai-sap-integration-decision-factors}

### Key Decision Areas

| Factor | Key Considerations | Recommendation |
|--------|-------------------|----------------|
| **Data Location** | Regulatory requirements, latency, bandwidth | Use Direct Link for on-premises; watsonx.data for multi-cloud federation |
| **Agent Scale** | 1-5 agents: Code Engine; 20+: OpenShift | Start serverless, scale to containers as complexity grows |
| **MCP Deployment** | Variable load: Code Engine; Consistent: OpenShift | Hybrid approach for mixed workloads |
| **Integration Pattern** | Real-time: Event-driven; Analytics: Data-centric | Combine patterns based on use case |
| **Cost** | Serverless for variable, reserved for predictable | Monitor and right-size resources |
| **Security** | Encryption, least-privilege, audit logging | Use Secrets Manager, enable compliance monitoring |
| **Performance** | Multi-zone deployment, load balancing | Design for HA with disaster recovery |

### Deployment Comparison

| Requirement | Code Engine | OpenShift | Hybrid |
|------------|-------------|-----------|--------|
| Variable load | ✅ Best | 💰 Costly | ⚠️ Overkill |
| Consistent load | 💰 Expensive | ✅ Best | ✅ Optimal |
| Complex networking | ⚠️ Limited | ✅ Best | ✅ Flexible |
| Rapid dev/test | ✅ Best | ⚠️ More setup | ⚠️ More setup |
| Enterprise governance | ⚠️ Basic | ✅ Best | ✅ Comprehensive |

**Legend:** ✅ Best | ⚠️ Works with caveats | 💰 Works but costly

**Detailed Comparison:**

- **Variable Load**
  - **Code Engine (✅)**: Auto-scales to zero, pay only for actual usage, ideal for unpredictable traffic
  - **OpenShift (💰)**: Always-on infrastructure incurs costs even during low usage periods
  - **Hybrid (⚠️)**: Over-engineered for simple variable load scenarios

- **Consistent Load**
  - **Code Engine (💰)**: Continuous usage makes serverless pricing expensive vs reserved capacity
  - **OpenShift (✅)**: Reserved capacity provides better economics for predictable workloads
  - **Hybrid (✅)**: Optimal cost balance using OpenShift for baseline, Code Engine for peaks

- **Complex Networking**
  - **Code Engine (⚠️)**: Limited VPC integration, basic networking features
  - **OpenShift (✅)**: Full Kubernetes networking, service mesh, advanced routing
  - **Hybrid (✅)**: Leverage OpenShift networking while using Code Engine where appropriate

- **Rapid Dev/Test**
  - **Code Engine (✅)**: Zero infrastructure setup, deploy in minutes, instant scaling
  - **OpenShift (⚠️)**: Requires cluster setup, configuration, more initial overhead
  - **Hybrid (⚠️)**: Additional complexity managing two platforms

- **Enterprise Governance**
  - **Code Engine (⚠️)**: Basic RBAC, limited policy controls, simpler compliance features
  - **OpenShift (✅)**: Advanced RBAC, network policies, compliance operators, audit logging
  - **Hybrid (✅)**: Comprehensive governance across both platforms with unified policies

---

## Deployment Patterns

### IBM Cloud-Based Deployment
Applications, agents, and MCP servers deployed on IBM Cloud infrastructure using managed services (Code Engine/OpenShift, watsonx.orchestrate, watsonx.data) for unified data access.

### Hybrid with External Agents
IBM Cloud agents communicate with external/partner agents via A2A protocol for multi-organization workflows.

### Edge-to-Cloud
Local agents at edge/on-premises for low-latency processing, with cloud agents for complex tasks and scalability.

> **Reference**: For detailed workflow patterns, see [IBM Cloud Agentic AI Workflow Documentation](https://cloud.ibm.com/docs/pattern-agentic-platform?topic=pattern-agentic-platform-agentic-ai-workflow).

---

## IBM Cloud Services for Agentic AI
{: #solution-agentic-ai-sap-integration-ibmcloud-services}

### Core Services

| Service | Purpose | Key Capabilities |
|---------|---------|------------------|
| **watsonx.orchestrate** | Agent platform | Pre-built templates, workflow automation, multi-agent coordination |
| **watsonx.ai** | Foundation models | LLM access, fine-tuning, prompt engineering, model governance |
| **watsonx.data** | Data lakehouse | Multi-source integration, query federation, SAP connectivity |
| **watsonx.governance** | AI governance | Model lifecycle management, risk assessment, compliance monitoring, audit trails |
| **Code Engine** | Serverless compute | MCP servers, auto-scaling, pay-per-use, zero infrastructure |
| **OpenShift** | Enterprise Kubernetes | Production deployments, service mesh, multi-zone HA |
| **Object Storage** | Scalable storage | Unstructured data, data lake, backups, AI training data |
| **Cloud Databases** | Managed databases | PostgreSQL, MongoDB, Redis, Elasticsearch |
| **VPC** | Private networking | Isolated subnets, security groups, VPN gateway, load balancers |
| **Direct Link** | Dedicated connection | Low-latency SAP access, high bandwidth, compliance |
| **Event Streams** | Event streaming | Real-time SAP events, agent communication, Kafka-based |
| **Secrets Manager** | Secrets management | SAP credentials, API keys, automatic rotation |
| **API Connect** | API gateway | Authentication, routing, rate limiting, API lifecycle management |
| **App ID** | User authentication | SSO, OAuth 2.1, user management, multi-factor authentication |
| **Cloud Functions** | Serverless functions | Event-driven processing, lightweight compute, pay-per-execution |
| **IBM Cloud Monitoring** | Infrastructure monitoring | Metrics, dashboards, alerts, performance monitoring |
| **IBM Cloud Log Analysis** | Log management | Centralized logging, search, filtering, real-time analysis |
| **Security and Compliance Center** | Security posture | Compliance monitoring, threat detection, audit logging |

---


## Implementation Best Practices
{: #solution-agentic-ai-sap-integration-implementation-considerations}

### Development Workflow
1. **Design**: Define agent capabilities, map SAP integration points, design MCP tools
2. **Develop**: Implement MCP servers, develop agent logic, create applications
3. **Test**: Integration, load, security, and UAT with SAP sandbox
4. **Deploy**: Deploy to Code Engine/OpenShift, configure agents, monitor

> **Reference**: [IBM Cloud Agentic AI Workflow Documentation](https://cloud.ibm.com/docs/pattern-agentic-platform?topic=pattern-agentic-platform-agentic-ai-workflow)

### Key Best Practices

| Area | Best Practices |
|------|---------------|
| **Agent Design** | Single responsibility, stateless design, robust error handling, comprehensive logging |
| **MCP Servers** | RESTful APIs, idempotency, rate limiting, versioning |
| **SAP Integration** | Connection pooling, batch operations, event-driven updates, retry logic |
| **Security** | Zero trust, least privilege, secrets rotation, audit trails |

### Monitoring & Troubleshooting

**Key Metrics**: Agent response time, tool execution success rate, SAP API latency, error rates, resource utilization, cost per transaction

**Tools**: IBM Cloud Monitoring (Sysdig), Log Analysis (LogDNA), watsonx.orchestrate analytics

**Common Issues**: Agent not responding (check status, connectivity, logs), MCP errors (validate configs, SAP connectivity), performance issues (analyze metrics, caching), integration failures (verify SAP availability, credentials)

---

## Conclusion
{: #solution-agentic-ai-sap-integration-conclusion}

Building Agentic AI solutions in IBM Cloud with RISE with SAP integration requires careful consideration of architecture, deployment patterns, and service selection. The flexibility of IBM Cloud services allows organizations to choose the right balance of performance, cost, and complexity for their specific needs.

Key takeaways:
- **Layered Architecture**: Separate concerns across data, tools, agents, and applications
- **Flexible Deployment**: Choose between serverless, containerized, or hybrid approaches
- **Service Selection**: Match IBM Cloud services to specific requirements
- **Decision Framework**: Use decision factors to guide architecture choices
- **Best Practices**: Follow established patterns for security, performance, and reliability

By following the patterns and guidelines in this document, organizations can build robust, scalable, and secure Agentic AI solutions that unlock the full potential of their SAP investments.

---

## Additional Resources
{: #solution-agentic-ai-sap-integration-additional-resources}

### IBM Cloud Documentation
- [IBM Cloud Agentic AI Workflow Pattern](https://cloud.ibm.com/docs/pattern-agentic-platform?topic=pattern-agentic-platform-agentic-ai-workflow) - **Primary Reference**
- [Accelerate Gen AI on IBM Cloud with Deployable Architectures](https://developer.ibm.com/tutorials/awb-maximize-gen-ai-on-ibm-cloud-deployable-architectures/)
- [IBM watsonx.orchestrate Documentation](https://www.ibm.com/docs/en/watsonx/orchestrate)
- [IBM Cloud Code Engine](https://cloud.ibm.com/docs/codeengine)
- [Red Hat OpenShift on IBM Cloud](https://cloud.ibm.com/docs/openshift)
- [watsonx.data Documentation](https://www.ibm.com/docs/en/watsonx/watsonxdata)

### External Resources
- [SAP API Business Hub](https://api.sap.com/)
- [Model Context Protocol (MCP) Specification](https://modelcontextprotocol.io/)
- [Agent-to-Agent (A2A) Protocol](https://a2a.ai/)

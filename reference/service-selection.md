# AWS service selection for AIF-C01

Last reviewed: November 3, 2026

The [official AIF-C01 in-scope list](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/aif-01-in-scope-services.html) contains 51 services across eleven categories. AWS calls the list non-exhaustive and subject to change. This page covers every currently listed service with its role, selection cues, and official references.

## Start with the workload

| The scenario needs... | Start with... |
|---|---|
| A standard speech, language, document, vision, or recommendation capability | A [purpose-built AI service](managed-ai-services.md) |
| Foundation-model APIs, managed GenAI features, RAG, agents, or Guardrails | Amazon Bedrock |
| Custom or classical ML training, chosen frameworks and compute, or end-to-end MLOps control | Amazon SageMaker AI |
| Business data analysis, dashboards, and generative BI | Amazon Quick |
| An AI coding and development environment | Kiro |
| An open-source SDK for a model-and-tools agent loop | Strands Agents |
| Managed agent loops, deployment, tools, identity, memory, policy, observability, evaluation, optimization, and payments | Amazon Bedrock AgentCore |

Then account for data type, latency, required control, security, operations, and cost.

## Analytics

| Service | Recognition cue | Official source |
| --- | --- | --- |
| AWS Data Exchange | Find, subscribe to, and use third-party datasets; think data marketplace rather than data processing | [AWS Data Exchange](https://docs.aws.amazon.com/data-exchange/latest/userguide/what-is-data-exchange.html) |
| Amazon EMR | Run big-data frameworks such as Apache Spark and Hadoop for large-scale processing and ML data preparation | [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) |
| AWS Glue | Serverless data integration, discovery, cataloging, and ETL for analytics and ML pipelines | [AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html) |
| AWS Glue DataBrew | Visual, no-code data profiling and preparation | [Glue DataBrew](https://docs.aws.amazon.com/databrew/latest/dg/what-is.html) |
| AWS Lake Formation | Build, secure, and govern data lakes with centralized permissions | [Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html) |
| Amazon OpenSearch Service | Managed search, analytics, and vector search; can store and search embeddings for RAG | [OpenSearch Service](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/what-is.html) |
| Amazon Quick | AI-powered workspace for business users with conversational assistance, source-traced research, multi-dataset analytics, flows, autonomous agents, and natural-language application building over connected data and applications | [Amazon Quick](https://docs.aws.amazon.com/quicksuite/latest/userguide/) |
| Amazon Redshift | Managed cloud data warehouse for SQL analytics over large structured datasets | [Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/mgmt/welcome.html) |

**Selection cues:** Glue moves and transforms data; DataBrew gives analysts a visual preparation tool; Lake Formation governs a data lake; Redshift is a warehouse; OpenSearch handles search and vectors; Quick presents business insight.

## Cloud financial management

| Service | Recognition cue | Official source |
| --- | --- | --- |
| AWS Budgets | Set cost or usage thresholds and receive alerts or trigger budget actions | [AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) |
| AWS Cost Explorer | Analyze historical spend and usage, view trends, and forecast costs | [Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html) |

**Trap:** Budgets alerts against a planned threshold. Cost Explorer investigates spend and trends.

## Compute

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon EC2 | Resizable virtual machines with operating-system and instance control; can host custom ML workloads | [Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| AWS Lambda | Run event-driven functions without managing servers; useful for light orchestration and agent tool logic | [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |

**Selection cue:** Choose EC2 when the team needs machine control or long-running custom compute. Choose Lambda for short, event-driven functions with less server management.

## Containers

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon Elastic Container Service (Amazon ECS) | AWS-native orchestration for containerized applications | [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) |
| Amazon Elastic Kubernetes Service (Amazon EKS) | Managed Kubernetes control plane for teams that need Kubernetes APIs and ecosystem | [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) |

**Selection cue:** ECS is AWS-native container orchestration. EKS is managed Kubernetes.

## Database

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon Aurora | MySQL- and PostgreSQL-compatible relational database; supported configurations can provide vector storage for RAG | [Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html) |
| Amazon DocumentDB (with MongoDB compatibility) | Managed document database for JSON-like document workloads | [Amazon DocumentDB](https://docs.aws.amazon.com/documentdb/latest/developerguide/what-is.html) |
| Amazon DynamoDB | Serverless NoSQL key-value and document database with low-latency access | [Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) |
| Amazon ElastiCache | Managed in-memory cache for low-latency data access and session or response caching | [Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/WhatIs.html) |
| Amazon Neptune | Managed graph database; supports graph relationships and vector-related RAG scenarios named in the exam outline | [Amazon Neptune](https://docs.aws.amazon.com/neptune/latest/userguide/intro.html) |
| Amazon RDS | Managed relational database service; RDS for PostgreSQL can support vector storage through suitable extensions | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |

**Selection cues:** Relationships and connected data point to Neptune. Relational rows and SQL point to RDS or Aurora. Key-value access points to DynamoDB. Documents point to DocumentDB. Fast cache points to ElastiCache.

## Developer tools

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Kiro | AI coding agent available through an agentic desktop environment, CLI, and other surfaces, with spec-driven development, built-in and custom agents, steering, and event-driven hooks | [Kiro documentation](https://kiro.dev/docs/) |
| Strands Agents | Open-source, model-driven SDK for agents with tools, memory, MCP integration, and multi-agent graph, swarm, and workflow patterns | [Strands Agents](https://strandsagents.com/latest/documentation/docs/) |

Kiro helps a developer work. Strands is a framework developers use to build agents. Neither is a foundation model or production hosting service.

## Machine learning

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon Bedrock | Managed access to foundation models plus GenAI capabilities such as Knowledge Bases, Amazon Bedrock Agents Classic for eligible existing customers, Guardrails, prompt management, evaluation, and customization | [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html) |
| Amazon Bedrock AgentCore | Composable Harness, Runtime, Gateway, Identity, Memory, Policy, Observability, Evaluations, Optimization, Payments, Browser, Code Interpreter, and Registry capabilities for agents | [Amazon Bedrock AgentCore](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/what-is-bedrock-agentcore.html) |
| Amazon Comprehend | Extract sentiment, entities, key phrases, topics, language, and other insight from text | [Amazon Comprehend](https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html) |
| Amazon Lex | Build voice and text conversational interfaces around intents, utterances, and slots | [Amazon Lex](https://docs.aws.amazon.com/lexv2/latest/dg/what-is.html) |
| Amazon Nova | Amazon foundation-model family available through Amazon Bedrock; choose models by modality, capability, latency, and cost | [Amazon Nova](https://docs.aws.amazon.com/nova/latest/userguide/) |
| Amazon Personalize | Build individualized recommendations and rankings from user and item interactions | [Amazon Personalize](https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html) |
| Amazon Polly | Convert text to lifelike speech | [Amazon Polly](https://docs.aws.amazon.com/polly/latest/dg/what-is.html) |
| Amazon Rekognition | Analyze images and video for objects, scenes, faces, text, and unsafe content | [Amazon Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html) |
| Amazon SageMaker AI | Build, train, tune, deploy, and govern ML models with broad control over frameworks and infrastructure | [Amazon SageMaker AI](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html) |
| Amazon SageMaker JumpStart | SageMaker AI hub for pre-trained models, algorithms, and solution templates | [SageMaker JumpStart](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-jumpstart.html) |
| Amazon Textract | Extract text, handwriting, forms, tables, and fields from documents | [Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/what-is.html) |
| Amazon Transcribe | Convert streaming or recorded speech to text | [Amazon Transcribe](https://docs.aws.amazon.com/transcribe/latest/dg/what-is.html) |
| Amazon Translate | Translate text between languages | [Amazon Translate](https://docs.aws.amazon.com/translate/latest/dg/what-is.html) |
| AWS Transform | Agentic AI service for modernizing applications, code, and infrastructure and reducing migration work | [AWS Transform](https://docs.aws.amazon.com/transform/latest/userguide/what-is-service.html) |

Read [Managed AI services](managed-ai-services.md), [Bedrock vs SageMaker AI](bedrock-vs-sagemaker-ai.md), and [Agentic AI and AgentCore](agentic-ai-mcp-strands-agentcore.md) for the deep group.

## Management and governance

| Service | Recognition cue | Official source |
| --- | --- | --- |
| AWS CloudTrail | Record AWS API calls and account activity for auditing: who did what, when, and from where | [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) |
| Amazon CloudWatch | Collect metrics, logs, alarms, dashboards, and traces for operational monitoring | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) |
| AWS Config | Record resource configuration changes and evaluate resources against configuration rules | [AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| AWS Trusted Advisor | Check AWS environments against best-practice recommendations across cost optimization, performance, security, fault tolerance, service limits, and operational excellence | [Trusted Advisor](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor.html) |
| AWS Well-Architected Tool | Review a workload against AWS Well-Architected Framework questions and improvement guidance | [Well-Architected Tool](https://docs.aws.amazon.com/wellarchitected/latest/userguide/intro.html) |

**Trap:** CloudTrail audits account activity; CloudWatch monitors system behavior; Config tracks resource configuration and compliance.

## Networking and content delivery

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon CloudFront | Content delivery network that caches content near users for lower latency | [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Amazon VPC | Logically isolated network for AWS resources; controls subnets, routes, and network boundaries | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |

Know that AWS PrivateLink provides private service connectivity through VPC endpoints, although AWS lists it as a feature in the content outline rather than as a standalone entry on the current service page.

## Security, identity, and compliance

| Service | Recognition cue | Official source |
| --- | --- | --- |
| AWS Artifact | Download AWS compliance reports and review agreements; think audit evidence about AWS | [AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/what-is-aws-artifact.html) |
| AWS Identity and Access Management (IAM) | Define identities and least-privilege permissions for AWS actions and resources | [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Amazon Inspector | Scan supported workloads for software vulnerabilities and unintended network exposure | [Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| AWS Key Management Service (AWS KMS) | Create and control encryption keys used to protect data | [AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) |
| Amazon Macie | Discover and classify sensitive data in Amazon S3 | [Amazon Macie](https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html) |
| AWS Secrets Manager | Store, retrieve, and rotate secrets such as API keys and database credentials | [Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |

**Selection cues:** IAM authorizes access; KMS manages encryption keys; Secrets Manager stores credentials; Macie finds sensitive S3 data; Inspector finds workload vulnerabilities; Artifact supplies AWS compliance documents.

## Storage

| Service | Recognition cue | Official source |
| --- | --- | --- |
| Amazon S3 | Durable object storage for datasets, documents, model artifacts, logs, and data-lake content | [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |
| Amazon S3 Glacier | S3 archival storage classes for low-cost, long-term data with retrieval tradeoffs | [S3 Glacier storage classes](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html) |

## Current maintenance notices for named SageMaker features

AWS closed SageMaker Clarify, SageMaker Model Monitor, and Amazon A2I to new customers on July 30, 2026. Existing customers can continue normal use, but AWS does not plan new features. Clarify still appears in the current exam objectives, and all three can appear in existing architectures. Learn their roles while checking current alternatives for a new implementation.

- **Clarify:** bias analysis and feature-attribution explainability.
- **Model Monitor:** scheduled data-quality, model-quality, bias-drift, or feature-attribution monitoring for supported endpoint and batch workflows.
- **A2I:** human review for low-confidence or sampled predictions, with built-in Textract key-value and Rekognition moderation task types plus custom tasks.

## Named features and principles outside the 51-service table

The content outline also names features and concepts that can decide an answer:

- Amazon Bedrock Knowledge Bases, Amazon Bedrock Agents (the exam outline's label, now Amazon Bedrock Agents Classic for eligible existing customers), Guardrails, Prompt Management, and Model Evaluations;
- SageMaker Clarify and SageMaker Model Cards;
- AgentCore Identity and Policy;
- AWS PrivateLink;
- encryption at rest and in transit;
- the AWS shared responsibility model;
- RAG, source citation, lineage, logging, output validation, and least privilege.

Treat them as testable even though AWS does not list each one as a separate service.

## Scenario drills

1. **A company wants sentiment and entity extraction from reviews with no model training.** Choose Comprehend.
2. **A bank wants full control over training a tabular fraud model.** Choose SageMaker AI.
3. **A team wants a managed RAG assistant using foundation models.** Choose Bedrock and consider Knowledge Bases.
4. **An agent needs one managed MCP endpoint backed by existing APIs.** Choose AgentCore Gateway.
5. **Auditors need a record of AWS API activity.** Choose CloudTrail.
6. **Security staff need to find PII in an S3 data lake.** Choose Macie.
7. **Developers need to modernize legacy applications with specialized AI agents.** Choose AWS Transform.
8. **Business analysts need dashboards, natural-language data analysis, and workflows.** Choose Amazon Quick.
9. **A team needs to catalog third-party datasets it can subscribe to.** Choose AWS Data Exchange.
10. **An application needs low-latency key-value state.** Choose DynamoDB; use ElastiCache when the main requirement is in-memory caching.

[Domain guide](../README.md#domain-guide) · [Reference index](README.md) · [Common exam traps](common-exam-traps.md)

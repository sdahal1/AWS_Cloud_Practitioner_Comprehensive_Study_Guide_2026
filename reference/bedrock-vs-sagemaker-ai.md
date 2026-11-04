# Amazon Bedrock vs Amazon SageMaker AI

Both services support AI on AWS. The exam usually turns on the workload, the level of control, and the team's ML expertise.

## Fast decision

Choose **Amazon Bedrock** as the starting point when a team wants to build a generative AI application or agent with managed foundation models, APIs, prompting, RAG, Guardrails, model evaluation, or managed customization without managing model infrastructure.

Choose **Amazon SageMaker AI** when a team needs broader ML work or control over data preparation, algorithms, training jobs, frameworks, compute, endpoints, MLOps, and predictive or custom models.

The services can work together. A team can train or fine-tune a supported model in SageMaker AI and import it into Bedrock for managed inference, subject to Bedrock's current custom-model support.

## Side-by-side comparison

| Decision | Amazon Bedrock | Amazon SageMaker AI |
|---|---|---|
| Main scope | Generative AI applications and agents | End-to-end AI and ML development, including current foundation-model customization and deployment |
| Starting models | Managed foundation models from Amazon and other providers; supported imported custom models | Built-in algorithms, your code and containers, models from hubs and the public model catalog, and custom models |
| Infrastructure control | Managed model APIs and application features; AgentCore also supplies managed agent infrastructure | Managed options range from serverless model customization to chosen training jobs, containers, accelerators, endpoints, and deployment patterns |
| ML expertise | Lower barrier for application developers | Supports guided and serverless paths while retaining detailed controls for data scientists and ML engineers |
| Classical ML | Not the main use | Core use: regression, classification, forecasting, computer vision, and other ML workloads |
| Foundation-model access | Unified managed APIs, inference profiles, several service tiers, and Bedrock application capabilities | Customize and deploy supported open or proprietary models through Studio, SDKs, serverless jobs, or managed endpoints; JumpStart remains one starting point |
| RAG | Knowledge Bases manages ingestion, retrieval, supported vector-store integrations, generation, citations, and RAG evaluation | Build a custom retrieval pipeline with chosen data, embedding, search, training, and endpoint components |
| Agents | AgentCore Harness and composable Runtime, Gateway, Identity, Memory, Policy, Observability, Evaluations, Optimization, Payments, Browser, Code Interpreter, and Registry; Amazon Bedrock Agents Classic remains for eligible existing customers | Host models or custom agent components and assemble the rest of the stack with chosen services |
| Safety | Bedrock Guardrails can evaluate content through invocation configuration, selective `guardContent`, or the standalone `ApplyGuardrail` API | Implement application and model controls or call `ApplyGuardrail` around a SageMaker-hosted model's input and output where appropriate |
| Evaluation | Model evaluation with programmatic, human, or judge-model methods; RAG evaluation; AgentCore evaluation for agents | SageMaker evaluation tools and custom code; SageMaker Clarify remains available to eligible existing customers but closed to new customers on July 30, 2026 |
| Customization | Prompting, RAG, model distillation, fine-tuning, reinforcement fine-tuning, and supported import paths vary by model | Serverless customization for supported models, including SFT, DPO, RFT, LoRA, or full fine-tuning where supported, plus custom training jobs and containers |
| Operations | Less model-serving infrastructure management; AgentCore adds managed agent operations | More hosting choices and operational control, with managed and serverless options alongside provisioned endpoints |
| Typical pricing cue | On-demand token or modality pricing, batch, prompt caching, service tiers, Provisioned Throughput, customization, evaluations, Guardrails, Knowledge Bases, and AgentCore capability charges | Pay for customization or training jobs, inference endpoints or serverless usage, processing, storage, data transfer, and selected supporting services |

## Scenario cues

| Scenario says... | Best starting answer | Reason |
|---|---|---|
| "Use several foundation models through managed APIs" | Amazon Bedrock | Bedrock provides managed FM access and GenAI features |
| "Build a RAG assistant with a managed knowledge-base workflow" | Amazon Bedrock Knowledge Bases | It manages common retrieval and generation steps |
| "Apply content, denied-topic, or sensitive-information rules before, during, or after a model call" | Amazon Bedrock Guardrails | Use invocation configuration for supported Bedrock calls, selective `guardContent`, or standalone `ApplyGuardrail`; the standalone API can screen content around a SageMaker-hosted or third-party model |
| "Train a fraud-classification model on tabular data" | Amazon SageMaker AI | This is predictive ML, not a foundation-model application |
| "Choose the training algorithm, framework, container, and GPU instances" | Amazon SageMaker AI | The team requires training and infrastructure control |
| "Start from a pre-trained open model in a model hub and deploy to a SageMaker endpoint" | SageMaker JumpStart | JumpStart supplies pre-trained models, algorithms, and solution templates inside SageMaker AI |
| "Train a model from scratch" | Amazon SageMaker AI | Bedrock focuses on consuming and adapting foundation models rather than general custom training |
| "Build a GenAI prototype with little ML expertise and no server management" | Amazon Bedrock | Its managed capabilities reduce ML and infrastructure work |

## Common traps

**Bedrock does more than call text models.** It supports multimodal models and capabilities such as Knowledge Bases, Agents, Guardrails, prompt management, and evaluations. Match the feature to the question.

**SageMaker AI also supports foundation models.** The phrase `foundation model` does not force Bedrock. Full control over training, containers, endpoints, or infrastructure points toward SageMaker AI.

**Fine-tuning alone no longer settles the choice.** Bedrock supports managed customization for selected models. SageMaker AI wins when the scenario requires broader model, framework, training, or hosting control.

**JumpStart is part of SageMaker AI.** It helps you discover and deploy pre-trained models and solutions. It is not Bedrock's model catalog.

**A purpose-built AI service may be simpler than either platform.** Choose Transcribe for speech to text or Textract for document fields when the scenario asks for that standard capability and no custom model.

## Platform capabilities

Bedrock capabilities include model access, Converse-style unified inference, Knowledge Bases, Guardrails, Prompt Management, evaluations, customization, and AgentCore. Amazon Bedrock Agents Classic remains an existing-customer feature. SageMaker AI covers building, training, and deploying models, JumpStart, Model Cards, training jobs, endpoints, and MLOps. Clarify and Model Monitor remain existing-customer features.

## Official sources

- [AWS decision guide: Amazon Bedrock or Amazon SageMaker AI?](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/bedrock-or-sagemaker.html)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Amazon SageMaker AI Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)
- [SageMaker JumpStart](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-jumpstart.html)
- [Amazon Bedrock custom models](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html)

[Domain guide](../README.md#domain-guide) · [Service selection](service-selection.md) · [Reference index](README.md)

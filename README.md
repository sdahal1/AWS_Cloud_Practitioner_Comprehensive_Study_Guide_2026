# AWS Certified AI Practitioner (AIF-C01) comprehensive study guide

[Exam overview](exam-overview.md): exam scope, candidate profile, formats, and official references.

AIF-C01 is a foundational exam with **65 questions in 90 minutes**: 50 scored and 15 unscored. The passing score is **700 on a 100–1,000 scale**. Question formats include multiple choice, multiple response, ordering, and matching. Scoring is compensatory across the exam, rather than a separate pass requirement for every domain.

This independent community guide contains **14 task-based lessons and all 69 objectives**, organized below in exam order. It is not AWS training and does not contain official AWS exam questions. The objective descriptions condense and rephrase the official AWS wording. AWS can change the outline and in-scope services; the [official exam guide](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html) and [revision history](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/aif-01-revisions.html) establish the version for an exam date.

## Domain guide

| Domain | Weight | Tasks | Objectives | Lesson folder |
|---|---:|---|---:|---|
| [1. Fundamentals of AI and ML](#domain-1-fundamentals-of-ai-and-ml-20) | 20% | 1.1–1.3 | 17 | [Lessons 01–03](lessons/domain-1-ai-ml/) |
| [2. Fundamentals of GenAI](#domain-2-fundamentals-of-genai-24) | 24% | 2.1–2.3 | 14 | [Lessons 04–06](lessons/domain-2-generative-ai/) |
| [3. Applications of Foundation Models](#domain-3-applications-of-foundation-models-28) | 28% | 3.1–3.4 | 19 | [Lessons 07–10](lessons/domain-3-foundation-models/) |
| [4. Guidelines for Responsible AI](#domain-4-guidelines-for-responsible-ai-14) | 14% | 4.1–4.2 | 11 | [Lessons 11–12](lessons/domain-4-responsible-ai/) |
| [5. Security, Compliance, and Governance for AI Solutions](#domain-5-security-compliance-and-governance-for-ai-solutions-14) | 14% | 5.1–5.2 | 8 | [Lessons 13–14](lessons/domain-5-security-compliance-governance/) |

## Domain 1: Fundamentals of AI and ML (20%)

Source: [Official Domain 1 page](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain1.html)

### Task 1.1: Explain basic AI concepts and terminologies

[Lesson 01: AI and ML concepts](lessons/domain-1-ai-ml/01-ai-ml-concepts.md) · [Practice: Task 1.1](practice/question-bank.md#task-11)

**Concepts:** Distinguish AI, ML, deep learning, GenAI, and agentic AI; compare supervised, unsupervised, and reinforcement learning; identify data types, overfitting, underfitting, and inference modes.

**Relevant AWS services and features:** Amazon SageMaker AI.

**Objectives**

- [ ] Define core AI terms, including AI, ML, deep learning, neural networks, computer vision, NLP, models, algorithms, training, inference, bias, fairness, fit, LLMs, GenAI, and agentic AI. [Lesson: Core terms](lessons/domain-1-ai-ml/01-ai-ml-concepts.md#core-terms)
- [ ] Compare AI, ML, GenAI, deep learning, and agentic AI. [Lesson: Mental model: rules, learning, generation, and action](lessons/domain-1-ai-ml/01-ai-ml-concepts.md#mental-model-rules-learning-generation-and-action)
- [ ] Describe batch, real-time, asynchronous, and serverless inference. [Lesson: Inference choices](lessons/domain-1-ai-ml/01-ai-ml-concepts.md#inference-choices)
- [ ] Distinguish labeled, unlabeled, tabular, time-series, image, text, structured, and unstructured data. [Lesson: Data types use two separate axes](lessons/domain-1-ai-ml/01-ai-ml-concepts.md#data-types-use-two-separate-axes)
- [ ] Describe supervised, unsupervised, and reinforcement learning. [Lesson: Learning methods](lessons/domain-1-ai-ml/01-ai-ml-concepts.md#learning-methods)

### Task 1.2: Identify practical use cases for AI

[Lesson 02: AI use cases and service selection](lessons/domain-1-ai-ml/02-ai-use-cases.md) · [Practice: Task 1.2](practice/question-bank.md#task-12)

**Concepts:** Decide whether AI fits; match classification, regression, and clustering to outcomes; choose traditional ML, managed AI, a foundation model, or an agent.

**Relevant AWS services and features:** SageMaker AI, Transcribe, Translate, Comprehend, Lex V2, Polly, Rekognition, Textract.

**Objectives**

- [ ] Recognize where AI or ML adds value through decision support, scale, or automation. [Lesson: Where AI and ML add value](lessons/domain-1-ai-ml/02-ai-use-cases.md#where-ai-and-ml-add-value)
- [ ] Determine when AI or ML is unsuitable based on cost-benefit analysis or the need for a fixed result. [Lesson: When AI is the wrong choice](lessons/domain-1-ai-ml/02-ai-use-cases.md#when-ai-is-the-wrong-choice)
- [ ] Match regression, classification, or clustering to a use case. [Lesson: Select the ML technique](lessons/domain-1-ai-ml/02-ai-use-cases.md#select-the-ml-technique)
- [ ] Identify real-world uses such as computer vision, NLP, speech recognition, recommendations, fraud detection, forecasting, knowledge bases, and agentic AI. [Lesson: Real-world application map](lessons/domain-1-ai-ml/02-ai-use-cases.md#real-world-application-map)
- [ ] Explain the capabilities of AWS managed AI and ML services. [Lesson: AWS managed AI and ML services](lessons/domain-1-ai-ml/02-ai-use-cases.md#aws-managed-ai-and-ml-services)
- [ ] Choose between traditional ML and foundation models based on regulation, explainability, and operational constraints. [Lesson: Traditional ML or a foundation model](lessons/domain-1-ai-ml/02-ai-use-cases.md#traditional-ml-or-a-foundation-model)

### Task 1.3: Describe the AI/ML development lifecycle

[Lesson 03: AI/ML lifecycle, MLOps, and metrics](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md) · [Practice: Task 1.3](practice/question-bank.md#task-13)

**Concepts:** Order lifecycle stages; compare model sources and hosting; explain MLOps, monitoring, drift, retraining, classification metrics, and business metrics.

**Relevant AWS services and features:** SageMaker AI, Amazon Bedrock, Amazon S3, Amazon CloudWatch, Amazon Quick, Kiro.

**Objectives**

- [ ] Describe and distinguish the components of an AI/ML pipeline. [Lesson: Pipeline components](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#pipeline-components)
- [ ] Describe foundation model sources, including open-source pretrained models and custom-trained models. [Lesson: Sources of foundation models](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#sources-of-foundation-models)
- [ ] Compare managed APIs and self-hosted APIs for production model use. [Lesson: Production access: managed API or self-hosted API](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#production-access-managed-api-or-self-hosted-api)
- [ ] Match AWS services and features to each AI/ML pipeline stage. [Lesson: Service selection across the lifecycle](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#service-selection-across-the-lifecycle)
- [ ] Describe MLOps concepts such as experimentation, repeatable processes, scale, technical debt, production readiness, monitoring, and retraining. [Lesson: MLOps concepts](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#mlops-concepts)
- [ ] Use model performance metrics and business metrics to evaluate ML models. [Lesson: Classification metrics](lessons/domain-1-ai-ml/03-lifecycle-mlops-metrics.md#classification-metrics)

## Domain 2: Fundamentals of GenAI (24%)

Source: [Official Domain 2 page](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain2.html)

### Task 2.1: Explain the basic concepts of generative AI (GenAI)

[Lesson 04: Generative AI concepts and agents](lessons/domain-2-generative-ai/04-genai-concepts-agents.md) · [Practice: Task 2.1](practice/question-bank.md#task-21)

**Concepts:** Explain FMs, LLMs, transformers, tokens, context windows, embeddings, vectors, chunking, multimodality, the FM lifecycle, and agentic concepts.

**Relevant AWS services and features:** Amazon Bedrock and Knowledge Bases as lesson examples.

**Objectives**

- [ ] Define tokens, chunking, embeddings, vectors, prompt engineering, transformer-based LLMs, foundation models, multimodal models, and diffusion models. [Lesson: Foundation concepts](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#foundation-concepts)
- [ ] Identify GenAI uses such as media generation, summarization, assistants, translation, code generation, customer service, search, and recommendations. [Lesson: GenAI use cases](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#genai-use-cases)
- [ ] Describe the foundation model lifecycle from data and model selection through feedback. [Lesson: Foundation-model lifecycle](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#foundation-model-lifecycle)
- [ ] Explain how token-based pricing affects inference cost and performance. [Lesson: Token pricing and inference performance](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#token-pricing-and-inference-performance)
- [ ] Describe the role of context engineering in foundation model applications. [Lesson: Context engineering](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#context-engineering)
- [ ] Define agentic AI concepts, including multi-agent patterns, MCP, agent communication, memory, tools, and workflow orchestration. [Lesson: Agentic AI building blocks](lessons/domain-2-generative-ai/04-genai-concepts-agents.md#agentic-ai-building-blocks)

### Task 2.2: Understand the capabilities and limitations of GenAI for solving business problems

[Lesson 05: Generative AI value and limitations](lessons/domain-2-generative-ai/05-genai-value-limitations.md) · [Practice: Task 2.2](practice/question-bank.md#task-22)

**Concepts:** Connect GenAI benefits to business value; identify hallucination, inaccuracy, nondeterminism, and interpretability limits; select models by quality, cost, latency, and risk.

**Relevant AWS services and features:** Amazon Bedrock, Bedrock Guardrails.

**Objectives**

- [ ] Describe GenAI advantages such as adaptability, responsiveness, conversation, and content generation. [Lesson: GenAI advantages](lessons/domain-2-generative-ai/05-genai-value-limitations.md#genai-advantages)
- [ ] Identify GenAI disadvantages such as hallucinations, limited interpretability, inaccuracy, and nondeterminism. [Lesson: Limitations and failure modes](lessons/domain-2-generative-ai/05-genai-value-limitations.md#limitations-and-failure-modes)
- [ ] Select GenAI models by type, performance, capability, constraints, compliance, cost, latency, and complexity. [Lesson: Select a model by constraints](lessons/domain-2-generative-ai/05-genai-value-limitations.md#select-a-model-by-constraints)
- [ ] Measure GenAI business value with metrics such as ROI, efficiency, conversion, revenue per user, accuracy, and customer lifetime value. [Lesson: Business value and metrics](lessons/domain-2-generative-ai/05-genai-value-limitations.md#business-value-and-metrics)

### Task 2.3: Describe AWS infrastructure and technologies for building GenAI applications

[Lesson 06: AWS services for generative AI](lessons/domain-2-generative-ai/06-aws-genai-services.md) · [Practice: Task 2.3](practice/question-bank.md#task-23)

**Concepts:** Choose a managed FM API, ML platform, business workspace, developer environment, agent SDK, or production agent platform; compare pricing, capacity, security, and Region choices.

**Relevant AWS services and features:** Amazon Bedrock, SageMaker AI, SageMaker JumpStart, Amazon Quick, Kiro, Strands Agents, Amazon Bedrock AgentCore.

**Objectives**

- [ ] Identify AWS services and features for GenAI application development. [Lesson: Service-selection guide](lessons/domain-2-generative-ai/06-aws-genai-services.md#service-selection-guide)
- [ ] Describe how AWS GenAI services improve access, efficiency, cost, delivery speed, and business outcomes. [Lesson: Advantages of AWS GenAI services](lessons/domain-2-generative-ai/06-aws-genai-services.md#advantages-of-aws-genai-services)
- [ ] Describe AWS infrastructure benefits for GenAI security, compliance, responsibility, and safety. [Lesson: Security, compliance, responsibility, and safety](lessons/domain-2-generative-ai/06-aws-genai-services.md#security-compliance-responsibility-and-safety)
- [ ] Compare AWS GenAI cost tradeoffs involving responsiveness, availability, redundancy, performance, regions, token pricing, provisioned throughput, and custom models. [Lesson: Cost and architecture tradeoffs](lessons/domain-2-generative-ai/06-aws-genai-services.md#cost-and-architecture-tradeoffs)

## Domain 3: Applications of Foundation Models (28%)

Source: [Official Domain 3 page](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain3.html)

### Task 3.1: Describe design considerations for applications that use foundation models (FMs)

[Lesson 07: Design applications that use foundation models](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md) · [Practice: Task 3.1](practice/question-bank.md#task-31)

**Concepts:** Select a model and inference controls; calculate full application cost; explain prompt caching and RAG; compare chunking and vector stores; distinguish an agent from a chatbot.

**Relevant AWS services and features:** Amazon Bedrock, Bedrock Knowledge Bases, Amazon OpenSearch Service, Amazon Aurora, Amazon Neptune, Amazon RDS for PostgreSQL.

**Objectives**

- [ ] Select foundation models by cost, modality, latency, multilingual support, model size, model complexity, customization, input/output length, and prompt caching. [Lesson: Select a foundation model](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#select-a-foundation-model)
- [ ] Describe how inference parameters such as temperature and input or output length affect responses. [Lesson: Control inference without changing the model](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#control-inference-without-changing-the-model)
- [ ] Define Retrieval Augmented Generation and describe its business uses. [Lesson: RAG supplies request-time knowledge](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#rag-supplies-request-time-knowledge)
- [ ] Identify AWS services that store embeddings in vector databases. [Lesson: Choose a vector store](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#choose-a-vector-store)
- [ ] Compare customization costs for pre-training, fine-tuning, in-context learning, RAG, and model distillation. [Lesson: Pick the lightest adaptation method](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#pick-the-lightest-adaptation-method)
- [ ] Define AI agents and describe their business uses. [Lesson: Agents complete multi-step work](lessons/domain-3-foundation-models/07-fm-design-rag-agents.md#agents-complete-multi-step-work)

### Task 3.2: Choose effective prompt engineering techniques

[Lesson 08: Prompt engineering](lessons/domain-3-foundation-models/08-prompt-engineering.md) · [Practice: Task 3.2](practice/question-bank.md#task-32)

**Concepts:** Identify prompt parts; choose zero-shot, single-shot, few-shot, chain-of-thought, chaining, and templates; recognize prompt attacks; test, version, and deploy prompts.

**Relevant AWS services and features:** Amazon Bedrock Prompt Management, Bedrock Guardrails.

**Objectives**

- [ ] Define prompt engineering concepts and parts, including context, instructions, and negative prompts. [Lesson: Build a prompt from clear parts](lessons/domain-3-foundation-models/08-prompt-engineering.md#build-a-prompt-from-clear-parts)
- [ ] Define chain-of-thought, zero-shot, single-shot, few-shot, and prompt-template techniques. [Lesson: Choose the prompt method](lessons/domain-3-foundation-models/08-prompt-engineering.md#choose-the-prompt-method)
- [ ] Apply prompt engineering benefits and practices such as experimentation, guardrails, discovery, specificity, and concision. [Lesson: Improve a weak prompt](lessons/domain-3-foundation-models/08-prompt-engineering.md#improve-a-weak-prompt)
- [ ] Identify prompt exposure, poisoning, hijacking, and jailbreaking risks. [Lesson: Prompt attacks and failures](lessons/domain-3-foundation-models/08-prompt-engineering.md#prompt-attacks-and-failures)
- [ ] Describe prompt versioning and management with Amazon Bedrock Prompt Management. [Lesson: Amazon Bedrock Prompt Management](lessons/domain-3-foundation-models/08-prompt-engineering.md#amazon-bedrock-prompt-management)

### Task 3.3: Describe the training and fine-tuning process for FMs

[Lesson 09: Training and customization](lessons/domain-3-foundation-models/09-training-customization.md) · [Practice: Task 3.3](practice/question-bank.md#task-33)

**Concepts:** Compare pre-training, continued pre-training, fine-tuning, instruction tuning, RLHF, reinforcement fine-tuning, distillation, transfer learning, RAG, and in-context learning; evaluate training data.

**Relevant AWS services and features:** Amazon Bedrock model customization, Amazon SageMaker AI.

**Objectives**

- [ ] Describe pre-training, fine-tuning, continued pre-training, and distillation. [Lesson: Training methods compared](lessons/domain-3-foundation-models/09-training-customization.md#training-methods-compared)
- [ ] Define instruction tuning, domain adaptation, transfer learning, and continued pre-training. [Lesson: Fine-tuning teaches stable behavior](lessons/domain-3-foundation-models/09-training-customization.md#fine-tuning-teaches-stable-behavior)
- [ ] Prepare representative, governed, sized, and labeled data for fine-tuning and RLHF. [Lesson: Prepare training data](lessons/domain-3-foundation-models/09-training-customization.md#prepare-training-data)

### Task 3.4: Describe methods to evaluate FM performance

[Lesson 10: Evaluate foundation models and applications](lessons/domain-3-foundation-models/10-evaluation.md) · [Practice: Task 3.4](practice/question-bank.md#task-34)

**Concepts:** Compare human-in-the-loop evaluation, benchmark datasets, programmatic metrics, and LLM-as-a-judge; use ROUGE, BLEU, and BERTScore; evaluate RAG, agents, workflows, and business outcomes.

**Relevant AWS services and features:** Amazon Bedrock evaluations, SageMaker AI, Amazon CloudWatch.

**Objectives**

- [ ] Choose evaluation approaches such as human review, benchmark datasets, and Amazon Bedrock model evaluation. [Lesson: Evaluation approaches](lessons/domain-3-foundation-models/10-evaluation.md#evaluation-approaches)
- [ ] Use relevant metrics such as ROUGE, BLEU, BERTScore, and LLM-as-a-judge. [Lesson: Metrics for generated text](lessons/domain-3-foundation-models/10-evaluation.md#metrics-for-generated-text)
- [ ] Determine whether a foundation model meets business objectives such as productivity, engagement, and task engineering. [Lesson: Connect evaluation to business objectives](lessons/domain-3-foundation-models/10-evaluation.md#connect-evaluation-to-business-objectives)
- [ ] Evaluate foundation model applications that use RAG, agents, or workflows. [Lesson: Evaluate RAG in two stages](lessons/domain-3-foundation-models/10-evaluation.md#evaluate-rag-in-two-stages)
- [ ] Measure business alignment with task completion, user satisfaction, and cost per interaction. [Lesson: Design an evaluation plan](lessons/domain-3-foundation-models/10-evaluation.md#design-an-evaluation-plan)

## Domain 4: Guidelines for Responsible AI (14%)

Source: [Official Domain 4 page](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain4.html)

### Task 4.1: Explain the development of AI systems that are responsible

[Lesson 11: Responsible AI](lessons/domain-4-responsible-ai/11-responsible-ai.md) · [Practice: Task 4.1](practice/question-bank.md#task-41)

**Concepts:** Identify bias, fairness, inclusivity, robustness, safety, and veracity risks; evaluate data and subgroups; select controls for harmful content, PII, grounding, and human review.

**Relevant AWS services and features:** SageMaker Clarify, Amazon Bedrock Guardrails, Amazon CloudWatch, AWS KMS.

**Objectives**

- [ ] Identify responsible AI features such as bias, fairness, inclusivity, robustness, safety, and veracity. [Lesson: Responsible AI features](lessons/domain-4-responsible-ai/11-responsible-ai.md#responsible-ai-features)
- [ ] Explain how tools such as Amazon Bedrock Guardrails help identify responsible AI features. [Lesson: Amazon Bedrock Guardrails](lessons/domain-4-responsible-ai/11-responsible-ai.md#amazon-bedrock-guardrails)
- [ ] Apply environmental and sustainability considerations when selecting a model. [Lesson: Sustainability and model selection](lessons/domain-4-responsible-ai/11-responsible-ai.md#sustainability-and-model-selection)
- [ ] Identify GenAI legal risks involving intellectual property, biased output, customer trust, end users, and hallucinations. [Lesson: Legal, intellectual-property, and trust risks](lessons/domain-4-responsible-ai/11-responsible-ai.md#legal-intellectual-property-and-trust-risks)
- [ ] Assess datasets for inclusivity, diversity, curation, and balance. [Lesson: Data quality, labels, and subgroup analysis](lessons/domain-4-responsible-ai/11-responsible-ai.md#data-quality-labels-and-subgroup-analysis)
- [ ] Describe how bias and variance affect demographic groups, accuracy, overfitting, and underfitting. [Lesson: Bias, variance, overfitting, and underfitting](lessons/domain-4-responsible-ai/11-responsible-ai.md#bias-variance-overfitting-and-underfitting)
- [ ] Describe methods for detecting and monitoring bias, trustworthiness, and truthfulness through label analysis, human audits, and subgroup analysis. [Lesson: Control selection table](lessons/domain-4-responsible-ai/11-responsible-ai.md#control-selection-table)

### Task 4.2: Recognize the importance of transparent and explainable models

[Lesson 12: Transparency and explainability](lessons/domain-4-responsible-ai/12-transparency-explainability.md) · [Practice: Task 4.2](practice/question-bank.md#task-42)

**Concepts:** Separate transparency, interpretability, and explainability; match stakeholder needs to evidence; document models; detect bias and explain features; compare safety and transparency; design review and appeal paths.

**Relevant AWS services and features:** SageMaker Model Cards, SageMaker Clarify, Amazon Bedrock evaluations.

**Objectives**

- [ ] Distinguish transparent and explainable models from models that lack those qualities. [Lesson: Transparent and opaque models](lessons/domain-4-responsible-ai/12-transparency-explainability.md#transparent-and-opaque-models)
- [ ] Describe tools and evidence for model transparency and explainability, including Model Cards, model evaluations, open-source details, data, and licensing. [Lesson: Match the question to the evidence](lessons/domain-4-responsible-ai/12-transparency-explainability.md#match-the-question-to-the-evidence)
- [ ] Identify tradeoffs between model safety and transparency, including interpretability and performance measures. [Lesson: Transparency and safety tradeoffs](lessons/domain-4-responsible-ai/12-transparency-explainability.md#transparency-and-safety-tradeoffs)
- [ ] Apply human-centered explainable AI principles such as user feedback and decision transparency. [Lesson: Human-centered explainable AI](lessons/domain-4-responsible-ai/12-transparency-explainability.md#human-centered-explainable-ai)

## Domain 5: Security, Compliance, and Governance for AI Solutions (14%)

Source: [Official Domain 5 page](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain5.html)

### Task 5.1: Explain methods to secure AI systems

[Lesson 13: Security for AI systems](lessons/domain-5-security-compliance-governance/13-security.md) · [Practice: Task 5.1](practice/question-bank.md#task-51)

**Concepts:** Apply shared responsibility, least privilege, encryption, private connectivity, sensitive-data discovery, content controls, audit logging, threat detection, vulnerability management, grounding, and tool authorization.

**Relevant AWS services and features:** IAM, AWS KMS, AWS PrivateLink, Amazon Macie, Bedrock Guardrails, AgentCore Identity and Policy, AWS CloudTrail, Amazon Inspector. Amazon GuardDuty and AWS WAF are supplementary architecture context, not examples named in the official Task 5.1 objective.

**Objectives**

- [ ] Identify AWS security services and features for AI systems, including IAM, encryption, Macie, PrivateLink, shared responsibility, AgentCore Identity and Policy, and Bedrock Guardrails. [Lesson: Control and service decision table](lessons/domain-5-security-compliance-governance/13-security.md#control-and-service-decision-table)
- [ ] Describe source citation and data-origin records such as lineage, catalogs, and SageMaker Model Cards. [Lesson: Citations, catalogs, lineage, and Model Cards](lessons/domain-5-security-compliance-governance/13-security.md#citations-catalogs-lineage-and-model-cards)
- [ ] Apply secure data engineering practices for quality, privacy, access control, and integrity. [Lesson: Secure data engineering](lessons/domain-5-security-compliance-governance/13-security.md#secure-data-engineering)
- [ ] Address AI security and privacy risks through application security, threat detection, vulnerability management, infrastructure protection, prompt-injection defenses, encryption, leakage prevention, output validation, audit logging, and toxicity controls. [Lesson: Application and infrastructure protection](lessons/domain-5-security-compliance-governance/13-security.md#application-and-infrastructure-protection)
- [ ] Describe hallucination detection methods and grounding techniques that improve output accuracy, including RAG grounding, output validation, and confidence scoring. [Lesson: Grounding and hallucination detection](lessons/domain-5-security-compliance-governance/13-security.md#grounding-and-hallucination-detection)

### Task 5.2: Recognize governance and compliance regulations for AI systems

[Lesson 14: Governance and compliance](lessons/domain-5-security-compliance-governance/14-governance-compliance.md) · [Practice: Task 5.2](practice/question-bank.md#task-52)

**Concepts:** Connect obligations to policies, controls, evidence, reviews, and corrections; govern data across its lifecycle; address residency, retention, logging, monitoring, observation, lineage, and model documentation.

**Relevant AWS services and features:** AWS Config, Amazon Inspector, AWS Artifact, AWS CloudTrail, AWS Trusted Advisor. AWS Audit Manager and AWS Glue Data Catalog are supplementary architecture context, not examples named in the official Task 5.2 objective.

**Objectives**

- [ ] Identify AWS services and features that support governance and regulatory compliance. [Lesson: AWS service decision table](lessons/domain-5-security-compliance-governance/14-governance-compliance.md#aws-service-decision-table)
- [ ] Describe governance strategies for data lifecycles, logging, residency, monitoring, observation (the official wording), observability, and retention. [Lesson: Data governance across the lifecycle](lessons/domain-5-security-compliance-governance/14-governance-compliance.md#data-governance-across-the-lifecycle)
- [ ] Follow governance protocols for policies, review cadence, review strategies, governance frameworks, transparency standards, and team training. [Lesson: Governance protocols](lessons/domain-5-security-compliance-governance/14-governance-compliance.md#governance-protocols)

## Reference

| Topic | Reference |
|---|---|
| AWS service choices | [Service selection](reference/service-selection.md) |
| Speech, text, image, document, and bot capabilities | [Purpose-built AWS AI services](reference/managed-ai-services.md) |
| Foundation-model applications and custom ML | [Amazon Bedrock vs. Amazon SageMaker AI](reference/bedrock-vs-sagemaker-ai.md) |
| Agent concepts and platform boundaries | [Agentic AI, MCP, Strands Agents, and AgentCore](reference/agentic-ai-mcp-strands-agentcore.md) |
| Model, application, and business measures | [Metrics](reference/metrics.md) |
| Terms and definitions | [Glossary](reference/glossary.md) |
| Closely related services and approaches | [Common exam traps](reference/common-exam-traps.md) |

## Practice questions

The [question bank](practice/question-bank.md) contains **419 CloudCertPrep questions and 20 SaveMyCert worked questions**, with answers and explanations. The task links above point directly to each relevant section. These community materials have not passed an AWS review and are not an exam simulator. The [correction ledger](THIRD_PARTY_NOTICES.md#practice-correction-ledger) records question-bank corrections and audit scope.

## Sources and licensing

[Sources](SOURCES.md) · [Third-party notices](THIRD_PARTY_NOTICES.md) · [Changelog](CHANGELOG.md)

Original guide prose uses [Creative Commons Attribution 4.0 International](LICENSE). Third-party questions and adapted material retain their original licenses, with attributions and modification details in the notices.

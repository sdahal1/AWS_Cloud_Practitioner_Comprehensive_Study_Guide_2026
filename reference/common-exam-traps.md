# Common AIF-C01 exam traps

Most distractors are real services or valid concepts. They fail because they solve a neighboring problem, ignore a stated constraint, or act at the wrong layer.

## Service-direction traps

| Pair | Distinction |
|---|---|
| Transcribe vs Polly | Transcribe: speech to text. Polly: text to speech. |
| Textract vs Rekognition | Textract reads document text and structure. Rekognition analyzes images and video. |
| Comprehend vs Translate | Comprehend finds meaning and attributes in text. Translate changes its language. |
| Lex vs Bedrock | Lex builds intent-and-slot conversational interfaces. Bedrock supports generative assistants and agents with foundation models. |
| Personalize vs Quick | Personalize ranks items for an individual. Quick analyzes and visualizes business data. |
| Bedrock vs SageMaker AI | Bedrock starts with managed foundation models and GenAI features. SageMaker AI supplies broader ML training, hosting, and infrastructure control. |
| CloudTrail vs CloudWatch | CloudTrail records API activity for audit. CloudWatch monitors metrics, logs, alarms, and traces. |
| Config vs Inspector | Config checks resource configurations against rules. Inspector scans supported workloads for vulnerabilities and exposure. |
| KMS vs Secrets Manager | KMS manages encryption keys. Secrets Manager stores and rotates secret values. |
| IAM vs Guardrails | IAM authorizes AWS actions. Guardrails filters GenAI prompts and responses. |

## Approach traps

### Prompting, RAG, and fine-tuning

- Improve **instructions, examples, format, or context in one request** with prompt engineering.
- Add **current or private facts at request time** with RAG.
- Change **consistent task behavior, style, or domain performance** with fine-tuning when prompting or RAG is insufficient.
- Build broad model knowledge from more unlabeled domain data with continued pre-training.
- Train from scratch only when the organization needs a new base model and can support the data, compute, expertise, time, and cost.

These approaches can be combined. RAG does not change model weights. Fine-tuning does not keep a changing knowledge base current without more training.

### Purpose-built service vs broad platform

Choose a purpose-built service for a standard capability with low ML effort. Choose Bedrock for foundation-model applications. Choose SageMaker AI for custom/classical ML or more control. A broad platform can perform some related work, but `least operational effort` often points to the narrower managed service.

## Metric traps

- High accuracy can hide poor minority-class performance.
- Precision focuses on false positives. Recall focuses on false negatives.
- F1 balances precision and recall; it does not include business cost or latency.
- BLEU and ROUGE compare generated text with references. They do not prove factual correctness.
- A good model score does not prove the application completes tasks or creates ROI.
- Overall averages can hide poor results for demographic subgroups.

Use [Metrics](metrics.md) for formulas and examples.

## Responsible AI, security, and governance

| Scenario | Main category |
|---|---|
| One demographic receives worse predictions | Responsible AI: bias and fairness |
| A user cannot understand why a loan was denied | Explainability and human-centered design |
| A chatbot exposes private customer data | Security and privacy |
| An agent can delete resources it only needs to read | IAM and least privilege |
| A company cannot show who called an AWS API | Auditability with CloudTrail |
| Resources drift from approved configuration | Governance and compliance with Config |
| The team needs AWS compliance reports | Artifact |
| The model generates toxic output | Safety controls and evaluation; consider Guardrails |

Guardrails does not replace IAM, encryption, human approval, testing, or legal review.

## Agent traps

- A single generated answer is not enough to make a system agentic. Look for goals, planning, tool use, memory, or multi-step action.
- MCP connects AI applications to capabilities through a standard interface. It does not supply permissions.
- Strands Agents is an SDK, not a model or hosting service.
- AgentCore is a composable managed agent platform. Amazon Bedrock Agents Classic provides the earlier Bedrock-native orchestration for eligible existing customers and is closed to new customers.
- More agents do not guarantee a better design. Multi-agent systems add handoff, cost, latency, observability, and permission questions.
- Tool output can carry prompt injection. Treat retrieved content and arguments as untrusted.

## Data and learning traps

- Classification predicts a category; regression predicts a number; clustering groups unlabeled examples.
- Training fits model parameters. Inference uses the trained model on new input.
- The validation set guides model choices. The test set provides a final estimate and should not guide training.
- Overfitting means strong training performance but weak new-data performance. Underfitting means the model fails to capture the pattern.
- Statistical bias and fairness bias are different concepts.
- An embedding represents meaning as a vector. A vector database stores and searches those vectors.
- Chunking splits source content before embedding and retrieval. Larger chunks preserve context but may retrieve irrelevant text and consume more tokens.

## Claims that should trigger doubt

Be cautious when an option says a technique:

- guarantees factual accuracy;
- removes all bias;
- prevents every prompt injection attack;
- makes human review unnecessary;
- sends no data to logs under any configuration;
- always costs less;
- automatically grants secure tool access.

AWS questions favor risk reduction, layered controls, evaluation, and tradeoffs over absolute guarantees.

[Domain guide](../README.md#domain-guide) · [Service selection](service-selection.md) · [Metrics](metrics.md)

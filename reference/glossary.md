# AIF-C01 glossary

Use this page for recall after you have studied a concept in context. Each definition is written for exam recognition, not implementation.

## AI and ML foundations

- **Algorithm:** A procedure that learns patterns from data or follows defined steps to solve a problem.
- **Artificial intelligence (AI):** The broad field of building systems that perform tasks associated with human intelligence.
- **Machine learning (ML):** A type of AI in which a system learns patterns from data instead of relying only on hand-written rules.
- **Deep learning:** ML based on neural networks with many layers.
- **Neural network:** A model made of connected weighted units arranged in layers.
- **Model:** The learned artifact that turns new input into a prediction or generated output.
- **Parameter:** A value the model learns during training.
- **Hyperparameter:** A setting chosen for the training process rather than learned from the data.
- **Feature:** An input variable a model uses for prediction.
- **Feature engineering:** Selecting or transforming raw data into useful model inputs.
- **Training:** Fitting model parameters to data.
- **Inference:** Using a trained model on new input.
- **Batch inference:** Processing many inputs together when immediate output is not required.
- **Real-time inference:** Returning a prediction for one request with low latency.
- **Asynchronous inference:** Queuing a long-running or large inference request and returning the result later.
- **Serverless inference:** An inference option in which the provider provisions and scales serving capacity and the customer does not manage instances; billing, concurrency, cold starts, payload limits, and availability depend on the specific service.
- **Labeled data:** Examples paired with expected answers.
- **Unlabeled data:** Examples without expected answers.
- **Structured data:** Data organized in a defined schema, often rows and columns.
- **Unstructured data:** Text, images, audio, video, and other data without a fixed tabular structure.
- **Tabular data:** Structured data arranged in rows and columns.
- **Time-series data:** Values recorded in time order.
- **Supervised learning:** Learning a mapping from labeled examples to predict outcomes for new examples.
- **Unsupervised learning:** Finding patterns in unlabeled data.
- **Reinforcement learning:** Learning actions through rewards and penalties from an environment.
- **Self-supervised learning:** Creating training signals from the data itself, such as predicting hidden or next tokens.
- **Classification:** Predicting a category.
- **Regression:** Predicting a continuous numeric value.
- **Clustering:** Grouping similar examples without predefined labels.
- **Anomaly detection:** Finding examples that differ from normal patterns.
- **Training set:** Data used to fit model parameters.
- **Validation set:** Separate data used to compare model choices and tune settings.
- **Test set:** Held-out data used for final evaluation.
- **Overfitting:** Learning the training data too closely and performing poorly on new data.
- **Underfitting:** Failing to learn enough of the pattern to perform well even on training data.
- **Statistical bias:** Error caused by assumptions that are too simple, which often leads to underfitting.
- **Variance:** Sensitivity to the specific training data, which can lead to overfitting.
- **MLOps:** Practices that make ML experiments, deployment, monitoring, and retraining repeatable and controlled.
- **Model drift:** Loss or change in performance as real-world data or relationships shift.
- **Data quality:** Fitness of data for its use, including accuracy, completeness, consistency, and relevance.

## Generative AI

- **Generative AI (GenAI):** AI that creates new content such as text, images, audio, video, or code.
- **Foundation model (FM):** A broad model trained on large, varied data and adaptable to many tasks.
- **Large language model (LLM):** A foundation model trained to process and generate language.
- **Transformer:** A neural-network architecture that uses attention to relate tokens across a sequence.
- **Attention:** A mechanism that weights which parts of the input matter for processing another part.
- **Diffusion model:** A generative model that learns to reverse a noise process, often for image generation.
- **Multimodal model:** A model that accepts or produces more than one data type.
- **Token:** A unit of input or output processed by a model; one token may be a word, part of a word, punctuation, or another unit.
- **Tokenization:** Converting content into tokens a model can process.
- **Context window:** The maximum tokens a model can consider in one request, including input and generated output.
- **Context engineering:** Selecting, organizing, and delivering the information an application gives a model at each step.
- **Prompt:** Input that tells a generative model what to do and may include context, examples, and output rules.
- **Prompt engineering:** Improving prompts to shape model output without changing model weights.
- **Zero-shot prompting:** Asking for a task without examples.
- **One-shot prompting:** Giving one example before the task.
- **Few-shot prompting:** Giving several examples before the task.
- **Prompt template:** A reusable prompt structure with variables.
- **Negative prompt:** An instruction that identifies content or behavior to avoid.
- **Chain-of-thought prompting:** Asking for intermediate reasoning steps; use with care because generated reasoning is not proof.
- **Inference parameters:** Request settings such as temperature and maximum output tokens that shape a response.
- **Temperature:** A setting that changes output randomness; lower values tend toward more consistent choices.
- **Top-p:** A sampling setting that limits token selection to a probability mass, not a percentage of words.
- **Max output tokens:** A cap on generated response length and the maximum possible billed output for that request; it lowers actual output-token charges only when the model would otherwise generate beyond the cap.
- **Hallucination:** Generated content that is unsupported by the available evidence, conflicts with facts, or fabricates details; tone and confidence do not define it.
- **Nondeterminism:** The property that repeated inference can produce different outputs for the same input because of sampling, serving behavior, model updates, or other implementation factors; lowering temperature can reduce variation but does not guarantee identical output.
- **Knowledge cutoff:** A provider-stated training-data boundary, when one exists, after which the base model should not be assumed to know events; it is not a guarantee that the model knows every earlier fact or no later fact.
- **Embedding:** A numeric vector that represents semantic features of content.
- **Vector:** An ordered list of numbers.
- **Vector search:** Finding nearby vectors to retrieve semantically similar content.
- **Vector database:** A system that stores embeddings and searches them by similarity.
- **Chunking:** Splitting source content into sections for embedding and retrieval.
- **Grounding:** Connecting a response to supplied evidence or data.
- **Retrieval Augmented Generation (RAG):** Retrieving relevant external content and placing it in the model's context before generation.
- **Fine-tuning:** Training a pre-trained model further on narrower data to change its task behavior or specialization.
- **Instruction tuning:** Fine-tuning with instruction-and-response examples.
- **Continued pre-training:** Extending training on domain data to add broader domain specialization.
- **Transfer learning:** Reusing learning from a pre-trained model for another task.
- **Model distillation:** Training a smaller model to imitate a larger model.
- **Pre-training:** Training a base model on large datasets before task-specific adaptation.
- **RLHF:** Reinforcement learning from human feedback, which uses human preferences to help align model behavior.
- **Prompt caching:** Reusing a previously processed prompt prefix to reduce repeated processing, latency, or cost when supported.
- **Provisioned Throughput:** Dedicated Bedrock model units billed hourly whether used or not. Omit `commitmentDuration` for no commitment; `OneMonth` and `SixMonths` are the other API values. Custom models support all three levels, while base-model support varies.

## Agents and tools

- **Agentic AI:** AI that works toward a goal through planning, tool use, memory, or multiple steps.
- **AI agent:** An application that uses a model to decide actions and may call tools until it reaches an outcome.
- **Agent loop:** The repeated model, tool-call, tool-result cycle that ends with a final output.
- **Tool:** A callable function or service that gives an agent data or lets it take an action.
- **Tool use:** A model selecting a tool and producing arguments for the application to execute.
- **Orchestration:** Coordinating model calls, tools, steps, retries, state, and handoffs.
- **Workflow:** A sequence of tasks; it may be fixed or controlled in part by an agent.
- **Memory:** Information retained for later steps or sessions.
- **Short-term memory:** State kept within a conversation or session.
- **Long-term memory:** Information retained across sessions.
- **Multi-agent system:** Several agents that divide work or communicate to reach an outcome.
- **Model Context Protocol (MCP):** A standard interface for connecting AI applications with tools, resources, and prompts exposed by servers.
- **MCP host:** The AI application that coordinates MCP clients and the user experience.
- **MCP client:** The component that maintains a connection from a host to an MCP server.
- **MCP server:** A program that exposes capabilities to MCP clients.
- **Agent-to-Agent (A2A) protocol:** A protocol for direct communication and task coordination between agents.
- **Human in the loop:** A person who reviews, corrects, labels, or approves an AI decision or action.
- **Strands Agents:** An open-source SDK for building agents around models, tools, and an agent loop.
- **Amazon Bedrock Agents Classic:** The maintenance-mode name for the Bedrock Agents feature launched in November 2023. It orchestrates models, instructions, action groups, and knowledge bases for eligible existing customers; new customers cannot access it after July 30, 2026.
- **Amazon Bedrock AgentCore:** Composable managed capabilities for defining agent loops, deploying and connecting agents, managing identity and memory, enforcing policy, collecting observability, evaluating and optimizing behavior, executing browser or code tools, governing discovery, and handling supported agent payments.
- **AgentCore Harness:** Managed agent loop configured with a model, system prompt, and tools; it handles orchestration, tool execution, state, failure recovery, and isolated sessions.
- **AgentCore Runtime:** Serverless, isolated environment for deploying and scaling custom agent or tool workloads with framework and model flexibility.
- **AgentCore Gateway:** Converts APIs and Lambda functions into agent-compatible tools and connects existing MCP servers behind managed endpoints.
- **AgentCore Identity:** Agent and user identity plus credential brokering for AWS and third-party services, including on-behalf-of-user access.
- **AgentCore Memory:** Managed short-term conversation state and long-term information across sessions, with controls over retained content.
- **Policy in AgentCore:** Deterministic authorization for agent-to-tool requests through Gateway.
- **AgentCore Observability:** Standardized traces, logs, and metrics for instrumented agent activity; telemetry and sampling determine coverage.
- **AgentCore Evaluations:** Online or on-demand scoring of agent behavior with built-in or custom evaluators, including task-completion and tool-use measures.
- **AgentCore Optimization:** Production-trace analysis for failure, intent, and trajectory insights, plus proposed improvements validated through batch evaluation or A/B tests before approval.
- **AgentCore Payments:** Payment orchestration for supported paid APIs, MCP servers, agents, and content, with third-party wallets, spending controls, supported payment protocols, and transaction observability.
- **AgentCore Browser:** Managed browser environment for agent web interaction.
- **AgentCore Code Interpreter:** Isolated sandbox for agent-generated code execution.
- **AgentCore Registry:** Governed catalog and discovery layer for agents, tools, MCP servers, and skills.

## Evaluation and business value

- **Confusion matrix:** A table of true positives, false positives, true negatives, and false negatives.
- **Accuracy:** Correct predictions divided by all predictions.
- **Precision:** True positives divided by all predicted positives.
- **Recall:** True positives divided by all actual positives.
- **F1 score:** The harmonic mean of precision and recall.
- **Mean absolute error (MAE):** Average absolute regression error.
- **Mean squared error (MSE):** Average squared regression error.
- **Root mean squared error (RMSE):** The square root of MSE, which returns error to the target's units.
- **R-squared (`R²`):** `1 - SS_res / SS_tot`; `1` is perfect, `0` matches prediction of the evaluation-set mean, and a negative value is worse than that baseline.
- **BLEU:** A translation metric based on the geometric mean of modified n-gram precisions and a brevity penalty, usually aggregated across a corpus.
- **ROUGE:** A family of summary-reference overlap metrics; ROUGE-N often emphasizes n-gram recall, while ROUGE-L uses longest common subsequence and can report precision, recall, or F-measure.
- **BERTScore:** A contextual-embedding metric that aligns candidate and reference tokens and reports precision, recall, and F1.
- **Perplexity:** Exponentiated average negative log-likelihood of the observed token sequence; lower is better only across comparable data, tokenization, and modeling setups.
- **Benchmark dataset:** A standard test set used to compare models.
- **Human evaluation:** People rate model output against defined criteria.
- **LLM-as-a-judge:** A model scores another model's output against a rubric.
- **Groundedness:** The degree to which an answer follows supplied source material.
- **Task completion rate:** Verified goals completed correctly divided by eligible assigned goals under stated rules and exclusions.
- **Cost per interaction:** Total included cost divided by eligible interactions; define whether failed or retried requests count.
- **Return on investment (ROI):** `(attributable benefit - total investment cost) / total investment cost` over a stated period, with the baseline, attribution method, and cost scope documented.
- **Conversion rate:** The share of users who complete a desired action.
- **Customer lifetime value:** Expected value of a customer relationship over time.

## Responsible AI

- **Responsible AI:** Practices for building and using AI in ways that address fairness, safety, transparency, privacy, and human impact.
- **Fairness:** A use-case-specific goal for treatment or outcomes across relevant groups, defined through chosen criteria such as error rates, calibration, access, or opportunity; no single metric proves fairness.
- **Fairness bias:** Systematic skew that disadvantages people or groups.
- **Inclusivity:** Designing and evaluating a system for the range of people it will serve.
- **Robustness:** Ability to keep performing under varied, noisy, or adversarial inputs.
- **Safety:** Prevention and reduction of harmful outputs or actions.
- **Veracity:** Truthfulness and factual reliability.
- **Transparency:** Information about how a model or system was built, evaluated, and intended to be used.
- **Explainability:** Ability to understand why a model produced a specific output.
- **Interpretability:** How understandable a model's internal relationship between input and output is to people.
- **Black-box model:** A model whose internal decisions are hard for people to follow.
- **Subgroup analysis:** Comparing outcomes and errors across relevant groups.
- **Representative dataset:** Data that reflects the population and conditions the model will encounter.
- **Balanced dataset:** Data with suitable representation of important classes or groups.
- **Model card:** Structured documentation for a model's intended use, risk, training, evaluation, and limits.
- **Amazon Bedrock Guardrails:** Configurable controls for filtering prompts and responses, sensitive information, denied topics, prompt attacks, and groundedness checks.
- **SageMaker Clarify:** Bias-analysis and feature-attribution capability for eligible existing SageMaker customers; AWS closed it to new customers on July 30, 2026 and does not plan new features.
- **SageMaker Model Cards:** SageMaker AI records for documenting model purpose, risk, training, and evaluation information.
- **SageMaker Model Monitor:** Scheduled monitoring for supported data-quality, model-quality, bias-drift, and feature-attribution workflows; AWS closed it to new customers on July 30, 2026 and does not plan new features.
- **Amazon Augmented AI (Amazon A2I):** Human-review workflows for low-confidence or sampled ML predictions, with built-in Textract key-value and Rekognition moderation task types plus custom tasks; AWS closed it to new customers on July 30, 2026 and does not plan new features.

## Security, compliance, and governance

- **Authentication:** Verifying the identity of a person or workload.
- **Authorization:** Deciding which actions an authenticated identity may perform.
- **Least privilege:** Granting only the permissions needed for a task.
- **IAM role:** An AWS identity that provides temporary permissions when assumed.
- **Encryption at rest:** Protecting stored data with encryption.
- **Encryption in transit:** Protecting data while it moves, often with TLS.
- **AWS KMS key:** A cryptographic key managed through AWS Key Management Service.
- **AWS PrivateLink:** Private connectivity to supported services through VPC endpoints without using the public internet.
- **Prompt injection:** Input that attempts to override instructions or manipulate an AI system.
- **Jailbreaking:** Input designed to bypass a model's safety behavior.
- **Data poisoning:** Corrupting training or retrieval data to influence model behavior.
- **Data leakage:** Unauthorized exposure of sensitive information through data, prompts, logs, tools, or model output.
- **Output validation:** Checking a model response against expected structure, values, policy, or evidence before using it.
- **Audit trail:** A record of actions that supports monitoring and investigation.
- **Data lineage:** The recorded path of data from its source through transformations and use.
- **Data catalog:** An inventory of datasets with metadata such as description, owner, location, and classification.
- **Data residency:** A requirement for data to remain in a geographic jurisdiction.
- **Data retention:** A rule for how long data remains stored.
- **Governance:** Policies, responsibilities, controls, and evidence used to direct and oversee AI systems.
- **Compliance:** Meeting applicable legal, regulatory, industry, and internal requirements.
- **Shared responsibility model:** AWS secures the infrastructure that runs AWS services. The customer secures and governs its data, identities, configurations, application code, controls, and use of service output; the boundary changes with the selected service.
- **Generative AI Security Scoping Matrix:** An AWS framework for defining security responsibilities based on how an organization consumes or builds a GenAI model.
- **AWS CloudTrail:** AWS service that records API calls and account activity.
- **Amazon CloudWatch:** AWS service for operational metrics, logs, alarms, dashboards, and traces.
- **AWS Config:** AWS service that records resource configurations and checks them against rules.
- **AWS Artifact:** Portal for AWS compliance reports and agreements.
- **Amazon Inspector:** Service that finds software vulnerabilities and unintended network exposure in supported workloads.
- **Amazon Macie:** Service that discovers and classifies sensitive data in Amazon S3.
- **AWS Secrets Manager:** Service for storing, retrieving, and rotating secrets.

## AWS service quick definitions

- **Amazon Bedrock:** Managed foundation-model and GenAI application platform.
- **Amazon SageMaker AI:** Managed platform for building, training, deploying, and governing ML models.
- **SageMaker JumpStart:** SageMaker AI hub for pre-trained models, algorithms, and solution templates.
- **Amazon Nova:** Amazon's family of foundation models available through Amazon Bedrock.
- **Amazon Comprehend:** Text analysis for sentiment, entities, key phrases, and related NLP tasks.
- **Amazon Lex:** Voice and text conversational-interface service.
- **Amazon Personalize:** Managed personalized recommendation service.
- **Amazon Polly:** Text-to-speech service.
- **Amazon Rekognition:** Image- and video-analysis service.
- **Amazon Textract:** Document text and structure extraction service.
- **Amazon Transcribe:** Speech-to-text service.
- **Amazon Translate:** Language translation service.
- **Amazon Quick:** AI-powered workspace for business users that combines conversational assistance, source-traced research, multi-dataset analytics, flows, autonomous agents, and natural-language application building over connected enterprise data and applications.
- **AWS Transform:** Agentic AI service for application, code, and infrastructure modernization.
- **Kiro:** AI coding agent available through an agentic desktop development environment, CLI, and other surfaces, with spec-driven development, built-in and custom agents, steering, and event-driven hooks. It can generate and run tests; optional Specs correctness property testing is an IDE feature.
- **Amazon OpenSearch Service:** Managed search and analytics service with vector-search capabilities.
- **Amazon Aurora:** Managed MySQL- and PostgreSQL-compatible relational database.
- **Amazon RDS:** Managed relational database service.
- **Amazon Neptune:** Managed graph database service.
- **Amazon DynamoDB:** Serverless NoSQL key-value and document database.
- **Amazon S3:** Object storage used for datasets, documents, artifacts, and logs.

## Related pages

- [Service selection](service-selection.md)
- [Managed AI services](managed-ai-services.md)
- [Bedrock vs SageMaker AI](bedrock-vs-sagemaker-ai.md)
- [Agentic AI and AgentCore](agentic-ai-mcp-strands-agentcore.md)
- [Metrics](metrics.md)
- [Common exam traps](common-exam-traps.md)

Check terminology against the [official AIF-C01 exam guide](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html) and [in-scope service list](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/aif-01-in-scope-services.html) before your exam.

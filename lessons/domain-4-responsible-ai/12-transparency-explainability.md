# Task 4.2: Recognize the importance of transparent and explainable models

- Exam domain: 4, Guidelines for Responsible AI
- Task: 4.2, Recognize the importance of transparent and explainable models
- Domain weight: 14% across Tasks 4.1 and 4.2
- Objective snapshot: 2026 AIF-C01 exam guide
- Last reviewed: November 2026

## Exam focus

Task 4.2 tests whether you can separate transparency, interpretability, and explainability, then choose the right evidence or AWS feature. Pay attention to whether a scenario asks about the model as a whole, one prediction, bias, model documentation, or comparative evaluation.

The fastest exam method is to finish this sentence: "The audience needs to understand ____." The blank usually points to the answer.

## Mental model: system facts, model behavior, one decision

- **Transparency** gives stakeholders facts about the system: who built it, which data and license terms apply, its intended use, how it was evaluated, and its limits.
- **Interpretability** describes how directly a person can understand the model's internal relationship between inputs and outputs.
- **Explainability** helps a person understand why the model produced a result or how features influenced it.

A model can have strong transparency documentation and weak per-output explainability. A black-box model can support post-hoc explanations without exposing its internal logic. An LLM that writes a convincing explanation of its own answer has generated more text; it has not supplied a faithful execution trace.

## Transparent and opaque models

| Model or approach | Typical interpretability | What a person can inspect | Limitation |
|---|---|---|---|
| Linear or logistic regression | High | Coefficients and direction of feature effects | Correlated features and transformations can confuse interpretation |
| Small decision tree | High | Human-readable split path | Deep trees overfit and become hard to follow |
| Rule-based system | High | Explicit rules and exceptions | Rules can grow complex and brittle |
| Large tree ensemble | Low to medium | Aggregate and local feature attributions | Hundreds of trees are not readable as one decision path |
| Deep neural network | Low | Post-hoc feature attribution or probes | Internal representations remain hard to explain |
| Foundation model or LLM | Low | Prompt, context, output, evaluations, citations, and external traces | Generated rationales may not match the model's internal computation |
| Open-source model | Varies | Code or weights may be inspectable | Open access does not guarantee understandable behavior, disclosed training data, or broad license rights |

"Open source" can improve inspectability and independent testing. It does not make a model fair, safe, explainable, or suitable for commercial use. Review the model card, training-data disclosures, evaluation results, dependencies, and each license.

## Match the question to the evidence

| Stakeholder question | Needed evidence | AWS feature or method |
|---|---|---|
| What is this model for, and what are its limits? | Intended use, risk rating, assumptions, training and evaluation details | SageMaker Model Cards |
| Does the data or model show potential bias? | Pre-training and post-training bias metrics | SageMaker Clarify |
| Why did this tabular model make this prediction? | Feature attribution for the prediction | SageMaker Clarify with SHAP-based explanations |
| Which foundation model meets our quality and safety target? | Comparable test dataset and evaluation metrics | Amazon Bedrock evaluations |
| Does a response meet a subjective brand or expert standard? | Human ratings with a rubric | Bedrock human evaluation |
| Can users verify a generated claim? | Source citation and access to supporting evidence | RAG citations and application design |
| Can an auditor reconstruct the model's history? | Versions, data origin, approvals, metrics, and changes | Model Cards plus lineage and governance records |
| Can an affected person contest an outcome? | Plain-language reason, review channel, and accountable human owner | Human-centered workflow |

## SageMaker Model Cards

A model card is a standardized governance record. It can capture:

- owner, purpose, and intended uses;
- uses the team excludes;
- model risk rating and business impact;
- training details, datasets, and model artifacts;
- assumptions, constraints, and ethical considerations;
- evaluation metrics, observations, caveats, and recommendations;
- lifecycle status and review history.

Model Cards improve transparency and auditability. They do not calculate feature attribution and do not prove that a model is unbiased. Start the card during problem definition, update it through development, and version it when model facts change.

AWS AI Service Cards play a related but different role. AWS publishes them for selected AWS AI services. Use SageMaker Model Cards for models that your organization documents and governs.

## SageMaker Clarify

**Current availability:** As of July 30, 2026, SageMaker Clarify is not open to new customers. Existing customers can continue to use it, and AWS states that it will continue security and availability improvements without new features. Clarify remains named exam material, even though a new workload needs another implementation path.

SageMaker Clarify addresses two exam needs:

1. **Bias detection:** Analyze potential bias in data before training and in model predictions after training or deployment.
2. **Explainability:** Produce feature attributions that show how input features contributed to predictions.

Clarify can detect a disparity; people must decide whether it is unacceptable and how to respond. A feature-attribution chart also needs context. A large attribution indicates influence, not causation or moral legitimacy.

## Amazon Bedrock evaluations

Use Bedrock evaluations to compare foundation models, Knowledge Bases, RAG sources, or supplied responses with consistent datasets and metrics.

| Evaluation method | Best use | Examples |
|---|---|---|
| Programmatic evaluation | Repeatable, scaled comparison | Accuracy, robustness, toxicity, task metrics |
| LLM-as-a-judge | Scoring open-ended responses against a rubric | Correctness, completeness, faithfulness, harmfulness |
| Human evaluation | Subjective, high-context, or high-risk judgment | Style, relevance, brand fit, expert acceptability |
| RAG evaluation | Retrieval and grounded-generation quality | Context relevance, retrieval correctness, response faithfulness |

A judge model can scale review but may have its own bias and inconsistency. Calibrate it against human-labeled examples. Human review gives context but costs more and may vary across reviewers. Use clear rubrics and measure reviewer agreement.

Evaluation results support a decision; they do not explain every production output. Use representative datasets, record model and prompt versions, and repeat tests after changes.

## Transparency and safety tradeoffs

| Choice | Benefit | Cost or risk |
|---|---|---|
| Simpler interpretable model | Direct reasoning, easier audit | May miss complex patterns |
| Complex high-performing model | May improve task performance | Harder to explain and validate |
| Publish detailed system information | Supports scrutiny and trust | Can expose intellectual property or attack details |
| Hide all implementation details | Protects sensitive design information | Weakens accountability and external review |
| Provide a generated rationale | Gives users readable context | May be unfaithful to the actual computation |
| Provide evidence and calibrated uncertainty | Supports verification and challenge | Requires data, testing, and interface work |

The exam rarely rewards "maximum transparency" without qualification. Disclose enough for the audience to make an informed decision while protecting personal data, security controls, and legitimate intellectual property.

A model with a one-point accuracy gain may be a poor choice if a regulated workflow requires understandable adverse-action reasons. A small performance loss can be acceptable when interpretability lowers legal and operational risk. High-stakes decisions often need human review even when an explanation tool exists.

## Human-centered explainable AI

Design the explanation for the person who must act on it.

### Identify the audience

A data scientist may need feature distributions and SHAP values. A loan applicant needs a plain-language reason, the important factors, and a way to correct bad data. An auditor needs versions, approvals, tests, and evidence.

### Provide useful decision transparency

Tell users:

- when AI contributes to a decision;
- what the system is intended to do;
- which information influenced the outcome when disclosure is safe and lawful;
- the model's limits and uncertainty;
- who remains accountable;
- how to ask for review, correct data, or report harm.

### Build feedback and challenge paths

A feedback button without ownership is decoration. Define who reviews feedback, response targets, escalation rules, and how the team feeds confirmed issues into data, model, prompt, or policy changes. High-risk outcomes need a human with authority to reverse or pause the decision.

### Test comprehension

Ask representative users to explain the result back in their own words. Measure whether the explanation helps them make a better decision rather than whether it looks detailed. Accessibility, language, time pressure, and domain knowledge change what works.

## Control and service decision table

| Need in the scenario | Choose | Do not confuse it with |
|---|---|---|
| Standardized model facts for governance | SageMaker Model Cards | SageMaker Clarify |
| Bias metrics or feature attribution | SageMaker Clarify | Model Cards |
| Compare FMs on quality, safety, or subjective criteria | Bedrock evaluations | Guardrails |
| Block harmful content during inference | Bedrock Guardrails | Model evaluation |
| Explain a small tree's exact decision path | Inspect the decision tree | Post-hoc LLM rationale |
| Show how a feature affects predictions across a range | Partial dependence plot | Training convergence chart |
| Verify generated claims | Sources, citations, and grounding | Model card alone |
| Disclose an AWS-managed service's intended use | AWS AI Service Card | Your custom model's Model Card |
| Choose an inspectable third-party model | Review open model artifacts and licenses | Assume "open" means unrestricted |

## Scenario reasoning

### Scenario 1: a regulator asks why one application was denied

A bank uses a gradient-boosted model and must explain an individual credit decision.

**Best response:** Use local feature attribution, provide a plain-language reason, retain the input and model version, and offer human review.

**Reasoning:** A model card explains the system but not the contribution of features to one decision. Source code alone would not give the applicant a useful explanation.

### Scenario 2: a risk committee asks what a model may be used for

The committee wants the owner, intended use, prohibited use, risk rating, datasets, and evaluation results.

**Best response:** Create and maintain a SageMaker Model Card.

**Reasoning:** The need is standardized lifecycle documentation, not a prediction-level explanation.

### Scenario 3: a team compares three summarization models

The team needs repeatable correctness and toxicity scores plus employee ratings for brand voice.

**Best response:** Use Bedrock programmatic evaluation for repeatable metrics and human evaluation for brand voice.

**Reasoning:** One evaluation method does not fit both an objective test and a subjective preference.

### Scenario 4: a medical model has the highest accuracy but weak explanations

A slightly less accurate decision tree meets the clinical threshold and lets clinicians inspect each decision path.

**Best response:** Consider the decision tree if the measured performance meets the safety requirement and inspectability improves clinical oversight.

**Reasoning:** The best model is the model that meets the full use-case requirements, not the one with the highest single metric.

### Scenario 5: an open-weight model is proposed for commercial use

The team can inspect the weights, but the training-data record is incomplete and the license restricts some uses.

**Best response:** Review the model and data licenses, provenance, model card, and independent evaluations before adoption.

**Reasoning:** Open weights increase access. They do not settle transparency, explainability, safety, or commercial rights.

### Scenario 6: a chatbot explains its own answer

The application asks the LLM to "show its reasoning," then presents the generated rationale as proof.

**Best response:** Treat the rationale as generated content. Provide citations, evidence, validated traces from external components, and uncertainty or refusal when support is missing.

**Reasoning:** A plausible narrative is not a faithful account of hidden model computation.

## Common exam traps

- **Transparency versus explainability:** Transparency covers system facts and lifecycle documentation. Explainability addresses behavior or a result.
- **Interpretability versus explanation tooling:** A small decision tree exposes its logic. A black-box model needs a post-hoc method.
- **Model Cards versus Clarify:** Model Cards document. Clarify detects potential bias and explains predictions.
- **Evaluation versus Guardrails:** Evaluation measures behavior. Guardrails enforce inference-time policies.
- **Generated rationale versus evidence:** An LLM can hallucinate its explanation.
- **Feature importance versus causation:** Influence in a model does not prove a real-world cause.
- **Open source versus transparent training data:** Code or weights may be open while the dataset remains undisclosed.
- **More detail versus better explanation:** Users need relevant, understandable, actionable information.
- **One global explanation versus one local decision:** A global trend does not explain every individual prediction.
- **Human in the loop versus accountability:** The reviewer needs authority and an appeal process.

## Self-check

1. A team needs a standardized record of intended use, risk rating, training details, and evaluation results. Which AWS feature fits?
2. A customer asks why a tabular model rejected one transaction. Which type of evidence fits?
3. Why is an LLM-generated rationale not a faithful explanation by default?
4. Which Bedrock evaluation method fits brand tone judged by marketing specialists?
5. Does an open-source model guarantee transparency and unrestricted use?

### Answers

1. SageMaker Model Cards.
2. A local feature-attribution explanation, paired with the input, model version, and a review path.
3. The model generates the rationale as text and can invent a plausible story that does not trace its hidden computation.
4. Human evaluation with a defined rubric. A judge model may supplement it after calibration.
5. No. Inspectability depends on which artifacts are open, and use depends on the model, code, and data licenses.

## Practice

- [Domain 4 questions with answers and explanations](../../practice/question-bank.md#task-42)

## Official sources

- [AIF-C01 Domain 4 objectives](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain4.html)
- [SageMaker Model Cards](https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html)
- [SageMaker model governance](https://docs.aws.amazon.com/sagemaker/latest/dg/governance.html)
- [SageMaker Clarify fairness, explainability, and bias detection](https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-configure-processing-jobs.html)
- [SageMaker Clarify availability change](https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-availability-change.html)
- [Evaluate and explain models with SageMaker AI](https://docs.aws.amazon.com/sagemaker/latest/dg/model-explainability.html)
- [Evaluate Amazon Bedrock resources](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html)
- [Amazon Bedrock evaluations overview](https://aws.amazon.com/bedrock/evaluations/)
- [AWS AI Service Cards](https://aws.amazon.com/ai/responsible-ai/resources/)
- [AWS guidance on transparency and explainability](https://aws.amazon.com/blogs/security/securing-generative-ai-data-compliance-and-privacy-considerations/)

---

[Domain contents](README.md) · [All domains and objectives](../../README.md#domain-guide)

**Previous:** [Lesson 11](11-responsible-ai.md) · **Next:** [Lesson 13](../domain-5-security-compliance-governance/13-security.md)

# Task 2.2: Understand the capabilities and limitations of GenAI for solving business problems

## Exam focus

Domain 2 accounts for **24% of scored exam content**. Task 2.2 asks you to connect a business need to a GenAI advantage, identify a failure mode, choose a model under stated constraints, and select metrics that show business value.

This lesson covers every Task 2.2 objective in the [current AWS Domain 2 outline](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain2.html).

## Mental model: value must exceed risk and total cost

Evaluate a GenAI proposal with three questions:

1. Can the model produce the required type of output at the required quality?
2. Can the application control errors, sensitive data, and high-impact decisions?
3. Does measured business value exceed build, review, and operating cost?

A strong demo answers none of these by itself. Teams need evaluations on representative inputs and business measurements after release.

## GenAI advantages

| Advantage | Business effect | Good fit |
|---|---|---|
| Adaptability | One model can support several tasks through instructions and context | Draft, summarize, classify, and answer questions |
| Responsiveness | Users receive generated help without waiting for manual drafting | Employee assistants and support suggestions |
| Conversational capability | Users express needs in natural language and refine them over turns | Search, guided support, and analysis |
| Content generation | The model creates new text, images, audio, video, or code | First drafts, concepts, and synthetic variations |
| Cross-domain performance | A general model can work across several subjects | An assistant that supports several departments |

Adaptability lowers the cost of creating separate narrow interfaces, but it does not guarantee equal quality across tasks. Each important task needs its own evaluation set.

## Limitations and failure modes

| Limitation | Meaning | Control |
|---|---|---|
| Hallucination | The model generates content that lacks support from available evidence, conflicts with facts, or fabricates details | Ground with trusted sources, require citations, validate outputs, use human review |
| Inaccuracy | The answer is wrong, incomplete, or unsuitable for the task, whether or not it looks like a hallucination | Test against representative cases and verify high-impact outputs |
| Limited interpretability | The team cannot provide a simple causal explanation for each output | Prefer simpler models for explainability needs; document evidence and process |
| Nondeterminism | The same input can produce different outputs because of sampling, serving behavior, model updates, or other implementation factors | Lower randomness where supported, constrain formats, validate, and test distributions of results |

A **knowledge cutoff**, when a provider states one, is a training-data boundary after which the base model should not be assumed to know events. It does not guarantee complete knowledge before that date or zero exposure to later facts. A **hallucination** is generated content unsupported by the evidence or facts. **Drift** means performance changes as live data or relationships change. **Nondeterminism** means the same input can yield different output without drift; a low temperature can reduce variation but does not guarantee identical results.

Grounding can reduce hallucinations but cannot guarantee truth. Retrieved documents may be wrong, stale, malicious, or outside the user's authorization. The application should control source quality and access.

### Worked example: checking a refund answer against evidence

![Without policy evidence an assistant states You have 60 days. With Policy P4 saying Refunds accepted within 30 days, the assistant states 30 days according to P4. The diagram requires checking whether the policy is relevant, current, authorized, and supportive of the claim.](visuals-diagrams/grounded-answers.png)

*Grounding supplies relevant evidence for an answer; checking the citation and its applicability remains a separate step.*

A customer asks, **“How long do I have to request a refund?”** Without the company’s policy, an assistant generates “You have **60 days**.” The wording sounds plausible, but no supplied source supports that rule. **Grounding** means connecting an answer to relevant evidence rather than relying only on the model’s learned patterns.

The application retrieves **Policy P4**, which says, “Refunds accepted within **30 days**.” The model now answers “30 days, according to Policy P4.” The next check is to open P4 and confirm that the cited passage supports the answer and applies to this customer’s purchase. A stale or unrelated policy could still produce a grounded but wrong answer. Lowering randomness would not supply the missing policy. If relevant evidence is unavailable, acknowledging that limitation is more appropriate than inventing a confident deadline.

## Select a model by constraints

Model selection is a tradeoff, not a leaderboard lookup.

| Factor | Ask | Likely direction |
|---|---|---|
| Model type | Does the task need text, image, audio, video, embeddings, or several modalities? | Choose a model that supports the required inputs and outputs |
| Performance | Which quality threshold matters on representative examples? | Test candidates with task-specific data |
| Capability | Does the model support reasoning, tool use, languages, context length, or structured output? | Remove candidates that lack a required feature |
| Constraints | What are the input, output, throughput, region, and integration limits? | Validate before architecture commitment |
| Compliance | Which privacy, residency, audit, retention, and explainability duties apply? | Choose services and regions that support the control set |
| Cost | What will input, output, retrieval, tools, review, and hosting cost at volume? | Use the smallest model that meets quality |
| Latency | Does a user wait, or can the job run in a queue or batch? | Favor fast models or noninteractive processing as required |
| Complexity | Can the team operate customization, agents, and retrieval paths? | Prefer the simplest design that meets the target |

A larger model may improve complex reasoning, but it tends to cost more and may respond more slowly. A smaller model may handle extraction or classification with lower unit cost. Test with real inputs before selecting.

### Worked example: selecting a model under two requirements

![An illustrative plot compares A at 80% correctness and 0.5 seconds, B at 92% and 1.2 seconds, and C at 96% and 2.8 seconds. The acceptable region requires at least 90% correctness and at most 2 seconds. Only B qualifies. Invented costs per 1,000 requests are $1, $3, and $8.](visuals-diagrams/model-tradeoffs.png)

*All prices, measured results, and acceptance thresholds in this example are invented; they are not AWS pricing or product benchmarks.*

A support assistant must answer at least **90 of 100 reviewed questions correctly** and respond within **2 seconds** in this simplified comparison. **Latency** is the time before a result arrives. The team tests three fictional candidates with the same representative questions. A scores **80%** at **0.5 seconds**, B scores **92%** at **1.2 seconds**, and C scores **96%** at **2.8 seconds**. Their invented costs per **1,000 requests** are **$1, $3, and $8**.

First, apply the quality threshold: A fails. Next, apply the latency limit: C fails. B meets both requirements and becomes the candidate to evaluate further. Choosing the cheapest option alone would miss the quality target; choosing the highest score alone would miss the response-time target. Production selection would also examine safety, privacy, integration limits, and the distribution of latency rather than relying on one simplified value.

## Business value and metrics

Define a baseline before launch. Compare the GenAI workflow with the current process or a non-GenAI alternative.

| Metric | Definition | Example use |
|---|---|---|
| ROI | `(attributable benefit - total investment cost) / total investment cost` over a stated period | Decide whether the project returns enough attributable value relative to its full cost |
| Efficiency | Time, labor, or compute required per completed task | Measure handling-time reduction |
| Conversion rate | Share of users who complete a target action | Measure purchases after assisted product discovery |
| Average revenue per user (ARPU) | Revenue divided by active users for a period | Track monetization changes |
| Accuracy | Share of evaluated outputs that meet a correctness rule | Track answer or classification quality |
| Customer lifetime value (CLV) | Expected value of a customer relationship over time | Measure long-term retention and revenue effects |
| Cross-domain performance | Quality across several tasks or subject areas | Check whether one assistant works across departments |

ROI should define the baseline, measurement period, benefit attribution, and full cost scope. Include model inference, retrieval, storage, network use, engineering, security, evaluations, human review, and incident handling. The formula is undefined when total investment cost is zero. A model that reduces drafting time but doubles review time may not improve efficiency.

### Match the metric to the goal

- Faster case resolution: handling time, tasks per hour, and quality.
- More purchases: conversion rate and revenue, with return and complaint rates as guardrails.
- Better support: resolution rate, grounded-answer accuracy, escalation rate, and customer feedback.
- Broad employee assistant: task-level quality by department, adoption, time saved, and cost per active user.

A vanity metric such as total prompts says little about business value. High usage could indicate value, confusion, or repeated failures.

## Risk controls by impact

Use stronger controls as the consequence of an error rises.

- Low-impact brainstorming can tolerate variation if a person reviews the draft.
- Public support answers need grounding, testing, content controls, and escalation.
- Medical, legal, credit, hiring, or safety decisions need domain review, clear accountability, strict data controls, and limits on autonomous action.
- Any agent that changes records or spends money needs least-privilege tools, parameter validation, audit logs, and approval thresholds.

AWS frames AI safety and security as a shared responsibility. AWS secures the cloud infrastructure; customers remain responsible for their data, access configuration, application behavior, and appropriate use. See [Amazon Bedrock security](https://docs.aws.amazon.com/bedrock/latest/userguide/security.html).

## Scenario practice

### Scenario 1: fabricated policy

A support assistant invents a refund exception that is absent from company policy.

**Answer: hallucination.** Ground responses in approved policy, require evidence, and route uncertain or high-value cases to a person. Nondeterminism describes variation, not the unsupported claim itself.

### Scenario 2: same prompt, different drafts

A marketing team receives different wording from repeated runs of the same prompt.

**Answer: nondeterminism.** The behavior can be useful for ideation. A workflow that needs stable JSON should constrain generation and validate the schema.

### Scenario 3: live chat under a strict latency target

Two models pass the quality threshold. One is cheaper but misses the response-time target.

**Answer: choose the model and service option that meets latency within budget.** The cheapest token price does not satisfy the business requirement if users abandon the chat.

### Scenario 4: sales assistant pilot

A retailer wants to know whether a shopping assistant increases completed purchases.

**Answer: measure conversion rate against a baseline or controlled comparison.** Prompt count and answer length do not measure the stated outcome. Track accuracy and complaints as guardrail metrics.

### Scenario 5: company-wide assistant

One assistant supports HR, finance, and engineering. Aggregate quality looks acceptable, but finance answers fail often.

**Answer: measure cross-domain performance by domain.** A single average can hide a weak high-impact area. Apply separate acceptance thresholds and access controls.

### Scenario 6: audit explanation

A lender must explain why each applicant received a risk decision. A general LLM gives plausible prose but cannot show a stable causal decision path.

**Answer: favor an interpretable traditional model or rules-based process for the decision.** GenAI can help draft a reviewed explanation from approved facts, but it should not invent the rationale.

## Common confusions and traps

- Hallucination and inaccuracy overlap, but hallucination points to unsupported generated material.
- Nondeterminism is run-to-run variation. Drift is a change in performance over time.
- Grounding reduces risk. It does not certify that sources or answers are correct.
- Low token price does not equal low total cost. Include retrieval, tool calls, review, and operations.
- The largest model is not the default answer. Required quality under cost and latency constraints decides.
- Accuracy is a model or application quality metric. ROI, conversion, ARPU, and CLV measure business outcomes.
- Cross-domain performance should be broken down by task or domain so an average does not hide failures.
- Human review must have a clear purpose and trained reviewers. A person clicking "approve" without evidence adds little control.

## Compact decision table

| Prompt priority | Select or measure |
|---|---|
| Create varied new content | GenAI content generation |
| Explain every decision to an auditor | Interpretable model or deterministic rules |
| Reduce unsupported answers | Grounding, evaluation, validation, and review |
| Stable machine-readable output | Constrained format plus validation |
| User waits for a reply | Latency-qualified model and serving option |
| Prove sales impact | Conversion rate and revenue metrics |
| Prove economic return | ROI with total cost |
| One model across departments | Cross-domain performance by domain |

## Self-check

1. **What limitation describes a model inventing a source?**

   Hallucination.

2. **Why is total prompt count a weak success metric?**

   It measures activity, not task completion, quality, cost, or business outcome.

3. **Which metric best tests whether an assistant increases purchases?**

   Conversion rate, paired with revenue and quality guardrails.

4. **Does a larger model always provide more business value?**

   No. It must improve the required task enough to justify added cost, latency, and complexity.

5. **Which controls fit an agent that can issue refunds?**

   Least-privilege tool access, validated parameters, audit logs, policy checks, and human approval above defined thresholds.

## Practice links

- [Domain 2 questions with answers and explanations](../../practice/question-bank.md#task-22)

## Official sources

- [AWS Certified AI Practitioner Domain 2 objectives](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain2.html)
- [Amazon Bedrock model evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html)
- [Amazon Bedrock security](https://docs.aws.amazon.com/bedrock/latest/userguide/security.html)
- [Amazon Bedrock data protection](https://docs.aws.amazon.com/bedrock/latest/userguide/data-protection.html)
- [Amazon Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html)
- [AWS Responsible AI Lens](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/welcome.html)
- [AWS AI Service Cards](https://aws.amazon.com/ai/responsible-ai/resources/)

Source descriptions in this lesson were rephrased for compliance with licensing restrictions.

---

[Domain contents](README.md) · [All domains and objectives](../../README.md#domain-guide)

**Previous:** [Lesson 04](04-genai-concepts-agents.md) · **Next:** [Lesson 06](06-aws-genai-services.md)

# Task 3.4: Describe methods to evaluate FM performance

A model can score well on a benchmark and still fail the business workflow. AIF-C01 tests evaluation at several levels: generated text, the model, RAG retrieval and grounding, agent behavior, end-to-end workflows, and business outcomes.

## Exam focus

You should be able to:

- compare benchmark, human, programmatic, and LLM-as-a-judge evaluation;
- match ROUGE, BLEU, and BERTScore to the right generation task;
- describe Amazon Bedrock evaluations;
- evaluate RAG retrieval and answer generation as separate stages;
- measure agent tool selection and task completion;
- connect technical quality to productivity, engagement, task effectiveness, user satisfaction, and cost per interaction.

Watch the wording. "Best translation metric" points to BLEU. "Meaning despite different wording" points to BERTScore. "Subjective tone judged by experts" points to human evaluation. "Open-ended scoring at scale" points to LLM-as-a-judge.

## Mental model: evaluate the whole chain

Use a stack of questions:

1. **Output:** Does the generated text match the reference or rubric?
2. **Model:** Does the FM perform across the target dataset, edge cases, safety tests, and latency limits?
3. **Component:** Does retrieval find the right evidence? Does the agent pick the right tool?
4. **Workflow:** Does the complete application produce the intended result?
5. **Business:** Do users finish work with acceptable satisfaction and cost?

A strong score at one layer cannot prove success at the next layer. A good model cannot answer from a document that retrieval missed. A correct answer does not prove that an agent executed the correct refund.

## Evaluation approaches

| Approach | Best fit | Strength | Limitation |
| --- | --- | --- | --- |
| Benchmark dataset | Repeatable comparison across models | Fast, consistent, easy to rerun | May not represent your users or data |
| Programmatic metrics | Tasks with references or deterministic checks | Scales at low marginal cost | Can miss tone, nuance, and usefulness |
| Human evaluation | Subjective quality, safety, domain judgment | Captures expert and user preferences | Slow, costly, and prone to reviewer disagreement |
| LLM-as-a-judge | Open-ended responses at scale | Flexible rubric and explanation | Judge bias, position effects, cost, and model dependence |
| Online A/B test | Real user and business impact | Measures production behavior | Risk, confounding factors, and longer feedback cycle |

Use more than one method for consequential systems. Automated checks support breadth. Humans inspect nuance and calibrate judge models. Production metrics reveal whether the application helps users.

## Build a representative evaluation dataset

An evaluation dataset should mirror the expected workload and include:

- common requests in realistic proportions;
- rare but costly failure cases;
- supported languages and modalities;
- short and long inputs;
- ambiguous, incomplete, and conflicting information;
- safety and prompt-attack cases;
- expected answers, source passages, tool traces, or rubric labels as required.

Keep test data out of training and prompt development. Track dataset versions. Report results by subgroup because an average can hide a failure for one language, product, or user group.

## Metrics for generated text

### ROUGE

ROUGE, Recall-Oriented Understudy for Gisting Evaluation, is a family of overlap measures between generated and reference text. It is associated with summarization.

Common forms include:

- **ROUGE-N:** n-gram overlap, often reported with recall emphasis but also available as precision or F-measure;
- **ROUGE-L:** longest-common-subsequence overlap, which can also report precision, recall, or F-measure.

A high ROUGE score shows word or sequence overlap. It does not prove factual accuracy, readability, or grounding. A good paraphrase can score poorly if it uses different words.

### BLEU

BLEU, Bilingual Evaluation Understudy, is usually computed across a corpus as the geometric mean of modified n-gram precisions multiplied by a brevity penalty. It is associated with machine translation.

BLEU works best across a dataset rather than as a verdict on one sentence. A translation can preserve meaning with different wording and receive a lower overlap score.

### BERTScore

BERTScore aligns candidate and reference tokens by contextual-embedding similarity and reports precision, recall, and F1. It captures semantic similarity better than surface overlap, so it can reward a paraphrase that preserves meaning.

BERTScore still depends on the embedding model and reference quality. Semantic similarity does not guarantee that every fact is correct.

### LLM-as-a-judge

A judge model scores another model's response against a rubric. The rubric might cover correctness, completeness, relevance, faithfulness, style, or safety. The judge can also explain its score.

Use LLM-as-a-judge for open-ended tasks that lack a simple deterministic metric. Calibrate the judge against human ratings. Reduce bias by randomizing answer order in pairwise tests, hiding model identity, using clear criteria, and checking agreement on a human-reviewed sample.

| Metric or method | Measures best | Weak fit |
| --- | --- | --- |
| ROUGE | Reference overlap for summaries | Factuality or subjective helpfulness |
| BLEU | Reference overlap for translations | Agent completion or chatbot satisfaction |
| BERTScore | Semantic similarity to reference text | Tool correctness or business value |
| LLM-as-a-judge | Rubric-based open-ended quality | Unchecked high-stakes final authority |
| Human evaluation | Nuance, preference, domain correctness | Cheap evaluation of millions of outputs |

## Amazon Bedrock evaluations

Amazon Bedrock supports evaluation of models, knowledge bases, and RAG sources. The service can use programmatic metrics, human workers, an LLM judge, or RAG-focused evaluation jobs.

### Model evaluation choices

| Bedrock evaluation type | Data | Use case |
| --- | --- | --- |
| Programmatic model evaluation | Built-in or custom prompt dataset | Measure a model on a defined task with computed metrics |
| Human evaluation | Custom prompts and reviewer instructions | Rate or compare outputs on subjective or domain criteria |
| Judge-model evaluation | Prompts, model responses, and selected metrics or rubrics | Score open-ended responses through a second LLM |
| RAG evaluation | Queries plus expected retrieved text and/or responses | Measure retrieval and generation quality |

Programmatic jobs can use built-in datasets or your own prompts. Human jobs use a workforce such as employees or subject-matter experts. A judge job uses an evaluator model and can invoke a generator model, or it can score responses that you supply in the input dataset. Current supported models, regions, metrics, and job limits are documented by AWS and can change.

## Evaluate model quality beyond one metric

A model scorecard should cover the dimensions that matter to the task.

| Dimension | Example measure |
| --- | --- |
| Correctness | Exact match, rubric score, factual error rate |
| Completeness | Required points present |
| Relevance | Response addresses the request |
| Robustness | Score change after harmless input variations |
| Safety | Toxicity, policy violation, sensitive-data leakage |
| Fairness | Performance and error gaps across subgroups |
| Latency | Time to first token and total response time |
| Cost | Input/output tokens and cost per accepted result |
| Reliability | Error, timeout, and malformed-output rate |

Compare models with the same prompts, inference settings, retrieval context, and acceptance criteria. Otherwise, the test confounds model quality with system configuration.

## Evaluate RAG in two stages

RAG has a retrieval stage and a generation stage. Diagnose them separately before measuring the whole answer.

### General retrieval metrics

These information-retrieval metrics apply to RAG systems in general. They are not all built-in Amazon Bedrock RAG evaluation metrics.

| Metric | Question it answers |
| --- | --- |
| Recall@K | Relevant items found in the top K divided by all relevant items for the query |
| Precision@K | Relevant items in the top K divided by K; if fewer than K results can be returned, state the denominator used |
| Hit rate / success@K | Share of evaluated queries whose top K contains at least one expected relevant item |
| Mean reciprocal rank (MRR) | Mean reciprocal rank of the first relevant result, with zero for a query that has none |
| Normalized discounted cumulative gain (nDCG) | Graded relevance with lower-ranked results discounted and normalization against the ideal ranking |
| Retrieval latency | Time spent in search and reranking |

### Built-in Bedrock RAG evaluation metrics

Amazon Bedrock RAG evaluations use judge-model metrics for retrieve-only or retrieve-and-generate jobs. Current retrieve-only metrics are **context relevance** and **context coverage** (the latter requires ground truth). Current retrieve-and-generate metrics are **correctness, completeness, helpfulness, logical coherence, faithfulness, citation precision, citation coverage, harmfulness, stereotyping, and refusal**. Bedrock also supports custom judge metrics. This built-in list differs from general IR measures such as Recall@K, Precision@K, MRR, and nDCG.

### General generation and grounding metrics

| Metric | Question it answers |
| --- | --- |
| Answer correctness | Does the response match the expected answer or rubric? |
| Faithfulness / groundedness | Does the answer stay supported by retrieved evidence? |
| Citation correctness | Do citations support the claims they accompany? |
| Answer relevance | Does the response address the user's question? |
| Refusal quality | Does the model decline when the evidence is missing? |

### End-to-end RAG diagnosis

- Relevant passage absent: inspect chunking, embeddings, query rewriting, filters, K, and reranking.
- Passage present but answer wrong: inspect the generation prompt, model, context order, and grounding instructions.
- Correct answer with wrong citation: evaluate citation mapping as its own failure.
- Good offline scores but weak user results: inspect real query mix, stale content, access rules, and latency.

A RAG evaluation set should include the expected retrieved passages and expected answer when both stages matter. Amazon Bedrock RAG evaluations can assess retrieval-only and retrieve-and-generate behavior.

## Evaluate agents

Agent evaluation must inspect decisions and results, not prose alone. Define the denominator and exclusions for every rate.

| Agent metric | Definition |
| --- | --- |
| Task completion rate | Verified goals completed correctly divided by eligible assigned goals; state treatment of cancellations and policy-denied tasks |
| Tool selection accuracy | Acceptable tool choices divided by evaluated tool-selection opportunities, including a valid no-tool choice where relevant |
| Argument accuracy | Calls with valid, authorized, intent-grounded arguments divided by evaluated attempted tool calls |
| Step count | Steps per eligible task, interpreted with completion quality rather than minimized alone |
| Tool failure recovery rate | Eligible tool failures recovered within policy divided by eligible tool failures |
| Policy violation rate | Confirmed prohibited actions or attempts divided by a stated population of decisions, tool attempts, or sessions |
| Human escalation rate | Eligible tasks escalated divided by eligible tasks, paired with escalation appropriateness |
| End-to-end latency | Time from request to verified completion for the stated task population |
| Cost per completed task | Total included model, retrieval, tool, infrastructure, evaluation, and human cost divided by verified completed tasks |

Inspect traces for evaluation, but protect personal data and secrets. A verbose answer can hide a failed action. Confirm the external state, such as the ticket ID, reservation status, or database record.

## Evaluate workflows

An FM workflow can include classification, retrieval, generation, validation, human review, and an external action. Measure each step and the final result.

For a claims workflow:

1. Did extraction capture the correct claim fields?
2. Did retrieval return the applicable policy?
3. Did generation cite that policy?
4. Did validation detect unsupported claims?
5. Did the workflow route uncertain cases to a reviewer?
6. Did the claim reach the correct outcome within the service target?

Component metrics support debugging. End-to-end metrics decide whether the workflow works.

## Connect evaluation to business objectives

Technical evaluation should map to a business hypothesis.

| Business objective | Useful metric | Guardrail metric |
| --- | --- | --- |
| Improve employee productivity | Time saved per accepted task; tasks completed per hour | Correction and escalation rate |
| Increase user engagement | Successful sessions, return use, useful follow-up actions | Complaint and abandonment rate |
| Complete the intended task | Task completion rate | Incorrect completion and policy violation rate |
| Improve user experience | Satisfaction score and qualitative feedback | Latency and failure rate |
| Control unit economics | Cost per interaction or completed task | Quality floor and human-review cost |

The official objective lists **task engineering** beside productivity and user engagement but does not define the phrase. Retain it as official exam-guide wording rather than assigning it a separate meaning. Evaluate the intended task through explicit acceptance criteria and business outcomes.

### Cost per interaction

A useful estimate includes:

```text
(model input cost + model output cost + retrieval cost + tool cost
 + allocated evaluation/operations cost + human-review cost)
÷ completed interactions
```

Cost per raw request can reward a cheap system that fails often. Cost per successful task connects spending to value.

## Design an evaluation plan

1. Write the business outcome and failure limits.
2. Define model, component, workflow, and business metrics.
3. Build a representative held-out dataset.
4. Record the current model and application as a baseline.
5. Run programmatic tests for breadth.
6. Add human review for subjective and high-risk cases.
7. Calibrate an LLM judge if you need scalable rubric scoring.
8. Test RAG retrieval and generation separately.
9. Test agent actions against the resulting system state.
10. Monitor production drift, user feedback, cost, and safety after release.

Set acceptance thresholds before comparing candidates. Choosing the winner after seeing the results encourages cherry-picking.

## Scenario practice with reasoning

### Scenario 1: Translation quality

A travel company compares Spanish translations with approved human references.

**Best choice:** Use BLEU as a standard automated translation metric, then add bilingual human review for nuance and high-impact text.

**Reasoning:** BLEU matches the translation task and reference-based setup. ROUGE is tied to summarization, while user satisfaction alone cannot diagnose translation fidelity.

### Scenario 2: Summary paraphrases

A legal summarizer preserves the meaning of reference summaries but uses different wording.

**Best choice:** Use BERTScore alongside factuality and human checks.

**Reasoning:** BERTScore captures semantic similarity better than word-overlap metrics. It still cannot prove that every legal fact is correct.

### Scenario 3: Support tone at scale

A company wants to score one million open-ended support replies for empathy, completeness, and policy compliance.

**Best choice:** Use an LLM judge with a detailed rubric, calibrate it against expert ratings, and send uncertain or high-risk samples to people.

**Reasoning:** A judge scales open-ended evaluation. Human calibration catches judge bias and rubric gaps.

### Scenario 4: Good model, bad RAG answer

The correct policy section exists in the knowledge base, but it never appears in the top five retrieved chunks.

**Best choice:** Fix and evaluate retrieval before changing the generation model.

**Reasoning:** The FM cannot ground an answer in evidence it never receives. Hit rate at K and first-relevant-rank metrics expose this one-passage retrieval failure; Recall@K applies when the query has a set of relevant passages.

### Scenario 5: Agent claims success

A booking agent says it canceled a reservation, but the reservation remains active in the booking system.

**Best choice:** Mark the task as failed and verify tool results plus final system state in the evaluation.

**Reasoning:** Fluent confirmation text is not task completion. Agent evaluation must check the action outcome.

### Scenario 6: Cheapest model has more retries

Model A costs half as much per call as Model B. Model A needs three attempts for many requests, while Model B succeeds once.

**Best choice:** Compare cost per completed task, latency, and quality rather than price per call.

**Reasoning:** Unit token price hides retries and human correction. The business pays for successful outcomes.

### Scenario 7: Benchmark winner loses in production

A model leads a public benchmark but struggles with the company's short, code-switched customer messages.

**Best choice:** Use a custom representative dataset and report results by language and message type.

**Reasoning:** The benchmark distribution does not match the production workload. Averages can hide subgroup failures.

## Common exam traps

- **ROUGE is for translation:** BLEU is the standard exam match for translation; ROUGE is associated with summarization.
- **BERTScore checks business value:** It measures semantic similarity to reference text.
- **LLM judges remove human evaluation:** Humans should define rubrics, calibrate scores, and review high-risk cases.
- **A benchmark winner is the best application model:** Your data, latency, safety, and cost can produce a different choice.
- **RAG quality is one score:** Evaluate retrieval and generation separately.
- **Relevant retrieval proves a grounded answer:** The model can still ignore or contradict the context.
- **An agent's success message proves completion:** Verify tool responses and resulting state.
- **Low cost per request means low business cost:** Use cost per successful interaction or completed task.
- **Offline evaluation ends at launch:** Production inputs, data, user behavior, and model versions can drift.
- **Human ratings are objective:** Reviewer instructions, expertise, and agreement affect results.

## Self-check

### 1. Which metric is most associated with machine translation?

**Answer:** BLEU. It compares a candidate translation with one or more reference translations through n-gram overlap and a brevity adjustment.

### 2. Which metric handles meaning-preserving paraphrases better than surface overlap?

**Answer:** BERTScore, because it uses contextual embeddings to compare semantic similarity.

### 3. Retrieval returned no relevant passage, and the answer was wrong. Which component should you investigate first?

**Answer:** The retrieval stage. Inspect chunks, embeddings, query construction, metadata filters, top K, and reranking before replacing the generator model.

### 4. Which metric best shows whether an agent did the requested work?

**Answer:** Task completion rate backed by verification of tool results and final external state. Text quality alone cannot prove completion.

### 5. Why is cost per completed task better than cost per request?

**Answer:** It includes failures, retries, and correction. A low-cost request creates little value if users must repeat it or ask a person to fix the result.

## Practice

- [Domain 3 question bank](../../practice/question-bank.md#task-34)

## Official sources

- [Official AIF-C01 Domain 3 objectives](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain3.html)
- [Amazon Bedrock evaluations](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html)
- [Model evaluation task types](https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-tasks.html)
- [Prompt datasets for model evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-prompt-datasets.html)
- [Human model evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-type-human.html)
- [LLM-as-a-judge evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation-judge.html)
- [RAG evaluations](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation-kb.html)
- [Review RAG evaluation metrics](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-eval-llm-results.html)
- [Amazon SageMaker FMEval overview](https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-foundation-model-evaluate-whatis.html)

Content was rephrased for compliance with licensing restrictions. This lesson was written from the official AWS sources above. The local question bank informed the mix of original scenarios; no question text was copied.

---

[Domain contents](README.md) · [All domains and objectives](../../README.md#domain-guide)

**Previous:** [Lesson 09](09-training-customization.md) · **Next:** [Lesson 11](../domain-4-responsible-ai/11-responsible-ai.md)

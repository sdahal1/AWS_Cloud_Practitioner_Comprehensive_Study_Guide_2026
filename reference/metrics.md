# Metrics for AWS Certified AI Practitioner

Choose a metric that matches the task and state its denominator. A model can score well on an offline test while the application fails users or costs too much.

## Classification metrics

For one designated positive class:

|  | Predicted positive | Predicted negative |
|---|---:|---:|
| Actually positive | True positive (TP) | False negative (FN) |
| Actually negative | False positive (FP) | True negative (TN) |

- `Accuracy = (TP + TN) / (TP + TN + FP + FN)`
- `Precision = TP / (TP + FP)`
- `Recall = TP / (TP + FN)`
- `F1 = 2 × precision × recall / (precision + recall)`

Accuracy is the share of evaluated examples classified correctly. It can hide poor minority-class performance. Precision answers, "Of the items predicted positive, how many were positive?" Recall answers, "Of the actual positive items, how many did the model find?" F1 is their harmonic mean.

### Undefined and multiclass cases

A denominator can be zero. Precision is undefined if the model predicts no positives. Recall is undefined if the evaluation set contains no actual positives. A tool may return zero, omit the value, or apply a configurable `zero_division` rule. Record that choice instead of treating the result as measured performance.

Binary precision, recall, and F1 depend on which class you designate as positive. For multiclass or multilabel tasks, report the aggregation method:

- **Macro:** compute the metric for each class, then take an unweighted mean. Rare classes count as much as common classes.
- **Weighted:** average class metrics by class support. Large classes contribute more.
- **Micro:** pool TP, FP, and FN across classes before computing the metric.
- **Per-class:** publish each class separately when one class carries distinct risk.

In single-label multiclass classification, micro precision, recall, and F1 can equal accuracy. The plain binary formulas do not define a complete multiclass score without a one-vs-rest class choice or averaging rule.

### Worked example

A detector produces 40 TP, 10 FP, 20 FN, and 130 TN.

- Accuracy: `(40 + 130) / 200 = 85%`
- Precision: `40 / 50 = 80%`
- Recall: `40 / 60 ≈ 66.7%`
- F1: `2 × (.80 × .667) / (.80 + .667) ≈ 72.7%`

The accuracy hides that the detector misses one-third of actual positives.

## Regression metrics

| Metric | Meaning | Reading the result |
|---|---|---|
| Mean absolute error (MAE) | Mean absolute difference between prediction and actual value | Lower is better; expressed in the target's units |
| Mean squared error (MSE) | Mean squared difference | Lower is better; large errors receive more weight |
| Root mean squared error (RMSE) | Square root of MSE | Lower is better; returns to the target's units |
| R-squared (`R²`) | `1 - SS_res / SS_tot`, relative to predicting the evaluation-set mean | `1` is perfect, `0` matches the mean baseline, and a negative value is worse than that baseline; it does not prove usefulness or causation |

`R²` is not always a percentage of causally explained variation. It can be negative on evaluation data and can be undefined when the target has no variation, depending on the implementation.

## Generative-output metrics

| Metric | Definition and typical use | Main limitation |
|---|---|---|
| BLEU | Corpus-level geometric mean of modified n-gram precisions multiplied by a brevity penalty; common for machine translation | Valid translations can use different wording; sentence-level use often needs smoothing |
| ROUGE | Family of overlap measures for summarization. ROUGE-N often emphasizes n-gram recall; ROUGE-L uses longest common subsequence and can report precision, recall, or F-measure | Surface overlap does not establish factual accuracy |
| BERTScore | Aligns candidate and reference tokens by contextual-embedding similarity and reports precision, recall, and F1, often with optional baseline rescaling | Semantic similarity depends on the encoder and reference and does not prove truth |
| Perplexity | Exponentiated average negative log-likelihood, or the inverse geometric mean probability assigned to the observed tokens | Lower is better only for comparable tokenization, data, and modeling setup; it does not prove helpfulness, safety, or factuality |
| Toxicity | Harmful-output score or rate under a stated detector and threshold | Depends on definitions, language, threshold, and test data |
| Robustness | Change in performance under perturbations or challenging inputs | A narrow perturbation set can miss production failures |
| Human evaluation | People rate output against defined criteria | Costs more and depends on reviewer guidance and agreement |
| LLM-as-a-judge | A model scores output against a rubric | The judge can carry bias and error; calibrate it with human review |

Use benchmark datasets for repeatable comparison. Add representative private evaluation data when public benchmarks do not match the application.

[Amazon Bedrock evaluations](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html) supports model evaluation through programmatic, human, and judge-model methods, plus RAG evaluation. AgentCore Evaluations covers agent behavior.

## RAG and application metrics

General information-retrieval metrics and built-in Bedrock RAG evaluation metrics are not the same list.

### General retrieval metrics

- **Recall@K:** relevant items retrieved in the top K divided by all relevant items for the query.
- **Precision@K:** relevant items in the top K divided by K, unless the implementation documents another denominator for short result lists.
- **Hit rate@K / success@K:** evaluated queries with at least one relevant item in the top K divided by all eligible evaluated queries.
- **MRR:** mean of reciprocal rank for the first relevant result, assigning zero when a query has no relevant result.
- **nDCG@K:** discounted graded relevance normalized by the ideal ranking at K.

### Bedrock RAG evaluation

Amazon Bedrock RAG evaluations support retrieve-only and retrieve-and-generate jobs. Current retrieve-only metrics are **context relevance** and **context coverage** (which requires ground truth). Current retrieve-and-generate metrics are **correctness, completeness, helpfulness, logical coherence, faithfulness, citation precision, citation coverage, harmfulness, stereotyping, and refusal**. Bedrock also supports custom judge metrics. Check the [current RAG metric documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-eval-llm-results.html) because supported metrics can change.

Evaluate retrieval, grounding, answers, and system behavior separately. RAG can reduce unsupported answers but cannot guarantee accuracy.

## Agent metrics

Define the eligible population for every rate. Excluding failed, canceled, denied, or escalated work without saying so can inflate performance.

- **Task completion rate:** verified goals completed correctly divided by eligible assigned goals. State whether user cancellations and policy-denied tasks are excluded.
- **Tool-call success rate:** tool calls that return the defined successful result divided by attempted tool calls. A transport-level 200 response does not prove business success.
- **Tool selection accuracy:** decisions that select the expected or acceptable tool divided by evaluated tool-selection opportunities. Include a valid "no tool" class when relevant.
- **Argument accuracy:** tool calls whose required arguments are valid, authorized, and grounded divided by evaluated attempted tool calls.
- **Policy violation rate:** confirmed prohibited actions or attempts divided by evaluated agent decisions, tool attempts, or sessions. Name the denominator.
- **Human escalation rate:** eligible tasks routed to a person divided by eligible tasks. Pair it with escalation appropriateness so a low rate does not reward missed escalations.
- **Cost per completed task:** total model, retrieval, tool, infrastructure, evaluation, and allocated human-review cost divided by verified completed tasks.

Inspect traces and final external state as well as aggregate scores. AgentCore Evaluations can measure end-to-end goal attainment and tool-use accuracy, but the evaluator configuration defines the assessed population.

## Business metrics

| Metric | Definition or use |
|---|---|
| Return on investment (ROI) | `(attributable benefit - total investment cost) / total investment cost`, usually reported as a percentage over a stated period; define attribution, baseline, and included costs |
| Cost per user or interaction | Total included cost divided by unique users or eligible interactions; state which one |
| Productivity or time saved | Difference from a baseline for accepted work, including correction time |
| Conversion rate | Eligible users or sessions completing the defined action divided by eligible users or sessions |
| User engagement | A stated behavior such as retained active users or useful follow-up actions, not raw clicks alone |
| Customer satisfaction | Rating under a stated scale, sampling method, and response rate |
| Customer lifetime value | Expected contribution from a customer relationship under stated revenue, margin, retention, and discount assumptions |

ROI is undefined when total investment cost is zero. A positive model metric does not establish positive ROI; the calculation needs an attributable business benefit and the full cost base.

## Responsible-AI checks

Calculate performance for relevant subgroups and intersections, not only the overall population. Report sample size and uncertainty. Compare false-positive and false-negative rates, review dataset representation and label quality, and test explainability and safety. A high overall F1 score can coexist with poor outcomes for an underrepresented group.

## Exam cues

- `Avoid false alarms` points toward precision.
- `Do not miss positive cases` points toward recall.
- `Balance precision and recall` points toward F1.
- `Translation quality against references` points toward BLEU.
- `Summary overlap with references` points toward ROUGE.
- `Semantic similarity` points toward BERTScore.
- `Did the agent finish the job?` points toward task completion rate with verified state.
- `Did the investment pay off?` points toward ROI with a stated period, baseline, and cost scope.

Return to [Glossary](glossary.md) or [Common exam traps](common-exam-traps.md).

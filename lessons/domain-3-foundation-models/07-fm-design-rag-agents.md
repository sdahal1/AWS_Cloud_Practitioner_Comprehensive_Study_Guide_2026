# Task 3.1: Describe design considerations for applications that use foundation models (FMs)

Domain 3 accounts for 28% of the scored AIF-C01 exam. Task 3.1 asks you to choose a model, set inference controls, decide how the application should gain business knowledge, and recognize when an agent fits.

## Exam focus

Expect scenario questions with competing solutions that could all work. Pick the option that meets the stated need with the least cost and effort. Check hard requirements first, such as modality, language support, context length, and customization support. Then compare quality, latency, and cost.

You should be able to:

- select an FM by cost, modality, latency, language support, size, complexity, customization support, input and output limits, and prompt-caching support;
- explain how temperature and token limits affect responses;
- trace a Retrieval Augmented Generation (RAG) pipeline;
- identify AWS vector-store choices;
- compare in-context learning, RAG, fine-tuning, continued pre-training, pre-training, and distillation;
- distinguish an agent from a chatbot or a RAG-only application.

## Mental model: model, memory, controls, and actions

Picture an FM application as four choices:

1. **Model:** Which engine can accept the input and produce the required output?
2. **Memory:** Which current or private facts must the application retrieve?
3. **Controls:** How should each response vary in length and randomness?
4. **Actions:** Must the application answer, or must it call tools and complete work?

The FM supplies broad learned capability. RAG supplies request-time knowledge. Inference parameters shape one response. An agent decides which tools and knowledge sources to use across several steps.

## Select a foundation model

A larger model can handle harder reasoning, but it tends to cost more and respond more slowly. Model size is one signal, not a guarantee. Test candidate models on your own workload.

### Selection decision table

| Requirement | Check first | Likely decision |
| --- | --- | --- |
| Text, image, audio, or video input | Supported input and output modalities | Reject models that cannot handle the required modality |
| Users across several countries | Supported languages and quality by language | Test each target language, not English alone |
| Real-time assistant | Time to first token and total latency | Favor a smaller or latency-optimized model if quality passes |
| Complex planning or reasoning | Capability on representative tasks | Favor a more capable model when smaller models miss key steps |
| High request volume | Input/output token price and throughput mode | Minimize prompt size, output cap, and model cost |
| Long contracts or manuals | Context window and output limit | Verify prompt plus expected output fits |
| Consistent domain behavior | Supported customization methods | Check whether the model supports the needed fine-tuning method |
| Repeated long instructions | Prompt-caching support and token threshold | Cache a stable prefix when requests repeat within the cache lifetime |
| Data residency requirement | Regional availability and inference-profile routing | Choose a region or geographic profile that meets the boundary |

### Cost includes more than model price

Count the full application:

- input and output tokens;
- repeated context and few-shot examples;
- embeddings, retrieval, reranking, and vector storage;
- customization jobs and custom-model hosting or throughput;
- agent loops and tool calls;
- evaluation, monitoring, and human review.

A cheap model that needs several retries can cost more per completed task than a stronger model that succeeds once. The exam may express this as **cost per interaction** or ask for the solution with the least operational effort.

### Input length, output length, and context window

The **context window** is the request budget shared by the prompt, conversation history, retrieved passages, tool results, and generated response. A request that exceeds a model's accepted input or context limit can fail. A low maximum-output setting can cut off an answer.

Use the output-token cap to bound answer length, cost, and quota use. Do not treat it as a quality control. If a report needs 2,000 tokens and you allow 300, the response may stop before the conclusion.

### Prompt caching

Prompt caching reuses a stable input prefix, such as a long system prompt, tool definitions, reference material, or few-shot examples. The first qualifying request writes the cache. Later requests can read it while the cache remains valid.

Use caching when:

- a long prefix stays byte-for-byte stable;
- the model supports caching;
- the prefix meets the model's minimum token threshold;
- at least two requests reuse the prefix within the time-to-live window.

Avoid caching short or one-use prompts. Cache writes can cost more than standard input, so one request can increase cost. Put timestamps, session IDs, and user-specific context after the cache point to prevent cache fragmentation. Confirm cache use through cache-write and cache-read token metrics instead of assuming it worked.

## Control inference without changing the model

Inference parameters affect response generation for a single request. They do not add knowledge or update weights.

| Parameter | Lower setting | Higher setting | Exam cue |
| --- | --- | --- | --- |
| Temperature | Usually more focused and repeatable, but not guaranteed deterministic | Usually more varied and creative | Low for extraction; higher for brainstorming |
| Top P | Considers a narrower probability mass | Considers a broader probability mass | Lower narrows token choice |
| Top K | Considers fewer next-token candidates | Considers more candidates | Lower narrows token choice |
| Maximum output tokens | Lower output ceiling and greater truncation risk; lowers billed output only if generation would have continued | Higher output ceiling and possible higher cost | Set enough for the required response |
| Stop sequence | Ends generation at a chosen marker | Not applicable | Prevent extra sections or unwanted continuation |

Do not tune every sampling parameter at once. Models expose different controls and valid ranges. Low temperature often reduces variation, but hosted inference can still produce different outputs because model implementations, serving paths, and other sampling behavior can be nondeterministic. Use deterministic application checks when the result must be exact.

## RAG supplies request-time knowledge

RAG retrieves relevant information and places it in the model's context before generation. It works well for facts that are private, current, traceable, or too large to include in each prompt.

### RAG pipeline

1. **Collect:** Connect source documents such as policies, manuals, records, or web content.
2. **Parse and chunk:** Break each document into useful passages. Chunk boundaries affect retrieval quality.
3. **Embed:** Convert each chunk into a numerical vector that represents meaning.
4. **Store and index:** Put vectors, source text, and metadata in a vector store.
5. **Embed the query:** Convert the user's question with a compatible embedding model.
6. **Retrieve:** Find vectors close to the query and apply filters or reranking.
7. **Augment:** Add the selected passages and instructions to the generation prompt.
8. **Generate and cite:** Ask the FM to answer from the evidence and return source references when the application needs them.
9. **Evaluate:** Measure retrieval relevance, answer faithfulness, latency, and cost.

The offline ingestion path handles steps 1 through 4. The request path handles steps 5 through 8. Updating the source and running ingestion can refresh knowledge without retraining the FM.

### Amazon Bedrock Knowledge Bases

Amazon Bedrock Knowledge Bases manages much of the RAG workflow, including ingestion, chunking, embeddings, storage integration, retrieval, and response generation. You can retrieve chunks alone for a custom application or use retrieve-and-generate for an answer with source attribution.

RAG can reduce unsupported claims, but it does not guarantee truth. Poor chunks, stale documents, weak queries, missing access filters, or irrelevant retrieval can still produce a bad answer.

### Chunking choices

| Strategy | Best fit | Tradeoff |
| --- | --- | --- |
| Fixed-size | FAQs and uniform short text | Easy to run; may split a thought across chunks |
| Semantic | Long articles and technical documents | Preserves meaning better; adds ingestion work and cost |
| Hierarchical | Manuals, policies, and legal documents with sections | Keeps parent and child context; more setup complexity |
| No chunking | Pre-chunked content or very short documents | Gives the producer full control; requires prepared input |

Tables and complex figures may need advanced parsing. More chunks can raise recall but also increase storage, retrieval noise, and context tokens.

## Choose a vector store

The exam objective gives general vector-database examples: Amazon OpenSearch Service, Amazon Aurora, Amazon Neptune, and Amazon RDS for PostgreSQL. Do not assume that every general example is a current Amazon Bedrock Knowledge Bases storage integration.

| Service | Exam-level fit | Current Bedrock Knowledge Bases distinction |
| --- | --- | --- |
| Amazon OpenSearch Service | Vector and hybrid search with filtering | Knowledge Bases supports OpenSearch Serverless and supported OpenSearch managed clusters |
| Amazon Aurora PostgreSQL-Compatible Edition | Relational data plus PostgreSQL vector search | Knowledge Bases supports an Amazon RDS storage configuration backed by supported Aurora PostgreSQL setups |
| Amazon RDS for PostgreSQL | PostgreSQL vector extensions beside business data | It remains an official exam example; verify the exact Knowledge Bases-supported RDS configuration before implementation |
| Amazon Neptune | Official broad exam example for graph and connected-data scenarios | Knowledge Bases uses Neptune Analytics, not the broad Neptune Database product, for its managed graph/vector integration |
| Other current Knowledge Bases integrations | Product-specific rather than extra exam examples | S3 Vectors, Pinecone, Redis Enterprise Cloud, and MongoDB Atlas are among the supported integrations; availability depends on data source, Region, and configuration |

The exam guide uses the broad Amazon Neptune name. Current Knowledge Bases APIs identify `NEPTUNE_ANALYTICS` for the managed integration, so do not treat Neptune Database and Neptune Analytics as interchangeable.

The embedding dimensions must match the vector index. Metadata belongs beside each chunk so the application can filter by tenant, product, date, access level, or document type.

## Pick the lightest adaptation method

| Method | Changes model weights? | Data used | Best fit | Relative upfront cost |
| --- | --- | --- | --- | --- |
| Prompt engineering / in-context learning | No | Instructions and examples in the request | Tone, format, simple task guidance | Lowest |
| RAG | No | Retrieved current or private passages | Knowledge that changes or needs citations | Low to moderate |
| Fine-tuning | Yes | Curated labeled examples | Stable style, format, or task behavior | Moderate to high |
| Continued pre-training | Yes | Large unlabeled domain corpus | Specialized language and domain knowledge | High |
| Distillation | Yes, for a student model | Teacher outputs and task examples | Lower latency and inference cost at scale | Training cost, then lower run cost |
| Pre-training from scratch | Yes, creates the base model | Vast general corpus and compute | Building a new FM | Highest |

A common progression is prompt engineering, then RAG for knowledge, then fine-tuning if behavior remains weak. A production system can combine all three.

Distillation transfers task behavior from a larger teacher model to a smaller student model. The student may lose general capability, so evaluate it on the target workload and edge cases. Distillation pays off when inference savings exceed the one-time data and training expense.

## Agents complete multi-step work

An AI agent combines an FM with instructions, knowledge, tools, and orchestration. The FM interprets the goal and selects the next step. Tools perform bounded operations such as checking inventory, creating a ticket, or booking an appointment.

| Need | RAG application | Agent |
| --- | --- | --- |
| Answer from documents | Strong fit | Can use a knowledge base as one step |
| Call an API | Custom application code required | Action groups or tools support actions |
| Gather missing parameters | Application handles the dialogue | Agent can ask follow-up questions |
| Plan several dependent steps | Fixed workflow in code | Agent can select and sequence steps |
| Predictable path and strict control | Often easier | Requires tool limits, validation, and monitoring |

Amazon Bedrock Agents, now named **Amazon Bedrock Agents Classic**, can use a chosen FM, instructions, action groups, and associated knowledge bases. AWS moved the feature to maintenance on July 30, 2026. Existing customers can continue using it; new customers cannot access it. For a new implementation, evaluate AgentCore Harness, Runtime, Gateway, and related capabilities. An action group in an existing Agents Classic design describes available functions or API operations. Lambda or the calling application can perform the action. Treat model-generated arguments as untrusted input. Validate authorization, types, ranges, and business rules before a tool changes data.

Use an agent for variable, multi-step tasks. Use a fixed workflow for a known sequence that must remain deterministic. Use RAG alone when the user needs an answer rather than an action.

## Scenario practice with reasoning

### Scenario 1: Global image-support assistant

A retailer needs an assistant that accepts product photos and questions in six languages. Replies must arrive in under two seconds.

**Best choice:** Filter models by image input and tested support for all six languages, then benchmark latency and quality with representative requests.

**Reasoning:** Modality and language are hard requirements. Price cannot rescue a model that cannot process an image. Model size alone does not prove multilingual quality or latency.

### Scenario 2: Daily policy updates

A bank updates operating policies each day and needs answers with citations from the current policy set.

**Best choice:** Use RAG through an Amazon Bedrock knowledge base, ingest policy changes, retrieve relevant passages, and return citations.

**Reasoning:** The knowledge changes often and must remain traceable. Fine-tuning would create a stale snapshot and add retraining cost.

### Scenario 3: Repeated long system instructions

A contact-center application sends the same 8,000-token policy and tool description with thousands of requests each hour. Each request adds a short customer message.

**Best choice:** Use a model that supports prompt caching. Cache the stable prefix and place the customer message after the cache point.

**Reasoning:** Many requests reuse long identical content within the cache lifetime. The application should verify cache-read tokens and keep dynamic values outside the prefix.

### Scenario 4: Consistent invoice extraction

A finance team extracts fixed fields from invoices. It values repeatability and concise JSON over creative wording.

**Best choice:** Use a capable text or multimodal model, a low temperature, a strict output schema, and a sufficient output-token cap.

**Reasoning:** Low temperature narrows variation. A higher temperature adds randomness. A tiny output cap risks truncating valid JSON.

### Scenario 5: Change a delivery address

A customer assistant must authenticate the user, retrieve an order, confirm eligibility, change an address, and record an audit event.

**Best choice:** Use an agent or controlled workflow with narrow tools, validation, and an approval step where policy requires it.

**Reasoning:** RAG can explain the address policy but cannot perform the transaction by itself. The application must validate each generated tool argument.

### Scenario 6: Lower inference cost at high volume

A large model classifies support tickets with high accuracy. Volume will grow to millions of requests, and a smaller model performs poorly without help.

**Best choice:** Distill the large teacher into a smaller student, then compare task accuracy and cost per successful classification.

**Reasoning:** Distillation adds one-time training expense but can cut recurring latency and token cost. Prompt changes alone may not transfer enough of the teacher's task behavior.

### Scenario 7: Product graph questions

A manufacturer wants answers that depend on parts, suppliers, substitutions, and assembly relationships.

**Best choice:** Use Amazon Neptune Analytics for the managed Amazon Bedrock Knowledge Bases GraphRAG pattern.

**Reasoning:** The task depends on relationships across entities. Neptune Analytics supports the current managed GraphRAG integration and can preserve connections that isolated text chunks may hide.

## Common exam traps

- **Bigger model means better solution:** Hard requirements and workload tests come before model size.
- **Low temperature adds facts:** Temperature changes randomness, not knowledge.
- **Maximum tokens expands the context window:** It caps generated output and consumes part of the context budget.
- **RAG trains the model:** RAG changes request context. It does not update weights.
- **Fine-tuning keeps facts current:** Fine-tuning captures a training snapshot. Use RAG for changing documents.
- **A vector store holds only vectors:** Useful RAG stores source text and metadata with embeddings.
- **A chatbot is an agent:** An agent selects tools and actions. A chat interface can exist without agency.
- **Prompt caching helps every request:** Short, changing, or one-use prefixes may cost more or miss the cache.
- **An agent makes tool calls safe:** The application must validate permissions and parameters at the tool boundary.
- **Pre-training is the normal business choice:** It has the greatest data, compute, and skill requirements.

## Self-check

### 1. Which model-selection criteria should you test before cost for an application that analyzes photos?

**Answer:** Required modality comes first. Reject models that cannot accept the image format and produce the needed output. Then compare language support, context limits, latency, quality, and cost.

### 2. A company changes its product manuals each week. Should it fine-tune or use RAG?

**Answer:** Use RAG. The application can re-ingest updated documents without updating model weights, and it can cite retrieved passages.

### 3. Why can a low maximum-output setting break a correct prompt?

**Answer:** The model can hit the cap before it completes the response. Structured output may end with missing fields or invalid syntax.

### 4. Which AWS data service best matches a scenario centered on connected entities and GraphRAG?

**Answer:** Choose the Amazon Neptune family when the exam asks for connected graph data. For the current managed Amazon Bedrock Knowledge Bases GraphRAG integration, choose Neptune Analytics.

### 5. A user asks an assistant to cancel a reservation. Why is an agent a better fit than RAG alone?

**Answer:** Cancellation requires actions and often several steps, such as finding the reservation, checking policy, requesting confirmation, and calling an API. RAG supplies knowledge but does not execute the cancellation.

## Practice

- [Domain 3 question bank](../../practice/question-bank.md#task-31)

## Official sources

- [Official AIF-C01 Domain 3 objectives](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain3.html)
- [Supported foundation models in Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html)
- [Inference parameters](https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html)
- [Prompt caching](https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-caching.html)
- [Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)
- [How Knowledge Bases work](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html)
- [Set up a vector store for a knowledge base](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-setup.html)
- [Knowledge Bases storage configuration API](https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent_StorageConfiguration.html)
- [Amazon Titan Text Embeddings](https://docs.aws.amazon.com/bedrock/latest/userguide/titan-embedding-models.html)
- [Model customization](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html)
- [Model distillation](https://docs.aws.amazon.com/bedrock/latest/userguide/model-distillation.html)
- [Amazon Bedrock Agents](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html)
- [Amazon Bedrock Agents Classic maintenance mode](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-classic-maintenance-mode.html)
- [How Amazon Bedrock Agents work](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-how.html)

Content was rephrased for compliance with licensing restrictions. This lesson was written from the official AWS sources above. The local question bank informed the mix of original scenarios; no question text was copied.

---

[Domain contents](README.md) · [All domains and objectives](../../README.md#domain-guide)

**Previous:** [Lesson 06](../domain-2-generative-ai/06-aws-genai-services.md) · **Next:** [Lesson 08](08-prompt-engineering.md)

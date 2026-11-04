# AWS Certified AI Practitioner (AIF-C01) question bank

439 community questions organized by exam domain and task, with answers and explanations in expandable sections.

## Sources, licenses, and quality

- CloudCertPrep AIF-C01 questions: https://github.com/nastaso/cloudcertprep, MIT License. The CloudCertPrep domain sections retain that license.
- SaveMyCert worked questions: https://github.com/savemycert/aif-c01-study-guide, CC BY 4.0. The SaveMyCert section retains that license.
- Official exam guide: https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html

The repository's CC BY 4.0 license covers original guide prose. It does not relicense either question source.

SaveMyCert material appears under CC BY 4.0 with attribution to SaveMyCert: https://www.savemycert.com/.
These independent study materials are not official AWS exam questions.

Licenses and adaptation details appear in [third-party notices](../THIRD_PARTY_NOTICES.md). Official AWS references appear in [SOURCES.md](../SOURCES.md).

## Jump to a domain or task

- [Domain 1](#domain-1-fundamentals-of-ai-and-ml): [1.1](#task-11) · [1.2](#task-12) · [1.3](#task-13)
- [Domain 2](#domain-2-fundamentals-of-generative-ai): [2.1](#task-21) · [2.2](#task-22) · [2.3](#task-23)
- [Domain 3](#domain-3-applications-of-foundation-models): [3.1](#task-31) · [3.2](#task-32) · [3.3](#task-33) · [3.4](#task-34)
- [Domain 4](#domain-4-guidelines-for-responsible-ai): [4.1](#task-41) · [4.2](#task-42)
- [Domain 5](#domain-5-security-compliance-and-governance-for-ai-solutions): [5.1](#task-51) · [5.2](#task-52)
- [SaveMyCert worked questions](#savemycert-worked-sample-questions)

# Domain 1: Fundamentals of AI and ML

Questions in this domain: 133

## Task 1.1

Questions for this task: 33

### Question 1: aif-q006

A company runs an ML pipeline on Amazon SageMaker AI in production. Its requests carry large payloads of up to 1 GB and can take up to an hour to process, and the company wants near real-time latency. Which SageMaker AI inference option meets these requirements?

- **A.** Real-time inference
- **B.** Batch transform
- **C.** Serverless inference
- **D.** Asynchronous inference

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Asynchronous inference

**Explanation:**

Asynchronous inference is built for large payloads of up to 1 GB and long processing times of up to an hour; it queues incoming requests and processes them in the background, returning results when ready without requiring the caller to wait synchronously, which suits workloads that need near real-time handling of demanding requests.
Real-time inference targets small payloads and fast synchronous responses, and its payload and timeout limits would be exceeded by 1 GB inputs and hour-long processing. Serverless inference suits intermittent traffic with smaller payloads and likewise cannot handle such large inputs or long durations. Batch transform processes large datasets offline in bulk and is not designed to deliver near real-time latency.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-06-03

---

### Question 2: aif-q017

A retailer has accumulated petabytes of customer records that have no labels or predefined categories. The business wants to group these customers into distinct segments to target them with tailored promotions. Which machine learning approach best fits this requirement?

- **A.** Supervised learning
- **B.** Unsupervised learning
- **C.** Reinforcement learning
- **D.** Semi-supervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Unsupervised learning

**Explanation:**

Unsupervised learning discovers patterns and natural groupings within unlabeled data, making it the right approach for segmenting customers when no predefined labels or categories exist, as is the case with the retailer's unlabeled records.
Supervised learning requires labeled training data where each record has a known target output, which the retailer does not have. Reinforcement learning trains an agent through rewards and penalties as it interacts with an environment, which does not apply to segmenting a static dataset of customers. Semi-supervised learning relies on a small amount of labeled data combined with a larger pool of unlabeled data, but here there are no labels at all, so a purely unsupervised approach is the correct fit.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 3: aif-q058

A team wants to improve a support chatbot with reinforcement learning. Which plan correctly describes the learning process?

- **A.** Train a policy in a controlled environment or approved offline workflow with a reward signal, evaluate it, and deploy an approved version
- **B.** Allow the production chatbot to change its weights after every live conversation without review
- **C.** Cluster customer questions without a reward signal
- **D.** Update a FAQ and assume the model weights change automatically

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Train a policy in a controlled environment or approved offline workflow with a reward signal, evaluate it, and deploy an approved version

**Explanation:**

Reinforcement learning optimizes behavior from reward signals during a controlled training process. Production systems do not need to learn autonomously from live users, and teams should evaluate and approve trained versions before deployment.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 4: aif-q062

An insurance company needs to run its ML model over several years of archived claims records to generate predictions, with each dataset running to several gigabytes. The results are not required immediately. Which Amazon SageMaker AI inference option best fits this need?

- **A.** Serverless inference
- **B.** Batch transform
- **C.** Real-time inference
- **D.** Asynchronous inference

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Batch transform

**Explanation:**

Batch transform runs inference as an offline job over an entire dataset without a persistent endpoint, so it can process the multiple-gigabyte archived data efficiently when the predictions are not needed immediately.
Real-time inference and serverless inference both return predictions synchronously from a live endpoint for low-latency, on-demand requests, so neither suits offline bulk processing of large datasets. Asynchronous inference queues incoming requests and is intended for large individual payloads that need near-real-time handling, rather than running a single job across an entire archived dataset.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-06-02

---

### Question 5: aif-q093

A retail store plans to forecast demand for a product over the coming weeks using the Amazon SageMaker AI DeepAR algorithm. Which type of data is required to meet this requirement?

- **A.** Text data
- **B.** Time series data
- **C.** Audio data
- **D.** Image data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Time series data

**Explanation:**

DeepAR is a forecasting algorithm that predicts future values from historical observations recorded in sequence over time, so it needs time series data such as past demand indexed by date in order to learn temporal patterns and project them forward.
Text data suits Natural Language Processing tasks, image data suits Computer Vision tasks, and audio data suits speech or sound processing; none of these capture the chronological, time-indexed measurements that a demand-forecasting model relies on.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 6: aif-q115

A wildlife research team wants to train a model that identifies the animal species shown in camera-trap photos. It has a large set of images that are already tagged with the correct species and will not be labeling any more. Which type of learning should it use?

- **A.** Reinforcement learning
- **B.** Supervised learning
- **C.** Active learning
- **D.** Unsupervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Supervised learning

**Explanation:**

Supervised learning is the right choice because the team already has a large dataset in which every image is paired with a known label identifying the species. The model learns to map inputs to the correct output labels from this labeled training data, which is the defining characteristic of supervised learning.
Unsupervised learning is used when no labeled data is available and the model must discover patterns or groupings on its own, which does not apply here because labeled data already exists. Reinforcement learning trains an agent to take actions in an environment to maximize a cumulative reward through trial and error, and is not suited to classifying images from a static labeled dataset. Active learning is a strategy that iteratively selects the most uncertain examples and requests human labelers to annotate them, reducing the total labeling effort needed; however, the team has explicitly stated they will not be labeling any more data, so active learning's core mechanism cannot be used and it offers no benefit in this scenario.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 7: aif-q206

A logistics company ingests several gigabytes of shipment records each day and uses them to train an ML model that predicts next-day delivery volumes. The company only needs predictions generated once per day on the full set of accumulated data. Which type of inference best meets this requirement?

- **A.** Batch inference
- **B.** Asynchronous inference
- **C.** Real-time inference
- **D.** Serverless inference

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Batch inference

**Explanation:**

Batch inference is designed for high-volume predictions on large datasets processed together on a schedule, so the company can run a single daily job over all accumulated shipment records to generate its forecasts without maintaining a persistent endpoint.
Asynchronous inference is suited to handling individual requests with large payloads or long processing times by queuing them, rather than scoring an entire daily dataset in one scheduled run. Real-time inference provides immediate predictions through a continuously running endpoint for low-latency use cases, which is unnecessary and more costly when results are only needed once per day. Serverless inference automatically provisions capacity for intermittent, on-demand requests, which suits unpredictable traffic rather than a predictable bulk job processed on a fixed daily schedule.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 8: aif-q209

Which ML technique uses training data that is labeled with the correct output values?

- **A.** Supervised learning
- **B.** Unsupervised learning
- **C.** Reinforcement learning
- **D.** Transfer learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Supervised learning

**Explanation:**

Supervised learning trains models on datasets where each input example is paired with a known correct output label, allowing the model to learn the mapping between inputs and targets and make predictions on new unseen data.
Unsupervised learning works with entirely unlabeled data and discovers hidden patterns or groupings without known target values. Reinforcement learning optimizes actions from reward signals rather than ordinary input-target labels; it may learn from live interaction or recorded experience. Transfer learning adapts knowledge from a pretrained model to another task, which describes model reuse rather than the labeling structure of this dataset.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 9: aif-q232

A company is building an application that must automatically organize customers and products into groups of similar items based on their attributes. Which ML strategy should the company use to meet this requirement?

- **A.** Supervised learning
- **B.** Reinforcement learning
- **C.** Unsupervised learning
- **D.** Semi-supervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Unsupervised learning

**Explanation:**

Unsupervised learning automatically discovers patterns and natural groupings within data, which makes it the right strategy for clustering similar customers and products by their attributes when no predefined groups are provided.
Supervised learning requires labeled training data with known target outputs, so it cannot form groups when no labels or categories are supplied. Reinforcement learning trains an agent through rewards and penalties as it interacts with an environment, which does not apply to grouping items in a static dataset. Semi-supervised learning combines a small amount of labeled data with a larger pool of unlabeled data, but here there are no labels at all, so a fully unsupervised approach is the correct fit.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 10: aif-q240

A healthcare company has trained a model on historical patient data, including medical history, demographics, and treatments, to predict in real time whether a patient will be readmitted within 30 days of discharge. Which task in this scenario represents AI model inference?

- **A.** Apply the trained model to predict whether a patient will be readmitted
- **B.** Collect historical patient readmission records
- **C.** Measure the model's performance using suitable evaluation metrics
- **D.** Analyze the data to uncover patterns and correlations among patients

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Apply the trained model to predict whether a patient will be readmitted

**Explanation:**

Model inference is the stage of applying an already-trained model to new data to generate predictions, so using the trained model to predict whether a patient will be readmitted is the task that represents inference in this scenario.
Collecting historical readmission records is the data collection stage that happens before training. Measuring the model's performance with evaluation metrics is the evaluation stage, which assesses a model rather than serving predictions. Analyzing the data to uncover patterns and correlations is exploratory analysis carried out before or during model building, not the act of generating predictions from a finished model.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 11: aif-q251

A company needs to collect a large dataset to train an AI assistant in a specific content area. Which dataset will meet this requirement?

- **A.** Diverse conversations that use relevant terminology
- **B.** Time series data of general purpose historical sales
- **C.** Sentiment analysis of news articles
- **D.** Unique product IDs and corresponding user IDs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Diverse conversations that use relevant terminology

**Explanation:**

Diverse conversations that use relevant terminology provide the contextual, domain-specific language an AI assistant needs to learn how to understand and respond accurately within the targeted content area, making this the appropriate training dataset.
Time series data of general purpose historical sales is structured numerical data suited to forecasting trends over time, not to training a conversational assistant in a specialized subject. Sentiment analysis of news articles produces classifications of positive or negative tone rather than the conversational examples needed to teach an assistant how to interact. Unique product IDs and corresponding user IDs are identifiers used for tasks such as recommendation systems, and contain no linguistic or contextual content from which an assistant could learn to converse.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 12: aif-q264

Which of the following scenarios is an example of unsupervised learning?

- **A.** A model that organizes thousands of news articles into related topics without predefined categories
- **B.** A model that flags a loan application as high risk or low risk
- **C.** A model that forecasts a city's electricity demand for the next day
- **D.** A model that teaches a robot to walk by rewarding successful movements

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. A model that organizes thousands of news articles into related topics without predefined categories

**Explanation:**

Organizing news articles into related topics without predefined categories is an example of unsupervised learning, where the model finds natural patterns and clusters in the data without relying on any labeled outputs.
Flagging a loan application as high risk or low risk is supervised learning, because the model is trained on labeled examples where the correct outcome is already known. Forecasting a city's electricity demand for the next day is also supervised learning, specifically a regression task that learns from labeled historical values. Teaching a robot to walk by rewarding successful movements is reinforcement learning, where an agent improves by receiving rewards and penalties from its actions rather than discovering clusters in unlabeled data.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 13: aif-q273

Which of the following is an example of Unsupervised Learning?

- **A.** Training a model to identify animals in photographs
- **B.** Producing human-like text in response to a written prompt
- **C.** Grouping data points into clusters based on how similar they are
- **D.** Predicting a house's selling price from features such as its size and location

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Grouping data points into clusters based on how similar they are

**Explanation:**

Grouping data points into clusters by similarity is a classic example of Unsupervised Learning, where the algorithm finds structure and natural groupings in the data on its own, without any labeled examples to guide it.
Training a model to identify animals in photographs is Supervised Learning, since it learns from images already labeled with the correct animal. Predicting a house's selling price from its features is also Supervised Learning, specifically regression, because it is trained on examples with known prices. Producing human-like text from a prompt is Generative AI, which creates new content rather than discovering groupings in unlabeled data.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 14: aif-q280

An energy provider wants to monitor voltage levels across a power grid in rural regions. It plans to record voltage readings continuously and store them in Amazon RDS, then analyze how the readings fluctuate throughout each day to build an AI model that predicts potential power outages. Which type of data should the provider collect for this task?

- **A.** Tabular data
- **B.** Text data
- **C.** Time series data
- **D.** Audio data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Time series data

**Explanation:**

Time series data consists of values recorded sequentially over time, such as voltage readings taken at regular intervals, which is exactly what is needed to analyze fluctuations throughout the day and build a model that predicts power outages.
Tabular data organizes information into rows and columns of features but does not inherently capture the time-ordered sequence required to model changes throughout the day. Text data represents unstructured written language such as documents or messages, which is not relevant to numerical voltage measurements. Audio data captures sound signals and has no application to monitoring electrical readings over time.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 15: aif-q300

In the context of AI, what does the term inference refer to?

- **A.** Gathering the training data used to build AI systems
- **B.** Designing brand-new AI algorithms from scratch
- **C.** Merging several AI models together into a single model
- **D.** Applying an already-trained model to new, unseen data to produce predictions or decisions

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Applying an already-trained model to new, unseen data to produce predictions or decisions

**Explanation:**

Inference is the stage where an already-trained model is applied to new, unseen data to generate predictions or decisions, drawing on the patterns it learned during training. It is distinct from training, when the model is still learning from data.
Designing new AI algorithms is research and development work, not the act of running a finished model. Merging several models into one describes model ensembling or consolidation rather than producing predictions. Gathering training data is the data collection step that happens before training, well ahead of inference.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 16: aif-q304

A public health agency has collected a year of patient records and wants to produce a monthly trend report for officials. Each month it needs to run a model across a large set of historical records at one scheduled time, with no requirement for immediate results. Which inference method meets this need most cost-effectively?

- **A.** Real-time inference
- **B.** Asynchronous inference
- **C.** Batch transform
- **D.** Serverless inference

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Batch transform

**Explanation:**

Batch transform is designed to run inference over a large dataset all at once as a scheduled, offline job, so the agency can process a whole month of records to generate the report without paying for a continuously running endpoint, which makes it the most cost-effective choice for this periodic bulk workload.
Real-time inference keeps an endpoint permanently available for low-latency individual predictions, which is unnecessary and more expensive for a scheduled bulk job. Serverless inference suits intermittent, unpredictable request traffic that still needs a quick response per request, not large scheduled batch processing. Asynchronous inference queues individual requests with large payloads or long processing times for near-real-time handling, but it still runs a hosted endpoint and is not intended for processing an entire dataset in one pass.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 17: aif-q306

A bank is building an ML model to predict the likelihood that a loan applicant will default. The model uses applicant data such as income, credit score, employment length, and existing debt. The historical dataset includes a label indicating whether each past applicant ultimately defaulted. Which ML technique meets these requirements?

- **A.** Unsupervised learning
- **B.** Supervised learning
- **C.** Reinforcement learning
- **D.** Semi-supervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Supervised learning

**Explanation:**

Supervised learning is the right technique when the dataset contains both input features, such as income, credit score, and existing debt, and a known label indicating the outcome, because the model learns to predict that labeled target from the example data.
Unsupervised learning works with unlabeled data to discover patterns or clusters, which does not fit a problem where a known default outcome is already provided for each record. Reinforcement learning trains an agent through rewards and penalties as it interacts with an environment, which does not apply to predicting an outcome from a fixed labeled dataset. Semi-supervised learning is used when only a small portion of the data is labeled and the rest is not, whereas here every historical record already has a known outcome, making fully supervised learning the appropriate choice.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 18: aif-q312

Which statement best describes how Artificial Intelligence (AI) and Machine Learning (ML) relate to each other?

- **A.** AI is a branch of ML
- **B.** AI and ML mean the same thing
- **C.** ML is a branch of AI
- **D.** AI and ML are unrelated fields

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. ML is a branch of AI

**Explanation:**

Machine Learning is a branch of Artificial Intelligence. AI is the broad field of building systems that mimic human intelligence, and ML is one approach within it that lets systems learn patterns from data and improve without being explicitly programmed for every rule.
Stating that AI is a branch of ML reverses the relationship and is incorrect. Saying the two are unrelated ignores that ML sits inside the wider field of AI. Claiming they mean the same thing wrongly equates the broad field with just one of its techniques, overlooking other AI approaches such as rule-based or expert systems.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 19: aif-q313

Which of the following is NOT a type of machine learning?

- **A.** Supervised learning
- **B.** Unsupervised learning
- **C.** Reinforcement learning
- **D.** Diagnostic learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Diagnostic learning

**Explanation:**

Diagnostic learning is not a recognized type of machine learning and does not appear in the AI/ML literature or the AWS exam guide, making it the option that does not belong among the established ML learning paradigms.
Supervised learning, unsupervised learning, and reinforcement learning are the three primary types of machine learning. Supervised learning trains models on labeled datasets where each input is paired with a known correct output. Unsupervised learning discovers hidden patterns in unlabeled data without any predefined output values to learn from. Reinforcement learning trains an agent to make sequential decisions by rewarding desirable behaviors and penalising undesirable ones.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 20: aif-q314

A team is building a Computer Vision model. Which type of data is the best fit for training it?

- **A.** Text data
- **B.** Image data
- **C.** Tabular data
- **D.** Time-series data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Image data

**Explanation:**

Image data is the best fit because Computer Vision models learn from the visual features and pixel patterns in images (and video frames) to perform tasks such as object detection and image classification.
Tabular data holds structured rows and columns and suits classic ML problems like regression. Time-series data captures values ordered over time, such as sensor or sales readings. Text data is the input for Natural Language Processing (NLP) tasks. None of these carry the visual information a Computer Vision model needs.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 21: aif-q319

You have a large dataset in which every example is already labeled. Which type of machine learning is the best fit?

- **A.** Unsupervised learning
- **B.** Supervised learning
- **C.** Semi-supervised learning
- **D.** Reinforcement learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Supervised learning

**Explanation:**

Supervised learning trains on labeled examples, where each input is paired with its correct output, so the model learns the mapping from inputs to known targets. That makes it the right choice when you have a large, fully labeled dataset.
Unsupervised learning works with unlabeled data to uncover hidden structure or groupings, so it does not make use of the labels available here. Semi-supervised learning is intended for cases with a small amount of labeled data alongside a large amount of unlabeled data, not a fully labeled set. Reinforcement learning trains an agent through trial-and-error rewards from an environment and does not rely on a labeled dataset at all.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 22: aif-q326

Which type of machine learning is most appropriate for training an agent to make decisions by interacting with its environment?

- **A.** Supervised learning
- **B.** Unsupervised learning
- **C.** Reinforcement learning
- **D.** Transfer learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Reinforcement learning

**Explanation:**

Reinforcement learning trains an agent to make decisions by interacting with an environment, where it receives rewards for desirable actions and penalties for undesirable ones and gradually learns a strategy that maximizes cumulative reward.
Supervised learning trains a model on labeled examples with known correct outputs, rather than having an agent learn from the consequences of its own actions. Unsupervised learning finds patterns or clusters in unlabeled data and does not involve an agent, an environment, or a reward signal. Transfer learning reuses knowledge from a model trained on one task to improve performance on a related task, which describes a way of reusing model knowledge rather than learning through environmental interaction.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 23: aif-q329

Which of the following is an example of unsupervised learning?

- **A.** Predicting house prices
- **B.** Spam detection
- **C.** Clustering customer segments
- **D.** Image classification

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Clustering customer segments

**Explanation:**

Clustering customer segments is an example of unsupervised learning because the algorithm groups data points based on similarity without being given any labeled examples or predefined categories to learn from. The model discovers the structure in the data on its own.
Predicting house prices uses labeled training data where each example has a known price, making it a supervised regression task. Spam detection trains a model on emails already labeled as spam or not spam, making it a supervised classification task. Image classification trains a model on images with known labels, such as cat or dog, also making it a supervised classification task.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-05-30

---

### Question 24: aif-q330

What is the main difference between batch inferencing and real-time inferencing?

- **A.** Batch inferencing is always more accurate
- **B.** Real-time inferencing can only be done on small datasets
- **C.** Batch inferencing processes multiple inputs at once, while real-time inferencing processes individual inputs as they arrive
- **D.** Real-time inferencing is always faster than batch inferencing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Batch inferencing processes multiple inputs at once, while real-time inferencing processes individual inputs as they arrive

**Explanation:**

Batch inferencing collects multiple inputs and processes them together in a single job, making it well suited for non-time-sensitive workloads where throughput and efficiency are the priority. Real-time inferencing processes each input individually as it arrives and returns a prediction immediately, making it suitable for applications that require instant responses such as fraud detection or content moderation.
Batch inferencing is not always more accurate than real-time inferencing because accuracy is a property of the model and its training data, not of the inferencing method used to serve predictions. Real-time inferencing is not limited to small datasets as it processes individual inputs on demand regardless of the overall size of the data being served. Real-time inferencing is not always faster than batch inferencing because while it offers lower latency per individual request, batch inferencing can achieve higher overall throughput by processing many inputs simultaneously.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 25: aif-q036

A company deployed a deep learning model for object detection to production. When the model examines a new image to identify the objects in it, which AI process is taking place?

- **A.** Training
- **B.** Inference
- **C.** Bias correction
- **D.** Model deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Inference

**Explanation:**

Inference is the process in which a deployed model analyzes new data, such as a new image, to produce a prediction, so identifying objects in an incoming image is inference.
Training is the earlier process of fitting the model to data, model deployment is making the trained model available to serve requests, and bias correction adjusts for unfair outcomes. None of these describes analyzing a new image to make a prediction.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 26: aif-q355

Which description best defines agentic AI?

- **A.** AI that generates images from text prompts
- **B.** AI that autonomously plans, decides, and takes actions to achieve goals
- **C.** AI that converts speech to text
- **D.** AI that groups similar data points into clusters

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. AI that autonomously plans, decides, and takes actions to achieve goals

**Explanation:**

Agentic AI refers to AI systems that can autonomously plan, make decisions, and take actions to accomplish goals, often by using tools, managing memory, and orchestrating multi-step workflows without constant human direction.
Generating images from text prompts describes diffusion models or image-generation AI. Converting speech to text describes speech recognition. Grouping similar data points into clusters describes unsupervised learning techniques like K-means.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 27: aif-q356

How does agentic AI differ from traditional AI systems?

- **A.** Agentic AI requires more training data than traditional AI
- **B.** Agentic AI can only process text, while traditional AI handles all data types
- **C.** Agentic AI can autonomously execute multi-step tasks, while traditional AI typically responds to single requests
- **D.** Agentic AI is always more accurate than traditional AI

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Agentic AI can autonomously execute multi-step tasks, while traditional AI typically responds to single requests

**Explanation:**

Agentic AI systems can autonomously break down goals into steps, use tools, and execute multi-step workflows to achieve objectives, whereas traditional AI systems typically process individual requests and return single responses without autonomous planning or action-taking.
Agentic AI does not inherently require more training data than traditional AI. Agentic AI can work with multiple data types, not just text. Accuracy depends on the specific model and task, not on whether the system is agentic.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 28: aif-q362

What does the term Large Language Model (LLM) refer to?

- **A.** A database that stores large amounts of text
- **B.** A deep learning model trained on vast text data to understand and generate human language
- **C.** A tool for translating between programming languages
- **D.** A system that converts speech to text

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. A deep learning model trained on vast text data to understand and generate human language

**Explanation:**

A Large Language Model (LLM) is a deep learning model trained on massive amounts of text data that can understand context, generate coherent text, answer questions, and perform various language tasks.
A database stores data but does not understand or generate language. A programming language translator converts code syntax, not natural language understanding. A speech-to-text system transcribes audio but is not what the term LLM describes.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 29: aif-q363

Which statement best describes Generative AI?

- **A.** AI that only classifies data into predefined categories
- **B.** AI that creates new content such as text, images, or audio based on learned patterns
- **C.** AI that exclusively detects anomalies in datasets
- **D.** AI that only retrieves existing information from databases

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. AI that creates new content such as text, images, or audio based on learned patterns

**Explanation:**

Generative AI refers to AI systems that can create new content, including text, images, audio, video, and code, by learning patterns from training data and generating novel outputs that resemble that data.
Classifying data into predefined categories describes classification models, not generative models. Detecting anomalies describes anomaly detection systems. Retrieving existing information describes search or retrieval systems. None of these involves creating new content.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 30: aif-q365

Which statement best describes how Deep Learning differs from traditional Machine Learning?

- **A.** Deep Learning requires manually engineered features, while traditional Machine Learning does not
- **B.** Deep Learning uses multi-layered neural networks that automatically learn feature representations from raw data
- **C.** Deep Learning can only be applied to text data
- **D.** Deep Learning always requires less data than traditional Machine Learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Deep Learning uses multi-layered neural networks that automatically learn feature representations from raw data

**Explanation:**

Deep Learning uses neural networks with many layers that automatically discover useful feature representations directly from raw data, removing the need for manual feature engineering that traditional Machine Learning typically requires.
Traditional Machine Learning is the approach that usually depends on manually engineered features, so option A reverses the relationship. Deep Learning applies to images, audio, text, and other data types, not only text. Deep Learning generally requires more data than traditional Machine Learning because its multi-layered networks have many more parameters to train.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 31: aif-q367

Which of the following is an example of unstructured data?

- **A.** A database table of customer orders with columns for date, quantity, and price
- **B.** A spreadsheet listing employee IDs, names, and salaries
- **C.** A collection of free-form customer support emails
- **D.** A CSV file containing sensor readings indexed by timestamp

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. A collection of free-form customer support emails

**Explanation:**

Free-form customer support emails are unstructured data because they have no predefined schema or fixed format: the content varies in length, style, and layout, making them unsuitable for direct storage in rows and columns without processing.
A database table with defined columns, a spreadsheet with named fields, and a CSV file with consistent columns are all examples of structured data because each record follows a predefined schema where every field has a known type and position.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 32: aif-q371

In Machine Learning, what does the term bias most commonly refer to?

- **A.** The speed at which a model trains
- **B.** A systematic error that causes a model to consistently favor certain outcomes over others
- **C.** The total number of parameters in a model
- **D.** The process of splitting data into training and test sets

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. A systematic error that causes a model to consistently favor certain outcomes over others

**Explanation:**

In Machine Learning, bias refers to a systematic error where the model consistently skews toward certain predictions or outcomes, which can arise from unrepresentative training data, flawed assumptions in the algorithm, or imbalanced datasets. Identifying and reducing bias is essential for building fair and accurate models.
Training speed is a measure of computational performance, not bias. The total number of parameters describes model capacity or complexity. Splitting data into training and test sets is a data preparation step called train-test splitting. None of these relates to the concept of systematic prediction error.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 33: aif-q458

Match each machine learning approach or technique on the left with the scenario on the right that best represents it. Pair each left item with exactly one right item.

- **A.** Supervised learning (classification)
- **B.** Unsupervised learning (clustering)
- **C.** Reinforcement learning
- **D.** Supervised learning (regression)

**Match targets:**

- **1.** Grouping retail customers into segments based on purchasing behavior when no predefined labels exist
- **2.** Predicting the dollar amount of a house sale from features such as size and location
- **3.** Training a warehouse robot to navigate by rewarding successful moves and penalizing collisions
- **4.** Labeling incoming emails as spam or not spam using a dataset of previously labeled emails

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A → 4 (Labeling incoming emails as spam or not spam using a dataset of previously labeled emails); B → 1 (Grouping retail customers into segments based on purchasing behavior when no predefined labels exist); C → 3 (Training a warehouse robot to navigate by rewarding successful moves and penalizing collisions); D → 2 (Predicting the dollar amount of a house sale from features such as size and location)

**Explanation:**

Supervised classification (A) learns from labeled examples to assign inputs to discrete categories, which fits sorting emails into spam or not spam using previously labeled emails (4). Unsupervised clustering (B) finds structure in unlabeled data, matching customer segmentation with no predefined labels (1); reinforcement learning (C) learns through rewards and penalties, matching the robot trained by trial and error (3); and supervised regression (D) predicts a continuous numeric value, matching the house sale price prediction (2).
The key distinction is the type of output and the supervision signal: classification produces a category, regression produces a number, and both require labeled data, while clustering needs no labels and reinforcement learning uses reward signals from interaction or recorded experience rather than ordinary labeled target pairs. A tempting error is to pair the house price scenario (2) with classification, but a continuous dollar amount is a numeric prediction, which makes it regression, not a discrete class.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.1
- Format: matching
- Services: None listed
- Last verified by source: 2026-06-13

---

## Task 1.2

Questions for this task: 47

### Question 34: aif-q007

A company needs to build models for several new but related tasks. Rather than training models from scratch, it wants to adapt existing pre-trained models. Which ML strategy meets this requirement?

- **A.** Increase the number of epochs
- **B.** Use transfer learning
- **C.** Decrease the number of epochs
- **D.** Use unsupervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use transfer learning

**Explanation:**

Transfer learning lets a company take a model already trained on one task and adapt it to new, related tasks, which reuses the knowledge captured in the pre-trained model and saves significant time and data compared to training from scratch.
Increasing the number of epochs simply trains a model for more passes over the data and does not provide a way to reuse an existing pre-trained model. Decreasing the number of epochs reduces training passes and likewise has nothing to do with adapting pre-trained models for new tasks. Unsupervised learning finds patterns in unlabeled data but is a learning approach rather than a strategy for reusing and adapting an already trained model.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 35: aif-q014

A startup is building an educational quiz app that asks players questions such as: "A bag holds six red, four green, and three yellow marbles. What is the probability of drawing a green marble?" Which approach satisfies this requirement with the LEAST operational overhead?

- **A.** Train a supervised learning regression model to predict the probability
- **B.** Build an unsupervised learning model to estimate the probability density
- **C.** Apply reinforcement learning to train a model that returns the probability
- **D.** Write simple code that calculates the probability using basic arithmetic rules

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Write simple code that calculates the probability using basic arithmetic rules

**Explanation:**

The probability here is a deterministic calculation of favorable outcomes divided by total outcomes, so a few lines of code applying basic arithmetic produce an exact answer with no data to gather, no model to train, and no endpoint to host, giving the least operational overhead.
The three machine learning options all stand up an unnecessary pipeline of data collection, training, tuning, and hosting for a problem that already has a known closed-form answer. Beyond that shared waste, supervised regression would only approximate a value that can be computed exactly; unsupervised learning is meant to uncover structure in unlabeled data, which is irrelevant when the formula is known; and reinforcement learning is designed for sequential decision-making guided by rewards in an environment, not for answering a static arithmetic question.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 36: aif-q020

A company wants to use AI to protect its application from threats by checking whether an incoming IP address comes from a suspicious source. Which solution meets this requirement?

- **A.** Build a speech recognition system
- **B.** Develop an anomaly detection system
- **C.** Create a fraud forecasting system
- **D.** Set up a named entity recognition system using Natural Language Processing (NLP)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Develop an anomaly detection system

**Explanation:**

An anomaly detection system learns what normal traffic and behavior look like and flags activity that deviates from those patterns, so it can pick out IP addresses that behave suspiciously or differ from legitimate sources, directly meeting the goal of protecting the application from threats.
A speech recognition system converts spoken audio into text and has nothing to do with analyzing IP addresses. A named entity recognition system based on NLP extracts entities such as names and places from text, not network threat signals. A fraud forecasting system predicts future fraud volumes or trends rather than flagging an individual suspicious IP as it arrives.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 37: aif-q031

A wildlife researcher has a large collection of animal photos and wants to automatically identify and categorize the animals in each image without manual effort. Which strategy meets this requirement?

- **A.** Named entity recognition
- **B.** Inpainting
- **C.** Object detection
- **D.** Anomaly detection

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Object detection

**Explanation:**

Object detection is a Computer Vision technique that automatically finds and classifies the objects within an image, so it can locate each animal in a photo and assign it to a category without manual effort, which is exactly what the researcher needs.
Anomaly detection flags data points that deviate from normal patterns, not the contents of an image. Named entity recognition is a Natural Language Processing (NLP) technique that extracts entities such as names and places from text rather than from photos. Inpainting is a generative Computer Vision technique that fills in missing or removed regions of an image, rather than identifying and categorizing what is in it.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 38: aif-q045

A hotel chain wants to read sentiment from written guest reviews. Which two AWS services can meet this requirement?

- **A.** Amazon Comprehend
- **B.** Amazon Polly
- **C.** Amazon Bedrock
- **D.** Amazon Lex
- **E.** Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Comprehend; C. Amazon Bedrock

**Explanation:**

Amazon Comprehend is a Natural Language Processing (NLP) service with built-in sentiment analysis that can determine whether text is positive, negative, neutral, or mixed, making it well suited to analyze written reviews. Amazon Bedrock provides access to foundation models that can also classify the sentiment of text through prompting.
Amazon Polly is a text-to-speech service that converts written text into lifelike spoken audio, which is the opposite of analyzing text content. Amazon Lex is a service for building conversational chatbots and voice interfaces, not for analyzing the sentiment of existing text. Amazon Rekognition is a Computer Vision service that analyzes images and video for objects, faces, and scenes, and cannot process written text for sentiment.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Comprehend, Amazon Bedrock, Amazon Polly, Amazon Lex, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 39: aif-q068

A recruitment agency receives a growing volume of resumes as PDF files that it can no longer review manually. It needs an automated way to convert these PDF resumes into plain text for further processing. Which AWS service meets this requirement?

- **A.** Amazon Lex
- **B.** Amazon Textract
- **C.** Amazon Transcribe
- **D.** Amazon Personalize

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Textract

**Explanation:**

Amazon Textract automatically extracts text and data from scanned documents and PDFs, so it can turn the resumes into plain text for downstream processing.
Amazon Lex builds conversational chatbots and voice interfaces. Amazon Transcribe converts speech audio into text rather than reading documents. Amazon Personalize generates real-time recommendations. None of these extract text from PDF files.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Textract, Amazon Lex, Amazon Transcribe, Amazon Personalize
- Last verified by source: 2026-06-02

---

### Question 40: aif-q073

A company recovered a set of text documents after a database error, but some words are missing. It wants an ML model that can predict the most likely word for each gap. Which type of model is suitable?

- **A.** Topic modeling
- **B.** Clustering models
- **C.** BERT-based models
- **D.** Prescriptive analytics models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. BERT-based models

**Explanation:**

BERT-based models are transformer language models trained with masked language modeling, so they predict a missing token by drawing on the context that surrounds it on both sides, which is exactly what suggesting words to fill the gaps requires.
Topic modeling discovers the themes present across a collection of documents but does not predict individual missing words. Clustering models group similar items together in an unsupervised way and produce no word-level predictions. Prescriptive analytics models recommend which action to take given a predicted outcome and have nothing to do with text completion.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 41: aif-q092

A software company wants to use AI to boost its developers' productivity when writing software. Which solution meets this requirement?

- **A.** Use a binary classification model to generate code reviews
- **B.** Use a clustering algorithm to group similar code snippets together
- **C.** Use a Natural Language Processing (NLP) tool to generate code
- **D.** Use a forecasting model to predict future numbers of code defects

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Use a Natural Language Processing (NLP) tool to generate code

**Explanation:**

Natural Language Processing (NLP) tools, which underpin generative AI coding assistants, can turn plain-language descriptions into working code, autocomplete snippets, and write whole blocks of code, automating repetitive work and speeding up development, so they directly increase developer productivity.
A binary classification model only assigns inputs to one of two categories, so it cannot generate code or reviews. A clustering algorithm groups similar items together but produces no new code. A forecasting model predicts future numeric values, such as defect counts over time, and likewise does nothing to help developers write code faster.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 42: aif-q103

An AI practitioner needs to predict which species each flower belongs to, using its petal length, petal width, sepal length, and sepal width. Which algorithm meets this requirement?

- **A.** Linear regression
- **B.** K-nearest neighbors (k-NN)
- **C.** K-means
- **D.** Autoregressive Integrated Moving Average (ARIMA)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. K-nearest neighbors (k-NN)

**Explanation:**

K-nearest neighbors (k-NN) is a supervised classification algorithm that labels a new data point by the majority class of its closest neighbors in feature space, so it fits assigning a flower to a species from its petal and sepal measurements.
K-means is an unsupervised clustering algorithm that groups unlabeled data rather than assigning known categories. Autoregressive Integrated Moving Average (ARIMA) is a time-series forecasting method for sequential data ordered over time. Linear regression predicts a continuous numeric value, not a category.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 43: aif-q120

A manufacturing company uses AI to inspect products and find any damages or defects. Which type of AI application is the company using?

- **A.** Recommendation system
- **B.** Natural language processing (NLP)
- **C.** Computer vision
- **D.** Image processing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Computer vision

**Explanation:**

Computer Vision is the field of AI that enables machines to interpret and analyze visual information from images and videos, making it the technology behind automated inspection systems that detect product damage or defects on a production line.
A recommendation system analyzes user behavior and preferences to suggest relevant products or content, which is unrelated to visual defect detection. Natural Language Processing (NLP) focuses on understanding and generating human language in text or speech, not on analyzing images. Image processing refers to low-level manipulation of images such as resizing, filtering, or enhancing them; while it can be part of a vision pipeline, it does not involve the AI-driven interpretation and classification required for defect detection.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 44: aif-q130

A nonprofit is building an accessible voice assistant. It must convert a spoken question to text and read the generated answer aloud. Which pair of AWS services supplies those two speech functions?

- **A.** Amazon Transcribe and Amazon Polly
- **B.** Amazon Comprehend and Amazon Translate
- **C.** Amazon Lex and Amazon Textract
- **D.** Amazon Rekognition and Amazon Kendra

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Transcribe and Amazon Polly

**Explanation:**

Amazon Transcribe converts speech to text. Amazon Polly converts text to speech. Together they cover both directions required by the stem.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe, Amazon Polly
- Last verified by source: 2026-11-03

---

### Question 45: aif-q135

A property company needs a baseline model that predicts sale price and shows a directly interpretable linear contribution for each numeric feature. Which algorithm best fits?

- **A.** Linear regression
- **B.** k-means clustering
- **C.** Decision tree classification
- **D.** Association-rule mining

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Linear regression

**Explanation:**

Linear regression predicts a continuous value as a weighted linear combination of features. Its coefficients provide the requested direct linear interpretation. The other options do not meet both requirements.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 46: aif-q181

A bank wants to label every credit card transaction as either fraudulent or legitimate based on its transaction data. Which type of ML model meets this requirement?

- **A.** Regression
- **B.** Binary classification
- **C.** Multi-class classification
- **D.** Diffusion

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Binary classification

**Explanation:**

Binary classification predicts which of exactly two categories an input belongs to, so it is the right model type for labeling each transaction as one of two outcomes, fraudulent or legitimate, based on its features.
Multi-class classification assigns inputs to one of three or more categories, which is unnecessary when there are only two possible outcomes. Regression predicts continuous numeric values rather than discrete categories. Diffusion models are generative models that create new content such as images, not models that classify transactions.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 47: aif-q182

A medical clinic wants doctors to dictate their clinical notes and have the audio automatically converted into text. Which AWS service meets this requirement?

- **A.** Amazon Comprehend
- **B.** Amazon Transcribe
- **C.** Amazon Polly
- **D.** Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Transcribe

**Explanation:**

Amazon Transcribe is the managed AI service that converts speech into text, so it can turn doctors' dictated clinical notes into written text, which meets the requirement.
Amazon Polly does the reverse, converting text into speech. Amazon Rekognition analyzes images and video. Amazon Comprehend extracts insights such as entities and sentiment from text that already exists, but it does not convert speech to text.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe, Amazon Comprehend, Amazon Polly, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 48: aif-q183

Which type of AI model is built to predict continuous numeric values?

- **A.** Transformer
- **B.** Multi-modal
- **C.** Diffusion
- **D.** Regression

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Regression

**Explanation:**

Regression is a supervised learning technique designed to predict continuous numerical values by learning the relationship between input features and a numeric output, making it the appropriate model type for tasks such as forecasting sales figures, estimating house prices, or predicting temperatures.
Diffusion models are generative models that learn to create new content such as images or audio by gradually denoising random noise, and are not used for numeric prediction tasks. Transformers are a neural network architecture that processes sequential data using attention mechanisms and form the basis of large language models, but the architecture itself is not a model type associated with numeric prediction. Multi-modal models are designed to process and generate multiple types of data such as text, images, and audio together, which describes the input and output modalities of a model rather than its predictive function.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 49: aif-q216

A studio that produces animated films wants to automatically generate subtitles for the dialogue in its videos. Which AWS service meets this requirement?

- **A.** Amazon Transcribe
- **B.** Amazon Translate
- **C.** Amazon Polly
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Transcribe

**Explanation:**

Amazon Transcribe uses automatic speech recognition to convert spoken audio into time-stamped text and can output caption files, so it can generate the subtitles for the dialogue in the studio's animated videos.
Amazon Translate converts text from one language to another but does not turn audio into text, so it cannot produce subtitles on its own. Amazon Polly performs the opposite task, synthesising speech from written text rather than transcribing speech. Amazon Comprehend is a natural language processing service that extracts insights such as sentiment and entities from existing text and does not create transcripts from audio.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe, Amazon Translate, Amazon Polly, Amazon Comprehend
- Last verified by source: 2026-06-01

---

### Question 50: aif-q217

An online retailer wants to divide its customers into segments based on their buying behavior and preferences so it can tailor the app experience to each segment. Which ML technique should it use?

- **A.** Classification
- **B.** Regression
- **C.** Clustering
- **D.** Content Generation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Clustering

**Explanation:**

Clustering is an unsupervised technique that automatically groups customers with similar purchase histories and preferences into segments without any predefined labels, which is exactly what the retailer needs in order to personalize the experience for each segment.
Classification is a supervised technique that assigns items to predefined categories, which would require the segments to be labeled in advance, but they are not. Regression is a supervised technique that predicts a continuous numeric value such as expected spend, not groups of similar customers. Content generation produces new content such as text or images and does not segment customers at all.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 51: aif-q228

A business wants to automatically read incoming support emails and route each one into a topic such as billing, technical issues, or account changes. Which AI concept does this scenario represent?

- **A.** Speech Recognition
- **B.** Natural Language Processing (NLP)
- **C.** Computer Vision
- **D.** Forecasting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Natural Language Processing (NLP)

**Explanation:**

Reading support emails and routing each one into a topic is a Natural Language Processing task, specifically text classification, because it requires interpreting human language in text and assigning it to a predefined category.
Speech Recognition converts spoken audio into text and deals with the spoken word rather than analyzing and categorizing existing written text. Computer Vision interprets images and video rather than language, so it does not apply to email content. Forecasting predicts future numerical values from historical data, which is unrelated to sorting written messages by topic.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 52: aif-q233

An online learning platform publishes its course materials in English and wants to make the same content available to learners in several other languages. Which solution meets these requirements?

- **A.** Add Amazon Transcribe to the platform
- **B.** Use the real-time translation feature of Amazon Translate
- **C.** Add Amazon Personalize to the platform
- **D.** Use the real-time document processing feature of Amazon Textract

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use the real-time translation feature of Amazon Translate

**Explanation:**

Amazon Translate provides fast, high-quality language translation of text, making it the right choice for automatically converting course materials from English into multiple other languages.
Amazon Transcribe is an automatic speech recognition service that converts spoken audio into text, which does not translate content between languages. Amazon Personalize generates personalized recommendations based on user behavior, which is unrelated to translating content. Amazon Textract extracts text and structured data from scanned documents and images, which addresses document data extraction rather than language translation.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe, Amazon Translate, Amazon Personalize, Amazon Textract
- Last verified by source: 2026-06-01

---

### Question 53: aif-q236

A documentary filmmaker wants to reach a wider audience by automatically adding subtitles and voice-overs in multiple languages to their films. Which two steps together meet this requirement?

- **A.** Use Amazon Polly to generate voice-overs in multiple languages
- **B.** Use Amazon Transcribe and Amazon Translate to produce subtitles in multiple languages
- **C.** Use Amazon Translate to generate voice-overs in multiple languages
- **D.** Use Amazon Textract and Amazon Translate to produce subtitles in multiple languages

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Amazon Polly to generate voice-overs in multiple languages; B. Use Amazon Transcribe and Amazon Translate to produce subtitles in multiple languages

**Explanation:**

Amazon Transcribe converts the film's spoken dialogue into text using automatic speech recognition, and Amazon Translate then renders that text into other languages to create multilingual subtitles. Amazon Polly is a text-to-speech service that turns the translated text into lifelike spoken audio, enabling the multilingual voice-overs the filmmaker needs.
The option pairing Amazon Textract with Amazon Translate is incorrect because Textract extracts text from scanned documents and images using optical character recognition, not from spoken audio in video files. The option using only Amazon Translate for voice-overs is incorrect because Translate converts text between languages but outputs text, not audio; generating spoken voice-overs requires Amazon Polly to synthesize speech from the translated text.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe, Amazon Translate, Amazon Polly, Amazon Textract
- Last verified by source: 2026-06-02

---

### Question 54: aif-q241

An existing Amazon SageMaker AI customer wants workflows in which staff review predictions from its ML models. The customer needs configurable confidence thresholds that route selected predictions to human review. Which eligible existing-customer capability meets these requirements?

- **A.** Amazon SageMaker Ground Truth
- **B.** Amazon Inspector
- **C.** Amazon Augmented AI (Amazon A2I)
- **D.** AWS Audit Manager

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Augmented AI (Amazon A2I)

**Explanation:**

For an eligible existing customer, Amazon Augmented AI (Amazon A2I) can add human review to ML workflows and route selected predictions according to configured conditions, including confidence thresholds. Amazon A2I is no longer open to new customers.
Amazon SageMaker Ground Truth supports data labeling rather than this prediction-review workflow. Amazon Inspector scans workloads for vulnerabilities, and AWS Audit Manager helps collect audit evidence.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Augmented AI (Amazon A2I), Amazon SageMaker Ground Truth, Amazon Inspector, AWS Audit Manager
- Last verified by source: 2026-06-01

---

### Question 55: aif-q256

An online retailer wants to divide its customers into groups based on their demographics and purchasing behavior. Which algorithm should it use to meet this requirement?

- **A.** Decision tree
- **B.** Support vector machine
- **C.** K-nearest neighbours (k-NN)
- **D.** K-means

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. K-means

**Explanation:**

K-means is an unsupervised clustering algorithm that partitions data points into a chosen number of groups based on similarity, so it naturally segments customers by shared demographics and buying patterns without needing labeled examples.
K-nearest neighbours (k-NN), Decision tree, and Support vector machine are all supervised algorithms that require labeled training data to predict a known target or class, so they suit classification or regression rather than discovering natural groupings in unlabeled customer data.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 56: aif-q268

A support team uses sentiment analysis to determine the mood expressed in customer feedback. Sentiment analysis is a subset of which broader field of AI?

- **A.** Natural Language Processing (NLP)
- **B.** Computer Vision
- **C.** Time Series Forecasting
- **D.** Speech Recognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Natural Language Processing (NLP)

**Explanation:**

Sentiment analysis is a Natural Language Processing (NLP) task. NLP is the field of AI focused on enabling machines to understand, interpret, and derive meaning from human language, and detecting the emotional tone of text is one of its core applications.
Computer Vision deals with interpreting images and video rather than language. Speech Recognition converts spoken audio into text and does not itself analyze opinion or sentiment. Time Series Forecasting predicts future numeric values from sequential historical data and is unrelated to understanding language.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 57: aif-q270

A SaaS company collects large volumes of free-form customer feedback and wants to analyze its sentiment. Which solution meets this requirement?

- **A.** Use a regression algorithm to sort the feedback into predefined categories
- **B.** Use a recommendation engine to detect user sentiment
- **C.** Use a large language model (LLM) to perform Natural Language Processing (NLP) for sentiment analysis
- **D.** Use a time-series algorithm to predict user sentiment from past feedback

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Use a large language model (LLM) to perform Natural Language Processing (NLP) for sentiment analysis

**Explanation:**

A large language model can apply Natural Language Processing (NLP) to read unstructured text and determine whether the sentiment is positive, negative, or neutral, which suits large volumes of free-form feedback.
A regression algorithm predicts numeric values, not sentiment from text. A recommendation engine suggests items based on behavior. A time-series algorithm forecasts values over time. None of these analyzes the sentiment of unstructured text.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 58: aif-q281

A manufacturer wants to train an ML model that flags unusual readings in its equipment sensor data, but it has no labeled examples to learn from. Which ML method meets this requirement?

- **A.** Decision tree
- **B.** Autoencoders
- **C.** Linear regression
- **D.** Logistic regression

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Autoencoders

**Explanation:**

Autoencoders are an unsupervised method that learn to reconstruct normal patterns in the data; readings that produce a large reconstruction error stand out as anomalies, so the technique can detect abnormal sensor behavior without any labeled training data.
Decision tree, linear regression, and logistic regression all fail for the same reason: they are supervised methods that require labeled examples to learn from, which the company does not have. Linear regression predicts continuous values and the other two perform classification, but none can be trained for anomaly detection on unlabeled data.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 59: aif-q286

A music streaming app wants to suggest songs to each listener based on their listening history. Which AWS service meets this requirement?

- **A.** Amazon Personalize
- **B.** Amazon Transcribe
- **C.** Amazon Polly
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Personalize

**Explanation:**

Amazon Personalize is a fully managed ML service that delivers real-time personalized recommendations by analyzing each user's history, interactions, and behavior, making it purpose-built for use cases such as suggesting songs on a music streaming app.
Amazon Transcribe is an automatic speech recognition service that converts audio and speech into text transcripts and plays no role in analyzing listening history or producing recommendations. Amazon Polly is a text-to-speech service that synthesises written text into lifelike speech and cannot generate recommendations. Amazon Comprehend is a Natural Language Processing (NLP) service that extracts insights such as sentiment, entities, and key phrases from text and is not designed to produce personalized recommendations.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Personalize, Amazon Transcribe, Amazon Polly, Amazon Comprehend
- Last verified by source: 2026-06-02

---

### Question 60: aif-q308

A photo-sharing service needs to transpose and rotate large batches of images using simple numerical transformations. Which solution is MOST operationally efficient?

- **A.** Build a deep neural network that takes the images as input
- **B.** Use an Amazon Bedrock large language model (LLM) with a high temperature
- **C.** Create an AWS Lambda function to perform the transformations
- **D.** Use AWS Glue Data Quality to correct each image

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Create an AWS Lambda function to perform the transformations

**Explanation:**

An AWS Lambda function can run straightforward numerical image operations such as transposing and rotating at scale without training or hosting any model, which is the most operationally efficient approach.
Building a deep neural network is unnecessary effort for deterministic transformations. An Amazon Bedrock LLM generates text and cannot transform images. AWS Glue Data Quality validates and cleans data, not rotate images.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: AWS Lambda, Amazon Bedrock, AWS Glue
- Last verified by source: 2026-06-02

---

### Question 61: aif-q315

A company wants to automatically analyze customer feedback written as text. Which AWS service is best suited for this Natural Language Processing (NLP) task?

- **A.** Amazon SageMaker AI
- **B.** Amazon Comprehend
- **C.** Amazon Polly
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Comprehend

**Explanation:**

Amazon Comprehend is a managed Natural Language Processing service that analyzes text to extract sentiment, key phrases, entities, and language, making it the purpose-built choice for analyzing customer feedback.
Amazon SageMaker AI is a platform for building, training, and deploying custom ML models, which could perform NLP but requires significant development effort rather than providing ready-made NLP capabilities. Amazon Polly is a text-to-speech service that converts written text into lifelike speech, which is the opposite of analyzing text. Amazon Transcribe is an automatic speech recognition service that converts spoken audio into text, and does not analyze the meaning or sentiment of that text.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon Comprehend, Amazon Polly, Amazon Transcribe
- Last verified by source: 2026-06-02

---

### Question 62: aif-q327

A company wants to generate spoken audio narration from its written articles. Which AWS service is the best fit?

- **A.** Amazon Transcribe
- **B.** Amazon Polly
- **C.** Amazon Translate
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Polly

**Explanation:**

Amazon Polly is a text-to-speech service that turns written text into lifelike spoken audio, which is exactly what generating narration from articles requires.
Amazon Transcribe does the reverse, converting speech audio into text. Amazon Translate converts text from one language into another. Amazon Comprehend is a Natural Language Processing (NLP) service that extracts insights such as sentiment and entities from text, but it does not produce audio.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Polly, Amazon Transcribe, Amazon Translate, Amazon Comprehend
- Last verified by source: 2026-06-02

---

### Question 63: aif-q333

Which of these is NOT a typical use case for AI or ML?

- **A.** Fraud detection
- **B.** Manual record keeping
- **C.** Speech recognition
- **D.** Recommendation systems

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Manual record keeping

**Explanation:**

Manual record keeping is not a typical AI/ML use case because it is a routine, deterministic clerical task that does not involve learning from data or making predictions.
Fraud detection, recommendation systems, and speech recognition are all established AI/ML applications that rely on machine learning models to identify patterns, make predictions, or interpret unstructured data such as transactions, user behavior, or audio.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 64: aif-q345

Which AWS services can be used for document analysis and information extraction?

- **A.** Amazon Textract
- **B.** Amazon Comprehend
- **C.** Amazon Polly
- **D.** Amazon Translate
- **E.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Textract; B. Amazon Comprehend

**Explanation:**

Amazon Textract extracts text and structured data such as forms and tables directly from documents and images using optical character recognition, making it the primary service for the document analysis layer. Amazon Comprehend then applies natural language processing to extracted text to identify entities, key phrases, sentiment, and other insights, enabling information extraction from the content of documents.
Amazon Polly converts text to synthesised speech, Amazon Translate performs language translation between languages, and Amazon Transcribe converts spoken audio into text transcripts. None of these services are designed for document analysis or information extraction.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Textract, Amazon Comprehend, Amazon Polly, Amazon Translate, Amazon Transcribe
- Last verified by source: 2026-06-01

---

### Question 65: aif-q016

A telecom support team wants transcripts, detected call issues, sentiment, and call categories from recorded customer-agent calls. Which AWS capability best fits?

- **A.** Amazon Comprehend custom classification
- **B.** Amazon Lex
- **C.** Amazon Transcribe Call Analytics
- **D.** Amazon SageMaker Model Monitor

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Transcribe Call Analytics

**Explanation:**

Amazon Transcribe Call Analytics combines speech-to-text with call-specific analytics such as issue detection, sentiment, and categorization. Standard transcription alone would not satisfy the analytics requirements.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Transcribe Call Analytics, Amazon Comprehend, Amazon Lex, Amazon SageMaker Model Monitor
- Last verified by source: 2026-11-03

---

### Question 66: aif-q125

An online store wants to tailor its recommendations to each individual shopper. Which AWS service fits?

- **A.** Amazon Comprehend
- **B.** Amazon Personalize
- **C.** Amazon Kendra
- **D.** Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Personalize

**Explanation:**

Amazon Personalize builds machine learning models from user behavior to deliver individualized recommendations, which is exactly what tailoring results per shopper requires.
Amazon Comprehend analyzes text, Amazon Kendra provides enterprise search, and Amazon Rekognition analyzes images and video; none personalizes recommendations per user.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Personalize, Amazon Comprehend, Amazon Kendra, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 67: aif-q150

A company needs to produce its product descriptions in several languages automatically. Which AWS service does this?

- **A.** Amazon Polly
- **B.** Amazon Translate
- **C.** Amazon Comprehend
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Translate

**Explanation:**

Amazon Translate uses neural machine translation to convert text between languages automatically, which is what generating product descriptions in multiple languages requires.
Amazon Polly converts text to speech, Amazon Comprehend extracts insights from text, and Amazon Transcribe converts speech to text; none translates text.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Translate, Amazon Polly, Amazon Comprehend, Amazon Transcribe
- Last verified by source: 2026-06-02

---

### Question 68: aif-q153

A hospital has unstructured clinical notes and wants to extract conditions, medications, dosages, and relationships for a downstream summary template. Which service fits?

- **A.** Amazon Personalize
- **B.** Amazon Comprehend Medical
- **C.** Amazon Textract
- **D.** Amazon Kendra

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Comprehend Medical

**Explanation:**

Amazon Comprehend Medical extracts medical entities and relationships from unstructured clinical text. A separate application can use those fields to produce the summary.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Comprehend Medical, Amazon Personalize, Amazon Textract, Amazon Kendra
- Last verified by source: 2026-11-03

---

### Question 69: aif-q245

Which two capabilities make Amazon Kendra valuable for enterprise search applications?

- **A.** Managed relational database hosting
- **B.** Natural language understanding
- **C.** Video transcoding
- **D.** Semantic search
- **E.** Infrastructure monitoring

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Natural language understanding; D. Semantic search

**Explanation:**

Amazon Kendra provides natural language understanding that interprets user intent and semantic search that returns results by meaning and context, which together make it effective for enterprise search.
Managed relational database hosting, video transcoding, and infrastructure monitoring are unrelated tasks that Kendra does not perform.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Kendra
- Last verified by source: 2026-06-02

---

### Question 70: aif-q274

An online learning company has large volumes of educational material and wants enterprise search across it. Which AWS service fits?

- **A.** Amazon Polly
- **B.** Amazon Kendra
- **C.** Amazon Textract
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Kendra

**Explanation:**

Amazon Kendra is an intelligent enterprise search service that searches large volumes of unstructured content, such as educational materials, which fits this need.
Amazon Polly converts text to speech, Amazon Textract extracts text from documents, and Amazon Comprehend analyzes text for insights; none provides enterprise search.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Kendra, Amazon Polly, Amazon Textract, Amazon Comprehend
- Last verified by source: 2026-06-02

---

### Question 71: aif-q147

A company wants to find harmful language in the comments on social media posts and does not plan to use labeled data to train a model. Which approach should the company use?

- **A.** Use Amazon Rekognition moderation
- **B.** Use Amazon Comprehend toxicity detection
- **C.** Use Amazon SageMaker built-in algorithms to train a model
- **D.** Use Amazon Polly to monitor the comments

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use Amazon Comprehend toxicity detection

**Explanation:**

Amazon Comprehend provides pre-trained natural language processing, including toxicity detection, so it can identify harmful language in comments without the company having to label data or train a model.
Amazon Rekognition moderates images and video, not text. Amazon SageMaker built-in algorithms would require labeled data to train a model. Amazon Polly converts text to speech and does not analyze text for harmful content.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Comprehend, Amazon Rekognition, Amazon Polly, Amazon SageMaker AI
- Last verified by source: 2026-06-02

---

### Question 72: aif-q347

A bank is choosing a model for loan decisions. The approved gradient-boosting model can be analyzed with feature-attribution methods, while the proposed large language model produces free-form text. Which requirement most favors the approved model?

- **A.** A structured prediction with feature-attribution analysis
- **B.** Multilingual conversation
- **C.** Marketing-copy generation
- **D.** Open-ended summarization

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. A structured prediction with feature-attribution analysis

**Explanation:**

The structured model supports the requested prediction and feature-attribution analysis. Gradient boosting is not fully self-explanatory, so the bank must validate the explanation method and document its limits.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 73: aif-q348

A healthcare startup wants to deploy a diagnostic support tool that must run on devices with limited memory and no internet connection. Which constraint most strongly favors a traditional ML model over a foundation model?

- **A.** The need for real-time image generation
- **B.** Operational constraints on memory and connectivity
- **C.** The requirement for multilingual chat support
- **D.** The desire for open-ended text summarization

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Operational constraints on memory and connectivity

**Explanation:**

Traditional ML models are typically much smaller and can run efficiently on resource-constrained edge devices without requiring cloud connectivity, making them the appropriate choice when operational constraints such as limited memory and offline operation apply.
Real-time image generation, multilingual chat support, and open-ended text summarization are capabilities that favor foundation models, not constraints that would lead a team to choose traditional ML.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 74: aif-q349

A logistics company processes thousands of delivery route requests each day. Which benefit does AI/ML provide that a purely rule-based system cannot easily achieve?

- **A.** Deterministic outputs for every input
- **B.** Ability to scale and adapt to changing patterns in the data
- **C.** Guaranteed correctness without validation
- **D.** Elimination of all computational costs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Ability to scale and adapt to changing patterns in the data

**Explanation:**

AI/ML systems learn patterns from data and can adapt as those patterns change over time, and they scale to handle large volumes of requests by generalizing from examples rather than requiring manually coded rules for every scenario, which is a key advantage over rule-based systems.
Deterministic outputs are actually a characteristic of rule-based systems, not a unique benefit of AI/ML. No system can guarantee correctness without validation. AI/ML does not eliminate computational costs; in fact, training and inference often require significant compute resources.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 75: aif-q350

A retailer wants to personalize product recommendations for millions of customers. Why is AI/ML more suitable than a manual approach for this task?

- **A.** AI/ML removes the need for any data
- **B.** AI/ML can process large volumes of data and identify patterns humans cannot easily detect
- **C.** AI/ML guarantees 100% accuracy on every prediction
- **D.** AI/ML eliminates the need for computing infrastructure

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. AI/ML can process large volumes of data and identify patterns humans cannot easily detect

**Explanation:**

AI/ML excels at processing large volumes of customer data, identifying subtle patterns and preferences, and generating personalized recommendations at a scale that would be impractical for humans to achieve manually, which is why it adds value for this use case.
AI/ML requires data to learn from, so it does not remove the need for any data. No system guarantees 100% accuracy. AI/ML requires computing infrastructure for training and inference, so it does not eliminate infrastructure needs.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 76: aif-q354

An enterprise is modernizing legacy applications and wants an AWS service that helps transform and migrate workloads using AI-assisted tooling. Which AWS service meets this requirement?

- **A.** AWS Transform
- **B.** Amazon Textract
- **C.** Amazon Translate
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. AWS Transform

**Explanation:**

AWS Transform is an AWS service that uses AI-assisted tooling to help enterprises transform and modernize their legacy applications and workloads, which directly meets the company's requirement.
Amazon Textract extracts text and data from documents. Amazon Translate converts text between languages. Amazon Transcribe converts speech to text. None of these is designed for application modernization and transformation.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: AWS Transform, Amazon Textract, Amazon Translate, Amazon Transcribe
- Last verified by source: 2026-06-03

---

### Question 77: aif-q360

A contact center wants to build a voice-enabled virtual agent that understands customer requests and routes calls to the appropriate department. Which AWS service meets this requirement?

- **A.** Amazon Polly
- **B.** Amazon Lex
- **C.** Amazon Translate
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Lex

**Explanation:**

Amazon Lex is a service for building conversational interfaces using voice and text, enabling the contact center to create a virtual agent that understands spoken requests and can route calls based on customer intent.
Amazon Polly converts text to speech but does not understand or interpret spoken input. Amazon Translate converts text between languages. Amazon Comprehend extracts insights from text but does not build interactive conversational agents.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Lex, Amazon Polly, Amazon Translate, Amazon Comprehend
- Last verified by source: 2026-06-03

---

### Question 78: aif-q361

A law firm has thousands of legal documents and wants employees to find relevant case law and contract clauses using natural language questions. Which type of AI application best addresses this need?

- **A.** Fraud Detection
- **B.** Knowledge Base
- **C.** Time Series Forecasting
- **D.** Anomaly Detection

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Knowledge Base

**Explanation:**

A knowledge base application uses AI to index, understand, and retrieve information from large document collections, allowing users to find relevant content by asking natural language questions, which is exactly what the law firm needs for searching legal documents.
Fraud detection identifies suspicious transactions or activities. Time series forecasting predicts future values from historical sequential data. Anomaly detection flags unusual patterns in data. None of these enables natural language search across document collections.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 79: aif-q364

A company wants an AI system that can autonomously research competitors, compile findings into a report, and email the summary to stakeholders without human intervention at each step. Which type of AI application best fits this requirement?

- **A.** Speech Recognition
- **B.** Image Classification
- **C.** Agentic AI
- **D.** Sentiment Analysis

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Agentic AI

**Explanation:**

Agentic AI can autonomously plan and execute multi-step workflows, such as researching information, compiling reports, and sending emails, without requiring human intervention at each step, which matches the company's requirement.
Speech recognition converts spoken audio to text. Image classification assigns labels to images. Sentiment analysis determines the emotional tone of text. None of these can autonomously orchestrate multi-step tasks across different systems.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 80: aif-q366

A retail chain wants to automatically detect and blur customer faces in its security camera footage before storing the recordings. Which AWS service meets this requirement?

- **A.** Amazon Textract
- **B.** Amazon Rekognition
- **C.** Amazon Comprehend
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Rekognition

**Explanation:**

Amazon Rekognition is a Computer Vision service that can detect, analyze, and identify faces in images and video, so it can locate customer faces in security footage for the company to blur before storage.
Amazon Textract extracts text and structured data from documents and images but does not detect faces. Amazon Comprehend is a Natural Language Processing service that analyzes text for sentiment, entities, and key phrases. Amazon Transcribe converts spoken audio into text. None of these provides facial detection in video.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.2
- Format: multiple choice
- Services: Amazon Rekognition, Amazon Textract, Amazon Comprehend, Amazon Transcribe
- Last verified by source: 2026-06-03

---

## Task 1.3

Questions for this task: 53

### Question 81: aif-q004

A manufacturer built a model that classifies photos of parts as defective or not. The team wants to know what proportion of the part images the model classified correctly. Which evaluation metric should they use?

- **A.** Mean absolute error (MAE)
- **B.** Number of training epochs
- **C.** Root mean squared error (RMSE)
- **D.** Accuracy

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Accuracy

**Explanation:**

Accuracy is the ratio of correct predictions to the total number of predictions, so it directly measures how many part images the model classified correctly, which is exactly what the team wants for this classification task.
Root mean squared error (RMSE) and mean absolute error (MAE) are regression metrics that quantify the difference between predicted and actual continuous values, so neither is suited to measuring classification correctness. Number of training epochs is a training configuration setting that controls how many passes the model makes over the data; it is not an evaluation metric at all.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 82: aif-q015

A company has deployed a model to production and wants a metric that reflects how efficiently the model operates at runtime. Which metric should it use?

- **A.** Average inference latency
- **B.** Customer satisfaction score (CSAT)
- **C.** Number of training examples
- **D.** Training time per epoch

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Average inference latency

**Explanation:**

Average inference latency captures how long the model takes to return a prediction once it is running, so it directly reflects the runtime efficiency of operating the model in production, where lower latency means faster, more efficient responses.
Customer satisfaction score (CSAT) measures how happy users are with a product or service, which is a business outcome rather than a measure of operational efficiency. Training time per epoch and number of training examples both relate to the training phase, namely how long training runs and how much data it uses, and say nothing about how efficiently the deployed model operates at inference time.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 83: aif-q027

A company has built an image classification model and wants a web application to call it for real-time predictions. The company needs a fully managed way to host the model and serve those predictions that scales automatically with demand. Which solution meets these requirements?

- **A.** Use Amazon SageMaker Serverless Inference to deploy the model
- **B.** Use Amazon CloudFront to deploy the model
- **C.** Use Amazon API Gateway to host the model and serve predictions
- **D.** Use AWS Batch to host the model and serve predictions

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Amazon SageMaker Serverless Inference to deploy the model

**Explanation:**

Amazon SageMaker Serverless Inference is a fully managed option that hosts a model and serves predictions on demand while automatically provisioning and scaling the underlying compute, so a web application can call the model for real-time predictions without the company managing capacity.
Amazon CloudFront is a content delivery network that caches and distributes content to reduce latency, and it cannot host an ML model or generate predictions. Amazon API Gateway creates and manages the API layer that fronts a backend, but it does not itself host a model or run inference and would still need a compute service behind it. AWS Batch runs batch computing jobs on managed compute and is suited to offline bulk processing rather than serving low-latency, on-demand predictions to a web application.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon CloudFront, AWS Batch
- Last verified by source: 2026-06-01

---

### Question 84: aif-q056

An electronics company wants to forecast customer demand for its memory products. Its team has no coding skills and no knowledge of ML algorithms, yet needs to build a data-driven predictive model that draws on both internal and external data. Which solution meets these requirements?

- **A.** Import the data into Amazon SageMaker Data Wrangler and build the forecasting models using Amazon SageMaker AI built-in algorithms
- **B.** Import the data into Amazon SageMaker Canvas and build the forecasting models in Canvas
- **C.** Store the data in Amazon S3 and build the forecasting models using Amazon SageMaker AI built-in algorithms
- **D.** Import the data into Amazon SageMaker Data Wrangler and build the forecasting models by writing custom training code

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Import the data into Amazon SageMaker Canvas and build the forecasting models in Canvas

**Explanation:**

Amazon SageMaker Canvas is a no-code service that lets business users import data and build ML models and generate predictions through a visual point-and-click interface, without writing code or understanding ML algorithms, which is exactly what a team with no coding or ML experience needs to forecast demand.
The other options all require technical skills the team does not have. Using Amazon SageMaker AI built-in algorithms, whether the data is stored in Amazon S3 or prepared in Amazon SageMaker Data Wrangler, still involves coding to build and train the models, and writing custom training code clearly does too. Amazon SageMaker Data Wrangler is also focused on data preparation rather than no-code model building, so none of these meets the no-code requirement.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Canvas, Amazon SageMaker Data Wrangler, Amazon SageMaker AI, Amazon S3
- Last verified by source: 2026-06-02

---

### Question 85: aif-q059

A model classifies images into several dog breeds. Which artifact shows the count of predictions for every actual-class and predicted-class pair?

- **A.** A multiclass confusion matrix
- **B.** A feature correlation matrix
- **C.** R-squared
- **D.** Mean squared error

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. A multiclass confusion matrix

**Explanation:**

A multiclass confusion matrix has one row and column per class and shows which breeds the model confuses. It is an evaluation artifact rather than a scalar metric.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 86: aif-q072

A data science team has just gathered a new dataset and is examining it by calculating summary statistics, plotting charts, and building a correlation matrix. Which stage of the ML pipeline does this describe?

- **A.** Model training
- **B.** Exploratory data analysis
- **C.** Data collection
- **D.** Feature engineering

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Exploratory data analysis

**Explanation:**

Exploratory data analysis is the stage where a team summarizes a dataset through statistics, visualisations, and correlation matrices to understand its structure, distribution, and relationships before any modeling begins, which is exactly what the team is doing.
Model training is a later stage where an algorithm learns patterns from prepared data, not where the raw dataset is examined. Data collection is the earlier stage of gathering the raw data; although the data was just gathered, the activities described are about analyzing it rather than collecting it. Feature engineering creates or selects input variables to improve model performance, which happens after the data is understood.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 87: aif-q117

A restaurant chain wants to build an ML model to cut daily food waste and increase revenue, and it needs the model's accuracy to keep improving over time. Which solution meets these requirements?

- **A.** Use Amazon Personalize and refine it with historical data only
- **B.** Use Amazon Rekognition to improve the model
- **C.** Use Amazon SageMaker AI and retrain it on newer data
- **D.** Use Amazon CloudWatch to examine customer orders

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Use Amazon SageMaker AI and retrain it on newer data

**Explanation:**

Amazon SageMaker AI is a fully managed ML platform that supports the complete model development lifecycle, including building, training, and deploying models. Retraining on newer data lets a new model version incorporate recent patterns in food demand and waste. The team must evaluate and approve that version before deployment; retraining does not mean the production model learns continuously.
Amazon Personalize delivers personalized product and content recommendations and is not a general-purpose platform for training custom regression or forecasting models; relying on historical data only would also stop the model adapting to recent changes. Amazon CloudWatch is a monitoring and observability service for metrics, logs, and alarms on AWS resources, so it cannot examine customer orders or train ML models. Amazon Rekognition is a Computer Vision service for image and video analysis such as object detection and facial recognition, which does not apply to a demand-planning model for reducing food waste.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon Personalize, Amazon CloudWatch, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 88: aif-q118

A property company has built an ML model that predicts home sale prices and wants to host it for predictions without having to manage any servers or infrastructure. Which solution meets this requirement?

- **A.** Deploy the model on an Amazon EC2 instance
- **B.** Deploy the model using Amazon CloudFront with an Amazon S3 integration
- **C.** Deploy the model to an Amazon SageMaker AI endpoint
- **D.** Deploy the model on an Amazon Elastic Kubernetes Service (Amazon EKS) cluster

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Deploy the model to an Amazon SageMaker AI endpoint

**Explanation:**

An Amazon SageMaker AI endpoint is a fully managed deployment option that handles the underlying servers, scaling, and maintenance automatically, so the company can serve predictions from its model without provisioning or managing any infrastructure of its own.
Deploying the model on an Amazon EC2 instance or an Amazon EKS cluster would require the company to provision, scale, patch, and manage the servers or containers itself, which is the opposite of what it wants. Amazon CloudFront with Amazon S3 is a content delivery and static-storage combination for distributing files and web content, not a service for hosting and running ML model inference.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon EC2, Amazon Elastic Kubernetes Service (Amazon EKS), Amazon CloudFront, Amazon S3
- Last verified by source: 2026-06-02

---

### Question 89: aif-q121

A team wants Amazon SageMaker AI to search a defined hyperparameter range and select the job with the best validation metric. Which capability fits?

- **A.** Automatic model tuning
- **B.** SageMaker Feature Store
- **C.** SageMaker Model Monitor
- **D.** SageMaker Ground Truth

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Automatic model tuning

**Explanation:**

Automatic model tuning runs training jobs over configured ranges and optimizes a chosen metric. The team still must choose ranges, metrics, limits, data, and evaluation criteria; tuning is not a no-effort process.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-11-03

---

### Question 90: aif-q127

A company needs a highly scalable AWS service to monitor the performance of its production ML systems. Which AWS service meets this requirement?

- **A.** AWS CloudTrail
- **B.** AWS Config
- **C.** Amazon CloudWatch
- **D.** AWS Trusted Advisor

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon CloudWatch

**Explanation:**

Amazon CloudWatch is a highly scalable monitoring and observability service that collects real-time metrics such as resource usage, inference latency, request counts, and errors, and it supports alarms, dashboards, and automated actions, making it well suited to tracking ML system performance.
AWS CloudTrail records API activity for auditing and governance rather than performance metrics. AWS Config tracks resource configuration changes and compliance. AWS Trusted Advisor offers best-practice recommendations on cost, security, and fault tolerance. None of these is built for real-time performance monitoring of ML systems.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon CloudWatch, AWS CloudTrail, AWS Config, AWS Trusted Advisor
- Last verified by source: 2026-06-02

---

### Question 91: aif-q142

When evaluating a classification model, what does an F1 score measure?

- **A.** The model's speed in generating responses
- **B.** The financial cost of operating the model
- **C.** The model's precision and recall
- **D.** The energy efficiency of the model's computations

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. The model's precision and recall

**Explanation:**

The F1 score is the harmonic mean of precision and recall, so it measures the balance between them and is especially useful when the classes are imbalanced.
Response speed is a latency measure. Operating cost is a financial measure. Energy efficiency is a sustainability measure. None of these is what an F1 score captures.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 92: aif-q170

An online retailer has built a system that flags orders as potentially fraudulent, and a team manually reviews each flagged order. The company wants to reduce the time the team wastes reviewing flagged orders that turn out to be legitimate. Which evaluation metric should it optimize for?

- **A.** Recall
- **B.** Precision
- **C.** F1 score
- **D.** Accuracy

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Precision

**Explanation:**

Precision is the proportion of flagged cases that are genuinely fraudulent, calculated as TP / (TP + FP). Optimizing for precision minimizes false positives, which are exactly the legitimate orders wrongly flagged that waste the team's review time, so it directly targets the company's goal.
Recall measures how much of the actual fraud the system catches, TP / (TP + FN); maximizing it reduces missed fraud but does nothing to limit false positives and can even increase them. Accuracy is the share of all predictions that are correct, which is misleading on imbalanced fraud data where most transactions are legitimate. F1 score is the harmonic mean of precision and recall and balances both, rather than specifically reducing the false positives that drive the review burden.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 93: aif-q177

Which option is a benefit of using Infrastructure as Code (IaC) in Machine Learning Operations (MLOps)?

- **A.** IaC eliminates the need for hyperparameter tuning
- **B.** IaC always provisions powerful compute instances, contributing to the training of more accurate models
- **C.** IaC streamlines the deployment of scalable and consistent ML workloads in cloud environments
- **D.** IaC minimizes overall expenses by deploying only low-cost instances

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. IaC streamlines the deployment of scalable and consistent ML workloads in cloud environments

**Explanation:**

IaC allows infrastructure to be defined, versioned, and automated in code, enabling repeatable and consistent provisioning of ML environments across development, testing, and production stages, which directly supports the MLOps principles of scalable systems and repeatable processes.
Hyperparameter tuning is a model optimization activity that adjusts parameters such as learning rate and batch size during training to improve model performance; it is entirely separate from infrastructure provisioning, so IaC cannot eliminate it. IaC does not inherently provision powerful or low-cost instances, as it simply provisions whatever resources are defined in the configuration code; the choice of instance type and cost profile is determined by the engineer writing the template, not by IaC itself.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 94: aif-q204

A subscription streaming service is building an ML model to predict which customers are likely to cancel their plan. Which metric is appropriate for evaluating this binary classification model?

- **A.** R-squared
- **B.** Mean squared error (MSE)
- **C.** F1 score
- **D.** Model training time

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. F1 score

**Explanation:**

The F1 score combines precision and recall into a single value, which makes it well suited to a binary classification task such as churn prediction, where correctly identifying the customers who will cancel matters and a balance between false positives and false negatives is important.
R-squared and mean squared error (MSE) are regression metrics that measure error on continuous-value predictions, so they do not apply to a classification task. Model training time only reflects how long the model takes to train, an operational figure that says nothing about how accurately the model predicts churn.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 95: aif-q205

While evaluating a classification model in Amazon SageMaker AI, an AI practitioner needs a metric that gives the ratio of correctly classified items to the total number of items classified, whether correctly or incorrectly. Which metric meets this requirement?

- **A.** Recall
- **B.** Precision
- **C.** Accuracy
- **D.** F1 score

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Accuracy

**Explanation:**

Accuracy is the number of correct predictions (true positives plus true negatives) divided by the total number of predictions (all true and false positives and negatives), which is exactly the ratio of correctly classified items to every item classified that the requirement describes.
Precision measures the proportion of positive predictions that are actually correct (true positives over true positives plus false positives), not all classifications. Recall measures the proportion of actual positives the model correctly identifies (true positives over true positives plus false negatives). F1 score is the harmonic mean of precision and recall, balancing those two values rather than reporting overall correct classifications.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 96: aif-q243

A retail company wants to build and deploy ML models on AWS without writing any code. Which AWS service or feature meets this requirement?

- **A.** Amazon Rekognition
- **B.** Amazon Comprehend
- **C.** Amazon SageMaker Canvas
- **D.** AWS DeepRacer

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker Canvas

**Explanation:**

Amazon SageMaker Canvas offers a no-code visual interface that lets users build, train, and deploy custom ML models without writing any code, which is exactly what the company needs.
Amazon Rekognition (Computer Vision) and Amazon Comprehend (Natural Language Processing) are pre-built AI services that return predictions from their own models rather than letting you build and deploy your own. AWS DeepRacer is an educational tool for learning Reinforcement Learning through a simulated race car, not a service for building business ML models.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Canvas, Amazon Rekognition, Amazon Comprehend, AWS DeepRacer
- Last verified by source: 2026-06-02

---

### Question 97: aif-q276

A multiclass classifier has imbalanced classes. The team wants each class to contribute equally to one score that balances precision and recall. Which metric should it use?

- **A.** Accuracy
- **B.** Micro-averaged precision
- **C.** Macro-averaged F1 score
- **D.** Mean squared error

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Macro-averaged F1 score

**Explanation:**

Macro F1 calculates F1 for each class and averages the class scores without weighting by class frequency.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 98: aif-q277

A bank reviews financial transaction records and assigns each one to either a personal or a business category, recording that category on the record. Which data preparation step does this describe?

- **A.** Data normalisation
- **B.** Data encoding
- **C.** Data balancing
- **D.** Data labeling

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Data labeling

**Explanation:**

Data labeling is the step of attaching a meaningful category or tag to each record so it can serve as the target for Supervised Learning, which is exactly what assigning every transaction a personal or business category and storing it on the record achieves.
Data encoding converts categorical values into a numeric form that algorithms can process, rather than creating the categories in the first place. Data normalisation rescales numeric features onto a common range so that no single feature dominates. Data balancing adjusts the proportion of classes in a dataset, for example through over- or under-sampling, so they are more evenly represented; none of these produces the category labels themselves.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 99: aif-q290

A team is adopting MLOps to manage its machine learning workflows more reliably. Which two practices should the team prioritize?

- **A.** Model versioning for reproducibility
- **B.** Automated model testing and validation
- **C.** Manual-only deployment processes
- **D.** Minimal documentation
- **E.** No production monitoring

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Model versioning for reproducibility; B. Automated model testing and validation

**Explanation:**

Model versioning for reproducibility allows teams to track changes, reproduce results, and roll back to previous versions when needed, directly supporting the MLOps objective of repeatable processes. Automated model testing and validation verifies that a model performs correctly before deployment, supporting the MLOps objective of achieving production readiness. Together these practices help teams build scalable, reliable ML systems as defined in objective 1.3.5.
Manual-only deployment processes contradict the MLOps goal of automating repeatable workflows to reduce errors and increase consistency. Minimal documentation undermines collaboration, auditability, and maintainability, all of which are important to sustainable ML operations and managing technical debt. No production monitoring is the opposite of good practice, as continuous monitoring is essential for detecting performance degradation and data drift over time, which is explicitly called out in the MLOps objectives.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 100: aif-q316

During the ML development lifecycle, why does a data scientist perform exploratory data analysis (EDA) before building a model?

- **A.** To train the model
- **B.** To deploy the model
- **C.** To uncover the structure, quality, and relationships within the data
- **D.** To monitor the model in production

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. To uncover the structure, quality, and relationships within the data

**Explanation:**

Exploratory data analysis is carried out early in the ML development lifecycle to uncover the structure, distribution, quality, and relationships within a dataset, which informs later decisions about data cleaning, feature engineering, and algorithm selection before any training begins.
Training the model is a later stage that only happens after EDA and data preparation are complete. Deploying the model occurs after training and evaluation and is concerned with serving predictions, not with understanding the data. Monitoring the model in production is part of the final lifecycle stage, which focuses on detecting performance degradation and data drift once the model is already deployed.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 101: aif-q317

Which of these would NOT normally be a stage in an ML pipeline?

- **A.** Model training
- **B.** Brand advertising
- **C.** Data collection
- **D.** Feature engineering

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Brand advertising

**Explanation:**

Brand advertising is a marketing activity aimed at promoting a product and raising awareness, so it is not part of an ML pipeline, which is made up of technical stages for building, validating, and deploying models.
Data collection, feature engineering, and model training are all genuine stages of a typical ML pipeline. Data collection gathers the relevant raw data from available sources. Feature engineering transforms that raw data into meaningful input variables to improve model performance. Model training fits a model to the prepared data by adjusting its parameters to minimize prediction error.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 102: aif-q318

In the context of model performance metrics, what does the acronym AUC stand for?

- **A.** Area Under the Curve
- **B.** Average Usage Cost
- **C.** Augmented Use Case
- **D.** Automated Utility Calculation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Area Under the Curve

**Explanation:**

AUC stands for Area Under the Curve, specifically the area beneath the ROC (Receiver Operating Characteristic) curve. It measures how well a classification model separates the classes and ranges from 0 to 1, where 1.0 indicates perfect separation and 0.5 means the model is no better than random guessing.
The other choices are invented expansions that string together an A, U, and C word, but none of them is the recognized meaning of AUC as a model performance metric.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 103: aif-q320

What is a key advantage of using pre-trained models?

- **A.** They always outperform custom-built models
- **B.** They are guaranteed to be more accurate for every task
- **C.** They can be used straight away without providing your own training data
- **D.** They remove the need to fine-tune for specialized tasks

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. They can be used straight away without providing your own training data

**Explanation:**

A pre-trained model has already been trained on a large dataset, so it can be applied straight away for inference without the user supplying their own training data, which saves the time, data, and effort of building a model from scratch and is its main advantage.
Claiming a pre-trained model always outperforms custom-built models or is guaranteed to be more accurate for every task are both overclaims, because a model built or fine-tuned for a specific task can easily beat a general pre-trained model. Saying it removes the need to fine-tune for specialized tasks is also false, since pre-trained models frequently must be fine-tuned to perform well on domain-specific work.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 104: aif-q321

A data scientist has selected a training algorithm, tunable hyperparameters, search ranges, and an objective metric. Which SageMaker AI capability can run training jobs across those configurations and select the best-performing result?

- **A.** SageMaker Automatic Model Tuning
- **B.** Amazon Comprehend
- **C.** Amazon Polly
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Automatic Model Tuning

**Explanation:**

SageMaker Automatic Model Tuning, also called hyperparameter tuning, searches the configured hyperparameter ranges through multiple training jobs and selects the result that performs best on the chosen objective metric. The data scientist must define the algorithm, ranges, metric, and job settings.
Amazon Comprehend analyzes text, Amazon Polly converts text to speech, and Amazon Transcribe converts speech to text. They do not run configured hyperparameter searches.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon Comprehend, Amazon Polly, Amazon Transcribe
- Last verified by source: 2026-11-03

---

### Question 105: aif-q322

In a machine learning context, what is the term MLOps an abbreviation of?

- **A.** Machine Learning Optimization
- **B.** Managed Learning Outputs
- **C.** Machine Learning Operations
- **D.** Model Lifecycle Operations

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Machine Learning Operations

**Explanation:**

MLOps stands for Machine Learning Operations, the set of practices that bring machine learning together with DevOps principles to automate and manage the deployment, monitoring, and ongoing maintenance of models in production.
The remaining choices are invented expansions that string together plausible machine-learning-sounding words, but none of them is the recognized meaning of the acronym, so they are all incorrect.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 106: aif-q323

Which of the following is NOT a typical business metric used to evaluate Machine Learning models?

- **A.** Return on investment (ROI)
- **B.** F1 score
- **C.** Customer satisfaction
- **D.** Time to market

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. F1 score

**Explanation:**

F1 score is a model performance metric, the harmonic mean of precision and recall, so it measures prediction quality rather than business value, which makes it the option that is not a business metric.
Return on investment (ROI), customer satisfaction, and time to market are all business metrics that capture the real-world impact, value, and operational outcomes of deploying a model rather than its statistical accuracy.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 107: aif-q324

Which of the following are considered business metrics for AI model evaluation?

- **A.** Precision score
- **B.** Customer satisfaction score
- **C.** Mean Average Precision
- **D.** Time-to-value
- **E.** Root Mean Square Error

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Customer satisfaction score; D. Time-to-value

**Explanation:**

Customer satisfaction score measures how well an AI solution meets end user needs and directly reflects the value delivered to the business, while time-to-value measures how quickly the AI solution begins delivering measurable business outcomes, making both examples of business metrics used to assess whether an AI model is meeting organizational objectives.
Precision score is a technical model performance metric that measures the proportion of positive predictions that are actually correct (true positives divided by all positive predictions), not a business outcome measure. Mean Average Precision is a technical evaluation metric used in information retrieval and object detection tasks to quantify how well a model ranks relevant results, measuring accuracy across ranked outputs rather than business value. Root Mean Square Error is a regression metric that measures the average magnitude of prediction errors by taking the square root of the mean of squared differences between predicted and actual values, again a technical performance measure rather than an indicator of business impact.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 108: aif-q325

A company must decide whether its deployed AI assistant created business value. Which pair of measurements best addresses that decision?

- **A.** Business outcomes such as conversion or handle-time reduction, and financial outcomes such as ROI or cost per interaction
- **B.** Training loss and epoch count
- **C.** Parameter count and context-window size
- **D.** GPU utilization and batch size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Business outcomes such as conversion or handle-time reduction, and financial outcomes such as ROI or cost per interaction

**Explanation:**

Business and financial metrics connect the assistant to outcomes the organization values. Training and infrastructure measures do not establish business value.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 109: aif-q328

Within the ML development lifecycle, what is the main goal of feature engineering?

- **A.** To create new input variables or transform existing ones so the model performs better
- **B.** To gather additional raw data for the project
- **C.** To measure how well the trained model performs
- **D.** To release the model into a production environment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. To create new input variables or transform existing ones so the model performs better

**Explanation:**

Feature engineering is the stage where raw data is turned into useful model inputs by creating new features or transforming existing ones, which improves the model's accuracy and overall performance.
Gathering additional raw data describes the data collection stage, measuring how well the model performs describes model evaluation, and releasing the model into production describes deployment; each of these is a separate stage of the ML lifecycle rather than the purpose of feature engineering.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 110: aif-q331

A team wants to use a single AWS service to build, train, deploy, and monitor machine learning models end to end. Which service is best suited for this?

- **A.** Amazon Comprehend
- **B.** Amazon SageMaker AI
- **C.** Amazon Polly
- **D.** Amazon Translate

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker AI

**Explanation:**

Amazon SageMaker AI is a fully managed platform that supports the entire machine learning lifecycle, including data preparation, model training, hyperparameter tuning, deployment, and ongoing monitoring, making it the right choice for managing ML models end to end.
Amazon Comprehend is a natural language processing service for extracting insights such as sentiment and entities from text, not a platform for managing the full ML lifecycle. Amazon Polly is a text-to-speech service that converts text into lifelike speech, which addresses a single AI capability rather than end-to-end model development. Amazon Translate provides language translation between languages and likewise serves one specific task rather than supporting the complete ML lifecycle.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon Comprehend, Amazon SageMaker AI, Amazon Polly, Amazon Translate
- Last verified by source: 2026-06-01

---

### Question 111: aif-q116

At which stage of the ML lifecycle are regulatory and compliance obligations primarily established?

- **A.** Model training
- **B.** Data collection
- **C.** Business goal identification
- **D.** Feature engineering

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Business goal identification

**Explanation:**

Regulatory and compliance obligations are primarily established during business goal identification, because defining what you want to build determines which laws and regulations apply to the project before any data is collected or processed.
Data collection is where those obligations are applied in practice, such as obtaining consent and verifying data sources, but the obligations themselves must be understood before collection begins. Model training and feature engineering are later technical stages focused on building and optimizing the model, not on identifying the legal and regulatory framework that governs the project.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 112: aif-q148

A streaming service is an existing SageMaker Model Monitor customer. After deploying its custom model, the team wants scheduled checks that compare captured production data and quality metrics with a baseline. Which capability fits?

- **A.** Amazon SageMaker Clarify
- **B.** Amazon Comprehend
- **C.** Amazon SageMaker Model Monitor
- **D.** Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker Model Monitor

**Explanation:**

For an existing customer, SageMaker Model Monitor runs monitoring jobs on configured schedules and can report deviations from baselines for supported monitoring types. It is no longer open to new customers, and scheduled checks are not continuous observation.
SageMaker Clarify focuses on bias and explainability. Amazon Comprehend and Amazon Rekognition analyze text and images rather than monitoring a deployed custom model.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor, Amazon SageMaker Clarify, Amazon Comprehend, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 113: aif-q166

An existing SageMaker Model Monitor customer runs ML models in production and wants scheduled jobs to compare captured data or model-quality results with configured baselines. Which capability meets this need?

- **A.** Amazon SageMaker Data Wrangler
- **B.** Amazon SageMaker Model Monitor
- **C.** Amazon SageMaker JumpStart
- **D.** Amazon SageMaker HyperPod

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker Model Monitor

**Explanation:**

For existing customers, SageMaker Model Monitor runs configured monitoring schedules and can publish violations when results differ from a baseline. It is no longer open to new customers and does not watch endpoints continuously.
SageMaker Data Wrangler prepares data, SageMaker JumpStart provides pretrained models and solutions, and SageMaker HyperPod provides distributed training infrastructure.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor, Amazon SageMaker JumpStart, Amazon SageMaker Data Wrangler, Amazon SageMaker Hyperpod
- Last verified by source: 2026-06-02

---

### Question 114: aif-q230

After producing a number of ML models, a team needs one place to keep them, manage them, and track each version. Which AWS service or feature meets these requirements?

- **A.** Amazon SageMaker Model Monitor
- **B.** Amazon SageMaker Canvas
- **C.** Amazon SageMaker Model Registry
- **D.** AWS Audit Manager

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker Model Registry

**Explanation:**

Amazon SageMaker Model Registry is a central repository for storing, managing, and versioning ML models and tracking their deployment status across the lifecycle, which meets the team's needs.
Amazon SageMaker Model Monitor detects drift in deployed models, Amazon SageMaker Canvas builds models with a no-code interface, and AWS Audit Manager collects audit evidence; none of these is the service for model versioning and management.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Registry, Amazon SageMaker Model Monitor, Amazon SageMaker Canvas, AWS Audit Manager
- Last verified by source: 2026-06-02

---

### Question 115: aif-q261

Amazon SageMaker Model Monitor reports that input data drift crossed a threshold. What should the team do first?

- **A.** Investigate the affected features, data pipeline, and model performance before choosing remediation
- **B.** Retrain and deploy immediately without evaluation
- **C.** Restart the endpoint
- **D.** Lower the alert sensitivity until the alert clears

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Investigate the affected features, data pipeline, and model performance before choosing remediation

**Explanation:**

A drift alert is evidence of changed data, not proof that retraining is the right fix. Investigation should determine whether to repair data, adjust monitoring, retrain, or take another approved action.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor
- Last verified by source: 2026-11-03

---

### Question 116: aif-q332

Why do teams monitor models once they are running in production?

- **A.** To collect more data
- **B.** To detect issues such as model drift or data drift
- **C.** To perform feature engineering
- **D.** To train new models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. To detect issues such as model drift or data drift

**Explanation:**

The primary purpose of model monitoring in production is to detect issues such as model drift or data drift so teams can act before performance degrades.
Collecting more data, performing feature engineering, and training new models are separate lifecycle activities, not the purpose of monitoring a deployed model.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 117: aif-q346

For an existing SageMaker Model Monitor customer, which task can the capability perform through configured monitoring schedules?

- **A.** To serve models for inference
- **B.** To detect data drift and model performance degradation
- **C.** To create training datasets
- **D.** To train models faster

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. To detect data drift and model performance degradation

**Explanation:**

For eligible existing customers, SageMaker Model Monitor runs scheduled jobs that compare captured data or quality measurements with configured baselines and can publish violations for investigation. The capability is no longer open to new customers and does not inspect an endpoint continuously.
Serving models, creating training datasets, and accelerating training use other capabilities.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor
- Last verified by source: 2026-06-02

---

### Question 118: aif-q221

A company has built custom Computer Vision models and needs an easy-to-use interface for labeling data to reduce errors on new, real-world images. Which AWS tool fits?

- **A.** Amazon SageMaker Canvas
- **B.** Amazon SageMaker Ground Truth
- **C.** Amazon Rekognition Custom Labels
- **D.** Amazon SageMaker Autopilot

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker Ground Truth

**Explanation:**

Amazon SageMaker Ground Truth provides a built-in labeling interface with workflows and quality controls for tasks such as Computer Vision, producing high-quality labeled data that reduces model errors.
SageMaker Canvas is a no-code interface for building models, Rekognition Custom Labels trains a model rather than offering a general labeling interface, and SageMaker Autopilot auto-builds models from tabular data.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Ground Truth, Amazon SageMaker Canvas, Amazon Rekognition, Amazon SageMaker Autopilot
- Last verified by source: 2026-06-02

---

### Question 119: aif-q223

A bank deployed an ML model to predict customer churn and wants to measure how accurately it predicts churn compared with actual behavior. Which metric fits?

- **A.** Root mean squared error (RMSE)
- **B.** F1 score
- **C.** Return on investment (ROI)
- **D.** Perplexity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. F1 score

**Explanation:**

The F1 score balances precision and recall, which makes it well suited to measuring accuracy on a binary classification task such as predicting whether a customer will churn.
RMSE measures error for regression predictions, ROI is a business-value metric, and perplexity measures language-modeling fit; none fits binary churn classification.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 120: aif-q263

An existing SageMaker Model Monitor customer wants alerts from scheduled checks when captured production data or model-quality measurements deviate from a baseline. Which solution meets that detection requirement?

- **A.** Use Amazon SageMaker Model Monitor with baselines, monitoring schedules, and CloudWatch alarms
- **B.** Use SageMaker Feature Store to prevent drift
- **C.** Use SageMaker Clarify to prevent all quality changes
- **D.** Use an endpoint restart policy

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Amazon SageMaker Model Monitor with baselines, monitoring schedules, and CloudWatch alarms

**Explanation:**

For an eligible existing customer, SageMaker Model Monitor can run scheduled jobs, publish constraint violations, and support CloudWatch alarms. It is no longer open to new customers. Monitoring detects changes but does not prevent them; the team must investigate each signal.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor, Amazon SageMaker Clarify, Amazon CloudWatch, Amazon SageMaker Feature Store, Amazon SageMaker AI
- Last verified by source: 2026-11-03

---

### Question 121: aif-q011

A company is building an ML model with Amazon SageMaker and needs to share and manage variables used for model development across several teams. Which SageMaker feature meets this requirement?

- **A.** Amazon SageMaker Data Wrangler
- **B.** Amazon SageMaker Feature Store
- **C.** Amazon SageMaker Clarify
- **D.** Amazon SageMaker Model Cards

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker Feature Store

**Explanation:**

Amazon SageMaker Feature Store is a centralized repository for storing, sharing, and reusing features, which lets multiple teams manage the same variables for model development.
Amazon SageMaker Data Wrangler prepares and transforms data, Amazon SageMaker Clarify detects bias and supports explainability, and Amazon SageMaker Model Cards document model details. None of these is designed to share and manage features across teams.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Feature Store, Amazon SageMaker Data Wrangler, Amazon SageMaker Clarify, Amazon SageMaker Model Cards
- Last verified by source: 2026-06-02

---

### Question 122: aif-q253

A practitioner with limited ML experience wants to predict employee attrition without writing any code. Which Amazon SageMaker feature meets this requirement?

- **A.** SageMaker Canvas
- **B.** SageMaker Clarify
- **C.** SageMaker Model Monitor
- **D.** SageMaker Data Wrangler

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Canvas

**Explanation:**

Amazon SageMaker Canvas offers a no-code visual interface that lets a user with limited ML experience build, train, and generate predictions, such as employee attrition, without writing code.
SageMaker Clarify detects bias and explains predictions, SageMaker Model Monitor tracks deployed models for drift, and SageMaker Data Wrangler prepares data. None of these provides a no-code way to build a predictive model.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker Canvas, Amazon SageMaker Clarify, Amazon SageMaker Model Monitor, Amazon SageMaker Data Wrangler
- Last verified by source: 2026-06-02

---

### Question 123: aif-q351

A startup wants to use a foundation model for its application but lacks the data and resources to train one from scratch. Which approach allows the team to obtain a foundation model without pre-training it themselves?

- **A.** Use an open-source pre-trained model from a model hub
- **B.** Build a rule-based expert system instead
- **C.** Collect more labeled data and train a decision tree
- **D.** Write custom inference code without any model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use an open-source pre-trained model from a model hub

**Explanation:**

Open-source pre-trained models are available from model hubs and can be used directly or fine-tuned for specific tasks, allowing teams to leverage foundation models without the massive data and compute resources required to pre-train them from scratch.
Building a rule-based expert system does not provide a foundation model. Training a decision tree creates a traditional ML model, not a foundation model. Writing custom inference code without any model provides no predictive capability at all.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 124: aif-q352

A company wants to experiment with multiple foundation models before selecting one for production. Which AWS service provides access to a variety of pre-trained foundation models from different providers?

- **A.** Amazon Personalize
- **B.** Amazon SageMaker JumpStart
- **C.** Amazon Comprehend
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker JumpStart

**Explanation:**

Amazon SageMaker JumpStart provides access to a variety of pre-trained foundation models from AWS and third-party providers, allowing teams to experiment with different models and deploy them with minimal setup, which directly addresses the company's need.
Amazon Personalize builds recommendation models from user interaction data rather than providing access to general-purpose foundation models. Amazon Comprehend is a managed NLP service for text analysis. Amazon Transcribe converts speech to text. None of these provides a catalog of foundation models from multiple providers.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker JumpStart, Amazon Personalize, Amazon Comprehend, Amazon Transcribe
- Last verified by source: 2026-06-03

---

### Question 125: aif-q357

A team wants to define repeatable ML workflow steps for processing, training, evaluation, and conditional model registration. Which Amazon SageMaker AI capability fits?

- **A.** SageMaker Pipelines
- **B.** Amazon Transcribe
- **C.** Amazon Textract
- **D.** Amazon Personalize

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Pipelines

**Explanation:**

SageMaker Pipelines orchestrates repeatable ML workflow steps and supports conditions such as registering a model only when evaluation criteria pass. This is a current Task 1.3 lifecycle example.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-11-03

---

### Question 126: aif-q358

A software team wants to use AI to help define requirements, generate design documents, and implement features based on specifications. Which AWS service supports this spec-driven development workflow?

- **A.** Amazon Personalize
- **B.** Amazon Rekognition
- **C.** Kiro
- **D.** Amazon Polly

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Kiro

**Explanation:**

Kiro is an AI-powered development environment that supports spec-driven development, helping teams define requirements, generate design documents, and implement features based on specifications.
Amazon Personalize generates recommendations based on user behavior. Amazon Rekognition analyzes images and video. Amazon Polly converts text to speech. None of these supports spec-driven software development workflows.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Kiro, Amazon Personalize, Amazon Rekognition, Amazon Polly
- Last verified by source: 2026-06-03

---

### Question 127: aif-q359

A business analyst wants a managed workspace for natural-language questions, visual analysis, and AI-assisted business insights. Which AWS service fits?

- **A.** Amazon Athena
- **B.** Amazon Quick
- **C.** Amazon Redshift
- **D.** AWS Glue

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Quick

**Explanation:**

Amazon Quick provides AI-assisted business insights and natural-language analysis. Athena, Redshift, and Glue provide query, warehouse, and integration capabilities rather than the requested end-user workspace.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: Amazon Quick, Amazon Athena, Amazon Redshift, AWS Glue
- Last verified by source: 2026-11-03

---

### Question 128: aif-q368

In the context of MLOps, what does managing technical debt refer to?

- **A.** Reducing the financial cost of cloud compute instances
- **B.** Addressing accumulated shortcuts, outdated dependencies, and undocumented processes that make ML systems harder to maintain over time
- **C.** Increasing the number of model parameters to improve accuracy
- **D.** Deleting old datasets that are no longer needed

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Addressing accumulated shortcuts, outdated dependencies, and undocumented processes that make ML systems harder to maintain over time

**Explanation:**

Technical debt in MLOps refers to the accumulated cost of shortcuts, poorly documented pipelines, outdated dependencies, and tightly coupled components that make ML systems progressively harder to maintain, extend, and debug over time. Managing it means proactively refactoring, documenting, and modernizing these systems.
Reducing cloud compute costs is cost optimization, not technical debt management. Increasing model parameters is a modeling decision related to capacity, not maintenance burden. Deleting old datasets is a data governance activity rather than a response to accumulated engineering shortcuts.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 129: aif-q369

A data science team needs to compare training runs by recording hyperparameters, metrics, and artifacts. Which MLOps practice fits?

- **A.** Model deployment
- **B.** Experiment tracking
- **C.** Data labeling
- **D.** Feature serving

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Experiment tracking

**Explanation:**

Experiment tracking records run metadata and artifacts for comparison. Exact reproduction also depends on preserved code, data versions, dependencies, random seeds, and execution environment.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 130: aif-q370

What is the purpose of hyperparameter tuning in the ML development lifecycle?

- **A.** To collect and clean the raw training data
- **B.** To find the model configuration settings that produce the best performance
- **C.** To deploy the trained model to a production endpoint
- **D.** To monitor the model for data drift after deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. To find the model configuration settings that produce the best performance

**Explanation:**

Hyperparameter tuning searches for the optimal configuration settings, such as learning rate, batch size, and number of layers, that are set before training begins and directly influence model performance. Finding the best combination maximizes the model's accuracy or other target metric.
Collecting and cleaning raw data is the data collection and preprocessing stage. Deploying the model to a production endpoint is the deployment stage. Monitoring for data drift is part of the post-deployment monitoring stage. Each of these is a separate step in the ML lifecycle.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 131: aif-q109

A churn model performs much better on training data than on validation data. Which proposed change directly targets excessive model complexity?

- **A.** Reduce regularization
- **B.** Add unreviewed features
- **C.** Train for more epochs regardless of validation loss
- **D.** Increase regularization and re-evaluate on validation data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Increase regularization and re-evaluate on validation data

**Explanation:**

Stronger regularization can reduce overfitting by penalizing complexity, but it does not guarantee better generalization. Useful, validated features can sometimes help.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 132: aif-q044

A forecasting model performs well on training data but poorly in production. What should the team do first?

- **A.** Train longer
- **B.** Investigate data drift, leakage, sampling, pipeline differences, and validation performance
- **C.** Delete training examples
- **D.** Add model complexity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Investigate data drift, leakage, sampling, pipeline differences, and validation performance

**Explanation:**

The performance gap has several possible causes. The team should diagnose the data and pipeline before choosing a remedy. Representative data may help if investigation finds a coverage problem.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 133: aif-q457

A team at a logistics company is building a machine learning model that predicts delivery delays. Arrange the following stages of the ML development lifecycle in the correct order, from first to last.

- **A.** Train the model on the prepared dataset to learn patterns that predict delays
- **B.** Engineer features and clean the gathered data into a training-ready dataset
- **C.** Deploy the validated model to an endpoint so applications can request predictions
- **D.** Define the business problem and the success metric for the delay-prediction use case
- **E.** Collect historical shipment and delivery records from source systems

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Define the business problem and the success metric for the delay-prediction use case → E. Collect historical shipment and delivery records from source systems → B. Engineer features and clean the gathered data into a training-ready dataset → A. Train the model on the prepared dataset to learn patterns that predict delays → C. Deploy the validated model to an endpoint so applications can request predictions

**Explanation:**

The ML lifecycle starts by framing the business problem and defining a success metric (D), because every later choice depends on knowing what you are predicting and how success is measured. You then collect the raw data (E), prepare it and engineer features into a training-ready dataset (B), train the model on that dataset (A), and finally deploy the validated model to an endpoint (C) so applications can consume its predictions.
A common mistake is to start with data collection or jump straight to model training, but gathering or modeling data before the business goal is defined risks building the wrong model on the wrong data. Note that data preparation and feature engineering (B) must follow collection (E), since you cannot clean or transform data you have not yet gathered, and deployment (C) is the last step shown because a model is only served after it has been trained and validated.

</details>

**Question metadata**

- Domain: 1
- Task statement: 1.3
- Format: ordering
- Services: None listed
- Last verified by source: 2026-06-13

---

# Domain 2: Fundamentals of generative AI

Questions in this domain: 79

## Task 2.1

Questions for this task: 41

### Question 134: aif-q002

A publisher needs to turn long research reports into short briefs that capture their main points, using a large language model (LLM). Which solution meets this requirement?

- **A.** Build a recommendation engine
- **B.** Develop a summarization chatbot
- **C.** Build a named entity recognition system
- **D.** Create a multi-language translation system

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Develop a summarization chatbot

**Explanation:**

A summarization chatbot uses an LLM to read long documents and produce a shorter version that keeps the essential points, which is exactly what condensing research reports into briefs requires.
A recommendation engine suggests relevant items from user behavior and does not condense documents. A named entity recognition system only pulls out entities such as names, dates, and places rather than producing a coherent summary. A multi-language translation system converts text between languages without shortening or distilling the content.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 135: aif-q018

An ecommerce team is building visual search that accepts both a typed phrase and a product photo as the query. Which kind of foundation model (FM) should power it?

- **A.** Text embedding model
- **B.** Multimodal embedding model
- **C.** Image generation model
- **D.** Multimodal generation model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Multimodal embedding model

**Explanation:**

A multimodal embedding model encodes both text and images into a shared vector space, so queries of either type can be compared and matched, which is what a search application handling text and image queries needs.
A text embedding model handles only text. An image generation model creates images from prompts rather than encoding queries for search. A multimodal generation model produces new content across modalities rather than the embeddings needed for similarity search.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 136: aif-q022

A marketing agency is exploring generative AI. Which of these tasks is a generative AI use case?

- **A.** Improving network security by using an intrusion detection system
- **B.** Forecasting stock market trends from historical financial data
- **C.** Generating photorealistic images from text descriptions for a marketing campaign
- **D.** Speeding up database queries with optimized indexing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Generating photorealistic images from text descriptions for a marketing campaign

**Explanation:**

Generative AI creates new content, and producing photorealistic images from text descriptions for a marketing campaign is content generation, a classic generative AI use case.
Intrusion detection is a security and classification task. Forecasting stock trends from historical data is predictive analytics. Optimizing database indexing is performance tuning. None of these create new content, so they are not generative AI use cases.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 137: aif-q023

A team is selecting a foundation model for requests that contain instructions, retrieved passages, conversation history, and a generated answer. Which property limits the combined token budget the model can handle in one request?

- **A.** Temperature
- **B.** Parameter count
- **C.** Context window
- **D.** Batch size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Context window

**Explanation:**

The context window limits the tokens the model can consider for a request. The team must account for input context and the output budget under the selected model and API.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 138: aif-q035

A retail company keeps large volumes of sales data in a database. It wants an application that lets non-technical staff type a plain-language question and have it automatically turned into a SQL query. Which type of model is best suited to power this application?

- **A.** Residual neural network (ResNet)
- **B.** Support vector machine (SVM)
- **C.** WaveNet
- **D.** Generative pre-trained transformer (GPT)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Generative pre-trained transformer (GPT)

**Explanation:**

Generative pre-trained transformers are large language models trained to generate text, and they can translate a natural-language request into a structured SQL query, which lets non-technical staff retrieve data without writing SQL themselves, exactly as the requirement describes.
A residual neural network (ResNet) is a deep architecture built for image recognition and computer vision, not language generation. A support vector machine (SVM) is a classic supervised algorithm for classification or regression and cannot generate SQL from text. WaveNet is a generative model for producing realistic audio and speech, so it is the wrong modality for converting text into queries.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 139: aif-q055

A company is building an application that must generate synthetic data based on its existing data. Which type of model can the company use to meet this requirement?

- **A.** XGBoost
- **B.** WaveNet
- **C.** Generative adversarial network (GAN)
- **D.** Residual neural network

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Generative adversarial network (GAN)

**Explanation:**

A generative adversarial network (GAN) is built from two competing neural networks, a generator that creates synthetic samples resembling the real data and a discriminator that tries to tell real from generated, and through this competition it learns to produce realistic synthetic data based on an existing dataset, which is exactly what the company needs.
XGBoost is a gradient-boosting algorithm for supervised classification and regression, not for generating new data. A residual neural network (ResNet) is a deep convolutional architecture used mainly for image recognition and classification. WaveNet is a generative model, but it is specialized for synthesising raw audio such as speech rather than producing general synthetic data from an arbitrary existing dataset.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 140: aif-q063

In AI and Natural Language Processing (NLP), what is the term for the numerical representations of real-world objects and concepts that help models better understand text?

- **A.** Tokens
- **B.** Parameters
- **C.** Embeddings
- **D.** Models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Embeddings

**Explanation:**

Embeddings are numerical vector representations of objects and concepts such as words or phrases; by placing similar items close together in vector space they capture relationships and meaning, which helps AI and NLP models understand and work with text more effectively.
Tokens are the individual units, such as words or sub-words, that text is split into before processing, not representations of meaning. A model is the trained system that makes predictions, not a representation of a concept. Parameters are the internal weights a model learns during training and do not represent real-world objects or concepts.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 141: aif-q080

A travel company that already uses Amazon Bedrock Agents Classic wants to automate repetitive booking tasks and orchestrate multi-step workflows. Which capability describes a benefit available to this existing customer?

- **A.** Generating custom foundation models (FMs) to predict customer needs
- **B.** Choosing a foundation model (FM) based on predefined criteria and metrics
- **C.** Automating repetitive tasks and orchestrating complex, multi-step workflows
- **D.** Calling several foundation models (FMs) at once and merging their results

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Automating repetitive tasks and orchestrating complex, multi-step workflows

**Explanation:**

For existing customers, Amazon Bedrock Agents Classic can automate repetitive tasks and orchestrate multi-step workflows. Agents Classic is in maintenance mode and is no longer open to new customers; new designs should evaluate Amazon Bedrock AgentCore.
Agents Classic does not create foundation models or select a model from evaluation criteria, and its defining benefit is not merging several model responses.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 142: aif-q083

A startup is budgeting for on-demand text-model inference on Amazon Bedrock for a large language model priced by input and output tokens. Which request-level factor directly affects that charge?

- **A.** The temperature value used for generation
- **B.** The amount of data used to train the LLM
- **C.** The number of tokens consumed
- **D.** The total time spent training the LLM

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. The number of tokens consumed

**Explanation:**

For an on-demand text model whose price lists separate input and output token rates, the number of processed tokens directly affects the request charge. Bedrock also has models, modalities, service tiers, and purchasing options with other pricing units, so this answer does not describe every Bedrock workload.
Temperature shapes token sampling rather than the listed token rate. Training-data volume and training time concern model development, not this on-demand inference request.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 143: aif-q105

A developer gives an LLM a natural-language specification and asks it to create a new function from scratch. Which capability is being used?

- **A.** Code generation
- **B.** Code completion
- **C.** Text classification
- **D.** Embedding generation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Code generation

**Explanation:**

Code generation creates new code from an instruction. Code completion extends an existing partial program.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 144: aif-q112

A pharmacy chain wants a short overview of each new medication based on its customer reviews. Which solution meets this requirement?

- **A.** Build a time-series forecasting model to analyze the reviews with Amazon Personalize
- **B.** Build a classification model that sorts medications into groups with Amazon Comprehend
- **C.** Generate medication review summaries with Amazon Bedrock large language models (LLMs)
- **D.** Generate medication review summaries with Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Generate medication review summaries with Amazon Bedrock large language models (LLMs)

**Explanation:**

Amazon Bedrock provides large language models well suited to summarization, so generating concise summaries of medication reviews with Bedrock LLMs meets the requirement.
A time-series forecasting model with Amazon Personalize predicts future values and is not for summarizing text. A classification model with Amazon Comprehend sorts items into categories rather than producing a written overview. Amazon Rekognition analyzes images and video, not text reviews.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Personalize, Amazon Comprehend, Amazon Rekognition
- Last verified by source: 2026-06-02

---

### Question 145: aif-q137

An insurer's support chatbot on Amazon Bedrock needs several turns to resolve a claim. How can the large language model (LLM) use content from the customer's earlier messages?

- **A.** Turn on model invocation logging to collect the messages
- **B.** Use Amazon Personalize to store the conversation history
- **C.** Include the previous messages in the model prompt
- **D.** Use Provisioned Throughput for the LLM

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Include the previous messages in the model prompt

**Explanation:**

Including the previous messages in the model prompt gives the LLM the conversation history it needs, so it can keep context across turns and respond coherently.
Model invocation logging records requests for monitoring but does not feed history back into the model. Amazon Personalize is a recommendation service, not a way to supply prompt context. Provisioned Throughput sets capacity and does not add conversation context.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 146: aif-q152

An investment firm uses ML across its operations. Which of these is a generative AI use case?

- **A.** Classifying customers by product usage
- **B.** Forecasting revenue for certain products
- **C.** Summarizing customer complaints
- **D.** Segmenting customers by type of investment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Summarizing customer complaints

**Explanation:**

Summarizing customer complaints generates new, condensed text from longer input, which is a generative AI task typically handled by large language models.
Classifying customers by product usage and forecasting revenue are predictive tasks, and segmenting customers by investment type is clustering. These are traditional ML tasks that do not generate new content.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 147: aif-q158

Which statement describes a defining characteristic of transformer-based language models?

- **A.** They use convolutional layers to apply filters across the input and capture local patterns
- **B.** They use self-attention mechanisms to capture contextual relationships
- **C.** They can process only text data
- **D.** They process a sequence one element at a time in repeated cycles

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. They use self-attention mechanisms to capture contextual relationships

**Explanation:**

Transformer-based models use self-attention mechanisms that weigh the importance of each token relative to the others, which lets them capture contextual relationships across an entire input.
Convolutional layers are characteristic of CNNs, not transformers. Transformers are not limited to text and can be multimodal. Processing one element at a time in cycles describes recurrent networks (RNNs), not the parallel self-attention of transformers.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 148: aif-q375

A team sends the same long system instructions and reference material in many Amazon Bedrock requests. Which capability can reduce repeated input processing for supported models?

- **A.** Prompt caching
- **B.** SageMaker Model Monitor
- **C.** Amazon Transcribe Medical
- **D.** Amazon Rekognition

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Prompt caching

**Explanation:**

Prompt caching reuses supported, unchanged prompt prefixes across requests and can reduce latency and input-token cost. The team must use a supported model and meet its cache requirements.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 149: aif-q184

In a large language model (LLM), what do vector embeddings make possible?

- **A.** Splitting text into manageable pieces of data
- **B.** Comparing texts mathematically
- **C.** Grouping a set of characters to be treated as a single unit
- **D.** Counting every word in the input

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Comparing texts mathematically

**Explanation:**

Vector embeddings convert text into numerical vectors that capture meaning, so texts can be compared mathematically by measuring distance or similarity, which supports tasks like retrieval and clustering.
Splitting text into manageable pieces describes chunking. Grouping characters into a single unit describes tokenization. Counting every word is a simple word-frequency count, not an embedding.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 150: aif-q197

An edtech company is building an app where students type a question or snap a photo of one, and the app returns a written answer with an explanation. Which type of model should power the app?

- **A.** Computer Vision model
- **B.** Diffusion model
- **C.** Large multimodal language model
- **D.** Text-to-speech model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Large multimodal language model

**Explanation:**

A large multimodal language model can take both text and images as input and generate text output, so it can accept a typed or photographed question and return a written answer with an explanation.
A Computer Vision model analyzes images but does not generate explanatory text answers. A diffusion model generates images, not text answers. A text-to-speech model converts text into audio, which does not produce written answers from mixed inputs.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 151: aif-q199

Which statement correctly describes embeddings in generative AI?

- **A.** Embeddings search data to find the most helpful information for answering natural-language questions
- **B.** Embeddings lower hardware requirements by using a less precise data type for weights and activations
- **C.** Embeddings represent data as high-dimensional vectors that capture semantic relationships
- **D.** Embeddings store and retrieve data for generative AI applications

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Embeddings represent data as high-dimensional vectors that capture semantic relationships

**Explanation:**

Embeddings map inputs such as words or documents into high-dimensional vectors where semantic similarity corresponds to closeness in the vector space, letting models reason about meaning and relationships.
Searching data to find helpful information describes retrieval, as in RAG. Reducing hardware needs with a less precise data type describes quantization. Storing and retrieving data describes a database or vector store, not embeddings themselves.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 152: aif-q202

What is the term for the instructions you give a foundation model (FM) to help it return a more accurate answer?

- **A.** Direction
- **B.** Dialog
- **C.** Prompt
- **D.** Translation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Prompt

**Explanation:**

A prompt is the input instruction or query provided to a foundation model that guides what it should do, helping it produce a more accurate response.
Direction and dialog are not the term for the model's input instruction. Translation is a task type, not the instruction itself.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 153: aif-q275

A studio wants a managed AWS foundation model that generates video from text or image prompts. Which service-and-model pairing fits?

- **A.** Amazon Bedrock with Amazon Nova Reel
- **B.** Amazon Quick with Amazon Nova Canvas
- **C.** Amazon SageMaker Clarify with Amazon Nova Micro
- **D.** Amazon Transcribe with Amazon Nova Pro

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Bedrock with Amazon Nova Reel

**Explanation:**

Amazon Nova Reel is a video-generation model available through Amazon Bedrock. Nova Canvas generates images; the other service pairings do not provide Nova video generation.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Nova
- Last verified by source: 2026-11-03

---

### Question 154: aif-q278

A compliance team wants to pull the key insights out of long policy documents so staff can work faster. Which generative AI strategy meets this requirement?

- **A.** Regression
- **B.** Summarization
- **C.** Clustering
- **D.** Classification

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Summarization

**Explanation:**

Summarization condenses large documents into their key insights, so employees can quickly grasp and act on the essential information.
Regression predicts numeric values, clustering groups similar items, and classification assigns labels. None of these extracts and condenses the key insights from a document.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 155: aif-q284

Which scenario is a practical use case for generative AI?

- **A.** Using an ML model to forecast product demand
- **B.** Tracking website traffic and user behavior with an analytics dashboard
- **C.** Using a chatbot to give human-like responses to customer queries in real time
- **D.** Using a rule-based recommendation engine to suggest products

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Using a chatbot to give human-like responses to customer queries in real time

**Explanation:**

A chatbot that gives human-like responses to customer queries in real time uses a generative model to create relevant, natural-language answers, which is a practical generative AI use case.
Forecasting product demand with an ML model is predictive analytics. An analytics dashboard tracks metrics. A rule-based recommendation engine follows fixed rules. None of these generates new content.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 156: aif-q293

What is the difference between discriminative and generative AI models?

- **A.** Discriminative models are faster than generative models
- **B.** Discriminative models are more accurate than generative models
- **C.** Discriminative models classify or predict, while generative models create new content
- **D.** Discriminative models need more data than generative models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Discriminative models classify or predict, while generative models create new content

**Explanation:**

Discriminative models learn to classify inputs or predict outcomes, whereas generative models learn to create new content similar to their training data; this is the core distinction between the two.
Claims that discriminative models are inherently faster, more accurate, or need more data are not the defining difference and are not generally true; the real distinction is what each type of model produces.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 157: aif-q303

An edtech company is building a reading app that lets students add illustrations to their stories. Which solution meets this requirement?

- **A.** Use Amazon Polly to create an audiobook from the story text
- **B.** Use Amazon Rekognition to analyze image content and detect text attributes
- **C.** Use Amazon Bedrock Stable Diffusion 3.5 Large to generate images from text inputs
- **D.** Create a standard prompt template and use Amazon Q Business to illustrate the stories

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Use Amazon Bedrock Stable Diffusion 3.5 Large to generate images from text inputs

**Explanation:**

Amazon Bedrock Stable Diffusion 3.5 Large generates images from text prompts, so students can create illustrations for their stories from descriptions, which supports reading comprehension with visuals.
Amazon Polly converts text to speech, producing audio rather than illustrations. Amazon Rekognition analyzes existing images rather than generating new ones. Amazon Q Business is an enterprise assistant over company data and does not generate story illustrations.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Polly, Amazon Rekognition, Amazon Q Business
- Last verified by source: 2026-06-02

---

### Question 158: aif-q310

An ecommerce company needs to generate thousands of unique product descriptions a day, written as paragraphs with a consistent style and tone. Which type of generative model meets these requirements?

- **A.** A variational autoencoder (VAE) model
- **B.** A diffusion model
- **C.** A transformer-based model
- **D.** A generative adversarial network (GAN) model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. A transformer-based model

**Explanation:**

Transformer-based models, such as large language models, generate coherent paragraphs of text with consistent style and tone and scale to producing thousands of unique descriptions, which fits the requirement.
Variational autoencoders and generative adversarial networks are used mainly to generate images or other data, not fluent long-form text. Diffusion models generate images, so none of these is suited to producing styled product-description text at scale.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 159: aif-q334

What is a token in the context of generative AI?

- **A.** A security feature
- **B.** A type of neural network
- **C.** A unit of text processed by the model
- **D.** A model evaluation metric

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. A unit of text processed by the model

**Explanation:**

A token is the basic unit of text, such as a word or sub-word, that a model processes and generates, which is what the term refers to.
A token is not a security feature, not a type of neural network, and not a model evaluation metric; those describe unrelated concepts.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 160: aif-q339

What is a foundation model in generative AI?

- **A.** A model that can only generate text
- **B.** A model designed specifically for image generation
- **C.** A large, pre-trained model that can be adapted for many tasks
- **D.** A model that requires no training data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. A large, pre-trained model that can be adapted for many tasks

**Explanation:**

A foundation model is a large model pre-trained on vast amounts of data that can be adapted or fine-tuned for many downstream tasks such as text generation, summarization, and question answering.
A foundation model is not limited to text and is not built only for image generation, and it is trained on large amounts of data, so the claim that it needs no training data is incorrect.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 161: aif-q082

In generative AI, what are tokens?

- **A.** The vector representations of words or concepts
- **B.** The basic units of input and output, such as words or subwords
- **C.** The instructions or prompts given to the model
- **D.** The hidden layers of the neural network

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. The basic units of input and output, such as words or subwords

**Explanation:**

Tokens are the smallest units, such as words, subwords, or characters, that a generative model reads and produces, forming the basis of its input and output.
Vector representations describe embeddings, prompts are the instructions given to the model, and hidden layers are part of the model's architecture; none of these defines a token.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 162: aif-q193

Which two statements correctly describe an embedding space?

- **A.** Each item maps to a vector in a learned semantic space
- **B.** Semantically similar items tend to be closer under the selected distance measure
- **C.** Every coordinate has a guaranteed human-readable meaning
- **D.** The space verifies every generated claim

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A; B

**Explanation:**

Embedding models map content to vectors in a learned semantic space. Similar meanings often lie near one another under a chosen similarity or distance measure; individual dimensions need not have direct human interpretations.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 163: aif-q198

In the generative AI model lifecycle, which stage runs tests to check the model's accuracy?

- **A.** Pre-training
- **B.** Fine-tuning
- **C.** Evaluation
- **D.** Deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Evaluation

**Explanation:**

The evaluation stage tests the model against validation or hold-out data using metrics such as accuracy before it moves to deployment.
Pre-training builds the base model, fine-tuning adapts it to a task, and deployment puts the finished model into production; none of these is where accuracy testing happens.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 164: aif-q340

Which of the following is NOT a stage of the foundation model (FM) lifecycle?

- **A.** Fine-tuning
- **B.** Marketing
- **C.** Pre-training
- **D.** Deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Marketing

**Explanation:**

Marketing is a business activity and is not part of the technical FM lifecycle, which covers stages such as data selection, pre-training, fine-tuning, evaluation, and deployment.
Fine-tuning, pre-training, and deployment are all genuine lifecycle stages, so none of them is the correct answer to what is NOT a stage.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 165: aif-q342

In generative AI, what is prompt engineering?

- **A.** A method for compressing models to run faster
- **B.** The process of crafting effective input prompts to guide a model's outputs
- **C.** A technique for designing a model's neural network architecture
- **D.** The process of labeling training data for supervised learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. The process of crafting effective input prompts to guide a model's outputs

**Explanation:**

Prompt engineering is the practice of designing and refining input prompts, for example by adding context, constraints, or examples, to guide a generative model toward accurate, relevant outputs.
It is not model compression, not the design of a neural network architecture, and not the labeling of training data.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 166: aif-q376

A development team is building a customer support assistant on Amazon Bedrock. The assistant must remember account details from earlier in the conversation, reference relevant help articles, and follow company guidelines. Which concept describes managing all of this information that is fed to the foundation model?

- **A.** Prompt engineering
- **B.** Context engineering
- **C.** Model distillation
- **D.** Continuous pre-training

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Context engineering

**Explanation:**

Context engineering is the practice of managing the full set of information provided to a foundation model at inference time, including conversation history, retrieved documents, system instructions, and any other relevant data, so the model produces accurate, grounded responses that account for all necessary context.
Prompt engineering focuses specifically on crafting the instruction or query text itself, whereas context engineering encompasses the broader strategy of assembling all relevant information the model needs. Model distillation compresses a larger model into a smaller one for efficiency. Continuous pre-training updates a model's knowledge by training on new data over time, not by managing runtime context.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 167: aif-q377

A legal firm's AI assistant on Amazon Bedrock must combine the user's question, relevant contract clauses retrieved from a knowledge base, the firm's compliance rules, and the conversation history into a single model call. Which practice governs how these elements are assembled and prioritized?

- **A.** Fine-tuning
- **B.** Hyperparameter tuning
- **C.** Context engineering
- **D.** Feature engineering

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Context engineering

**Explanation:**

Context engineering governs how all the information elements, such as retrieved documents, system rules, user input, and conversation history, are assembled, prioritized, and structured before being passed to the model, ensuring it has the right context to answer accurately.
Fine-tuning updates model weights with new training data and does not control what is passed at inference time. Hyperparameter tuning adjusts training configuration settings like learning rate and batch size. Feature engineering transforms raw data into model inputs during the ML training pipeline, not at inference time for a foundation model.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 168: aif-q378

What is the role of Model Context Protocol (MCP) in agentic AI systems?

- **A.** It compresses models to reduce inference latency
- **B.** It provides a standard interface for connecting AI agents to external tools and data sources
- **C.** It encrypts model weights during training
- **D.** It measures model accuracy on benchmark datasets

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. It provides a standard interface for connecting AI agents to external tools and data sources

**Explanation:**

Model Context Protocol (MCP) provides a standardized interface that allows AI agents to connect to external tools, APIs, and data sources in a consistent way, enabling them to retrieve information and take actions across different systems without custom integrations for each one.
Model compression for reduced latency describes techniques like quantization or distillation. Encrypting model weights is a security practice handled by services like AWS KMS. Measuring accuracy on benchmarks is model evaluation. None of these describes a protocol for agent-to-tool connectivity.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 169: aif-q379

A financial services company wants multiple specialized AI agents to collaborate on complex customer requests. One agent handles account queries, another processes transactions, and a third checks compliance. Which agentic AI concept does this architecture represent?

- **A.** Single-agent reinforcement learning
- **B.** Multi-agent system pattern
- **C.** Supervised classification pipeline
- **D.** Batch inference workflow

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Multi-agent system pattern

**Explanation:**

A multi-agent system pattern uses multiple specialized AI agents that communicate and collaborate to handle complex tasks, with each agent responsible for a specific capability such as account queries, transactions, or compliance checks, which matches the architecture described.
Single-agent reinforcement learning trains one agent through environmental rewards without collaboration between multiple agents. A supervised classification pipeline assigns labels to inputs and does not involve agent collaboration. A batch inference workflow processes data in bulk offline and has no concept of multiple agents working together.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 170: aif-q380

An AI agent assists a healthcare researcher over multiple sessions spanning several days. The agent needs to recall findings from previous sessions to avoid repeating work. Which agentic AI capability enables this?

- **A.** Tool usage
- **B.** Memory management
- **C.** Workflow orchestration
- **D.** Model pre-training

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Memory management

**Explanation:**

Memory management in agentic AI allows an agent to persist and retrieve information across sessions, so it can recall previous findings, avoid redundant work, and build on past interactions over time.
Tool usage enables agents to call external APIs and services but does not handle storing and retrieving past interaction history. Workflow orchestration coordinates the sequence of steps an agent takes but does not address long-term memory. Model pre-training builds the base model's knowledge during initial training, not the ability to remember individual user sessions.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 171: aif-q383

A travel agency builds an AI agent that can search flight availability, book tickets, and process payments by calling the airline's APIs. Which agentic AI capability allows the agent to interact with these external systems?

- **A.** Memory management
- **B.** Tool usage
- **C.** Model fine-tuning
- **D.** Prompt caching

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Tool usage

**Explanation:**

Tool usage is the agentic AI capability that allows an agent to call external APIs, services, and systems to retrieve information or take actions, which is how the travel agent searches flights, books tickets, and processes payments through the airline's APIs.
Memory management stores and retrieves information across interactions but does not call external systems. Model fine-tuning updates model weights during training rather than enabling runtime API calls. Prompt caching stores frequently used prompts for efficiency but does not interact with external systems.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 172: aif-q437

A company uses an on-demand Amazon Bedrock text model priced by input and output tokens for a support chatbot. Full conversation histories are sent with every request. Which pricing behavior explains the higher charge?

- **A.** Cost is based on the number of API calls regardless of content
- **B.** Cost increases with the total number of input and output tokens processed per request
- **C.** Cost is determined by the time the model spends processing each request
- **D.** Cost depends on the number of concurrent users

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Cost increases with the total number of input and output tokens processed per request

**Explanation:**

For this on-demand text model, longer conversation histories increase the input tokens processed on each request, while generated responses contribute output tokens. The model's published input and output rates determine the charge.
This token explanation is limited to on-demand text models priced by tokens. Other Bedrock models, modalities, service tiers, and purchasing options can use different units or commitments.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-03

---

### Question 173: aif-q438

A model would naturally generate 600 output tokens, but a request sets the maximum output to 300 tokens. Which effect should the team expect?

- **A.** The response can be truncated near 300 tokens, reducing billed output tokens and often generation time
- **B.** The account token-per-minute quota is permanently lowered
- **C.** Input token charges disappear
- **D.** The model is guaranteed to finish its answer within 300 tokens

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. The response can be truncated near 300 tokens, reducing billed output tokens and often generation time

**Explanation:**

The cap cuts billed output tokens only when the model otherwise would generate more than the cap, and truncation may leave the answer incomplete. It can affect per-request quota reservation but does not change the account quota.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 174: aif-q443

Which stage of the foundation model lifecycle involves selecting the right data sources and preparing them before any model training begins?

- **A.** Deployment
- **B.** Evaluation
- **C.** Data selection
- **D.** Feedback

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Data selection

**Explanation:**

Data selection is the first stage of the foundation model lifecycle, where appropriate data sources are identified and curated before pre-training begins. The quality and breadth of selected data directly shapes what the model learns.
Deployment is a later stage where the trained model is made available for inference. Evaluation assesses model performance after training. Feedback is the final stage where user interactions inform improvements.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

## Task 2.2

Questions for this task: 14

### Question 175: aif-q010

A smart-home controller has 4 GB of available memory, no accelerator, intermittent connectivity, and a requirement for local low-latency text classification. Which approach best fits?

- **A.** Run an optimized small language model tested to fit the device
- **B.** Run an uncompressed large language model locally
- **C.** Call a remote model asynchronously for every event
- **D.** Assume any small language model will fit without measurement

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Run an optimized small language model tested to fit the device

**Explanation:**

The hardware and connectivity constraints favor a measured, optimized small model. The team must test memory, latency, power, and quality on the target hardware.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 176: aif-q134

A subscription box company runs a generative AI support chatbot and wants to measure its financial effect on operations. Which metric should the company track?

- **A.** Number of customer inquiries handled
- **B.** Cost per customer conversation
- **C.** Average handle time (AHT)
- **D.** Cost of training the AI models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Cost per customer conversation

**Explanation:**

Cost per customer conversation directly quantifies the operational expense of using the chatbot, so the company can measure its financial effect and compare it to alternatives such as human agents.
The number of inquiries handled measures volume, not cost. Average handle time measures efficiency and speed. The cost of training the models is a one-time build cost, not the ongoing operational cost of conversations.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 177: aif-q201

A company needs a generative AI model for an app that must answer users in real time. Which model characteristic matters most?

- **A.** Model complexity
- **B.** Inference speed
- **C.** Training time
- **D.** Innovation speed

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Inference speed

**Explanation:**

Inference speed determines how quickly the model generates a response, so it is the key characteristic for a real-time application where users need answers with low latency.
Model complexity affects capability and cost but not directly the real-time requirement. Training time is a one-time build concern. Innovation speed describes how fast a model family evolves, none of which governs real-time response latency.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 178: aif-q282

An online store uses a generative AI assistant on Amazon Bedrock to recommend products and wants to measure its direct impact on sales. Which metric meets this requirement?

- **A.** The number of customer interactions with the AI assistant
- **B.** Sentiment analysis scores from customer feedback after interactions
- **C.** The conversion rate of customers who purchase after interacting with the AI assistant
- **D.** Natural language understanding accuracy rates

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. The conversion rate of customers who purchase after interacting with the AI assistant

**Explanation:**

Conversion rate, the share of customers who buy after interacting with the assistant, ties assistant engagement directly to sales outcomes, so it measures the direct impact on sales.
The number of interactions measures usage volume, not sales. Sentiment scores measure customer mood. Natural language understanding accuracy measures technical quality. None of these directly measures sales impact.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 179: aif-q298

A company is comparing Amazon Nova models on Amazon Bedrock and needs a multimodal model that supports several languages. Which Nova model meets these requirements MOST cost-effectively?

- **A.** Nova Pro
- **B.** Nova Lite
- **C.** Nova Canvas
- **D.** Nova Reel

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Nova Lite

**Explanation:**

Amazon Nova Lite is a low-cost multimodal model that supports multiple languages, so it meets the multimodal and multilingual requirements as the most cost-effective Nova option.
Amazon Nova Pro is also multimodal but is a higher-cost, higher-capability model. Amazon Nova Canvas generates images and Amazon Nova Reel generates video, so these single-purpose generation models are not cost-effective multilingual multimodal choices.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 180: aif-q336

What is a primary advantage of the adaptability of generative AI?

- **A.** It can work only with structured data
- **B.** It always produces perfect results
- **C.** It can handle a wide range of tasks and domains
- **D.** It removes the need for any human oversight

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. It can handle a wide range of tasks and domains

**Explanation:**

Adaptability means a generative model can be applied to a wide range of tasks and domains, which is its key advantage.
Generative AI is not limited to structured data, it does not always produce perfect results, and it does not remove the need for human oversight; these claims misstate its capabilities.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 181: aif-q077

An AI practitioner uses a large language model to write marketing copy. The output sounds plausible and factual but is actually incorrect. Which problem is the model exhibiting?

- **A.** Data leakage
- **B.** Hallucination
- **C.** Overfitting
- **D.** Underfitting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Hallucination

**Explanation:**

Hallucination is when a large language model produces content that sounds plausible and factual but is actually incorrect or fabricated, which matches the marketing copy described.
Data leakage is the unintended exposure of information, overfitting is when a model memorizes training data and generalizes poorly, and underfitting is when a model is too simple to capture patterns. None of these describes confidently stated but false output.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 182: aif-q180

A company has an application that ingests consumer complaints from public sources and processes them with complex hard-coded rules. The company wants to scale this logic across new markets and product lines. Which advantage of generative AI models applies to this scenario?

- **A.** Predictable outputs
- **B.** Adaptability
- **C.** Reduced sensitivity to input changes
- **D.** Explainability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Adaptability

**Explanation:**

Adaptability is the generative AI advantage that applies here: the models can generalize learned patterns to new markets and product lines with little manual reconfiguration, avoiding the need to rewrite complex hard-coded rules.
Predictable outputs and reduced sensitivity to input changes are not strengths of generative AI, which is nondeterministic and sensitive to input wording. Explainability is unrelated to scaling the complaint-processing logic.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 183: aif-q302

An AI practitioner notices that a large language model returns different responses each time it receives the same input. Which risk of AI does this describe?

- **A.** Hallucinations
- **B.** Nondeterminism
- **C.** Accuracy
- **D.** Multimodality

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Nondeterminism

**Explanation:**

Nondeterminism is the property by which a large language model can return different responses to the same input because of randomness in how it generates text, which matches the observed behavior.
Hallucinations are fabricated but plausible outputs, accuracy concerns correctness, and multimodality is the ability to work across data types such as text and images. None of these describes varying responses to identical inputs.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 184: aif-q337

In the context of generative AI, what is a hallucination?

- **A.** A visual output produced by the model
- **B.** A type of model architecture
- **C.** An incorrect or fabricated output presented as fact
- **D.** A method of training a model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. An incorrect or fabricated output presented as fact

**Explanation:**

A hallucination is an output that is incorrect or fabricated but is presented by the model as if it were factual.
A hallucination is not a visual output, a type of model architecture, or a method of training a model. These options describe unrelated concepts.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 185: aif-q343

Which of the following is a potential disadvantage of generative AI solutions?

- **A.** Adaptability
- **B.** Responsiveness
- **C.** Inaccuracy
- **D.** Simplicity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Inaccuracy

**Explanation:**

Inaccuracy is a known disadvantage of generative AI, which can produce incorrect, biased, or fabricated information that requires validation and human oversight.
Adaptability and responsiveness are advantages of generative AI, and simplicity is not a disadvantage. None of these represents a drawback of generative AI solutions.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 186: aif-q441

A retailer wants to test whether its chatbot increased average revenue per user (ARPU). Which measurement design supports that attribution?

- **A.** Compare ARPU for randomly assigned chatbot and control groups over the same period
- **B.** Compare post-launch ARPU with no baseline or control
- **C.** Track model parameter count
- **D.** Track inference latency

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Compare ARPU for randomly assigned chatbot and control groups over the same period

**Explanation:**

A concurrent randomized control group supports a causal estimate of the chatbot's effect on ARPU. A before-and-after increase alone may reflect other changes.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 187: aif-q442

A company uses a generative AI assistant to help its support team and wants to measure operational efficiency gains. Which metric should it track?

- **A.** ROUGE score
- **B.** Efficiency measured as reduction in average handle time per case
- **C.** BERTScore
- **D.** Model perplexity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Efficiency measured as reduction in average handle time per case

**Explanation:**

Reduction in average handle time per case directly measures how much faster agents resolve issues with the AI assistant's help, which is an operational efficiency gain and a business value metric for GenAI applications.
ROUGE and BERTScore measure generated text quality against references. Model perplexity measures language-modeling fit. None of these captures operational efficiency.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 188: aif-q450

A company invested in a generative AI solution to automate report writing. Which metric best measures whether this investment delivered financial value?

- **A.** Return on investment (ROI)
- **B.** Model accuracy
- **C.** Number of model parameters
- **D.** Training data volume

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Return on investment (ROI)

**Explanation:**

Return on investment (ROI) measures whether the financial benefits of the AI solution, such as labor savings and faster output, exceed the costs of building and running it, which directly shows whether the investment delivered financial value.
Model accuracy measures prediction quality but not financial return. Number of parameters and training data volume are technical details unrelated to business value.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

## Task 2.3

Questions for this task: 24

### Question 189: aif-q012

A fintech engineering team plans to adopt Amazon Q Developer to ship features faster. What can Amazon Q Developer do to help the team?

- **A.** Run an application without provisioning or managing servers
- **B.** Convert audio files into text documents by using ML models
- **C.** Generate code snippets and provide reference tracking and open source license tracking
- **D.** Enable voice commands for coding and natural-language search

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Generate code snippets and provide reference tracking and open source license tracking

**Explanation:**

Amazon Q Developer boosts developer productivity by generating code snippets and providing reference tracking and open source license tracking.
Running an application without provisioning or managing servers describes serverless compute such as AWS Lambda. Converting audio files into text describes Amazon Transcribe. Enabling voice commands for coding is not a function of Amazon Q Developer.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Q
- Last verified by source: 2026-06-02

---

### Question 190: aif-q032

A small studio wants to prototype on Amazon Bedrock on a tight budget and avoid any long-term commitment. Which Amazon Bedrock pricing model fits?

- **A.** Provisioned Throughput
- **B.** Model customization
- **C.** On-Demand
- **D.** Spot Instances

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. On-Demand

**Explanation:**

The On-Demand pricing model charges only for what is used with no upfront or long-term commitment, which fits a limited budget that needs flexibility.
Provisioned Throughput requires committing to and paying for a fixed capacity level over time. Model customization is a fine-tuning activity, not a flexible pricing option. Spot Instances are an Amazon EC2 pricing concept and are not an Amazon Bedrock pricing model.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 191: aif-q033

A data-science team wants to stand up a foundation model (FM) quickly inside its own VPC. Which AWS service or feature lets the team do that?

- **A.** Amazon Personalize
- **B.** PartyRock, an Amazon Bedrock Playground
- **C.** Amazon SageMaker JumpStart
- **D.** Amazon SageMaker AI endpoints

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker JumpStart

**Explanation:**

Amazon SageMaker JumpStart offers pre-built foundation models that a team can deploy quickly inside its own VPC and begin using right away, which matches the requirement.
Amazon Personalize is a recommendation service, not an FM-deployment feature. PartyRock is a public playground for experimenting with apps, not for deploying FMs in a VPC. Amazon SageMaker AI endpoints host models for inference, but they do not provide a curated catalog of pre-built foundation models ready to deploy with a few clicks, which is the value JumpStart adds.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon SageMaker JumpStart, Amazon Personalize, Amazon Bedrock, Amazon SageMaker AI
- Last verified by source: 2026-06-02

---

### Question 192: aif-q050

A company summarizes contracts with an Amazon Bedrock base model and has now trained a custom model for better quality. What must the company do to use the custom model in Amazon Bedrock?

- **A.** Deploy the custom model to an Amazon SageMaker AI endpoint for real-time inference
- **B.** Register the model in the Amazon SageMaker Model Registry
- **C.** Request model access for the custom model in Amazon Bedrock
- **D.** Purchase Provisioned Throughput for the custom model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Purchase Provisioned Throughput for the custom model

**Explanation:**

To run a custom (fine-tuned) model in Amazon Bedrock, the company must purchase Provisioned Throughput for that model, which allocates the dedicated capacity Bedrock requires to serve custom models.
Deploying to a SageMaker AI endpoint or registering in the SageMaker Model Registry are Amazon SageMaker workflows, not how Bedrock serves a custom model. Requesting model access applies to Bedrock base models, not to using your own custom model.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon SageMaker AI
- Last verified by source: 2026-06-02

---

### Question 193: aif-q074

A retail analyst wants to ask natural-language questions about sales data and receive AI-assisted visuals and summaries. Which AWS service fits?

- **A.** Amazon Quick
- **B.** Amazon Q Developer
- **C.** AWS Chatbot
- **D.** Amazon EC2

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Quick

**Explanation:**

Amazon Quick provides AI-assisted business analysis and natural-language interaction with business data.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Quick
- Last verified by source: 2026-11-03

---

### Question 194: aif-q085

A company customized an Amazon Bedrock foundation model (FM) and now needs to upload a dataset for Bedrock to validate the model's answers. Which AWS service should hold that dataset?

- **A.** Amazon Elastic Block Store (Amazon EBS)
- **B.** AWS Snowcone
- **C.** Amazon S3
- **D.** Amazon Elastic File System (Amazon EFS)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon S3

**Explanation:**

Amazon S3 is the scalable object storage service that integrates with Amazon Bedrock, so it is the right place to upload and store the validation dataset for Bedrock to use.
Amazon EBS provides block storage for EC2 volumes, Amazon EFS provides shared file storage for instances, and AWS Snowcone is an edge data-transfer device. None of these is the storage service that Bedrock reads datasets from.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon S3, Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 195: aif-q099

A developer is working in Kiro on an AWS data-integration project. The developer wants help drafting a Glue job script from a written specification, then plans to review and test the code before use. Which tool fits this development scenario?

- **A.** AWS Config
- **B.** Amazon Comprehend
- **C.** Kiro
- **D.** Amazon Personalize

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Kiro

**Explanation:**

Kiro is an AI-powered development environment that can help create and explain code from project context and developer instructions. The developer remains responsible for reviewing, testing, and securing the generated Glue job before deployment.
AWS Config tracks resource configuration, Amazon Comprehend analyzes text, and Amazon Personalize builds recommendations. They do not provide the coding workflow described in the stem.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Kiro, AWS Glue, AWS Config, Amazon Personalize, Amazon Comprehend
- Last verified by source: 2026-11-03

---

### Question 196: aif-q129

A developer wants a service that offers foundation models (FMs) for building and scaling generative AI applications. Which AWS service provides this?

- **A.** Amazon Q Developer
- **B.** Amazon Kendra
- **C.** Amazon Bedrock
- **D.** Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Bedrock

**Explanation:**

Amazon Bedrock gives access to foundation models from AWS and third parties through a managed service, so users can build and scale generative AI applications without managing infrastructure.
Amazon Q Developer is a coding assistant. Amazon Kendra is an intelligent enterprise search service. Amazon Comprehend is an NLP service. None of these provides foundation models for building generative AI apps.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Q Developer, Amazon Kendra, Amazon Comprehend
- Last verified by source: 2026-06-02

---

### Question 197: aif-q138

A call-center team manually gives customers location-based product tips and wants foundation models (FMs) to automate it. Which AWS service meets this need?

- **A.** Amazon Macie
- **B.** Amazon Bedrock
- **C.** Amazon Textract
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock

**Explanation:**

Amazon Bedrock lets the company use foundation models to generate product descriptions and location-based recommendations without managing infrastructure, which automates the task.
Amazon Macie discovers and protects sensitive data. Amazon Textract extracts text from documents. Amazon Transcribe converts speech to text. None of these provides foundation models to generate recommendations.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Macie, Amazon Transcribe, Amazon Textract
- Last verified by source: 2026-06-02

---

### Question 198: aif-q168

A newsroom is piloting a generative AI writing aide. Pilot traffic is light, performance is not a concern, and future usage is unpredictable; the newsroom wants the lowest cost. Which solution meets these requirements?

- **A.** Use GPU-powered Amazon EC2 instances
- **B.** Use Amazon Bedrock with On-Demand pricing
- **C.** Use Amazon Bedrock with Provisioned Throughput
- **D.** Use Amazon SageMaker JumpStart

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use Amazon Bedrock with On-Demand pricing

**Explanation:**

Amazon Bedrock with On-Demand pricing charges only for the inference calls actually made, with no capacity commitment, so it keeps costs low during a small pilot and scales elastically with unpredictable future demand.
GPU-powered EC2 instances incur ongoing costs whether or not they are used. Provisioned Throughput requires paying for committed capacity that low, unpredictable usage would waste. Amazon SageMaker JumpStart still requires provisioning and managing hosting capacity, which is not the most cost-effective for this case.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon EC2, Amazon SageMaker JumpStart
- Last verified by source: 2026-06-02

---

### Question 199: aif-q174

A company needs reserved model capacity and consistent throughput for a supported Amazon Bedrock model. Which purchasing option meets the capacity requirement?

- **A.** Provisioned Throughput
- **B.** On-Demand inference
- **C.** Amazon EC2 Spot Instances
- **D.** Prompt caching

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Provisioned Throughput

**Explanation:**

Provisioned Throughput supplies purchased model capacity. The stem does not claim it costs less than On-Demand; the team must compare current pricing and utilization.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 200: aif-q242

A company wants employees to ask natural-language questions about authorized enterprise data and receive answers that respect source permissions. Which current AWS offering fits?

- **A.** Amazon Rekognition
- **B.** Amazon Textract
- **C.** Amazon Quick
- **D.** Amazon Lex

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Quick

**Explanation:**

Amazon Quick provides AI-assisted work with enterprise data, including natural-language questions and responses based on information the user can access. Amazon Q Business is no longer open to new customers, and AWS directs new customers to Amazon Quick for similar capabilities.
Amazon Rekognition analyzes images and video, Amazon Textract extracts document text, and Amazon Lex builds conversational interfaces without providing this managed enterprise-data experience by itself.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Quick, Amazon Rekognition, Amazon Textract, Amazon Lex
- Last verified by source: 2026-11-03

---

### Question 201: aif-q250

A team wants a managed console interface for hands-on experiments with foundation-model prompts and inference settings before writing application code. Which option fits?

- **A.** AWS Config
- **B.** Amazon Bedrock playgrounds
- **C.** AWS Audit Manager
- **D.** Amazon S3 Storage Lens

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock playgrounds

**Explanation:**

Amazon Bedrock playgrounds provide console interfaces for testing supported text, chat, image, and video models and changing inference settings. The team should review the selected model's current pricing because playground inference can incur charges.
AWS Config records resource configuration, Audit Manager collects audit evidence, and S3 Storage Lens reports storage usage. They do not provide model experimentation interfaces.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, AWS Config, AWS Audit Manager, Amazon S3
- Last verified by source: 2026-11-03

---

### Question 202: aif-q295

Which current AWS offering provides AI-assisted business analysis, natural-language interaction with enterprise information, and document or visual creation?

- **A.** Amazon SageMaker AI model training
- **B.** Amazon S3 object storage
- **C.** Amazon Quick
- **D.** Amazon CloudWatch infrastructure monitoring

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Quick

**Explanation:**

Amazon Quick provides AI-assisted analysis and work with enterprise information through natural-language interaction, business insights, and content creation. Amazon Q Business is no longer open to new customers, and AWS directs new customers to Amazon Quick for similar capabilities.
SageMaker AI trains and deploys ML models, Amazon S3 stores objects, and CloudWatch monitors systems. Those services do not provide the combined business-assistance experience described here.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Quick, Amazon SageMaker AI, Amazon S3, Amazon CloudWatch
- Last verified by source: 2026-11-03

---

### Question 203: aif-q309

A developer works in Kiro and wants assistance drafting a test case and documentation for existing code. Which option requires the least setup while keeping the developer responsible for reviewing and validating the result?

- **A.** Upload the code to an unapproved public coding service
- **B.** Use Kiro in the development environment, then review and run the generated test
- **C.** Build a new foundation-model application first
- **D.** Write both artifacts without development-tool assistance

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use Kiro in the development environment, then review and run the generated test

**Explanation:**

Kiro can draft code, tests, and documentation from the project context, which avoids building a separate AI application. Generated output can contain errors, so the developer must inspect the documentation and execute the test against the intended behavior.
An unapproved public service creates data-handling risk. Building a separate model application requires more setup, while writing everything without assistance does not meet the least-setup condition.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Kiro
- Last verified by source: 2026-11-03

---

### Question 204: aif-q338

Which AWS service is designed specifically for developing generative AI applications?

- **A.** Amazon EC2
- **B.** Amazon Bedrock
- **C.** Amazon S3
- **D.** Amazon RDS

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock

**Explanation:**

Amazon Bedrock is purpose-built for generative AI, providing access to foundation models and tools to build and scale generative AI applications.
Amazon EC2 provides general compute, Amazon S3 provides object storage, and Amazon RDS provides managed relational databases; none is specifically designed for developing generative AI applications.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon EC2, Amazon S3, Amazon RDS
- Last verified by source: 2026-06-02

---

### Question 205: aif-q341

What is a primary advantage of using AWS generative AI services to build applications?

- **A.** They are always free
- **B.** They guarantee 100% accuracy
- **C.** They lower the barrier to entry
- **D.** They remove the need for any coding

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. They lower the barrier to entry

**Explanation:**

AWS generative AI services provide managed infrastructure, pre-trained foundation models, and APIs, which lower the barrier to entry by removing the need to build and train large models from scratch.
These services are not always free, they do not guarantee perfect accuracy, and they do not remove the need for any coding; those statements overstate what the services provide.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 206: aif-q289

What is the primary benefit of Amazon SageMaker JumpStart?

- **A.** It reduces inference costs
- **B.** It provides access to pre-trained models and solutions
- **C.** It automatically tunes model hyperparameters
- **D.** It manages data labeling with a human workforce

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. It provides access to pre-trained models and solutions

**Explanation:**

Amazon SageMaker JumpStart provides access to pre-trained models, built-in algorithms, and end-to-end solutions, which speeds up the start of machine learning and generative AI projects.
Reducing inference cost, hyperparameter tuning, and managed human labeling are handled by other capabilities, such as SageMaker Automatic Model Tuning and SageMaker Ground Truth Plus.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon SageMaker JumpStart
- Last verified by source: 2026-06-02

---

### Question 207: aif-q353

A team wants to use Amazon-developed Nova foundation models through a managed AWS service. Which pairing is correct?

- **A.** Amazon Bedrock provides access to Amazon Nova models
- **B.** Amazon Quick hosts Amazon Nova model endpoints
- **C.** AWS Glue provides Amazon Nova inference
- **D.** Amazon Kendra trains Amazon Nova models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Bedrock provides access to Amazon Nova models

**Explanation:**

Amazon Bedrock is the managed service that provides access to Amazon Nova foundation models. Amazon Nova is the model family, not a separate model-hosting service.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Nova
- Last verified by source: 2026-11-03

---

### Question 208: aif-q381

A startup wants to build custom AI agents using an open-source Python SDK that supports tool use, multi-agent orchestration, and integration with multiple model providers. Which AWS service meets this requirement?

- **A.** Amazon Personalize
- **B.** Amazon Comprehend
- **C.** Strands Agents
- **D.** Amazon Lex

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Strands Agents

**Explanation:**

Strands Agents is an open-source Python SDK from AWS that lets developers build AI agents with tool use, multi-agent orchestration, and flexibility to work with different model providers, which matches what the startup needs.
Amazon Personalize generates recommendations from user behavior data. Amazon Comprehend performs Natural Language Processing tasks like sentiment analysis. Amazon Lex builds conversational chatbots and voice interfaces. None of these provides an open-source SDK for building custom AI agents with multi-agent orchestration.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Strands Agents, Amazon Personalize, Amazon Comprehend, Amazon Lex
- Last verified by source: 2026-06-03

---

### Question 209: aif-q382

An enterprise wants managed infrastructure to deploy, scale, and monitor its AI agents in production without handling the underlying compute and networking. Which AWS service meets this requirement?

- **A.** Amazon Bedrock AgentCore
- **B.** Amazon SageMaker Canvas
- **C.** Amazon Kendra
- **D.** Amazon Polly

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Bedrock AgentCore

**Explanation:**

Amazon Bedrock AgentCore provides managed infrastructure for deploying, scaling, and monitoring AI agents in production, handling the compute, networking, and operational concerns so the enterprise can focus on agent logic rather than infrastructure management.
Amazon SageMaker Canvas is a no-code interface for building ML models. Amazon Kendra provides intelligent enterprise search. Amazon Polly converts text to speech. None of these provides managed infrastructure specifically for running AI agents in production.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock AgentCore, Amazon SageMaker Canvas, Amazon Kendra, Amazon Polly
- Last verified by source: 2026-06-03

---

### Question 210: aif-q439

A startup with no ML infrastructure wants to launch a generative AI feature quickly. Which advantage of using AWS GenAI services like Amazon Bedrock is most relevant?

- **A.** The startup must train its own foundation model from scratch
- **B.** AWS GenAI services lower the barrier to entry by providing managed access to pre-trained foundation models
- **C.** AWS GenAI services require the startup to manage GPU clusters
- **D.** AWS GenAI services are only available to enterprise customers

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. AWS GenAI services lower the barrier to entry by providing managed access to pre-trained foundation models

**Explanation:**

AWS GenAI services like Amazon Bedrock provide managed access to pre-trained foundation models through APIs, which lowers the barrier to entry by removing the need to train models, manage infrastructure, or procure GPUs, letting the startup launch quickly.
The startup does not need to train its own model because pre-trained models are available. AWS manages the infrastructure so the startup does not manage GPU clusters. These services are available to all customers, not only enterprises.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-03

---

### Question 211: aif-q440

A regulated company is building an AI workload on AWS. Which statement correctly describes AWS compliance programs and controls?

- **A.** They provide infrastructure controls and evidence that can support the customer's compliance work
- **B.** They certify every customer workload automatically
- **C.** They transfer all compliance responsibility to AWS
- **D.** They remove the need to assess application configuration and data handling

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. They provide infrastructure controls and evidence that can support the customer's compliance work

**Explanation:**

AWS compliance programs and controls can support a customer's compliance work. The customer must still assess the workload, configuration, data, and obligations under the shared responsibility model.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---


---

### Question 212: aif-q460

Match each current AWS offering to its primary use.

**Offerings**

- **A.** Amazon Bedrock
- **B.** Amazon SageMaker JumpStart
- **C.** Amazon Quick
- **D.** Kiro

**Purposes**

- **1.** Build and operate custom generative AI applications with managed access to foundation models
- **2.** Discover and deploy pre-trained models through Amazon SageMaker AI
- **3.** Ask business questions, analyze information, and create AI-assisted insights
- **4.** Develop software with an AI coding environment and spec-driven workflows

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A → 1; B → 2; C → 3; D → 4

**Explanation:**

Amazon Bedrock provides managed foundation-model access and application capabilities. SageMaker JumpStart supplies pre-trained models and solution templates in SageMaker AI. Amazon Quick supports business analysis and AI-assisted work. Kiro supports software development, including spec-driven workflows.

</details>

**Question metadata**

- Domain: 2
- Task statement: 2.3
- Format: matching
- Services: Amazon Bedrock, Amazon SageMaker JumpStart, Amazon Quick, Kiro
- Last verified by source: 2026-11-03

---

# Domain 3: Applications of foundation models

Questions in this domain: 105

## Task 3.1

Questions for this task: 43

### Question 213: aif-q459

A team is building a Retrieval Augmented Generation (RAG) application on AWS to ground a foundation model in their internal documents. Arrange the steps of preparing and querying the knowledge base from first to last.

- **A.** Convert each text chunk into a numerical vector embedding using an embedding model
- **B.** Retrieve the most relevant chunks for a user question and pass them to the foundation model to generate a grounded answer
- **C.** Ingest the source documents from the data store and split them into smaller text chunks
- **D.** Store the embeddings in a vector database so they can be searched by similarity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Ingest the source documents from the data store and split them into smaller text chunks → A. Convert each text chunk into a numerical vector embedding using an embedding model → D. Store the embeddings in a vector database so they can be searched by similarity → B. Retrieve the most relevant chunks for a user question and pass them to the foundation model to generate a grounded answer

**Explanation:**

RAG first ingests the source documents and splits them into smaller chunks, then converts each chunk into a vector embedding, then stores those embeddings in a vector database that supports similarity search. Only after the knowledge base is indexed can the application, at query time, retrieve the most relevant chunks for a user question and feed them to the foundation model to generate a grounded answer.
The key idea is that indexing happens once up front while retrieval happens on every query, so storing embeddings must come before any search. A tempting mistake is to retrieve before embedding and storing, but you cannot search by similarity until the chunks have been embedded and indexed.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: ordering
- Services: None listed
- Last verified by source: 2026-11-03


---

### Question 214: aif-q021

An engineering team wants to use Amazon OpenSearch Service as the backbone of a vector search application. Which capability makes this possible?

- **A.** Full-text keyword (BM25) search and ranking
- **B.** Geospatial indexing and queries
- **C.** k-NN nearest neighbor search over high-dimensional vectors
- **D.** Cross-cluster replication for disaster recovery

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. k-NN nearest neighbor search over high-dimensional vectors

**Explanation:**

k-NN nearest neighbor search lets Amazon OpenSearch Service index embeddings and return the vectors most similar to a query, which is the core of a vector database application such as semantic search.
BM25 full-text search matches keywords rather than semantic vectors; geospatial indexing handles location data; cross-cluster replication supports availability and disaster recovery. None provides vector similarity search.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-06-02

---

### Question 215: aif-q038

A logistics company runs an Amazon Titan model on Amazon Bedrock and wants the model's answers to draw on its internal shipping documents. Which solution adds this private context?

- **A.** Fine-tune the FM on the internal documents
- **B.** Create an Amazon Bedrock knowledge base over the internal documents
- **C.** Lower the temperature value
- **D.** Switch to a larger foundation model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Create an Amazon Bedrock knowledge base over the internal documents

**Explanation:**

An Amazon Bedrock knowledge base indexes the internal documents and retrieves the relevant passages at query time (RAG), so the Titan model grounds its answers in the company's private data without any training.
Fine-tuning can embed knowledge but is costlier and static, so it is not the targeted way to supplement answers with frequently used documents; lowering the temperature only reduces randomness; switching to a larger model adds capability but still gives it no access to the private documents.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Bedrock Knowledge Bases
- Last verified by source: 2026-06-02

---

### Question 216: aif-q046

An appliance maker wants a chat interface over its PDF product manuals using large language models (LLMs) on Amazon Bedrock, at the lowest cost. Which approach fits best?

- **A.** Add all the manuals to every prompt as context
- **B.** Upload the manuals to an Amazon Bedrock knowledge base and retrieve only the relevant passages per query
- **C.** Fine-tune a model on the manuals and serve the fine-tuned model
- **D.** Continuously pre-train the base model on the manual content

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Upload the manuals to an Amazon Bedrock knowledge base and retrieve only the relevant passages per query

**Explanation:**

A knowledge base retrieves just the passages relevant to each question, so the model gets the right context cheaply, without paying to send whole manuals every time or to train the model.
Pasting all manuals into every prompt inflates token costs; fine-tuning adds training cost and must be redone when manuals change; continuous pre-training on the corpus is the most expensive option and unnecessary for a Q&A interface.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Bedrock Knowledge Bases
- Last verified by source: 2026-06-02

---

### Question 217: aif-q076

A team sends a daily few-shot prompt with 10 examples to a base model on Amazon Bedrock. The model performs well, but the team wants to cut the monthly cost. Which change helps?

- **A.** Purchase Provisioned Throughput for the model
- **B.** Reduce the number of examples and tokens in the prompt
- **C.** Fine-tune the model so the examples are no longer needed in the prompt
- **D.** Move the workload to a larger, more capable model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Reduce the number of examples and tokens in the prompt

**Explanation:**

Because cost scales with the tokens processed, trimming the number of examples and tokens in the prompt lowers the bill while the model keeps performing well.
Provisioned Throughput is meant for high, steady volume and would cost more for a once-a-day job; fine-tuning removes in-prompt examples but adds training cost; moving to a larger model increases the per-call cost.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 218: aif-q097

A company uses Retrieval Augmented Generation (RAG) with Amazon Bedrock and Stable Diffusion to create product images, but the results are random and miss requested details. The team wants the images to follow the prompts more closely. Which change helps?

- **A.** Increase the number of generation steps
- **B.** Increase the classifier-free guidance (CFG) scale
- **C.** Set a fixed random seed
- **D.** Increase the negative prompt weight

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Increase the classifier-free guidance (CFG) scale

**Explanation:**

The CFG scale controls how strongly the model follows the text prompt, so raising it makes the generated image adhere more closely to the requested details.
More generation steps mainly refine denoising quality; a fixed seed only makes results reproducible; increasing the negative prompt weight strengthens what to avoid rather than how closely the image matches the main prompt.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 219: aif-q098

A telecom company wants an LLM chatbot that gives support agents real-time answers grounded in internal policy documents, at the lowest cost. Which approach fits best?

- **A.** Fine-tune the LLM on the policy documents
- **B.** Implement Retrieval Augmented Generation (RAG) over the policy documents
- **C.** Pre-train a new model from scratch on the policy corpus
- **D.** Paste all policy documents into every prompt as context

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Implement Retrieval Augmented Generation (RAG) over the policy documents

**Explanation:**

RAG retrieves the relevant policy passages at query time and grounds the chatbot's answers in them, delivering accurate responses cheaply with no training.
Fine-tuning adds training cost and must be repeated as policies change; pre-training from scratch is by far the most expensive option; pasting all documents into every prompt drives up token costs.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 220: aif-q119

A company is designing a new insurance assistant that must query an authorized live claims API and answer from stored claim documents. Which current Amazon Bedrock design fits?

- **A.** An Amazon Bedrock AgentCore Harness agent with an AgentCore Gateway claims tool and access to retrieved claim documents
- **B.** A Knowledge Base alone for live transactions and documents
- **C.** A guardrail that calls the claims API
- **D.** A model fine-tuned on periodic claim exports

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. An Amazon Bedrock AgentCore Harness agent with an AgentCore Gateway claims tool and access to retrieved claim documents

**Explanation:**

For a new design, AgentCore Harness can run the configured agent, while AgentCore Gateway exposes the authorized claims API as a discoverable tool. The application can also supply retrieved document context. Gateway authentication, tool authorization, and request validation must enforce the caller's permissions.
A Knowledge Base does not perform live claims transactions. Guardrails evaluate content policies rather than call business APIs, and periodic fine-tuning cannot provide current claim status.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock AgentCore Harness, Amazon Bedrock AgentCore Gateway, Amazon Bedrock Knowledge Bases
- Last verified by source: 2026-11-03

---

### Question 221: aif-q143

A retailer runs an AI assistant that helps agents answer frequently asked questions, but the questions keep changing. Agents type a question and need an up-to-date generated answer at the lowest cost. Which approach fits?

- **A.** Use Retrieval Augmented Generation (RAG) with prompt engineering
- **B.** Fine-tune the model on a recurring schedule
- **C.** Pre-train the model on the FAQ data and benchmark it
- **D.** Embed the full FAQ set into the system prompt

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Retrieval Augmented Generation (RAG) with prompt engineering

**Explanation:**

RAG retrieves the most relevant, current information at query time and prompt engineering shapes the response, so the assistant stays accurate as questions change without repeated training cost.
Scheduled fine-tuning and pre-training both require recurring, expensive training runs; embedding the full FAQ set into every prompt drives up token costs and does not scale as the FAQ grows.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 222: aif-q146

A company wants more accurate answers from a generative AI application on Amazon Bedrock and wants the cheapest way to get them. Which approach fits?

- **A.** Fine-tune the FM
- **B.** Use prompt engineering
- **C.** Retrain the FM from scratch
- **D.** Apply model distillation to the FM

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use prompt engineering

**Explanation:**

Prompt engineering improves accuracy by refining the instructions and context with no training cost, making it the cheapest option.
Fine-tuning adds training cost and data preparation, model distillation requires a separate training process to build a smaller model, and retraining from scratch is the most expensive approach of all.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 223: aif-q155

An application summarizes books of varying lengths but fails on some of the longer ones. What is the most likely cause?

- **A.** The temperature is set too high
- **B.** The input exceeds the model's maximum context window
- **C.** The maximum output length is set too low
- **D.** The model does not support few-shot prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. The input exceeds the model's maximum context window

**Explanation:**

A model can only process a limited number of input tokens, so a book whose length exceeds the maximum context window cannot be handled in one pass, which explains why only the longer books fail.
A high temperature changes randomness, not capacity; a low maximum output length would shorten every summary rather than fail on selected books; and few-shot support is irrelevant to summarizing one long input.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 224: aif-q156

An airline is designing a new LLM assistant that must answer from flight-policy documents and use authorized tools for schedules, bookings, and payments. Which current managed approach requires the least custom orchestration code?

- **A.** Train tabular models with SageMaker Autopilot
- **B.** Fine-tune models on SageMaker JumpStart
- **C.** Configure an Amazon Bedrock AgentCore Harness agent with document retrieval and AgentCore Gateway tools
- **D.** Build a custom orchestration service around a self-hosted model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Configure an Amazon Bedrock AgentCore Harness agent with document retrieval and AgentCore Gateway tools

**Explanation:**

AgentCore Harness lets the team declare the model, instructions, and tools for a managed agent environment. AgentCore Gateway can expose approved schedule, booking, and payment APIs as authenticated tools, while retrieval supplies policy context. The team must still validate tool inputs and enforce authorization outside the model.
Autopilot targets tabular ML, JumpStart fine-tuning does not provide live business actions, and custom self-hosted orchestration requires more development work.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock AgentCore Harness, Amazon Bedrock AgentCore Gateway, Amazon Bedrock Knowledge Bases, Amazon SageMaker JumpStart
- Last verified by source: 2026-11-03

---

### Question 225: aif-q162

A publisher's Retrieval Augmented Generation (RAG) application must feel near real time, while new articles are published daily. Which two pipeline steps can run as offline batch jobs?

- **A.** Generating embeddings for each incoming user query
- **B.** Generating embeddings for the published content
- **C.** Ranking and returning results for a user's query
- **D.** Building or updating the vector search index
- **E.** Detecting the language of each user query

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Generating embeddings for the published content; D. Building or updating the vector search index

**Explanation:**

Generating content embeddings and building or updating the search index depend only on the documents, so they can run in periodic batches as new articles arrive, off the real-time path.
Generating embeddings for a user query, ranking and returning results, and detecting a query's language all happen per request and must run in real time.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 226: aif-q164

An AI practitioner must improve the accuracy of a text-generation model that depends on rapidly changing inventory data. Which technique helps most?

- **A.** Fine-tune the model on historical inventory data
- **B.** Retrieval Augmented Generation (RAG)
- **C.** Transfer learning
- **D.** Continuous pre-training on inventory snapshots

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Retrieval Augmented Generation (RAG)

**Explanation:**

RAG fetches the current inventory data at inference time and conditions generation on it, so the output reflects the latest information and stays accurate without retraining.
Fine-tuning on historical data, transfer learning, and continuous pre-training on snapshots all bake data in at training time, so they go stale as the inventory keeps changing.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 227: aif-q167

In a Retrieval Augmented Generation (RAG) workflow, what is the main purpose of chunking documents?

- **A.** To reduce the cost of storing the documents
- **B.** To improve the relevance of passages retrieved from the vector index
- **C.** To speed up training of the model
- **D.** To avoid having to generate embeddings for the documents

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. To improve the relevance of passages retrieved from the vector index

**Explanation:**

Splitting documents into smaller, semantically coherent chunks lets the retriever return only the most relevant segments for a query, improving the relevance of the context passed to the model.
Chunking is not aimed at lowering storage cost, it does not speed up model training, and chunked text is still embedded, so it does not avoid generating embeddings.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 228: aif-q173

Which statement describes an advantage of Retrieval Augmented Generation (RAG) for natural language processing (NLP) tasks?

- **A.** It speeds up training of the underlying language model
- **B.** It reduces the model's parameter count to save memory
- **C.** It draws on external knowledge sources to produce more accurate, informative responses
- **D.** It guarantees deterministic, repeatable outputs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. It draws on external knowledge sources to produce more accurate, informative responses

**Explanation:**

RAG retrieves relevant external documents at inference time and conditions generation on them, enriching responses with up-to-date, domain-specific knowledge without retraining the model.
RAG does not speed up training or reduce the model's parameter count, and it does not make a generative model's outputs deterministic.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 229: aif-q194

What are two primary use cases for storing embeddings in a vector database such as Amazon OpenSearch Service?

- **A.** Exact keyword string matching
- **B.** Semantic search over documents
- **C.** Scheduled batch ETL jobs
- **D.** Similarity-based recommendations
- **E.** Transactional primary-key lookups

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Semantic search over documents; D. Similarity-based recommendations

**Explanation:**

Semantic search and similarity-based recommendations both rely on nearest neighbor comparison of embeddings, which is exactly what a vector database provides.
Exact keyword matching is lexical rather than semantic, and primary-key lookups and scheduled batch ETL are standard database operations that do not use vector similarity.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-06-02

---

### Question 230: aif-q196

For AI applications, which two capabilities of Amazon Aurora with the pgvector extension are the most important?

- **A.** Standard SQL operations
- **B.** Vector similarity search
- **C.** Web hosting
- **D.** Combining vectors with structured data
- **E.** Email handling

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Vector similarity search; D. Combining vectors with structured data

**Explanation:**

Vector similarity search lets the application find the most semantically related content, which is the core retrieval step in tasks such as RAG, and the ability to combine vectors with structured data means those searches can run alongside existing relational records in the same database, so together these two capabilities are what make Aurora with pgvector valuable for AI workloads.
Standard SQL operations are a general database capability that is not specific to AI applications. Web hosting and email handling are not functions of Amazon Aurora at all and are unrelated to vector storage or AI workloads.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Aurora
- Last verified by source: 2026-06-01

---

### Question 231: aif-q224

A company's generative AI application uses a pre-trained foundation model (FM) on Amazon Bedrock and wants its answers to include the company's own information, at the lowest cost. Which solution fits?

- **A.** Use Amazon Bedrock Knowledge Bases
- **B.** Deploy a custom model on Amazon Bedrock
- **C.** Fine-tune the FM on the company information
- **D.** Use Amazon Bedrock Agents

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Amazon Bedrock Knowledge Bases

**Explanation:**

Amazon Bedrock Knowledge Bases index and retrieve the company's documents at inference time and inject relevant context into the prompt (RAG), adding the information cheaply with no training.
Deploying a custom model and fine-tuning the FM both add training cost; Amazon Bedrock Agents orchestrate tasks but do not, on their own, supply document context.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock Knowledge Bases, Agents for Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 232: aif-q226

A company is building an HR-policy chatbot on a large language model (LLM) with a large set of digital documents and wants to optimize the quality of its answers. Which technique fits best?

- **A.** Set the temperature to 1
- **B.** Use Retrieval Augmented Generation (RAG)
- **C.** Fine-tune the model on the policy documents
- **D.** Decrease the token size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use Retrieval Augmented Generation (RAG)

**Explanation:**

RAG retrieves precise, current passages from the policy documents at query time and grounds the chatbot's answers in them, optimizing accuracy without overloading the context window.
Setting the temperature to 1 only adds randomness; fine-tuning is costly and goes stale as policies change; decreasing the token size drops the context the model needs.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 233: aif-q237

A company is building a custom claims chatbot that must use a specific foundation model available in Amazon Bedrock and a company-managed retrieval workflow. Which option fits?

- **A.** Amazon Quick
- **B.** Amazon Bedrock with the selected model and retrieval workflow
- **C.** Amazon Transcribe
- **D.** Amazon Personalize

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock with the selected model and retrieval workflow

**Explanation:**

The explicit model-selection and custom retrieval constraints make Amazon Bedrock the defensible choice. Amazon Quick provides a managed business assistant experience rather than this custom model-level architecture.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Quick
- Last verified by source: 2026-11-03

---

### Question 234: aif-q259

A media streaming company wants natural-language image search with similarity and nearest neighbor queries, backed by a vector database. Which AWS service fits?

- **A.** Amazon DynamoDB
- **B.** Amazon OpenSearch Service
- **C.** Amazon Personalize
- **D.** Amazon RDS for MySQL

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon OpenSearch Service

**Explanation:**

Amazon OpenSearch Service supports vector storage with similarity (nearest neighbor) search, which is what natural-language image search and filtering require.
Amazon DynamoDB (key-value) and Amazon RDS for MySQL (relational) lack native vector similarity search, and Amazon Personalize generates recommendations rather than serving as a general vector store.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-06-02

---

### Question 235: aif-q271

A company needs an AI solution that produces both images and text descriptions for a product catalog and is comparing foundation models (FMs) by the output types each supports. Which FM characteristic is it evaluating?

- **A.** Latency
- **B.** Context window length
- **C.** Modality
- **D.** Multilingual support

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Modality

**Explanation:**

Modality describes the input and output types an FM supports, such as text or images, so evaluating whether a model can output both images and text descriptions is an assessment of modality.
Latency is response speed, context window length is how much input and output fit, and multilingual support concerns languages; none describes the output types a model can generate.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 236: aif-q283

Which Amazon OpenSearch Service capability finds the nearest stored embedding vectors to a query vector?

- **A.** k-nearest neighbors (k-NN) vector search
- **B.** Object lifecycle rules
- **C.** Relational joins
- **D.** Speech transcription

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. k-nearest neighbors (k-NN) vector search

**Explanation:**

OpenSearch k-NN vector search returns vectors nearest to a query under the configured similarity method. This capability supports semantic search and RAG retrieval.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-11-03

---

### Question 237: aif-q285

A company needs managed storage and similarity search for embeddings used by a RAG application. Which AWS service is one valid option?

- **A.** Amazon DynamoDB without vector features
- **B.** Amazon ElastiCache only
- **C.** Amazon OpenSearch Service
- **D.** Amazon SQS

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon OpenSearch Service

**Explanation:**

Amazon OpenSearch Service can store, index, and search embeddings. The stem asks for one valid managed vector-store option rather than claiming it is the only AWS option.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-11-03

---

### Question 238: aif-q296

Which two capabilities of Amazon OpenSearch Service are most relevant for AI/ML workloads?

- **A.** Full-text BM25 keyword search
- **B.** k-NN nearest neighbor search over vectors
- **C.** Geospatial distance queries
- **D.** Storing and indexing embeddings as a vector database
- **E.** Automated model training

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. k-NN nearest neighbor search over vectors; D. Storing and indexing embeddings as a vector database

**Explanation:**

k-NN nearest neighbor search and storing and indexing embeddings as a vector database underpin AI/ML tasks such as semantic search and RAG.
BM25 keyword search is lexical rather than semantic, geospatial queries handle location data, and OpenSearch does not perform model training.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon OpenSearch Service
- Last verified by source: 2026-06-02

---

### Question 239: aif-q301

A company is designing a new AI assistant that must evaluate approved data, invoke external APIs, and compare response options. Which current Amazon Bedrock capability provides a managed agent environment with governed tool connectivity?

- **A.** Prompt Management alone
- **B.** Knowledge Bases alone
- **C.** Amazon Bedrock AgentCore Harness with tools exposed through AgentCore Gateway
- **D.** Amazon Bedrock Model Evaluation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Bedrock AgentCore Harness with tools exposed through AgentCore Gateway

**Explanation:**

AgentCore Harness runs an agent from configured instructions, a model, and tools. AgentCore Gateway gives the agent a managed, authenticated tool surface for approved APIs or MCP servers. The tool layer must enforce authorization and validate model-generated parameters.
Prompt Management versions prompts, Knowledge Bases retrieve context, and Model Evaluation scores model or application behavior. None of them alone supplies governed external tool calls for the new design.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock AgentCore Harness, Amazon Bedrock AgentCore Gateway, Amazon Bedrock Knowledge Bases, Amazon Bedrock Model Evaluation
- Last verified by source: 2026-11-03

---

### Question 240: aif-q065

A news app runs sentiment analysis with a large language model (LLM) on Amazon Bedrock and wants the same input to yield steadier results. Which inference parameter should it change?

- **A.** Increase the temperature value
- **B.** Increase the maximum generation length
- **C.** Decrease the temperature value
- **D.** Reduce the maximum number of output tokens

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Decrease the temperature value

**Explanation:**

Lowering the temperature reduces randomness in token selection, making the model outputs more deterministic and consistent for the same input.
Raising the temperature increases randomness and variability. Changing the maximum generation length or reducing the number of output tokens only affects response length, not how consistent the responses are.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 241: aif-q110

A team is building a conversational search feature and needs a database that can store generative AI embeddings as vectors and run similarity queries over them. Which AWS service meets this requirement?

- **A.** Amazon Athena
- **B.** Amazon Redshift
- **C.** Amazon Aurora PostgreSQL
- **D.** Amazon EMR

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Aurora PostgreSQL

**Explanation:**

Amazon Aurora PostgreSQL supports the pgvector extension, which stores, indexes, and runs similarity queries over vector embeddings, making it suitable for storing and querying embeddings as vectors.
Amazon Athena is a serverless query service for data in Amazon S3. Amazon Redshift is a data warehouse for analytics. Amazon EMR runs big-data processing frameworks. None of these is designed to store and query vector embeddings for similarity search.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Aurora, Amazon Athena, Amazon Redshift, Amazon EMR
- Last verified by source: 2026-06-02

---

### Question 242: aif-q136

A company wants its large language model (LLM) to produce less varied responses to repeated prompts while keeping other inference settings fixed. Which change generally helps?

- **A.** Decrease the temperature inference parameter for the model
- **B.** Use an agent to supervise the model's training
- **C.** Remove every training record associated with an unwanted answer
- **D.** Switch to a foundation model guaranteed to return identical answers

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Decrease the temperature inference parameter for the model

**Explanation:**

Lower temperature favors higher-probability next tokens and generally reduces output variation. It does not verify facts or guarantee that a response is free of hallucinations.
Agents orchestrate work rather than supervise model training. A team cannot identify every training record behind an unwanted response, and no foundation model guarantees identical or factually correct answers.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 243: aif-q140

A text generator should exclude low-probability tail tokens while allowing the candidate-set size to change at each step. Which parameter should the team tune?

- **A.** Maximum output tokens
- **B.** top-p
- **C.** Context window
- **D.** Batch size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. top-p

**Explanation:**

Top-p sampling forms the smallest set of high-probability tokens whose cumulative probability reaches p, so the candidate-set size changes with the distribution.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 244: aif-q195

A team lowers top-p from 0.95 to 0.60 while holding other supported inference settings constant. What is the intended effect?

- **A.** Use a narrower cumulative-probability token pool
- **B.** Increase the context window
- **C.** Guarantee identical output
- **D.** Add more training examples

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use a narrower cumulative-probability token pool

**Explanation:**

A lower top-p narrows the cumulative-probability pool from which the model samples. Sampling can still vary, so the change does not guarantee identical output.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 245: aif-q200

A team wants less variable LLM responses. Which change generally reduces sampling randomness without promising identical outputs?

- **A.** Raise temperature
- **B.** Set a lower temperature, such as zero where the model supports it
- **C.** Increase maximum output tokens
- **D.** Ask the prompt to guarantee determinism

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Set a lower temperature, such as zero where the model supports it

**Explanation:**

Lower temperature favors higher-probability tokens and often reduces variation. Temperature zero does not guarantee bit-for-bit deterministic output across models, infrastructure, or service updates.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 246: aif-q210

Which large language model (LLM) parameter sets how many candidate next tokens the model considers at each generation step?

- **A.** Maximum tokens
- **B.** Temperature
- **C.** Top K
- **D.** Batch size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Top K

**Explanation:**

The Top K parameter limits sampling at each step to the K most probable next tokens, so it directly controls how many candidate tokens the model considers when generating each token.
Maximum tokens caps the total length of the output, not the candidate pool at each step. Temperature adjusts the randomness of the distribution rather than the number of candidates. Batch size concerns how many inputs are processed together, not token selection.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 247: aif-q220

An AI practitioner wants a large language model (LLM) to produce more diverse and creative output. How should the practitioner adjust an inference parameter?

- **A.** Decrease the Top K value
- **B.** Increase the response length
- **C.** Increase the temperature value
- **D.** Decrease the prompt length

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Increase the temperature value

**Explanation:**

Raising the temperature flattens the model's probability distribution and increases the chance of selecting less-likely tokens, which produces more varied and creative responses.
Decreasing the Top K value narrows the candidate tokens and makes output more focused, not more diverse. Increasing the response length only makes output longer. Decreasing the prompt length reduces context and does not increase creativity.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 248: aif-q246

Which two parameters are commonly used to control the diversity of a generative AI model's output?

- **A.** Model size
- **B.** Top-k sampling
- **C.** Training dataset size
- **D.** Top-p (nucleus) sampling
- **E.** Hardware configuration

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Top-k sampling; D. Top-p (nucleus) sampling

**Explanation:**

Top-k sampling limits selection to the k most likely next tokens, and Top-p (nucleus) sampling selects from the smallest set of tokens whose probabilities sum to p; both adjust the candidate pool to balance diversity and quality of generated text.
Model size, training dataset size, and hardware configuration affect a model's capability, cost, or speed, but they are not runtime parameters that control output diversity.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 249: aif-q247

A design team uses an image-generation foundation model (FM) on Amazon Bedrock and wants to control how detailed or abstract each generated image is. Which model parameter should they adjust?

- **A.** Model checkpoint
- **B.** Generation step
- **C.** Batch size
- **D.** Token length

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Generation step

**Explanation:**

The generation step parameter sets how many refinement steps the model runs while creating an image; more steps yield more detailed images and fewer steps yield more abstract ones, so it controls the level of detail.
A model checkpoint selects a saved version of the model, not the detail of a single image. Batch size sets how many images are produced at once. Token length applies to text generation, not image detail.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 250: aif-q244

For AI workloads, what is the main benefit of pairing Amazon Aurora with the pgvector extension?

- **A.** It automatically generates AI models
- **B.** It provides pre-trained language models
- **C.** It enables vector similarity search inside a relational database
- **D.** It provides serverless computing capabilities

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. It enables vector similarity search inside a relational database

**Explanation:**

Amazon Aurora with the pgvector extension enables vector similarity search inside a relational database, so embeddings can be stored alongside structured data and queried with SQL while keeping relational features.
Aurora does not automatically generate AI models or provide pre-trained language models. Serverless capacity is a deployment option but is not the primary advantage of pgvector for AI applications.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Aurora
- Last verified by source: 2026-06-02

---

### Question 251: aif-q387

A GraphRAG implementation must combine graph traversals with vector similarity search in the same analytical graph query. Which AWS capability fits?

- **A.** Neptune Analytics
- **B.** Amazon S3 Glacier
- **C.** Amazon RDS for MySQL without a vector extension
- **D.** Amazon SQS

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Neptune Analytics

**Explanation:**

Neptune Analytics supports graph analytics, traversals, and native vector similarity search for GraphRAG. The official exam service list may name the broader Amazon Neptune service; Neptune Analytics is the implementation context here.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Neptune
- Last verified by source: 2026-11-03

---

### Question 252: aif-q444

A company sends the same lengthy system prompt thousands of times daily with only the user query changing, and it wants to reduce latency and cost. Which FM selection criterion is most relevant?

- **A.** Multilingual support
- **B.** Prompt caching
- **C.** Model complexity
- **D.** Diffusion capability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Prompt caching

**Explanation:**

Prompt caching stores the processed representation of a repeated system prompt so the model does not re-process it on every request, reducing both latency and cost when the same prefix is sent repeatedly with only the user query varying.
Multilingual support concerns language coverage. Model complexity relates to reasoning capability. Diffusion capability applies to image generation models. None of these addresses the cost of processing a repeated prompt prefix.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 253: aif-q445

A company needs a foundation model that can accept both text and images as input and produce text output. Which FM selection criterion determines whether a model supports this?

- **A.** Temperature range
- **B.** Modality
- **C.** Context window size
- **D.** Training dataset size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Modality

**Explanation:**

Modality describes the types of input and output a model supports, such as text, images, audio, or video. A model must support multimodal input (text and images) to accept both types and produce text output.
Temperature range controls output randomness. Context window size determines how much information fits in a single prompt. Training dataset size affects model knowledge but does not determine supported input types.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 254: aif-q446

A company runs a large foundation model on Amazon Bedrock but finds the inference cost too high. It wants a smaller, cheaper model that retains most of the large model's quality. Which customization approach meets this requirement?

- **A.** Retrieval Augmented Generation (RAG)
- **B.** Model distillation
- **C.** Continuous pre-training
- **D.** In-context learning

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Model distillation

**Explanation:**

Model distillation trains a smaller student model to replicate the behavior of a larger teacher model, producing a compact model that retains most of the original's quality at lower inference cost.
RAG retrieves external documents at query time but does not reduce model size or cost. Continuous pre-training updates knowledge but does not shrink the model. In-context learning adds examples to the prompt, which actually increases token costs.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-03

---

### Question 255: aif-q447

A travel company wants an AI system that can search flight availability, compare prices across airlines, book tickets, and send confirmation emails, all from a single customer request. Which solution meets this requirement?

- **A.** A text summarization model
- **B.** An AI agent that orchestrates multi-step tasks using tool calls
- **C.** A classification model that routes requests to departments
- **D.** A recommendation engine that suggests popular flights

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. An AI agent that orchestrates multi-step tasks using tool calls

**Explanation:**

An AI agent can break down the customer's request into steps (searching flights, comparing prices, booking, and sending confirmation) and execute each by calling the appropriate tools and APIs, which is the defining capability of agents for complex business workflows.
A summarization model condenses text but cannot take actions. A classification model routes requests but cannot execute multi-step tasks. A recommendation engine suggests items but cannot book flights or send emails.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

## Task 3.2

Questions for this task: 26

### Question 256: aif-q005

A travel company uses a pre-trained large language model (LLM) to power a booking assistant. The company needs the assistant's replies to be brief and written in a particular language. Which approach will best align the LLM's output with these expectations?

- **A.** Choose an LLM of a different size
- **B.** Increase the temperature value
- **C.** Refine the prompt
- **D.** Increase the Top K value

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Refine the prompt

**Explanation:**

Refining the prompt lets the company state the required response length and target language directly, so the model returns brief replies in the chosen language.
Choosing a different model size changes the model's capacity and cost rather than enforcing length or language. Increasing the temperature adds randomness, making the output less controlled. Increasing the Top K value widens the pool of candidate tokens, which also does not control response length or language.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 257: aif-q024

A company is building a self-service support chatbot on a foundation model (FM). The chatbot's responses must match the company's brand tone. Which solution meets this requirement?

- **A.** Iterate on and refine the prompt until the FM produces responses in the desired style
- **B.** Set a low limit on the number of tokens the FM can produce
- **C.** Use batch inference to generate detailed responses
- **D.** Set a higher temperature value

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Iterate on and refine the prompt until the FM produces responses in the desired style

**Explanation:**

Iteratively refining the prompt steers the foundation model toward responses that match the company brand tone, because the prompt instructions and examples shape the style of the output.
Limiting output tokens only shortens responses. Batch inference changes how requests are processed, not their tone. Raising the temperature increases randomness, which makes tone less consistent rather than more aligned.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 258: aif-q025

A company wants to use a large language model (LLM) on Amazon Bedrock to label text passages as positive or negative. Which prompt engineering strategy meets this requirement?

- **A.** Add a detailed explanation of sentiment analysis and how LLMs work to the prompt
- **B.** Provide only the new passage to classify, with no examples or additional context
- **C.** Include a few example passages, each labeled positive or negative, in the prompt
- **D.** Include the new passage along with a few examples of unrelated tasks such as summarization or translation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Include a few example passages, each labeled positive or negative, in the prompt

**Explanation:**

Including a few example passages, each labeled positive or negative, is few-shot prompting, which shows the model the input-to-label pattern and improves classification accuracy on a new passage.
Adding an explanation of how sentiment analysis or LLMs work provides theory but no examples to learn from. Providing only the passage with no examples is zero-shot and gives the model less guidance. Examples of unrelated tasks such as summarization or translation steer the model away from sentiment classification.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 259: aif-q029

A startup is launching an LLM-powered agent and wants to reduce the risk that users coax it into unsafe actions or hidden-instruction leakage. Which action most directly helps among these choices?

- **A.** Increase temperature
- **B.** Put secrets in the system prompt
- **C.** Use explicit instructions and delimiters, combined with external authorization and input validation
- **D.** Grant every tool broad permissions

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Use explicit instructions and delimiters, combined with external authorization and input validation

**Explanation:**

Instructions and delimiters can reduce some attacks but are not a security boundary. The application must also use least-privilege tools, deterministic authorization, validation, content controls, monitoring, and approval for consequential actions.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 260: aif-q069

An online learning company runs a question-answering assistant and wants the answer style to match each learner's age range, which the app already passes to the model. Which approach needs the LEAST effort?

- **A.** Train a separate fine-tuned model for each age range
- **B.** Build a Retrieval Augmented Generation (RAG) pipeline of age-specific content
- **C.** Post-process every response with a second model to adjust the tone
- **D.** Add a role and audience instruction to the prompt that states the user's age range

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Add a role and audience instruction to the prompt that states the user's age range

**Explanation:**

Adding a role and audience instruction to the prompt is a simple prompt-engineering change that steers the style to the stated age range with almost no extra work.
Fine-tuning a model per age range, building a RAG pipeline of age-specific content, and running a second model to rewrite tone all add significant data, infrastructure, or processing effort.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 261: aif-q086

Which prompt-based attack is specifically aimed at revealing a model's hidden system instructions?

- **A.** Jailbreaking
- **B.** Prompt injection
- **C.** Extracting the prompt template
- **D.** Prompted persona switching

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Extracting the prompt template

**Explanation:**

Extracting (leaking) the prompt template coaxes the model into disclosing its underlying system prompt, directly exposing the hidden instructions that configure its behavior.
Jailbreaking bypasses safety controls, prompt injection inserts adversarial instructions to hijack behavior, and persona switching pushes the model into a different role; none of these is aimed at dumping the system instructions themselves.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 262: aif-q095

Which prompting approach deliberately tests hostile inputs to discover prompt-injection weaknesses before release?

- **A.** Chain-of-thought prompting
- **B.** Few-shot prompting
- **C.** Adversarial prompting
- **D.** Zero-shot prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Adversarial prompting

**Explanation:**

Adversarial prompting probes a model or application with hostile inputs to expose weaknesses. Testing alone does not harden the system. Teams must use the findings to improve deterministic authorization, least-privilege tool access, input validation, guardrails, monitoring, and review controls.
Chain-of-thought, few-shot, and zero-shot prompting shape task behavior but do not describe hostile security testing.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 263: aif-q107

A company's image-generation model keeps producing pictures unrelated to the prompts, and the team wants to adjust its prompting to cut down on these. Which technique helps?

- **A.** Add few-shot example images
- **B.** Use negative prompts that state what to exclude
- **C.** Use zero-shot prompts
- **D.** Make the prompts more open-ended

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use negative prompts that state what to exclude

**Explanation:**

Negative prompts explicitly tell the model what to leave out, constraining generation so fewer off-topic elements appear.
Adding example images or using zero-shot prompts gives no instruction about what to avoid, and making prompts more open-ended increases drift rather than reducing it.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 264: aif-q108

An electronics retailer wants an LLM to write short, feature-focused product descriptions. Which prompt-engineering approach works best?

- **A.** Write one generic prompt for all products and manually edit each output
- **B.** Create category-specific prompts that highlight key features and specify the output format and length
- **C.** List every product attribute in a single prompt and ask for a description
- **D.** Ask the model for the most creative description it can produce, then trim it

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Create category-specific prompts that highlight key features and specify the output format and length

**Explanation:**

Category-specific prompts that call out the key features and set the format and length steer the model to consistent, concise, feature-focused descriptions with little rework.
A single generic prompt needs heavy manual editing; listing every attribute produces long, unfocused text; asking for maximum creativity and trimming wastes effort and drifts from the required style.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 265: aif-q128

An analyst adds an instruction to a prompt on Amazon Bedrock asking the model to show its work and explain each step while solving math problems. Which prompt-engineering technique is being used?

- **A.** Few-shot prompting
- **B.** Tree of thoughts prompting
- **C.** Chain-of-thought prompting
- **D.** Zero-shot prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Chain-of-thought prompting

**Explanation:**

Chain-of-thought prompting asks the model to lay out its intermediate reasoning step by step, which is exactly what instructing it to show its work does, improving accuracy on math problems.
Few-shot prompting supplies worked examples; tree of thoughts explores several reasoning branches in parallel; zero-shot prompting gives only an instruction with no reasoning scaffold.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 266: aif-q131

A company needs higher-quality answers from a large language model (LLM) on complex problems that require detailed, step-by-step reasoning. Which prompt-engineering technique fits?

- **A.** Directional stimulus prompting
- **B.** Prompt chaining
- **C.** Least-to-most prompting
- **D.** Chain-of-thought prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Chain-of-thought prompting

**Explanation:**

Chain-of-thought prompting guides the model to produce its reasoning as a series of logical steps within the response, which improves answer quality on complex problems.
Directional stimulus prompting steers output with hints or keywords; prompt chaining sends several separate prompts in sequence; least-to-most prompting decomposes a task into ordered subproblems but is a distinct technique from generating an in-line reasoning chain.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 267: aif-q161

Which statement describes a genuine risk or limitation of prompt engineering for a generative AI model?

- **A.** Prompt engineering guarantees deterministic outputs, so validation is unnecessary
- **B.** Prompt engineering can expose the model to prompt injection attacks
- **C.** Prompt engineering permanently updates the model's weights with each prompt
- **D.** Prompt engineering eliminates all risk of data poisoning and model hijacking

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Prompt engineering can expose the model to prompt injection attacks

**Explanation:**

A real limitation of prompt engineering is that crafted inputs can still be exploited through prompt injection, where an attacker manipulates the prompt to change the model's behavior.
Prompt engineering does not make outputs deterministic or remove the need for validation, it does not update the model's weights (that is fine-tuning), and it cannot eliminate risks such as data poisoning or model hijacking.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 268: aif-q163

Which technique decomposes a complex task into smaller subtasks that are sent to a large language model (LLM) in sequence, each building on the last?

- **A.** Tree of thoughts
- **B.** Chain-of-thought prompting
- **C.** Prompt chaining
- **D.** Few-shot prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Prompt chaining

**Explanation:**

Prompt chaining breaks a complex task into smaller subtasks and feeds them to the LLM one after another, with each step using the output of the previous one.
Chain-of-thought reasons step by step within a single response; tree of thoughts explores multiple reasoning branches; few-shot prompting supplies examples rather than sequencing subtasks.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 269: aif-q176

A team built an agent with Amazon Bedrock Agents and wants to improve its accuracy by giving it a few specific examples. Which approach fits?

- **A.** Fine-tune the underlying model on the examples
- **B.** Add the examples to the agent's advanced prompts
- **C.** Add the examples to an Amazon Bedrock knowledge base
- **D.** Create a guardrail that includes the examples

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Add the examples to the agent's advanced prompts

**Explanation:**

Adding the specific input-output examples to the agent's advanced prompts is few-shot prompting, which steers the agent toward more accurate behavior with no retraining or extra services.
Fine-tuning the model is far heavier for a handful of examples; a knowledge base supplies retrieved context rather than behavioral examples; a guardrail enforces safety policies, not example-driven accuracy.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: Agents for Amazon Bedrock, Amazon Bedrock Knowledge Bases
- Last verified by source: 2026-06-02

---

### Question 270: aif-q212

A company wants a large language model (LLM) to write product descriptions and plans to include several example descriptions that follow a fixed format in the prompt. Which prompt-engineering technique does this use?

- **A.** Zero-shot prompting
- **B.** One-shot prompting
- **C.** Few-shot prompting
- **D.** Role prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Few-shot prompting

**Explanation:**

Few-shot prompting places several examples in the prompt so the model learns the pattern and format and generates new descriptions in the same style, without any training.
Zero-shot prompting supplies no examples, one-shot prompting supplies only a single example, and role prompting assigns a persona but does not provide formatted examples.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 271: aif-q214

A company is designing a new grocery assistant that must check live inventory before answering. Which current design meets the requirement?

- **A.** Few-shot prompting with yesterday's stock
- **B.** Chain-of-thought prompting without tools
- **C.** An AgentCore Harness agent using an authorized inventory tool exposed through AgentCore Gateway, with request validation in the tool implementation
- **D.** Zero-shot prompting without data access

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. An AgentCore Harness agent using an authorized inventory tool exposed through AgentCore Gateway, with request validation in the tool implementation

**Explanation:**

A prompt cannot read live inventory by itself. For a new design, AgentCore Gateway can expose the inventory API as an authenticated tool that an AgentCore Harness agent can discover and invoke. The tool implementation must validate model-generated inputs and enforce the user's authorization.
The other options provide no live data access.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: Amazon Bedrock AgentCore Harness, Amazon Bedrock AgentCore Gateway
- Last verified by source: 2026-11-03

---

### Question 272: aif-q234

A bank includes several approved question-and-answer examples in a prompt before a new account-opening question. Which technique is this?

- **A.** Directional stimulus prompting
- **B.** Zero-shot prompting
- **C.** Few-shot prompting
- **D.** One-shot prompting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Few-shot prompting

**Explanation:**

Few-shot prompting supplies several examples. One-shot supplies one example, and zero-shot supplies none.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 273: aif-q288

When designing prompts for a generative AI model, which two practices are important?

- **A.** Maximize prompt length regardless of relevance
- **B.** Provide clear context and instructions
- **C.** Use ambiguous wording to encourage creativity
- **D.** Include relevant examples when they help
- **E.** Omit instructions and rely on model defaults

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Provide clear context and instructions; D. Include relevant examples when they help

**Explanation:**

Clear context and instructions tell the model what is expected, and relevant examples (few-shot prompting) guide it toward the desired output format and style, so both improve prompt quality.
Maximizing length regardless of relevance, using ambiguous wording, and omitting instructions all add noise or ambiguity and degrade the model's responses.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 274: aif-q344

In generative AI, what distinguishes zero-shot, one-shot, and few-shot prompting?

- **A.** The model architecture used
- **B.** The number of examples provided in the prompt
- **C.** The number of reasoning steps the model takes
- **D.** The amount of data used to fine-tune the model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. The number of examples provided in the prompt

**Explanation:**

These terms describe how many examples are placed in the prompt: zero-shot gives none, one-shot gives a single example, and few-shot gives a small set, all without retraining the model.
They do not refer to the model architecture, the number of reasoning steps, or the amount of fine-tuning data, which are unrelated to how many in-prompt examples are supplied.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 275: aif-q048

A cosmetics brand wants a pre-trained generative AI model to write campaign copy that fits its brand voice and messaging. What should the team do?

- **A.** Add more layers to the model's architecture to increase its complexity
- **B.** Craft clear, well-structured prompts that provide instructions and context to guide the model's output
- **C.** Tune the model's architecture and hyperparameters to improve its overall performance
- **D.** Collect a large, diverse dataset and pre-train a new generative model from scratch

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Craft clear, well-structured prompts that provide instructions and context to guide the model's output

**Explanation:**

Crafting clear prompts with instructions and context guides the pre-trained model to generate content that matches the brand voice, without modifying the model itself.
Adding layers or tuning the architecture and hyperparameters means re-engineering or retraining the model, which is unnecessary and costly here. Pre-training a new model from scratch is even more resource-intensive and is not needed to align output with brand voice.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 276: aif-q075

A telecom company's chatbot uses a large language model (LLM) on Amazon Bedrock for intent detection, and the team wants to improve accuracy with few-shot learning. What data does the team need?

- **A.** Pairs of user messages and their correct user intents
- **B.** Pairs of user messages and their correct chatbot responses
- **C.** Pairs of chatbot responses and their correct user intents
- **D.** Pairs of user intents and their correct chatbot responses

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Pairs of user messages and their correct user intents

**Explanation:**

Few-shot learning supplies the model with example input-output pairs for the task, and intent detection maps a user message to an intent, so the company needs pairs of user messages and their correct user intents.
Pairs that involve chatbot responses, whether messages-to-responses, responses-to-intents, or intents-to-responses, train the wrong mapping and do not demonstrate how to detect a user intent from a message.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 277: aif-q089

During a red-team test of a foundation model (FM), an engineer tries to get past its safety filters so it produces harmful text. What is this technique called?

- **A.** Fuzzing the training data to find vulnerabilities
- **B.** Jailbreaking
- **C.** Authorized penetration testing
- **D.** Denial-of-service (DoS) attack

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Jailbreaking

**Explanation:**

Jailbreaking is the attempt to circumvent or disable a model built-in safety controls so it produces restricted or harmful content, which is exactly what the engineer is doing.
Fuzzing the training data probes for vulnerabilities by feeding malformed inputs during development, not by bypassing safety filters. Authorized penetration testing is a sanctioned security assessment. A denial-of-service attack targets availability rather than defeating content safeguards.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 278: aif-q257

A team generates images with an Amazon Nova Canvas model and needs to keep specific items out of the results. Which solution meets this requirement?

- **A.** Use a higher temperature value
- **B.** Use a negative prompt
- **C.** Use a more detailed prompt
- **D.** Switch to another foundation model (FM)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use a negative prompt

**Explanation:**

A negative prompt specifies the items or characteristics the model should avoid, so it keeps the unwanted items out of the generated images.
A higher temperature only adds randomness. A more detailed prompt describes what to include but does not reliably exclude specific items. Switching to another foundation model does not provide a mechanism to exclude items.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 279: aif-q384

A team wants reusable Amazon Bedrock prompt templates with placeholders such as {{product}} and {{audience}}. Which Prompt Management feature addresses this?

- **A.** Prompt variables
- **B.** Knowledge Base chunking
- **C.** Guardrail denied topics
- **D.** Model evaluation datasets

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Prompt variables

**Explanation:**

Prompt variables let an application supply values for placeholders in a managed prompt template at invocation time.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 280: aif-q448

Which two practices improve the quality of responses from a foundation model through prompt engineering?

- **A.** Be specific and concise in instructions
- **B.** Use vague language to allow creative freedom
- **C.** Experiment with different prompt structures and iterate
- **D.** Always use the maximum token limit for prompts
- **E.** Avoid providing any context to keep prompts short

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Be specific and concise in instructions; C. Experiment with different prompt structures and iterate

**Explanation:**

Being specific and concise tells the model exactly what is expected without ambiguity, and experimenting with different prompt structures and iterating helps discover what works best for each task, both of which are prompt engineering best practices.
Vague language introduces ambiguity that degrades response quality. Using the maximum token limit wastes tokens on irrelevant content. Avoiding context deprives the model of information it needs to respond accurately.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 281: aif-q449

A team wants to create and version reusable prompt templates in Amazon Bedrock. Which feature fits?

- **A.** Amazon Bedrock Knowledge Bases
- **B.** Amazon Bedrock Guardrails
- **C.** Amazon Bedrock Prompt Management
- **D.** Amazon Bedrock Model Evaluation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon Bedrock Prompt Management

**Explanation:**

Prompt Management stores and versions reusable prompt templates. Applications can invoke a pinned version and supply defined variables.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.2
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

## Task 3.3

Questions for this task: 15

### Question 282: aif-q008

A manufacturer needs a high-accuracy labeled image dataset for a defect-detection model and wants to keep mislabeled examples to a minimum. Which approach best meets these requirements?

- **A.** Automated annotation with Amazon Rekognition Custom Labels
- **B.** Human-in-the-loop validation with Amazon SageMaker Ground Truth Plus
- **C.** Synthetic image generation with an Amazon Bedrock foundation model
- **D.** Automated active-learning labeling with Amazon SageMaker Ground Truth

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Human-in-the-loop validation with Amazon SageMaker Ground Truth Plus

**Explanation:**

Human-in-the-loop validation with Amazon SageMaker Ground Truth Plus routes labels through expert reviewers who verify and correct them, producing the highest-accuracy annotations with the fewest mistakes.
Amazon Rekognition Custom Labels automates labeling but, without human review, can propagate errors; generating synthetic images with an Amazon Bedrock model creates data yet does nothing to validate the labels; SageMaker Ground Truth's automated active-learning labeling cuts effort but raises the chance of incorrect annotations, the opposite of the goal.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: Amazon SageMaker Ground Truth Plus, Amazon Rekognition, Amazon SageMaker Ground Truth, Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 283: aif-q019

A company will fine-tune a supported Amazon Bedrock model. How should it format the training data?

- **A.** Use the JSON Lines schema documented for that specific model and customization method
- **B.** Use one universal prompt/completion schema for every Bedrock model
- **C.** Rename a CSV file with a .jsonl extension
- **D.** Upload arbitrary binary records

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use the JSON Lines schema documented for that specific model and customization method

**Explanation:**

Bedrock customization datasets use JSON Lines, but required fields and schemas are model-specific. The team must follow the selected model's current customization documentation.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 284: aif-q064

A foundation model handles a field's terminology poorly. The team has a large unlabeled corpus from that field and wants to adapt the model's domain knowledge. Which method fits?

- **A.** Few-shot prompting
- **B.** Continued pre-training on the unlabeled domain corpus
- **C.** A smaller top-p value
- **D.** A confusion matrix

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Continued pre-training on the unlabeled domain corpus

**Explanation:**

Continued pre-training uses an unlabeled corpus to adapt a model to domain language and knowledge. Instruction fine-tuning instead uses labeled instruction-response examples.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 285: aif-q081

What is a benefit of continuously pre-training a foundation model (FM)?

- **A.** It adapts the model to a specific labeled task dataset
- **B.** It keeps improving the model's knowledge by training it further on new data over time
- **C.** It compresses the model to shrink its size and speed up inference
- **D.** It removes the need for an evaluation step

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. It keeps improving the model's knowledge by training it further on new data over time

**Explanation:**

Continuous pre-training keeps exposing the FM to fresh, mostly unlabeled data, so its knowledge stays current and its performance improves over time.
Adapting to a labeled task dataset describes fine-tuning; shrinking and speeding up the model describes distillation or quantization; and no training method removes the need to evaluate the model.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 286: aif-q175

Which technique trains an AI model on a labeled dataset so it adapts to a specific industry's terminology and requirements?

- **A.** Continuous pre-training
- **B.** In-context learning
- **C.** Fine-tuning
- **D.** Model distillation

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Fine-tuning

**Explanation:**

Fine-tuning continues training a pre-trained model on a labeled, domain-specific dataset so it learns the industry's terminology and task requirements directly from that data.
Continuous pre-training relies on large unlabeled data; in-context learning adds examples at inference time without training; model distillation transfers knowledge into a smaller model rather than adapting it to a labeled domain dataset.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 287: aif-q178

A company will use instruction-based fine-tuning to adapt a foundation model (FM) to its domain. How should it prepare the training data?

- **A.** Assemble a large unlabeled domain corpus and continue pre-training
- **B.** Create instruction-and-response (question-and-answer) pairs for the domain
- **C.** Build a vector index of the documents for retrieval
- **D.** Collect human preference rankings of model outputs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Create instruction-and-response (question-and-answer) pairs for the domain

**Explanation:**

Instruction-based fine-tuning needs instruction-response examples, so curating domain-specific question-and-answer pairs teaches the model how to interpret domain queries and produce correct answers.
An unlabeled corpus is for continuous pre-training; a vector index supports RAG rather than training; human preference rankings are the data used for RLHF, not instruction tuning.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 288: aif-q189

What is a benefit of fine-tuning a foundation model (FM)?

- **A.** It lets the model pull in external data at inference time
- **B.** It improves the model's performance on a specific task by further training it on task data
- **C.** It compresses the model to reduce size and speed up inference
- **D.** It refreshes the model's general knowledge by pre-training on newer data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. It improves the model's performance on a specific task by further training it on task data

**Explanation:**

Fine-tuning updates the model's weights using task-relevant data, sharpening its accuracy and relevance on that specific task.
Pulling in external data at inference time describes RAG; compressing the model describes distillation; refreshing general knowledge with newer pre-training describes continuous pre-training.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 289: aif-q238

A company uses supervised learning to train a model on a small labeled dataset for a specific task. Which step of the foundation model (FM) lifecycle is this?

- **A.** Pre-training
- **B.** Continuous pre-training
- **C.** Fine-tuning
- **D.** Deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Fine-tuning

**Explanation:**

Fine-tuning continues training a pre-trained model on a small labeled dataset for a target task, which is exactly the supervised step described.
Pre-training and continuous pre-training use large, mostly unlabeled data; deployment puts the finished model into production. None of these is the supervised, task-specific training step.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 290: aif-q258

A company wants to label training data with human feedback to fine-tune a foundation model (FM) but does not want to build labeling tools or manage a workforce. Which AWS service or feature fits?

- **A.** Amazon SageMaker Data Wrangler
- **B.** Amazon SageMaker Clarify
- **C.** Amazon SageMaker Autopilot
- **D.** Amazon SageMaker Ground Truth Plus

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Amazon SageMaker Ground Truth Plus

**Explanation:**

Amazon SageMaker Ground Truth Plus is a fully managed labeling service that uses a human workforce, so the company gets human-labeled data without building labeling tools or managing labelers.
SageMaker Data Wrangler prepares and transforms data, SageMaker Clarify detects bias and explains predictions, and SageMaker Autopilot automatically builds models. None of these provides managed human labeling.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: Amazon SageMaker Ground Truth Plus, Amazon SageMaker Data Wrangler, Amazon SageMaker Clarify
- Last verified by source: 2026-06-02

---

### Question 291: aif-q041

During training, validation performance is still improving and no overfitting signal has appeared. Which change may help the model learn further?

- **A.** Decrease epochs
- **B.** Delete validation data
- **C.** Increase epochs while monitoring validation performance and stop when it no longer improves
- **D.** Increase inference temperature

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Increase epochs while monitoring validation performance and stop when it no longer improves

**Explanation:**

Additional epochs may help while validation performance improves. Continuing after validation degrades can overfit the model, so epoch count alone does not guarantee accuracy.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 292: aif-q132

A company wants to keep its foundation model (FM) current by regularly retraining it on the latest data. Which training strategy meets this requirement?

- **A.** Batch learning
- **B.** Static training
- **C.** Latent training
- **D.** Continuous pre-training

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Continuous pre-training

**Explanation:**

Continuous pre-training periodically ingests the latest data and updates the model's weights, so the foundation model stays current without retraining from scratch each time.
Batch learning processes data in fixed batches but is not a strategy for ongoing model refresh. Static training produces a one-time fixed model that does not update. Latent training is not a recognized training strategy.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 293: aif-q190

A retailer has a high-quality, model-compliant set of input-output conversations and wants to adapt a supported Amazon Bedrock model to its tone. Which approach fits?

- **A.** Amazon Personalize
- **B.** An Amazon Bedrock fine-tuning job after checking that the dataset meets the selected model's requirements
- **C.** A HyperPod pre-training job
- **D.** Inference optimization only

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. An Amazon Bedrock fine-tuning job after checking that the dataset meets the selected model's requirements

**Explanation:**

Fine-tuning can adapt output style when the selected model supports it and the dataset meets that model's format and minimum-data requirements. No fixed count works for every model.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 294: aif-q239

A company will fine-tune a large language model (LLM) on Amazon Bedrock to refine the style of its app's output messages. Which type of data does the company need?

- **A.** Samples of only input messages
- **B.** Paired samples of input messages and their corresponding output messages
- **C.** Samples of only output messages
- **D.** Separate, unpaired samples of input messages and output messages

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Paired samples of input messages and their corresponding output messages

**Explanation:**

Fine-tuning to refine output style requires paired examples of input messages and their corresponding output messages, so the model learns the mapping from input to the desired styled output.
Samples of only input messages or only output messages lack the input-to-output relationship the model must learn. Separate, unpaired samples do not show which output goes with which input, so the model cannot learn the styling.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 295: aif-q260

A company is building a generative AI tool and will customize a foundation model (FM) with its internal documents. Which approach meets this requirement?

- **A.** Classification
- **B.** Distillation
- **C.** Continued pre-training
- **D.** Regression

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Continued pre-training

**Explanation:**

Continued pre-training further trains a foundation model on the company's internal documents, so the model adapts to the company's domain and content.
Classification and regression are supervised ML tasks, not ways to customize an FM on documents. Distillation transfers knowledge from a larger model to a smaller one rather than adapting a model to internal documents.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 296: aif-q461

A team is using Amazon Bedrock to customize a foundation model with their own labeled data so it performs better on a domain-specific support task. Arrange the steps of the fine-tuning workflow from first to last.

- **A.** Run the fine-tuning job, which adjusts the model weights on the provided examples
- **B.** Select a base foundation model that supports customization for the target task
- **C.** Provision throughput for the resulting custom model and deploy it for inference
- **D.** Prepare and upload a labeled training dataset to Amazon S3 in the required format
- **E.** Evaluate the tuned model against a held-out validation set to confirm it improved

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Select a base foundation model that supports customization for the target task → D. Prepare and upload a labeled training dataset to Amazon S3 in the required format → A. Run the fine-tuning job, which adjusts the model weights on the provided examples → E. Evaluate the tuned model against a held-out validation set to confirm it improved → C. Provision throughput for the resulting custom model and deploy it for inference

**Explanation:**

You must first select a base foundation model that supports customization, then prepare and upload a labeled dataset to S3, because the training job needs both a target model and formatted data before it can start. Running the fine-tuning job adjusts the weights, after which you evaluate the tuned model on a held-out set and, only once it passes, provision throughput to deploy it.
A common mistake is to evaluate before training or to deploy before evaluating, but you cannot measure a tuned model that does not yet exist, and shipping an unevaluated model risks regressions. Data preparation also precedes the job itself, since fine-tuning consumes the labeled examples rather than producing them.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.3
- Format: ordering
- Services: None listed
- Last verified by source: 2026-06-13

---

## Task 3.4

Questions for this task: 21

### Question 297: aif-q079

A travel company localizes its help articles into several languages with an LLM and scores each machine translation against a human reference. Which metric is purpose-built for machine translation?

- **A.** BERTScore
- **B.** Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
- **C.** Bilingual Evaluation Understudy (BLEU)
- **D.** Word error rate

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Bilingual Evaluation Understudy (BLEU)

**Explanation:**

BLEU is designed for machine translation, measuring n-gram overlap between the candidate translation and one or more human references, which is exactly the comparison described.
ROUGE targets summarization recall; BERTScore measures general semantic similarity rather than serving as the standard translation metric; word error rate evaluates speech transcription.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 298: aif-q088

A social platform wants to compare the output toxicity of several candidate LLMs from Amazon SageMaker JumpStart with the LEAST operational effort. Which evaluation approach fits?

- **A.** Model evaluation with a human review workforce
- **B.** Automatic model evaluation using built-in toxicity metrics
- **C.** Crowd-sourced human rating
- **D.** A/B testing the models with live users

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Automatic model evaluation using built-in toxicity metrics

**Explanation:**

Automatic model evaluation scores outputs with built-in toxicity metrics and needs no people to recruit or coordinate, giving the lowest operational effort.
Human-workforce evaluation and crowd-sourced rating both require managing reviewers, and A/B testing with live users adds exposure risk and coordination overhead.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 299: aif-q096

An IT support team fine-tuned an LLM to classify help desk tickets as hardware, software, access, or network issues. The classes are imbalanced, and the team wants each class to contribute equally while balancing precision and recall. Which metric should it use?

- **A.** Precision for the largest class
- **B.** Macro-averaged F1 score
- **C.** Time to first token
- **D.** Perplexity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Macro-averaged F1 score

**Explanation:**

Macro-averaged F1 calculates an F1 score for each class and gives each class equal weight in the final average. It fits this imbalanced multiclass classification scenario and balances precision with recall.
Precision for the largest class ignores recall and the other classes. Time to first token measures latency, and perplexity measures language-modeling fit rather than classification performance.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 300: aif-q102

A company built a text summarization solution on Amazon Bedrock and will use Amazon Bedrock Model Evaluation. Which metric should it use to measure summary quality?

- **A.** Area under the ROC curve (AUC)
- **B.** BERTScore
- **C.** Mean squared error (MSE)
- **D.** Perplexity

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. BERTScore

**Explanation:**

BERTScore compares the generated summary with reference text using contextual embeddings, capturing semantic similarity, which makes it suitable for measuring summarization quality.
AUC measures binary classification ranking, MSE measures regression error, and perplexity measures language-modeling fit; none of these compares a summary against references for quality.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 301: aif-q106

A language-learning app calls an LLM to rewrite text more clearly and has reference examples of the improved versions. It wants the model's output to resemble those examples. Which metric should it use?

- **A.** Perplexity of the generated text
- **B.** Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
- **C.** Semantic robustness score
- **D.** Average response latency

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)

**Explanation:**

ROUGE measures the n-gram and sequence overlap between the model's output and the reference examples, so it directly captures how closely the output resembles those improved versions.
Perplexity reflects language-modeling fit, semantic robustness measures stability under input changes, and latency measures speed; none compares output against reference examples.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 302: aif-q188

Which metric is commonly used to evaluate how well a foundation model (FM) performs on text summarization?

- **A.** F1 score
- **B.** Mean squared error (MSE)
- **C.** Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
- **D.** Bilingual Evaluation Understudy (BLEU) score

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)

**Explanation:**

ROUGE measures the overlap between a generated summary and reference summaries, which makes it the standard metric for summarization quality.
F1 is a classification metric, MSE measures regression error, and BLEU is built for machine translation; none targets summarization.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 303: aif-q219

A translation model produces candidate translations. Which metric compares those candidates with one or more approved reference translations using n-gram overlap?

- **A.** BLEU
- **B.** Perplexity
- **C.** Mean squared error
- **D.** Accuracy over class labels

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. BLEU

**Explanation:**

BLEU compares candidate text with approved references through modified n-gram precision and related adjustments. It does not establish factual correctness or human preference.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 304: aif-q227

A team must judge whether generated marketing copy matches the company's tone, clarity, and audience expectations. Which evaluation method fits best?

- **A.** Human evaluation with a defined style rubric
- **B.** BLEU against one arbitrary sentence
- **C.** Confusion matrix
- **D.** Root mean squared error

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Human evaluation with a defined style rubric

**Explanation:**

Qualified human reviewers using a documented rubric can assess tone and style. BLEU measures reference overlap and is not a reliable measure of brand voice.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 305: aif-q265

A company is comparing several large language models (LLMs) for text summarization and needs a metric for summary quality. Which metric fits?

- **A.** Bilingual Evaluation Understudy (BLEU) score
- **B.** Area under the ROC curve (AUC)
- **C.** Perplexity
- **D.** Recall-Oriented Understudy for Gisting Evaluation (ROUGE)

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)

**Explanation:**

ROUGE measures the overlap between generated summaries and reference summaries, making it the standard metric for summarization quality.
BLEU is built for translation, AUC is a classification metric, and perplexity measures language-modeling fit; none is designed for summary quality.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 306: aif-q272

An online retailer wants to evaluate a model that labels each customer review as positive, negative, or neutral. Which model evaluation task type fits this requirement?

- **A.** Open-ended text generation
- **B.** Text summarization
- **C.** Classification
- **D.** Question and answer

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Classification

**Explanation:**

Classification assigns each input to one of a fixed set of predefined categories, so sorting every customer review into one of three sentiment labels (positive, negative, or neutral) is a classification task and is evaluated with classification metrics.
Open-ended text generation produces free-form text from a prompt and has no fixed set of output labels. Text summarization condenses longer text into a shorter version rather than assigning it to a category. Question and answer returns a response to a posed question rather than placing the input into predefined sentiment categories.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 307: aif-q294

Which two metrics are commonly used to evaluate the output quality of generative AI models?

- **A.** GPU memory usage
- **B.** Bilingual Evaluation Understudy (BLEU) score for translation quality
- **C.** Request throughput in requests per second
- **D.** Recall-Oriented Understudy for Gisting Evaluation (ROUGE) score for summarization quality
- **E.** Model parameter count

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Bilingual Evaluation Understudy (BLEU) score for translation quality; D. Recall-Oriented Understudy for Gisting Evaluation (ROUGE) score for summarization quality

**Explanation:**

BLEU assesses translation quality and ROUGE assesses summarization quality by comparing generated text to reference text, so both measure the quality of generative output.
GPU memory usage, request throughput, and model parameter count are infrastructure and model-size metrics that say nothing about output quality.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 308: aif-q051

A consultancy must choose an Amazon Bedrock model for internal use, and its analysts care about the writing style of the answers. How should the firm choose the model?

- **A.** Evaluate the models with built-in prompt datasets
- **B.** Choose the model based on public model leaderboards
- **C.** Evaluate the models with a human workforce using custom prompt datasets
- **D.** Compare the models using the InvocationLatency runtime metric in Amazon CloudWatch

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Evaluate the models with a human workforce using custom prompt datasets

**Explanation:**

Using a human workforce to evaluate the models against custom prompt datasets captures subjective style preferences that automated scores miss, so it best identifies the model whose responses match what employees prefer.
Built-in prompt datasets and public leaderboards measure general performance, not the company specific style preference. The InvocationLatency metric in Amazon CloudWatch measures response speed, not response style.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: Amazon Bedrock, Amazon CloudWatch
- Last verified by source: 2026-06-02

---

### Question 309: aif-q070

A team needs to check how accurately its image-classification foundation model (FM) performs. Which strategy should the team use?

- **A.** Count the number of layers in the model's neural network
- **B.** Calculate the total cost of the resources the model uses
- **C.** Check the color accuracy of the images the model processes
- **D.** Measure the model's accuracy on a predefined benchmark dataset

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Measure the model's accuracy on a predefined benchmark dataset

**Explanation:**

Measuring the model's accuracy against a predefined benchmark dataset is the standard way to assess classification accuracy, because performance is compared against known correct labels.
Counting neural-network layers describes architecture, not accuracy. Calculating total resource cost measures expense. Checking the color accuracy of processed images is unrelated to classification correctness.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 310: aif-q114

How can a team determine whether a foundation model (FM) effectively meets its business objectives?

- **A.** Evaluate the model's performance on benchmark datasets
- **B.** Assess how well the model aligns with the specific use cases it must support
- **C.** Analyze the model's architecture and hyperparameters
- **D.** Measure the computational resources the model needs for deployment

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Assess how well the model aligns with the specific use cases it must support

**Explanation:**

Assessing how well the model aligns with the specific use cases it must support shows whether its outputs solve the real business problems, which is how you tell if it meets business objectives.
Benchmark performance measures general accuracy, not business fit. Analyzing architecture and hyperparameters is a technical detail unrelated to business value. Measuring computational resources addresses cost and feasibility, not whether the objectives are met.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 311: aif-q266

A research group wants several scientists to manually compare the outputs of different generative AI models for a defined prompt. Which solution meets this requirement?

- **A.** Use automatic evaluation on Amazon Personalize
- **B.** Use model evaluation on Amazon Bedrock
- **C.** Use content moderation on Amazon Rekognition
- **D.** Use sentiment analysis on Amazon Comprehend

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use model evaluation on Amazon Bedrock

**Explanation:**

Amazon Bedrock model evaluation supports human-based evaluation, so a team of scientists can review and compare the models' outputs against the group's prompt and criteria.
Amazon Personalize provides recommendations. Amazon Rekognition does image and video content moderation. Amazon Comprehend does NLP tasks such as sentiment analysis. None of these provides human evaluation of generative model output.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Personalize, Amazon Rekognition, Amazon Comprehend
- Last verified by source: 2026-06-02

---

### Question 312: aif-q042

A support center rolls out a large language model (LLM) chatbot to cut down how many steps agents take when answering customer questions. Which business metric best shows whether the chatbot is making a difference?

- **A.** Corporate social responsibility
- **B.** Regulatory compliance
- **C.** Average call duration
- **D.** Website engagement rate

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Average call duration

**Explanation:**

Average call duration directly reflects how much the chatbot reduces the steps agents take to resolve questions, so tracking it measures the chatbot's business impact.
Corporate social responsibility and regulatory compliance are organizational concerns unrelated to how quickly agents resolve customer questions. Website engagement rate measures online visitor behavior, not call center efficiency.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 313: aif-q385

A company deployed an AI assistant on Amazon Bedrock to handle customer service requests. It wants to measure how effectively the assistant resolves customer issues without escalation. Which metric best captures this?

- **A.** BLEU score
- **B.** Task completion rate
- **C.** Perplexity
- **D.** Model parameter count

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Task completion rate

**Explanation:**

Task completion rate measures the percentage of customer requests the assistant fully resolves without needing human escalation, directly reflecting how effectively it meets the business objective of handling service requests autonomously.
BLEU score measures translation quality by comparing generated text to references. Perplexity measures how well a language model predicts text. Model parameter count describes model size. None of these measures whether the assistant successfully completes customer tasks.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 314: aif-q386

Which two metrics are examples of business-alignment metrics for evaluating AI applications?

- **A.** User satisfaction
- **B.** BERTScore
- **C.** Cost per interaction
- **D.** ROUGE score
- **E.** Model training time

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. User satisfaction; C. Cost per interaction

**Explanation:**

User satisfaction measures how well the AI application meets end-user expectations, and cost per interaction measures the operational expense of each user engagement, both of which directly align with business objectives and are defined as business-alignment metrics for AI applications.
BERTScore and ROUGE score are technical metrics that measure the quality of generated text against references rather than business outcomes. Model training time is an operational metric about how long training takes and says nothing about whether the application achieves its business goals.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 315: aif-q388

A company generates long-form marketing content with a foundation model and wants to evaluate quality at scale without relying on human reviewers. Which evaluation approach uses another large language model to score the outputs?

- **A.** BLEU scoring
- **B.** LLM-as-a-judge
- **C.** Benchmark dataset comparison
- **D.** A/B testing with live users

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. LLM-as-a-judge

**Explanation:**

LLM-as-a-judge uses a separate large language model to evaluate and score the outputs of another model against defined criteria, providing scalable quality assessment without requiring human reviewers for every output.
BLEU scoring compares generated text to reference translations using n-gram overlap and requires pre-written references. Benchmark dataset comparison evaluates against fixed test sets with known answers. A/B testing requires live users to compare variants. None of these uses another LLM to judge output quality.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 316: aif-q436

A company deployed a RAG-based customer support assistant and wants to evaluate whether the retrieval component returns relevant documents for user queries. Which approach should the team use?

- **A.** Measure the model's perplexity on a held-out dataset
- **B.** Compare retrieved passages against known-correct source documents for a set of test queries
- **C.** Count the total number of API calls made to Amazon Bedrock
- **D.** Measure the BLEU score of the model's outputs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Compare retrieved passages against known-correct source documents for a set of test queries

**Explanation:**

Evaluating a RAG application requires assessing whether the retrieval component returns relevant documents, which is done by comparing retrieved passages for test queries against known-correct source documents and measuring retrieval precision and recall.
Perplexity evaluates language model quality, not retrieval relevance. Counting API calls measures usage volume. BLEU score evaluates translation quality. None of these assesses the retrieval pipeline.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-03

---

### Question 317: aif-q462

Match each foundation model evaluation metric to what it primarily measures. Pair each metric on the left with the correct description on the right.

- **A.** ROUGE
- **B.** BLEU
- **C.** BERTScore
- **D.** Perplexity

**Match targets:**

- **1.** Precision of n-gram overlap between generated text and references, used mainly to score machine translation quality
- **2.** How well a language model predicts a sample, measured as its uncertainty over the next token, where a lower value is better
- **3.** Recall-oriented overlap of n-grams between generated and reference text, used mainly to score summarization quality
- **4.** Semantic similarity between generated and reference text computed from contextual embeddings rather than exact token matches

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A → 3 (Recall-oriented overlap of n-grams between generated and reference text, used mainly to score summarization quality); B → 1 (Precision of n-gram overlap between generated text and references, used mainly to score machine translation quality); C → 4 (Semantic similarity between generated and reference text computed from contextual embeddings rather than exact token matches); D → 2 (How well a language model predicts a sample, measured as its uncertainty over the next token, where a lower value is better)

**Explanation:**

ROUGE is recall-oriented and is the standard choice for summarization, while BLEU emphasizes n-gram precision against references and is the classic machine translation metric, so these two are easy to swap if you only remember that both use n-gram overlap. BERTScore moves beyond exact token matching by comparing contextual embeddings to capture semantic similarity, and perplexity is an intrinsic measure of how confidently a model predicts the next token, where lower is better.
The key distinction is overlap-based metrics (ROUGE and BLEU) versus an embedding-based one (BERTScore) versus an intrinsic probability measure (perplexity). A tempting error is to assume a higher perplexity signals a better model, but perplexity reflects uncertainty, so lower values indicate stronger next-token prediction.

</details>

**Question metadata**

- Domain: 3
- Task statement: 3.4
- Format: matching
- Services: None listed
- Last verified by source: 2026-06-13

---

# Domain 4: Guidelines for responsible AI

Questions in this domain: 54

## Task 4.1

Questions for this task: 36

### Question 318: aif-q047

A media platform wants to evaluate whether a content-moderation model treats defined demographic subgroups fairly. Which data source best supports that evaluation?

- **A.** Unlabeled moderation logs with no subgroup attributes
- **B.** A random sample of user content with no reviewed outcomes
- **C.** Representative, labeled evaluation data with the relevant subgroup attributes and expected moderation outcomes
- **D.** Internal content-moderation guidelines without test cases

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Representative, labeled evaluation data with the relevant subgroup attributes and expected moderation outcomes

**Explanation:**

The team needs representative examples, reviewed labels, and the subgroup attributes defined in its fairness assessment. It can then compare error rates and other chosen outcomes across those groups against accepted thresholds.
Unlabeled logs and content do not provide known outcomes for evaluation. Guidelines define policy but do not supply a test dataset. A generic benchmark may omit the platform's users, subgroups, content, or moderation policy.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 319: aif-q049

A lender is building a generative AI solution that offers discounts to new applicants based on business rules. To use the model responsibly and limit bias that could harm some customers, which two actions should the company take?

- **A.** Check the data for imbalances or disparities across groups
- **B.** Run the model as frequently as possible
- **C.** Evaluate the model's behavior so the company can offer transparency to stakeholders
- **D.** Use the ROUGE metric to measure the quality of generated text
- **E.** Keep the model's inference time within accepted limits

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Check the data for imbalances or disparities across groups; C. Evaluate the model's behavior so the company can offer transparency to stakeholders

**Explanation:**

Checking the data for imbalances or disparities helps surface and reduce bias that could unfairly affect some applicants, and evaluating the model's behavior lets the company explain its decisions and offer transparency to stakeholders. Both are core responsible AI practices for limiting bias.
Running the model frequently and keeping inference time within limits are operational concerns that do not address bias. The ROUGE metric measures the overlap of generated text with reference text for summarization quality and does not detect bias.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 320: aif-q052

A student submits essays by copying text produced by a generative AI tool without attribution. Which responsible AI challenge does this illustrate?

- **A.** Toxicity
- **B.** Hallucinations
- **C.** Privacy
- **D.** Plagiarism

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Plagiarism

**Explanation:**

Reusing generative AI output as one's own work without attribution is plagiarism, which is a recognized responsible AI and intellectual-property concern.
Toxicity refers to harmful or offensive content, hallucinations are fabricated but plausible-sounding outputs, and privacy concerns the handling of personal data. None of these describes copying generated text and presenting it as original work.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 321: aif-q057

A fraud model flags one ethnic group at a higher false-positive rate. An audit finds that this group was substantially underrepresented in the training sample. Which bias source does that evidence support?

- **A.** Sampling bias
- **B.** No bias
- **C.** Automation bias by reviewers
- **D.** Prompt injection

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Sampling bias

**Explanation:**

The audit supplies evidence that the sample did not represent the population, which supports sampling bias. Unequal outcomes without this evidence would not identify a single cause.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 322: aif-q067

A hospital uses Amazon Bedrock to generate patient-facing replies. It needs to mask configured patient identifiers before delivery and notify staff when the guardrail detects sensitive information. Which solution fits?

- **A.** Use Amazon Macie to scan live model responses and block delivery
- **B.** Configure an Amazon Bedrock Guardrails sensitive-information policy with the `ANONYMIZE` action, use synchronous guardrail processing, and alarm on the emitted guardrail metric or approved log signal
- **C.** Use AWS CloudTrail to inspect response text and replace identifiers
- **D.** Use SageMaker Model Monitor to mask patient identifiers

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Configure an Amazon Bedrock Guardrails sensitive-information policy with the `ANONYMIZE` action, use synchronous guardrail processing, and alarm on the emitted guardrail metric or approved log signal

**Explanation:**

The `ANONYMIZE` action replaces configured sensitive information in the delivered response. Synchronous processing evaluates content before delivery; asynchronous streaming does not support sensitive-information masking. Bedrock Guardrails emits CloudWatch metrics that can drive an alarm, and an application can emit an approved log or custom metric from the guardrail assessment. Detection remains probabilistic, so this control reduces disclosure risk rather than promising that exposure can never occur.
Amazon Macie discovers sensitive data in Amazon S3, CloudTrail records API activity, and Model Monitor checks model and data quality. They do not mask live Bedrock responses.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails, Amazon CloudWatch, Amazon Macie, AWS CloudTrail, Amazon SageMaker Model Monitor
- Last verified by source: 2026-11-03

---

### Question 323: aif-q071

An insurance firm plans to deploy a large language model to automate document processing and wants to proceed responsibly to avoid harm. Which two actions should the firm take?

- **A.** Include fairness metrics when evaluating the model
- **B.** Adjust the model's temperature parameter
- **C.** Modify the training data to reduce bias
- **D.** Avoid overfitting on the training data
- **E.** Apply prompt engineering techniques

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Include fairness metrics when evaluating the model; C. Modify the training data to reduce bias

**Explanation:**

Including fairness metrics when evaluating the model helps confirm it treats cases equitably, and modifying the training data to reduce bias addresses bias at its source. Both directly support responsible use and reduce potential harm.
Adjusting the temperature parameter and applying prompt engineering techniques tune output style and quality but do not address fairness or bias. Avoiding overfitting improves generalization but is a general model-quality goal rather than a measure that limits biased or harmful outcomes.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 324: aif-q094

A bank wants to build an ML system to help its risk team decide loan allocations across different demographic groups. What should the bank do to develop an unbiased model?

- **A.** Reduce the size of the training dataset
- **B.** Make sure the model's predictions match historical results
- **C.** Build a separate model for each demographic group
- **D.** Measure class imbalance in the training data and adjust the training process accordingly

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Measure class imbalance in the training data and adjust the training process accordingly

**Explanation:**

Measuring class imbalance in the training data and adapting the training process, for example through resampling or class weights, helps the model treat under-represented groups equitably and reduces biased predictions.
Reducing the dataset size removes information and can worsen bias. Forcing predictions to match historical results can carry past discrimination into the model. Building a separate model per demographic group can entrench disparities and does not address imbalance within the data.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 325: aif-q100

A company is building a mobile app that uses a phone camera to assess insect bites. To train its image classification model, the company gathers a wide range of bite photos spanning different genders, ethnicities, and regions. Which responsible AI principle does this reflect?

- **A.** Explainability
- **B.** Transparency
- **C.** Fairness
- **D.** Governance

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Fairness

**Explanation:**

Gathering bite photos across different genders, ethnicities, and regions is aimed at preventing the model from working better for some groups than others, which reflects the fairness principle of responsible AI.
Explainability and transparency concern revealing how the model reaches its outputs, and governance concerns policies and oversight. None of these describes the act of assembling a representative, balanced dataset to avoid biased outcomes.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 326: aif-q101

An existing SageMaker Clarify customer is developing a loan-approval model in a supported configuration. The customer needs a point-in-time bias analysis and feature-attribution explanations. Which eligible capability meets these requirements?

- **A.** Amazon SageMaker Data Wrangler
- **B.** Amazon SageMaker Clarify
- **C.** Amazon SageMaker Model Cards
- **D.** AWS AI Service Cards

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon SageMaker Clarify

**Explanation:**

For eligible existing customers, SageMaker Clarify processing jobs can calculate supported bias metrics and feature-attribution explanations when the data, model, and analysis configuration meet the documented requirements. SageMaker Clarify is no longer open to new customers.
Data Wrangler prepares data. Model Cards document supplied model details, and AWS AI Service Cards describe AWS managed AI services.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon SageMaker Clarify, Amazon SageMaker Data Wrangler, Amazon SageMaker Model Cards
- Last verified by source: 2026-06-02

---

### Question 327: aif-q122

Which technique can a company use to reduce bias and toxicity in a generative AI application during the postprocessing stage of the ML lifecycle?

- **A.** Data augmentation
- **B.** Human-in-the-loop
- **C.** Feature engineering
- **D.** Adversarial training

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Human-in-the-loop

**Explanation:**

Human-in-the-loop adds human review during the postprocessing stage so that biased or toxic outputs can be caught and corrected before they reach users, which reduces bias and toxicity in the generative AI application.
Data augmentation and feature engineering act on data before or during training, and adversarial training hardens the model during training. None of these operates as a postprocessing safeguard on generated outputs.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 328: aif-q144

A company built an AI resume-screening system trained on a large dataset of resumes that did not represent all demographic groups. Which core dimension of responsible AI does this situation involve?

- **A.** Transparency
- **B.** Fairness
- **C.** Privacy and security
- **D.** Explainability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Fairness

**Explanation:**

Training on a dataset that does not represent all demographic groups can lead to biased predictions, which is a fairness concern. Fairness is the responsible AI dimension focused on equitable outcomes across groups.
Transparency and explainability concern revealing how the model makes decisions, and privacy and security concern protecting data. None of these describes the bias introduced by an unrepresentative training dataset.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 329: aif-q187

A healthcare company wants to use generative AI to answer patients' medical questions. Which AWS service should it use to support responsible AI for the application?

- **A.** Amazon Inspector
- **B.** Amazon Bedrock Guardrails
- **C.** Amazon Rekognition
- **D.** AWS Trusted Advisor

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock Guardrails

**Explanation:**

Amazon Bedrock Guardrails let the company define and enforce safety, content, and bias controls on generative AI responses, which supports responsible AI for an application that answers patients' medical questions.
Amazon Inspector scans for software vulnerabilities, Amazon Rekognition analyzes images and video, and AWS Trusted Advisor checks accounts against best practices. None of these enforces responsible AI controls on generated content.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-06-02

---

### Question 330: aif-q203

A retail company wants to build a product recommendation model using responsible practices. Which practice should it apply when collecting data to reduce bias in the model?

- **A.** Use data only from the company's most active customers
- **B.** Collect data from a single high-value customer segment
- **C.** Make sure the data is representative of the company's entire customer base
- **D.** Use the smallest dataset that lets the model train quickly

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Make sure the data is representative of the company's entire customer base

**Explanation:**

Collecting data that is representative of the company's entire customer base reduces skew toward any single group and helps the recommendation model treat all customers equitably, which is the responsible practice for limiting bias.
Using data only from the most active customers or from a single high-value segment produces a skewed dataset that increases bias. Using the smallest dataset that trains quickly risks under-representing groups and does not address fairness.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 331: aif-q207

An existing SageMaker Model Monitor customer has a deployed segmentation model. The team wants scheduled checks for bias drift and feature-attribution drift. Which eligible capability meets this requirement?

- **A.** Amazon SageMaker Feature Store
- **B.** Amazon SageMaker Clarify
- **C.** Amazon SageMaker Model Monitor
- **D.** Amazon SageMaker Model Cards

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker Model Monitor

**Explanation:**

For eligible existing customers and supported configurations, SageMaker Model Monitor can schedule bias-drift and feature-attribution-drift monitoring jobs using SageMaker Clarify analysis. Model Monitor is no longer open to new customers, and its scheduled jobs do not observe the endpoint continuously.
SageMaker Clarify can run point-in-time bias and explainability analyses. Feature Store manages features, and Model Cards document model details.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon SageMaker Model Monitor, Amazon SageMaker Clarify, Amazon SageMaker Model Cards, Amazon SageMaker Feature Store
- Last verified by source: 2026-06-02

---

### Question 332: aif-q222

A company is adding AI to its recruitment and hiring process and wants to reduce bias risks and keep hiring decisions equitable. Which two core dimensions of responsible AI should the company focus on?

- **A.** Fairness
- **B.** Flexibility
- **C.** Tolerance
- **D.** Open source
- **E.** Transparency

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Fairness; E. Transparency

**Explanation:**

Fairness keeps hiring outcomes equitable across demographic groups, which directly mitigates bias, and transparency makes the AI's decisions clear so they can be explained and audited. Both are core dimensions of responsible AI.
Flexibility, tolerance, and open source are not core responsible AI dimensions for ensuring equitable, accountable hiring decisions.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 333: aif-q225

A food company is collecting a dataset to predict customer food preferences and wants the preferences of all demographic groups represented in the data. Which dataset characteristic does this describe?

- **A.** Accuracy
- **B.** Diversity
- **C.** Recency bias
- **D.** Reliability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Diversity

**Explanation:**

Making sure the dataset represents all demographic groups addresses its diversity, so the model can learn from a wide range of customer preferences.
Accuracy and reliability concern the correctness and consistency of the data rather than how broadly it represents groups. Recency bias is a flaw in which recent data is over-weighted, which is not what including all demographics describes.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 334: aif-q252

A bank has defined equal-opportunity criteria for loan approvals, identified the legally and contextually relevant applicant groups, and set acceptable disparity thresholds. Which evaluation best checks whether its model meets those fairness requirements?

- **A.** Count the model's hidden layers
- **B.** Compare true-positive rates and decision outcomes across the defined groups on representative labeled evaluation data
- **C.** Keep the model's decision process secret
- **D.** Measure aggregate accuracy on one static dataset without group comparisons

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Compare true-positive rates and decision outcomes across the defined groups on representative labeled evaluation data

**Explanation:**

The bank must evaluate the outcomes tied to its chosen fairness definition across the groups identified in its risk assessment. Comparing group results with the accepted disparity thresholds tests the stated requirement.
Model depth does not measure fairness. Secrecy limits oversight, and aggregate accuracy can hide disparities between groups.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 335: aif-q292

Which Amazon Bedrock capability can detect an invisible watermark in images generated by Amazon Titan Image Generator?

- **A.** Amazon Bedrock watermark detection
- **B.** Amazon Macie
- **C.** SageMaker Model Monitor
- **D.** AWS CloudTrail

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Amazon Bedrock watermark detection

**Explanation:**

Bedrock watermark detection applies to watermarks embedded in images generated by Amazon Titan Image Generator. It is not a universal detector for images from every model.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon Titan Image Generator
- Last verified by source: 2026-11-03

---

### Question 336: aif-q053

A team is selecting EC2 compute for training a large model and prioritizes purpose-built training price performance and energy efficiency. Which instance family should it evaluate?

- **A.** P instances
- **B.** Trn instances powered by AWS Trainium
- **C.** G instances
- **D.** C compute-optimized CPU instances

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Trn instances powered by AWS Trainium

**Explanation:**

Trn instances use AWS Trainium, which AWS designed for efficient deep-learning training. Workload measurements are still required; this does not prove the lowest environmental impact in every deployment. C instances are compute-optimized CPU instances.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon EC2, AWS Trainium
- Last verified by source: 2026-11-03

---

### Question 337: aif-q160

A gaming community platform uses Amazon Bedrock Guardrails to screen harmful user inputs and model outputs. Which two content categories can the guardrails filter?

- **A.** Politics
- **B.** Hate
- **C.** Gambling
- **D.** Violence

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Hate; D. Violence

**Explanation:**

Amazon Bedrock Guardrails include configurable content filters for harmful categories such as Hate and Violence, which can be applied to both user inputs and model outputs.
Politics and Gambling are not standard Bedrock Guardrails content-filter categories, so the guardrails do not filter by them.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 338: aif-q192

A forum operator wants to stop users from posting discriminatory content and plans to use Amazon Bedrock. How can the operator use Amazon Bedrock to meet this requirement?

- **A.** Restrict user conversations to a set of predefined topics
- **B.** Block interactions that relate to predefined disallowed topics
- **C.** Let users interact based on their personal preferences
- **D.** Offer a range of responses for users to choose from

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Block interactions that relate to predefined disallowed topics

**Explanation:**

Amazon Bedrock Guardrails let the operator define disallowed topics or categories such as discriminatory or hateful content and automatically block inputs and outputs that fall under them, which prevents that content from being posted.
Restricting conversations to predefined allowed topics is a different control and would limit normal use rather than block specific harmful content. Letting users interact by preference and offering a range of responses do nothing to filter discriminatory content.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 339: aif-q037

A team trains a model that generates images of people in various jobs, but imbalanced data skews certain attributes and introduces bias. Which technique addresses this?

- **A.** Monitor the class distribution after deployment
- **B.** Augment the data to balance underrepresented classes
- **C.** Train for more epochs on the existing imbalanced data
- **D.** Apply stronger output filtering to the generated images

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Augment the data to balance underrepresented classes

**Explanation:**

Augmenting the data to balance underrepresented classes reduces the skew that causes the bias, addressing the problem at its source.
Monitoring only detects imbalance, training more epochs on the same imbalanced data reinforces the bias, and output filtering screens results without fixing the underlying dataset.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 340: aif-q054

A company builds an app that creates children's stories with Amazon Bedrock and must keep the content appropriate for young users. Which feature fits?

- **A.** Agents for Amazon Bedrock
- **B.** Amazon Bedrock Guardrails
- **C.** Amazon Bedrock Prompt Management
- **D.** Amazon Bedrock playgrounds

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock Guardrails

**Explanation:**

Amazon Bedrock Guardrails apply content filters and topic restrictions to model output, keeping generated stories appropriate for children.
Agents orchestrate tasks, Prompt Management versions prompts, and playgrounds is an experimentation console; none enforces content safety.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails, Agents for Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 341: aif-q123

An audit found that a bank's fine-tuned loan-approval model produces different approval rates across demographic groups. What should the bank do first?

- **A.** Add Retrieval Augmented Generation (RAG)
- **B.** Investigate data representation, label quality, decision thresholds, error rates, and the approved fairness criteria before choosing a remedy
- **C.** Pre-train a new model immediately
- **D.** Apply a content guardrail and assume the disparity is fixed

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Investigate data representation, label quality, decision thresholds, error rates, and the approved fairness criteria before choosing a remedy

**Explanation:**

A difference in outcomes does not identify one cause or one valid remedy. The bank should diagnose the disparity against its defined fairness criteria, inspect the data and labels, compare group error rates, and review the decision process. The evidence may support resampling, relabeling, threshold changes, retraining, process changes, or another approved response.
RAG does not repair a decision disparity. Immediate pre-training is costly and skips diagnosis, while a content guardrail does not establish fair loan decisions.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-11-03

---

### Question 342: aif-q169

A Retrieval Augmented Generation (RAG) newsletter app on Amazon Bedrock is surfacing politically slanted content. Which Amazon Bedrock Guardrails feature can filter this?

- **A.** Word filters
- **B.** Content filters
- **C.** Denied topics
- **D.** Sensitive information filters

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Denied topics

**Explanation:**

Denied topics let you define subjects, such as politics, that the model must avoid, and Amazon Bedrock enforces this during generation to filter out politically slanted content.
Word filters block only specific terms, content filters target categories like hate or violence, and sensitive information filters redact data such as PII.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-06-02

---

### Question 343: aif-q249

An online store's chatbot must filter harmful content from both user prompts and its responses. Which Amazon Bedrock feature fits?

- **A.** Amazon Bedrock Agents
- **B.** Amazon Bedrock Guardrails
- **C.** Amazon Bedrock Knowledge Bases
- **D.** Amazon Bedrock custom models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock Guardrails

**Explanation:**

Amazon Bedrock Guardrails filter harmful or inappropriate content in both input prompts and model responses, providing the safeguards the chatbot needs.
Amazon Bedrock Agents orchestrate tasks, Knowledge Bases retrieve context, and custom models customize behavior; none filters harmful content.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-06-02

---

### Question 344: aif-q297

A company uses large language models (LLMs) for tutoring apps and needs configurable safeguards that enforce standard safety rules with the LEAST effort. Which solution fits?

- **A.** Amazon SageMaker Clarify
- **B.** Amazon Bedrock Guardrails
- **C.** Amazon Bedrock Model Evaluation
- **D.** Amazon SageMaker JumpStart

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock Guardrails

**Explanation:**

Amazon Bedrock Guardrails provide configurable safeguards that enforce safety rules on LLM inputs and outputs with little setup effort.
SageMaker Clarify detects bias, Amazon Bedrock Model Evaluation scores models, and SageMaker JumpStart offers pre-trained models; none enforces configurable safety rules.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails, Amazon SageMaker Clarify
- Last verified by source: 2026-06-02

---

### Question 345: aif-q311

A model performs well on training data but poorly on evaluation data. What is the most likely cause?

- **A.** The model is underfit
- **B.** The model is overfit
- **C.** There is data leakage between the train and test sets
- **D.** The model needs more training epochs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. The model is overfit

**Explanation:**

Overfitting occurs when a model learns the training data too closely, including noise, so it performs well on training data but fails to generalize to unseen evaluation data.
An underfit model performs poorly even on training data, data leakage tends to inflate test performance rather than depress it, and adding more epochs would worsen overfitting rather than explain it.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 346: aif-q060

A company has built a chatbot that answers natural-language questions by returning images. It wants to reduce inappropriate or unwanted images before users receive them. Which solution most directly meets this requirement?

- **A.** Retrain the model on a large public dataset
- **B.** Automate the collection of user feedback
- **C.** Integrate content moderation APIs and define a review or blocking policy
- **D.** Carry out model validation only before launch

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Integrate content moderation APIs and define a review or blocking policy

**Explanation:**

Content moderation can detect policy violations in candidate images so the application can block or review them before delivery. Classifiers can miss prohibited content or flag acceptable content, so moderation reduces violations but does not guarantee that every unwanted image is stopped.
A public training dataset does not enforce the company's policy. User feedback acts after exposure, and prelaunch validation does not inspect each runtime output.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 347: aif-q389

A publishing company uses a generative AI model to create illustrations for its books. The company discovers that some generated images closely resemble copyrighted artwork from other publishers. Which responsible AI concern does this represent?

- **A.** Model hallucination
- **B.** Intellectual property infringement
- **C.** Data drift
- **D.** Overfitting

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Intellectual property infringement

**Explanation:**

When a generative AI model produces outputs that closely resemble copyrighted works, it raises the risk of intellectual property infringement, which is a legal risk of working with generative AI that companies must address through proper data curation and output review.
Model hallucination refers to generating plausible but factually incorrect content, not reproducing existing copyrighted material. Data drift describes changes in input data patterns over time. Overfitting means a model memorizes training data too closely and generalizes poorly, which is a different technical problem from IP infringement.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 348: aif-q390

A bank's generative AI chatbot gives incorrect financial guidance to customers. Complaints and negative press reduce customer confidence in the bank. Which reputational or business risk is the bank experiencing?

- **A.** Sampling bias in training data
- **B.** Loss of customer trust
- **C.** Model underfitting
- **D.** Increased inference latency

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Loss of customer trust

**Explanation:**

Incorrect guidance and public complaints can damage the bank's reputation and reduce customer trust. Legal or regulatory exposure may also arise, but the answer named here is the reputational and business effect stated in the scenario.
Sampling bias and underfitting are possible technical causes that the stem does not establish. Inference latency is unrelated to the reported complaints and negative press.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 349: aif-q391

An existing SageMaker AI customer uses an ML model to flag abnormal lab results. Medical professionals must review selected predictions before results reach patients. Which eligible existing-customer capability supports this human-review workflow?

- **A.** Amazon SageMaker Clarify
- **B.** Amazon Augmented AI (Amazon A2I)
- **C.** Amazon SageMaker Model Monitor
- **D.** Amazon Bedrock Guardrails

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Augmented AI (Amazon A2I)

**Explanation:**

For an eligible existing customer, Amazon A2I supports human-review workflows that can route selected predictions to qualified reviewers before delivery. Amazon A2I is no longer open to new customers.
SageMaker Clarify analyzes bias and explainability, Model Monitor runs scheduled monitoring jobs, and Bedrock Guardrails evaluate configured content policies. They do not create this A2I review loop.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: Amazon Augmented AI (Amazon A2I), Amazon SageMaker Clarify, Amazon SageMaker Model Monitor, Amazon Bedrock Guardrails
- Last verified by source: 2026-06-03

---

### Question 350: aif-q392

Which of the following is a legal risk that organizations should consider when deploying generative AI applications to customers?

- **A.** Reduced model training time
- **B.** Increased hardware utilization
- **C.** Potential harm to end users from inaccurate or biased outputs
- **D.** Lower cloud computing costs

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Potential harm to end users from inaccurate or biased outputs

**Explanation:**

Potential harm to end users from inaccurate or biased outputs is a legal risk organizations must consider, as customers who receive incorrect advice, biased decisions, or harmful content may suffer real consequences, leading to liability, regulatory penalties, and litigation.
Reduced model training time, increased hardware utilization, and lower cloud computing costs are operational benefits or metrics that do not represent legal risks to end users.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 351: aif-q454

A company is choosing between several foundation models and wants to minimize the environmental impact of its AI workloads. Which responsible AI practice should guide this decision?

- **A.** Choose the largest model available to maximize accuracy
- **B.** Select a model sized appropriately for the task to reduce unnecessary compute and energy consumption
- **C.** Always use the most expensive model to ensure quality
- **D.** Run inference continuously to keep the endpoint warm

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Select a model sized appropriately for the task to reduce unnecessary compute and energy consumption

**Explanation:**

Selecting a model appropriately sized for the task avoids wasting compute resources and energy on unnecessary capacity, which directly reduces the environmental footprint of AI workloads and reflects responsible model selection practices focused on sustainability.
Choosing the largest model wastes resources when a smaller one suffices. Using the most expensive model does not inherently reduce environmental impact. Running inference continuously wastes energy when demand is intermittent.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 352: aif-q463

A machine learning team is performing a responsible-AI bias and fairness evaluation for a loan-approval model before and after it goes live. Arrange the following activities in the correct order, from first to last.

- **A.** Run bias metrics on the trained model's predictions to compare outcomes across the protected groups
- **B.** Inspect the training dataset for class imbalance and under-representation of protected groups
- **C.** Define the fairness criteria and choose which attributes, such as age or gender, count as sensitive
- **D.** Record the intended use, evaluation results, and residual risk in a model card for reviewers
- **E.** Monitor the deployed endpoint for bias and feature-attribution drift over time

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Define the fairness criteria and choose which attributes, such as age or gender, count as sensitive → B. Inspect the training dataset for class imbalance and under-representation of protected groups → A. Run bias metrics on the trained model's predictions to compare outcomes across the protected groups → D. Record the intended use, evaluation results, and residual risk in a model card for reviewers → E. Monitor the deployed endpoint for bias and feature-attribution drift over time

**Explanation:**

You must first define the fairness criteria and identify the sensitive attributes, because every later measurement depends on knowing which groups you are comparing and what fair means for this use case. With that settled you analyze the training data for imbalance (pre-training bias), then measure the trained model's predictions across groups (post-training bias), document the intended use and findings in a model card, and finally monitor the live endpoint for drift, which only exists once the model is in production.
A learner should anchor the sequence to the lifecycle: criteria and definitions come before any data analysis, data bias is checked before model bias, governance documentation captures the results before release, and production monitoring is necessarily last. A tempting mistake is to analyze the training data first, but without agreed fairness criteria and a defined set of sensitive attributes you would not know which imbalances actually matter.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: ordering
- Services: None listed
- Last verified by source: 2026-06-13

---

### Question 353: aif-q464

Match each AWS responsible-AI capability to the purpose it serves. Treat SageMaker Clarify, SageMaker Model Monitor, and Amazon A2I as legacy capabilities available to eligible existing customers; they are no longer open to new customers.

- **A.** Amazon SageMaker Clarify (eligible existing customers)
- **B.** Amazon SageMaker Model Monitor (eligible existing customers)
- **C.** Amazon Augmented AI (Amazon A2I, eligible existing customers)
- **D.** Amazon SageMaker Model Cards

**Match targets:**

- **1.** Routes selected predictions to human reviewers under a configured review workflow
- **2.** Runs supported bias analyses and feature-attribution explanations
- **3.** Documents a model's intended use, evaluation results, and risk rating in one place for governance
- **4.** Runs configured monitoring schedules for data quality, model quality, bias drift, or feature-attribution drift

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A → 2 (Runs supported bias analyses and feature-attribution explanations); B → 4 (Runs configured monitoring schedules for data quality, model quality, bias drift, or feature-attribution drift); C → 1 (Routes selected predictions to human reviewers under a configured review workflow); D → 3 (Documents a model's intended use, evaluation results, and risk rating in one place for governance)

**Explanation:**

For eligible existing customers, SageMaker Clarify supports documented bias and explainability analyses, Model Monitor runs scheduled monitoring jobs, and Amazon A2I supports human-review workflows. These three capabilities are no longer open to new customers. Model Cards remain a documentation capability for intended use, evaluation, risk, and governance details.
Model Monitor works through configured schedules rather than continuous observation. Each capability also depends on supported data, model, endpoint, or workflow configurations.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.1
- Format: matching
- Services: Amazon SageMaker Clarify, Amazon SageMaker Model Monitor, Amazon Augmented AI (Amazon A2I), Amazon SageMaker Model Cards
- Last verified by source: 2026-11-03

---

## Task 4.2

Questions for this task: 18

### Question 354: aif-q001

A logistics company uses ML models to forecast demand each quarter. An analyst is preparing a report that helps stakeholders understand how the trained models reach their predictions. What should the analyst include to satisfy the transparency and explainability needs?

- **A.** Sample data used for training
- **B.** Model convergence tables
- **C.** Partial dependence plots (PDPs)
- **D.** Source code used to train the model

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Partial dependence plots (PDPs)

**Explanation:**

Partial dependence plots (PDPs) show how one or more input features relate to a model's predicted output, which makes them an effective way to explain feature influence and give stakeholders transparency into how the trained models reach their forecasts.
Source code used to train the model and sample training data reveal implementation and inputs but do not explain how individual features drive predictions. Model convergence tables describe how training progressed toward a solution rather than how the finished model behaves, so they do not meet the explainability requirement.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 355: aif-q003

A research lab needs to sort genetic samples into 20 categories based on their characteristics. The team requires an algorithm whose internal decision logic can be clearly documented to show how it produces each output. Which algorithm fits this need?

- **A.** Logistic regression
- **B.** Decision trees
- **C.** Neural networks
- **D.** Linear regression

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Decision trees

**Explanation:**

Decision trees make their internal logic explicit through a series of readable split rules, so the team can document exactly how the model moves from input characteristics to one of the 20 output categories. This interpretability is why decision trees fit the requirement.
Neural networks are highly opaque, so their internal mechanism is difficult to document. Linear regression predicts a continuous value rather than assigning discrete categories, which does not match a 20-class problem. Logistic regression is interpretable through its coefficients but is less natural for clearly documenting decision paths across many classes than a decision tree.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 356: aif-q091

A research team builds custom ML models and shares the model artifacts with other teams, while keeping the training code and data. The team wants a standardized way to document and later audit each model it publishes. Which solution should the team use?

- **A.** Write the details in documents and store them in Amazon S3
- **B.** Commit the model training scripts to a Git repository
- **C.** Create Amazon SageMaker Model Cards that capture intended uses and training and inference details
- **D.** Use AWS AI Service Cards to describe the models

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Create Amazon SageMaker Model Cards that capture intended uses and training and inference details

**Explanation:**

Amazon SageMaker Model Cards provide a standardized place to document a model's intended uses along with its training and inference details, giving the team a consistent, shareable record that other teams can later audit.
Writing the details in documents stored in Amazon S3 is unstructured and not standardized. Committing training scripts to a Git repository versions code rather than model metadata. AWS AI Service Cards describe AWS's own managed AI services, not custom models the team builds.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards
- Last verified by source: 2026-06-02

---

### Question 357: aif-q111

A bank is building a loan-decision solution on a foundation model. For audit and oversight, the bank needs the model's decisions to be explainable. Which factor most affects how explainable those decisions are?

- **A.** Training time
- **B.** Model complexity
- **C.** Number of hyperparameters
- **D.** Deployment time

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Model complexity

**Explanation:**

Model complexity most affects explainability: simpler models such as linear models or decision trees are easier to interpret, while highly complex models like deep neural networks behave as black boxes whose decisions are hard to explain for audit purposes.
Training time, the number of hyperparameters, and deployment time relate to how the model is built and operated, but they do not determine how interpretable its decisions are.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 358: aif-q113

A company wants a lead-scoring application that lets employees see and adjust the weight given to each input variable based on their domain expertise. Which type of ML model supports this requirement?

- **A.** K-nearest neighbors (k-NN) model
- **B.** Logistic regression model
- **C.** Deep learning model built on principal components
- **D.** Neural network

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Logistic regression model

**Explanation:**

A logistic regression model assigns an explicit weight (coefficient) to each input variable, so employees can see how each feature contributes and adjust those weights using their domain expertise. This interpretability matches the requirement.
K-nearest neighbors makes predictions from neighboring data points and has no per-feature weights to adjust. A neural network and a deep learning model built on principal components are opaque and do not expose simple, adjustable feature weights.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 359: aif-q141

What is a benefit of using Amazon SageMaker Model Cards to document AI models?

- **A.** Reducing a model's overall computational requirements
- **B.** Standardizing information about a model's purpose, performance, and limitations
- **C.** Providing a visually appealing summary of a model's capabilities
- **D.** Physically storing models for archival purposes

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Standardizing information about a model's purpose, performance, and limitations

**Explanation:**

Amazon SageMaker Model Cards standardize the documentation of a model's purpose, performance, and limitations, which supports transparency, governance, and easier tracking of models over time.
Reducing computational requirements and physically storing models for archival are not functions of Model Cards. Providing a visually appealing summary is a presentation detail rather than the core benefit of standardized documentation.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards
- Last verified by source: 2026-06-02

---

### Question 360: aif-q149

Which SageMaker AI feature records intended use, risk rating, training details, evaluation results, and other model-governance documentation?

- **A.** SageMaker Model Cards
- **B.** SageMaker Clarify
- **C.** SageMaker Feature Store
- **D.** SageMaker Ground Truth

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Model Cards

**Explanation:**

Model Cards document model information and completed analyses. They do not calculate prediction explanations; SageMaker Clarify performs bias and explainability analyses.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards, Amazon SageMaker Clarify
- Last verified by source: 2026-11-03

---

### Question 361: aif-q165

A company is collaborating with several research institutes to develop an AI model. It needs standardized documentation that tracks model versions and records how the model was developed. Which solution meets these requirements?

- **A.** Track model changes by using a Git repository
- **B.** Track model changes by using Amazon Comprehend
- **C.** Track model changes by using Amazon SageMaker Model Cards
- **D.** Track model changes by using Amazon S3

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Track model changes by using Amazon SageMaker Model Cards

**Explanation:**

Amazon SageMaker Model Cards provide a standardized framework for documenting model details and versions along with a record of how the model was developed, which meets the need for shared, auditable documentation across collaborators.
A Git repository versions code rather than standardized model documentation. Amazon Comprehend performs natural language processing, and Amazon S3 stores objects without any model-documentation structure.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards
- Last verified by source: 2026-06-02

---

### Question 362: aif-q172

A hospital built an AI system that gives patients personalized treatment recommendations. The system must explain the reasoning behind each recommendation and make those insights accessible to both doctors and patients. Which human-centered design principle does this reflect?

- **A.** Data governance
- **B.** Privacy and security
- **C.** Explainability
- **D.** Fairness

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Explainability

**Explanation:**

Explaining the reasoning behind each treatment recommendation and making those insights accessible to doctors and patients reflects explainability, a human-centered design principle that focuses on making AI decisions understandable.
Privacy and security concern protecting patient data, fairness concerns equitable outcomes across groups, and data governance concerns policies for managing data. None of these describes revealing the rationale behind the system's recommendations.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 363: aif-q231

An AI practitioner is building an ML model and wants to give stakeholders transparency and explainability into its predictions. Which solution meets this requirement?

- **A.** Present the model's Shapley values
- **B.** Provide the model's accuracy measure
- **C.** Provide the model's confusion matrix
- **D.** Provide a secure model inference endpoint

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Present the model's Shapley values

**Explanation:**

Shapley values quantify how much each feature contributes to an individual prediction, which gives stakeholders transparency and explainability into why the model produced a given output.
Accuracy and the confusion matrix measure overall model performance but do not explain individual predictions. A secure inference endpoint concerns how the model is deployed and accessed, not how its predictions are explained.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 364: aif-q255

A company has an ML model and wants to understand how the model arrives at its predictions. Which term describes understanding a model's predictions?

- **A.** Model interpretability
- **B.** Model training
- **C.** Model performance
- **D.** Model interoperability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Model interpretability

**Explanation:**

Model interpretability refers to understanding how a model arrives at its predictions, which is exactly what the company wants.
Model training is the process of fitting the model to data, model performance measures how well it predicts, and model interoperability concerns working across systems. None of these terms describes understanding the reasoning behind predictions.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 365: aif-q262

A bank uses a generative AI model to set credit limits for new customers and wants to make the model's decision-making process more transparent to those customers. Which solution meets this requirement?

- **A.** Replace the ML model with a rule-based system
- **B.** Apply explainable AI techniques to show which factors influenced the model's decision
- **C.** Build an interactive UI that gives customers detailed technical explanations of the system
- **D.** Increase the model's accuracy to reduce the need for transparency

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Apply explainable AI techniques to show which factors influenced the model's decision

**Explanation:**

Applying explainable AI techniques surfaces the specific factors that influenced each credit-limit decision, making the generative AI model's reasoning transparent to customers.
Replacing the model with a rule-based system changes the approach instead of explaining the model. An interactive UI with detailed technical explanations does not necessarily reveal which factors drove a decision. Increasing accuracy improves predictions but does not make the decision process transparent.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 366: aif-q267

An existing SageMaker Clarify customer wants feature-attribution explanations for an ML model in a supported analysis configuration. Which eligible capability meets this requirement?

- **A.** Amazon Quick
- **B.** Amazon Comprehend
- **C.** AWS Trusted Advisor
- **D.** Amazon SageMaker Clarify

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Amazon SageMaker Clarify

**Explanation:**

For eligible existing customers, SageMaker Clarify can produce feature-attribution explanations for supported models and analysis configurations. SageMaker Clarify is no longer open to new customers. The team must evaluate whether each explanation is suitable for its audience and use case.
Amazon Quick supports business analysis, Amazon Comprehend performs natural-language processing, and AWS Trusted Advisor checks AWS environments against recommendations.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Clarify
- Last verified by source: 2026-06-02

---

### Question 367: aif-q279

An existing SageMaker Clarify customer has a supported text-classification model and analysis configuration. The company needs feature attributions that show how input features influence model behavior. Which eligible capability meets this requirement?

- **A.** SageMaker Ground Truth
- **B.** SageMaker Clarify
- **C.** SageMaker Feature Store
- **D.** SageMaker Canvas

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. SageMaker Clarify

**Explanation:**

For eligible existing customers, SageMaker Clarify supports feature-attribution analysis for documented model and data configurations. SageMaker Clarify is no longer open to new customers, so the answer depends on the existing-customer and supported-configuration conditions in the stem.
SageMaker Ground Truth labels data, Feature Store manages features, and Canvas provides no-code model workflows.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Clarify
- Last verified by source: 2026-06-02

---

### Question 368: aif-q287

A team has completed a SageMaker Clarify explainability analysis and wants to record its findings with intended use and limitations. Which feature should it use?

- **A.** SageMaker Model Cards
- **B.** SageMaker Feature Store
- **C.** SageMaker Ground Truth
- **D.** SageMaker Data Wrangler

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Model Cards

**Explanation:**

Model Cards record completed explainability analyses and governance details. SageMaker Clarify calculates the explainability results; the card documents them.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards, Amazon SageMaker Clarify
- Last verified by source: 2026-11-03

---

### Question 369: aif-q039

A company has an existing-customer SageMaker AI model supported by SageMaker Clarify and wants feature attributions for individual predictions. Which capability fits?

- **A.** SageMaker Clarify online explainability
- **B.** SageMaker Ground Truth labeling
- **C.** SageMaker Feature Store
- **D.** Amazon Transcribe

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. SageMaker Clarify online explainability

**Explanation:**

SageMaker Clarify can provide online explanations for supported models and endpoint configurations. Availability and setup depend on the supported model and the customer's SageMaker environment.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: Amazon SageMaker Clarify
- Last verified by source: 2026-11-03

---

### Question 370: aif-q171

An electronics retailer has built an AI assistant that answers customer questions using its product manuals. Which approach is most likely to increase customers' trust in the assistant's answers?

- **A.** Displaying the model's confidence score with each answer
- **B.** Giving the assistant a robotic on-screen avatar
- **C.** Linking to the product manual sections that support each answer
- **D.** Tuning the assistant to match the brand's tone of voice

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Linking to the product manual sections that support each answer

**Explanation:**

Linking to the specific product manual sections that support each answer lets customers verify the information for themselves, which builds trust by grounding the response in a citable, authoritative source rather than relying on the model's output alone.
Displaying the model's confidence score exposes an internal value that customers are not equipped to interpret, and a high score on a wrong answer would mislead rather than reassure. Giving the assistant a robotic on-screen avatar is a presentation choice that signals the agent is not human but says nothing about the accuracy of its answers. Tuning the assistant to match the brand's tone of voice improves consistency and style but gives customers no way to confirm that the information itself is correct.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-01

---

### Question 371: aif-q455

A company is deciding between a deep neural network and a decision tree for a customer-facing application. The deep neural network is more accurate, but the company needs to explain every decision to regulators. Which tradeoff does this represent?

- **A.** Cost vs latency
- **B.** Interpretability vs performance
- **C.** Training time vs accuracy
- **D.** Data volume vs model size

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Interpretability vs performance

**Explanation:**

The interpretability-versus-performance tradeoff means more complex models (like deep neural networks) often achieve higher accuracy but are harder to explain, while simpler models (like decision trees) are easy to interpret but may sacrifice some performance, which is exactly the tension the company faces.
Cost vs latency, training time vs accuracy, and data volume vs model size are different tradeoffs that do not describe the tension between explanation capability and prediction accuracy.

</details>

**Question metadata**

- Domain: 4
- Task statement: 4.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

# Domain 5: Security, compliance, and governance for AI solutions

Questions in this domain: 48

## Task 5.1

Questions for this task: 32

### Question 372: aif-q009

A Bedrock retrieval component cannot read objects encrypted with Amazon S3 managed keys (SSE-S3). Which change should the team test first?

- **A.** Add the required s3:GetObject access and verify the bucket policy and explicit denies
- **B.** Add kms:Decrypt for an S3-managed key
- **C.** Make the bucket public
- **D.** Change the prompt

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Add the required s3:GetObject access and verify the bucket policy and explicit denies

**Explanation:**

SSE-S3 uses keys managed by Amazon S3, so the caller does not use kms:Decrypt for those objects. The team should verify S3 identity and bucket-policy authorization. SSE-KMS can require KMS authorization.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon S3, AWS Identity and Access Management (IAM)
- Last verified by source: 2026-11-03

---

### Question 373: aif-q013

A bank is building an AI application on Amazon Bedrock. The application sits in a VPC that, to satisfy regulators, must be cut off from all internet traffic. Which AWS service or feature meets these requirements?

- **A.** Internet gateway
- **B.** Amazon Macie
- **C.** AWS PrivateLink
- **D.** Amazon CloudFront

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. AWS PrivateLink

**Explanation:**

AWS PrivateLink creates private connectivity between a VPC and AWS services such as Amazon Bedrock, so traffic stays on the AWS network and never reaches the public internet, which satisfies the no-internet compliance requirement.
An internet gateway does the opposite of what is required by giving the VPC a path to the public internet. Amazon Macie discovers and protects sensitive data in Amazon S3 and does not provide private connectivity. Amazon CloudFront is a content delivery network that serves content over the internet.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS PrivateLink, Amazon Macie, Amazon CloudFront
- Last verified by source: 2026-06-02

---

### Question 374: aif-q026

A security company invokes foundation models (FMs) on Amazon Bedrock and wants to limit use to approved users only. Before tightening its IAM roles and policies later, it first needs to spot any attempts to reach the models without authorization. Which AWS service should it use?

- **A.** AWS Trusted Advisor
- **B.** Amazon Inspector
- **C.** AWS CloudTrail
- **D.** AWS Audit Manager

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. AWS CloudTrail

**Explanation:**

AWS CloudTrail records API activity across AWS services, so it captures who attempted to call Amazon Bedrock and when, letting the company identify unauthorized access attempts and refine its IAM roles and policies.
AWS Trusted Advisor gives best-practice recommendations on cost, performance, and security but does not log individual access attempts. Amazon Inspector scans workloads for software vulnerabilities. AWS Audit Manager automates evidence collection for audits rather than tracking who tried to access a service.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS CloudTrail, AWS Trusted Advisor, Amazon Inspector, AWS Audit Manager
- Last verified by source: 2026-06-02

---

### Question 375: aif-q061

An AI practitioner relies on an Amazon Bedrock base model to summarize support chats and wants to keep a record of what goes into and comes out of the model for monitoring. Which approach should the practitioner take?

- **A.** Set AWS CloudTrail as the model's log destination
- **B.** Configure model invocation logging in Amazon EventBridge
- **C.** Turn on model invocation logging in Amazon Bedrock
- **D.** Set AWS Audit Manager as the model's log destination

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Turn on model invocation logging in Amazon Bedrock

**Explanation:**

Turning on model invocation logging in Amazon Bedrock captures and stores the model's input and output data, which is exactly what the practitioner needs to monitor invocations.
AWS CloudTrail records management API calls but not the model's prompt and response payloads. Amazon EventBridge routes events between services and is not where Bedrock invocation logging is enabled. AWS Audit Manager collects audit evidence rather than invocation data.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock, AWS CloudTrail, AWS Audit Manager, Amazon EventBridge
- Last verified by source: 2026-06-02

---

### Question 376: aif-q066

Each team uses a separate retrieval component to read only its own prefix in an S3 knowledge source. Which IAM design enforces that boundary?

- **A.** Give one shared role full S3 access
- **B.** Give each actual retrieval component a role scoped to its required bucket prefix and actions
- **C.** Put the customer name in the prompt
- **D.** Make the bucket public

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Give each actual retrieval component a role scoped to its required bucket prefix and actions

**Explanation:**

IAM permissions belong on the application, Knowledge Base service role, Lambda function, or other component that accesses S3. Each role should allow only the required actions and resource ARNs.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS Identity and Access Management (IAM), Amazon S3, Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 377: aif-q078

A custom model was trained on confidential records that should not have been included. Which response best reduces the risk?

- **A.** Mask any visible values after generation only
- **B.** Encrypt generated text after delivery
- **C.** Remove or sanitize the records, retrain or replace the model, and add runtime filtering, authorization, and testing
- **D.** Encrypt the existing model artifact and assume memorization is removed

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Remove or sanitize the records, retrain or replace the model, and add runtime filtering, authorization, and testing

**Explanation:**

Removing the data and retraining prevents that version from continuing in use, while runtime controls reduce disclosure risk. No step guarantees that a model will never reveal sensitive information.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock, Amazon SageMaker AI, AWS Key Management Service (AWS KMS)
- Last verified by source: 2026-11-03

---

### Question 378: aif-q084

A team builds and trains ML models in Amazon SageMaker Studio notebooks, keeping its data in an Amazon S3 bucket. It needs to control how data moves between Amazon S3 and the notebooks. Which solution meets this requirement?

- **A.** Use Amazon Macie to monitor SageMaker Studio
- **B.** Configure SageMaker to use a VPC with an Amazon S3 endpoint
- **C.** Use Amazon Inspector to monitor SageMaker Studio
- **D.** Configure SageMaker to use S3 Glacier Deep Archive

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Configure SageMaker to use a VPC with an Amazon S3 endpoint

**Explanation:**

Configuring Amazon SageMaker to use a VPC with an Amazon S3 endpoint creates a managed, private path for data to flow between Amazon S3 and the Studio notebooks without traversing the public internet.
Amazon Macie and Amazon Inspector monitor for sensitive data and vulnerabilities respectively, but neither manages the data path between services. Amazon S3 Glacier Deep Archive is a low-cost archival storage class and does not control data flow.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker AI, Amazon S3, Amazon Macie, Amazon Inspector
- Last verified by source: 2026-06-02

---

### Question 379: aif-q087

A company is about to adopt Amazon Bedrock and needs to know which security duties stay with the company under the AWS shared responsibility model. Which duty belongs to the company?

- **A.** Protecting the infrastructure that hosts Amazon Bedrock
- **B.** Patching and updating the versions of Amazon Bedrock
- **C.** Provisioning Amazon Bedrock within the company network
- **D.** Securing the company's data in transit and at rest

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Securing the company's data in transit and at rest

**Explanation:**

Under the AWS shared responsibility model, AWS secures the cloud infrastructure and managed services such as Amazon Bedrock, while the customer is responsible for security in the cloud, including protecting its own data in transit and at rest.
Patching Amazon Bedrock versions and protecting the hosting infrastructure are AWS responsibilities for a managed service. Provisioning Amazon Bedrock within the company network is not how the managed service is accessed and is not a customer security responsibility.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 380: aif-q090

To satisfy regulators, a company must run its Amazon SageMaker AI training and inference in a sealed environment with no internet connectivity. Which solution will meet these requirements?

- **A.** Associate appropriate IAM roles with the SageMaker AI jobs
- **B.** Encrypt the data at rest using encryption for SageMaker geospatial capabilities
- **C.** Run the SageMaker AI training and inference jobs with network isolation
- **D.** Run the SageMaker AI training and inference jobs with SageMaker Experiments

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Run the SageMaker AI training and inference jobs with network isolation

**Explanation:**

Running the Amazon SageMaker AI training and inference jobs with network isolation removes internet access for those jobs, keeping them in the isolated environment that the regulations require.
Associating IAM roles controls permissions but does not remove internet connectivity. Encryption for geospatial capabilities protects data at rest, and SageMaker Experiments tracks training runs; neither isolates the job from the internet.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker AI, AWS Identity and Access Management (IAM)
- Last verified by source: 2026-06-02

---

### Question 381: aif-q104

A company runs custom models on Amazon Bedrock for a generative AI application and wants the model artifacts produced during customization jobs encrypted with a key the company controls. Which AWS service meets these requirements?

- **A.** Amazon Macie
- **B.** AWS Secrets Manager
- **C.** AWS Key Management Service (AWS KMS)
- **D.** Amazon Inspector

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. AWS Key Management Service (AWS KMS)

**Explanation:**

AWS Key Management Service (AWS KMS) lets the company create and control its own encryption key and use it to encrypt the model artifacts produced by Amazon Bedrock customization jobs.
Amazon Macie discovers sensitive data and Amazon Inspector scans for vulnerabilities, neither of which manages customer encryption keys. AWS Secrets Manager stores credentials and secrets, not the encryption keys used to protect model artifacts.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS Key Management Service (AWS KMS), Amazon Macie, AWS Secrets Manager, Amazon Inspector
- Last verified by source: 2026-06-02

---

### Question 382: aif-q139

A company will move customer service emails into Amazon S3 for an analytics application. Because some emails hold sensitive data, the company wants an alert whenever such data appears. Which solution fully automates this detection with the LEAST development effort?

- **A.** Build several custom regex patterns and run them in a custom application to detect sensitive data
- **B.** Configure Amazon Macie to detect sensitive information in the documents uploaded to Amazon S3
- **C.** Deploy a large language model (LLM) on Amazon SageMaker endpoints to redact sensitive data
- **D.** Ask customers not to share sensitive information in their emails

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Configure Amazon Macie to detect sensitive information in the documents uploaded to Amazon S3

**Explanation:**

Amazon Macie is a managed service that uses machine learning to automatically discover sensitive data such as PII in Amazon S3 and can raise alerts when it is found, meeting the requirement with the least development effort.
Building custom regex patterns in a custom application and deploying an LLM on Amazon SageMaker endpoints both require significant development and maintenance. Asking customers not to share sensitive information does not detect or alert on anything.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Macie, Amazon SageMaker AI, Amazon S3
- Last verified by source: 2026-06-02

---

### Question 383: aif-q179

Which statement about federated learning is accurate?

- **A.** It keeps raw training data at participating locations, reducing centralization, but privacy and compliance still require additional controls
- **B.** It guarantees privacy and regulatory compliance
- **C.** It makes encryption unnecessary
- **D.** It prevents every inference attack

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. It keeps raw training data at participating locations, reducing centralization, but privacy and compliance still require additional controls

**Explanation:**

Federated learning can reduce raw-data centralization. Model updates can still leak information, and organizations remain responsible for security, privacy, and compliance controls.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 384: aif-q185

A workload must keep Amazon Bedrock processing in an approved Region and keep VPC-to-service traffic off the public internet. Which two independent choices address these requirements?

- **A.** Select an approved Bedrock Region and avoid a cross-Region inference profile
- **B.** Use an interface VPC endpoint powered by AWS PrivateLink
- **C.** Use an internet gateway
- **D.** Assume PrivateLink controls the service processing Region

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A; B

**Explanation:**

Region and inference-profile selection control where requests may be processed. PrivateLink controls the network path from the VPC. PrivateLink does not by itself select or restrict the processing Region.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock, AWS PrivateLink
- Last verified by source: 2026-11-03

---

### Question 385: aif-q208

A company with Amazon Bedrock access wants to control which models specific employees are allowed to use. Which solution meets these requirements?

- **A.** Use AWS Identity and Access Management (IAM) service roles to restrict model subscription
- **B.** Use AWS Identity and Access Management (IAM) policies to restrict model access
- **C.** Use Amazon Inspector to monitor model access
- **D.** Use AWS Security Token Service (AWS STS) to generate temporary credentials for model use

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use AWS Identity and Access Management (IAM) policies to restrict model access

**Explanation:**

AWS Identity and Access Management (IAM) policies can allow or deny Amazon Bedrock API actions scoped to specific model resources, so the company can restrict which models each employee is allowed to invoke.
IAM service roles grant permissions to services rather than restricting which models a user can subscribe to, AWS STS issues temporary credentials but does not by itself limit model access, and Amazon Inspector scans for vulnerabilities rather than controlling access.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS Identity and Access Management (IAM), Amazon Bedrock, Amazon Inspector
- Last verified by source: 2026-06-02

---

### Question 386: aif-q215

A company analyzes confidential documents with a third-party model on Amazon Bedrock and is worried about data privacy. Which statement explains how Amazon Bedrock keeps that data private?

- **A.** User inputs are kept confidential, but model outputs are shared with the third-party model providers
- **B.** User inputs and model outputs are anonymized and then shared with the third-party model providers
- **C.** User inputs and model outputs are not shared with any third-party model providers
- **D.** User inputs and model outputs are redacted before they are shared with the third-party model providers

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. User inputs and model outputs are not shared with any third-party model providers

**Explanation:**

Amazon Bedrock processes data within the AWS environment and does not share user inputs or model outputs with the third-party model providers, so the company's confidential documents stay private.
The options stating that outputs are shared, that inputs and outputs are anonymized and shared, or that data is redacted before sharing are all incorrect because Amazon Bedrock does not send the inputs or outputs to the model providers at all.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock
- Last verified by source: 2026-06-02

---

### Question 387: aif-q229

A bank wants to evaluate generated answers for grounding against supplied source text and block responses that fail its threshold. Which design fits?

- **A.** Use Bedrock Guardrails contextual grounding checks and have the application enforce the returned intervention
- **B.** Use AWS Config
- **C.** Use Amazon Inspector
- **D.** Use a larger context window and assume every claim is correct

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Use Bedrock Guardrails contextual grounding checks and have the application enforce the returned intervention

**Explanation:**

Contextual grounding checks evaluate a response after or during the generation flow and can return an intervention. They do not stop the model from computing candidate text; the service or application blocks the failed response from reaching the user.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-11-03

---

### Question 388: aif-q235

A healthcare application in a VPC must call Amazon Bedrock without sending API traffic across the public internet. Which network design meets that requirement?

- **A.** Restrict access with IAM policies only
- **B.** Use an interface VPC endpoint powered by AWS PrivateLink for the required Amazon Bedrock API
- **C.** Encrypt data at rest with AWS KMS only
- **D.** Route calls through an internet gateway

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use an interface VPC endpoint powered by AWS PrivateLink for the required Amazon Bedrock API

**Explanation:**

An interface VPC endpoint lets resources in the VPC reach supported Amazon Bedrock APIs over the AWS network without an internet gateway, NAT device, or public IP address. The team must choose the endpoint that matches the API it calls and apply endpoint, IAM, and resource policies.
PrivateLink controls the network path. Amazon Bedrock remains an AWS managed service, and model processing does not occur inside the customer's VPC. IAM controls authorization, while KMS protects data at rest; neither alone creates a private API path.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS PrivateLink, Amazon Bedrock, AWS Identity and Access Management (IAM), AWS Key Management Service (AWS KMS)
- Last verified by source: 2026-11-03

---

### Question 389: aif-q248

A company with offices around the world requires that every API call between its generative AI applications and the foundation models (FMs) avoid the public internet. Which AWS service should it use?

- **A.** Amazon Q
- **B.** AWS CloudTrail
- **C.** AWS PrivateLink
- **D.** Amazon CloudFront

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. AWS PrivateLink

**Explanation:**

AWS PrivateLink provides private connectivity between VPCs and AWS services, so API calls between the generative AI applications and the foundation models stay on the AWS network and off the public internet.
Amazon Q is a generative AI assistant, AWS CloudTrail logs API activity, and Amazon CloudFront is a content delivery network that serves traffic over the internet; none of these keeps API traffic off the public internet.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS PrivateLink, Amazon Q, AWS CloudTrail, Amazon CloudFront
- Last verified by source: 2026-06-02

---

### Question 390: aif-q269

A company wants to reach Amazon Bedrock APIs privately from within its AWS account while keeping its data away from the public internet. Which solution meets these requirements?

- **A.** Use AWS Glue to set up data encryption across the company's data catalog
- **B.** Use AWS PrivateLink to configure a private connection between the company's VPC and Amazon Bedrock
- **C.** Use Amazon CloudFront to restrict access to the company's private content
- **D.** Use AWS Lake Formation to manage centralized data governance and cross-account data sharing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Use AWS PrivateLink to configure a private connection between the company's VPC and Amazon Bedrock

**Explanation:**

AWS PrivateLink configures a private connection between the company's VPC and Amazon Bedrock APIs, so calls and data transfers stay within the AWS network and are not exposed to the public internet.
AWS Glue handles data integration and cataloging, Amazon CloudFront restricts and delivers content over the internet, and AWS Lake Formation manages data governance and sharing; none of these creates a private network connection to Amazon Bedrock.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS PrivateLink, Amazon Bedrock, AWS Glue, Amazon CloudFront, AWS Lake Formation
- Last verified by source: 2026-06-02

---

### Question 391: aif-q040

A chatbot built on a fine-tuned Amazon SageMaker JumpStart model must meet several regulatory frameworks. Which two security-control categories can support the company's compliance program?

- **A.** Cost optimization
- **B.** Data protection
- **C.** Elastic auto scaling
- **D.** Threat detection
- **E.** Faster time to market

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Data protection; D. Threat detection

**Explanation:**

Data-protection and threat-detection controls can support a compliance program by protecting regulated data and identifying security events. The company must map implemented controls and collected evidence to each framework's requirements.
These control categories do not prove that the workload complies or transfer the customer's obligations to AWS. Cost optimization, scaling, and delivery speed do not address the stated security-control need.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker JumpStart
- Last verified by source: 2026-11-03

---

### Question 392: aif-q213

A bank wants to reduce the chance that a fine-tuned model exposes customer PII. Which control should it apply before training?

- **A.** Increase top-k
- **B.** Rely on a guardrail alone
- **C.** Remove or de-identify PII and verify the prepared dataset before training
- **D.** Use encryption alone

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Remove or de-identify PII and verify the prepared dataset before training

**Explanation:**

Data minimization and de-identification reduce the chance that the model learns customer identifiers. Runtime access controls, testing, and filtering remain necessary; preprocessing does not provide a never-disclose guarantee.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails, Amazon Bedrock
- Last verified by source: 2026-11-03

---

### Question 393: aif-q218

A company wants to control which publicly available foundation models (FMs) its employees can access. Which solution fits?

- **A.** Analyze usage in AWS Cost Explorer
- **B.** Configure Amazon SageMaker JumpStart to restrict which FMs are discoverable
- **C.** Download compliance reports from AWS Artifact
- **D.** Review recommendations in AWS Trusted Advisor

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Configure Amazon SageMaker JumpStart to restrict which FMs are discoverable

**Explanation:**

Amazon SageMaker JumpStart lets administrators curate the model catalog, so configuring it to restrict which FMs are discoverable controls the models employees can access.
AWS Cost Explorer analyzes spending, AWS Artifact provides compliance documents, and AWS Trusted Advisor gives best-practice recommendations; none governs which models employees can access.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker JumpStart
- Last verified by source: 2026-06-02

---

### Question 394: aif-q299

Which statement correctly describes the Amazon Bedrock Guardrails prompt-attack filter?

- **A.** It is one defense layer that can detect and block configured prompt attacks
- **B.** It eliminates the need for least-privilege tools and authorization
- **C.** It guarantees detection of every direct and indirect injection
- **D.** It sanitizes training data

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. It is one defense layer that can detect and block configured prompt attacks

**Explanation:**

The prompt-attack filter is one layer. Secure systems also treat retrieved content and tool inputs as untrusted, validate parameters, enforce authorization outside the model, and monitor activity.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-11-03

---

### Question 395: aif-q034

How can a company use large language models securely on Amazon Bedrock?

- **A.** Configure IAM roles and policies based on least privilege
- **B.** Enable AWS Audit Manager to run automatic model evaluation jobs
- **C.** Enable Amazon Bedrock automatic model evaluation jobs
- **D.** Use Amazon CloudWatch Logs to make models explainable and monitor for bias

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Configure IAM roles and policies based on least privilege

**Explanation:**

Configuring IAM roles and policies based on least privilege restricts which users and applications can access the Amazon Bedrock models and actions, which is the foundational way to use large language models securely.
AWS Audit Manager collects evidence for compliance and does not run model evaluation jobs. Amazon Bedrock model evaluation assesses model performance rather than securing access. Amazon CloudWatch Logs records activity but does not make models explainable or detect bias.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: AWS Identity and Access Management (IAM), Amazon Bedrock, AWS Audit Manager, Amazon CloudWatch
- Last verified by source: 2026-06-02

---

### Question 396: aif-q191

An ecommerce company runs an AI chatbot on its website that lets customers submit orders around the clock. Which input vulnerability should the company address before launching the chatbot?

- **A.** Data leakage
- **B.** Prompt injection
- **C.** Large language model (LLM) hallucinations
- **D.** Concept drift

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Prompt injection

**Explanation:**

Prompt injection is an input vulnerability in which a user crafts malicious input to override or manipulate the chatbot's instructions, so the company must sanitize and constrain inputs before launch.
Data leakage is the exposure of sensitive information, large language model hallucinations are fabricated outputs, and concept drift is a gradual change in data patterns over time. None of these is an input-level attack on the chatbot's instructions.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 397: aif-q393

A company is deploying AI agents on Amazon Bedrock that need to access multiple backend systems on behalf of users. The company wants each agent to authenticate with its own identity rather than sharing a single set of credentials. Which AWS feature meets this requirement?

- **A.** AWS Secrets Manager
- **B.** Amazon Bedrock AgentCore Identity
- **C.** Amazon Macie
- **D.** AWS CloudTrail

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Amazon Bedrock AgentCore Identity

**Explanation:**

Amazon Bedrock AgentCore Identity provides identity management for AI agents, allowing each agent to authenticate with its own distinct identity when accessing backend systems, which supports the principle of least privilege and avoids sharing credentials.
AWS Secrets Manager stores and rotates credentials but does not provide per-agent identity management. Amazon Macie discovers sensitive data in Amazon S3. AWS CloudTrail logs API activity for auditing. None of these assigns individual identities to AI agents.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock AgentCore, AWS Secrets Manager, Amazon Macie, AWS CloudTrail
- Last verified by source: 2026-06-03

---

### Question 398: aif-q394

Which statement best describes what RAG contributes to answer quality?

- **A.** It grounds generation in retrieved passages, while evaluation or verification is still needed
- **B.** It verifies every generated statement
- **C.** It guarantees deterministic output
- **D.** It removes access-control requirements

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. It grounds generation in retrieved passages, while evaluation or verification is still needed

**Explanation:**

RAG supplies relevant source context and can improve factuality. Retrieval can miss information and generation can still misstate it, so RAG does not verify every answer.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 399: aif-q395

Which two runtime techniques can detect unsupported claims and keep questionable generative AI responses from reaching users?

- **A.** Validate claims against approved grounding sources
- **B.** Increase the training-data volume
- **C.** Apply an abstention threshold or route failed validation to human review
- **D.** Reduce the number of model parameters
- **E.** Add more GPU compute during inference

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Validate claims against approved grounding sources; C. Apply an abstention threshold or route failed validation to human review

**Explanation:**

Grounding or claim validation compares statements with approved evidence. The application can abstain, block the response, or send it to a reviewer when validation fails or falls below an accepted threshold. These controls detect potential hallucinations and define what happens before delivery.
More training data may affect model quality but does not validate a specific response. Parameter count and GPU capacity do not establish factual support.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon Bedrock Guardrails
- Last verified by source: 2026-11-03

---

### Question 400: aif-q396

A financial institution wants a record of the datasets, processing jobs, code, and model artifacts used in an ML workflow. Which practice records the sources and transformations among those artifacts?

- **A.** Data augmentation
- **B.** Data lineage tracking
- **C.** Data normalization
- **D.** Data balancing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Data lineage tracking

**Explanation:**

Data lineage tracking records relationships among registered sources, transformations, jobs, code, and model artifacts. Reviewers can use those records to trace how an artifact was produced.
Lineage coverage depends on the artifacts and relationships the organization captures. It does not prove policy compliance or guarantee row-level provenance for every record. The institution needs separate controls and evidence for collection authority, policy compliance, and any required record-level traceability.
Data augmentation, normalization, and balancing change training data but do not record workflow lineage.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-11-03

---

### Question 401: aif-q397

Which pair correctly separates documentation from technical lineage verification?

- **A.** Model Cards record declared provenance and intended use; lineage systems track relationships among data, jobs, code, and model artifacts
- **B.** Model Cards cryptographically verify every dataset
- **C.** Lineage systems write intended-use statements for authors
- **D.** Neither supports governance

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Model Cards record declared provenance and intended use; lineage systems track relationships among data, jobs, code, and model artifacts

**Explanation:**

Model Cards hold declared documentation. SageMaker lineage capabilities capture and query artifact relationships that reviewers can use to check how a model was produced.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker Model Cards, Amazon SageMaker Data Wrangler, Amazon SageMaker Feature Store, Amazon SageMaker Autopilot
- Last verified by source: 2026-11-03

---

### Question 402: aif-q456

A financial institution needs to trace which registered source datasets and processing steps produced each model artifact. Which practice meets this workflow-traceability requirement?

- **A.** Data augmentation
- **B.** Data lineage tracking
- **C.** Data normalization
- **D.** Data balancing

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Data lineage tracking

**Explanation:**

Data lineage tracking records the relationships among captured source artifacts, processing steps, and model artifacts. It can show which registered inputs and transformations produced a model.
Lineage records do not prove compliance and do not guarantee provenance for every row unless the organization implements that level of capture. Data augmentation, normalization, and balancing modify data rather than record these relationships.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: multiple choice
- Services: Amazon SageMaker AI
- Last verified by source: 2026-11-03

---

### Question 403: aif-q466

Match each AWS security and governance service to the role it plays when securing an AI or machine learning workload. Pair each service on the left with the correct description of its purpose on the right.

- **A.** AWS IAM
- **B.** AWS KMS
- **C.** Amazon Macie
- **D.** AWS CloudTrail

**Match targets:**

- **1.** Uses machine learning to discover and classify sensitive data, such as personally identifiable information, stored in Amazon S3
- **2.** Records account API activity to provide an audit trail of who did what and when across AWS services
- **3.** Enforces least-privilege access control by defining which identities can perform which actions on which resources
- **4.** Creates, stores, and manages the encryption keys used to protect data at rest

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A → 3 (Enforces least-privilege access control by defining which identities can perform which actions on which resources); B → 4 (Creates, stores, and manages the encryption keys used to protect data at rest); C → 1 (Uses machine learning to discover and classify sensitive data, such as personally identifiable information, stored in Amazon S3); D → 2 (Records account API activity to provide an audit trail of who did what and when across AWS services)

**Explanation:**

AWS IAM enforces least-privilege access control by governing which identities may perform which actions on which resources, AWS KMS creates and manages the encryption keys that protect data at rest, Amazon Macie uses machine learning to discover and classify sensitive data such as PII in Amazon S3, and AWS CloudTrail records account API activity to provide an audit trail of who did what and when. Each service maps to a distinct governance function: identity and access, key management, sensitive-data discovery, and API auditing.
A common error is to confuse CloudTrail with Macie or KMS, but CloudTrail logs API calls rather than scanning data content or managing keys, while Macie inspects the data itself in S3 and KMS handles only the cryptographic keys, so each pairing is unique and unambiguous.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.1
- Format: matching
- Services: AWS IAM, AWS KMS, Amazon Macie, AWS CloudTrail
- Last verified by source: 2026-06-13

---

## Task 5.2

Questions for this task: 16

### Question 404: aif-q028

A company regularly audits its operations alongside independent software vendors (ISVs) and wants an email alert each time a new ISV compliance report is published. Which AWS service meets this requirement?

- **A.** AWS Data Exchange
- **B.** AWS Trusted Advisor
- **C.** AWS Artifact
- **D.** AWS Audit Manager

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. AWS Artifact

**Explanation:**

AWS Artifact provides on-demand access to compliance reports and agreements, including third-party reports, and can notify the company when a new report becomes available.
AWS Data Exchange is a marketplace for third-party datasets, not compliance reports. AWS Trusted Advisor offers best-practice checks. AWS Audit Manager automates evidence collection for the company's own audits rather than distributing ISV reports.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: AWS Artifact, AWS Data Exchange, AWS Trusted Advisor, AWS Audit Manager
- Last verified by source: 2026-06-02

---

### Question 405: aif-q030

An insurer is mapping its generative AI projects onto the Generative AI Security Scoping Matrix. Which scope leaves the insurer with the MOST security responsibility?

- **A.** Building and training a generative AI model from scratch using data the company owns
- **B.** Fine-tuning an existing third-party foundation model (FM) with the company's own data
- **C.** Building an application on top of an existing third-party foundation model (FM)
- **D.** Using a third-party enterprise application that has generative AI features built in

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Building and training a generative AI model from scratch using data the company owns

**Explanation:**

Building and training a model from scratch on data the company owns gives the company full control over the data, training, deployment, and safeguards, so it carries the most security responsibility.
Fine-tuning a third-party FM, building an application on a third-party FM, and using a vendor application with embedded generative AI each shift increasing portions of responsibility to the provider, so they grant the company less ownership.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 406: aif-q124

A company must audit reads and writes of sensitive S3 training objects and archive the logs under a defined retention policy. Which design fits?

- **A.** Enable CloudTrail S3 data events for the bucket and use an S3 lifecycle rule to transition logs to the approved Glacier storage class
- **B.** Use CloudTrail management events only and assume object reads are included
- **C.** Use S3 Intelligent-Tiering and assume it is always cheapest
- **D.** Use model invocation logging only

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Enable CloudTrail S3 data events for the bucket and use an S3 lifecycle rule to transition logs to the approved Glacier storage class

**Explanation:**

S3 object operations require CloudTrail data-event coverage. An explicit lifecycle rule can transition logs to the Glacier class selected for the retention and retrieval requirements; no storage class is always cheapest.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: AWS CloudTrail, Amazon S3, Amazon S3 Glacier
- Last verified by source: 2026-11-03

---

### Question 407: aif-q126

A hospital must keep sensitive patient data stored and processed within the country where it is held. Which data-governance strategy addresses that geographic requirement?

- **A.** Data quality
- **B.** Data enrichment
- **C.** Data residency
- **D.** Data discoverability

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Data residency

**Explanation:**

Data residency addresses where data is stored and processed. The hospital must select Regions, services, inference routing, backups, and transfer paths that satisfy the required geographic boundary.
Residency alone does not establish privacy or compliance. The hospital still needs access control, encryption, retention, consent, auditing, and other controls required by the applicable rules. Data quality, enrichment, and discoverability do not define the processing geography.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 408: aif-q145

A global bank created an ML application that analyzes market data to surface trends. Throughout development, the bank wants ongoing checks that its policies and industry regulations are being followed. Which two AWS services help the bank assess compliance?

- **A.** Amazon CloudWatch
- **B.** AWS Config
- **C.** AWS CloudTrail
- **D.** AWS Audit Manager
- **E.** Amazon Inspector

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. AWS Config; D. AWS Audit Manager

**Explanation:**

AWS Audit Manager continuously collects evidence and maps it to regulatory frameworks to assess compliance, and AWS Config tracks configuration changes against rules so the bank can confirm its resources stay within policy throughout development.
Amazon CloudWatch monitors metrics and logs, AWS CloudTrail records API activity, and Amazon Inspector scans for software vulnerabilities; these support security and operations but are not the primary services for assessing compliance against policies and regulations.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: AWS Audit Manager, AWS Config, Amazon Inspector, Amazon CloudWatch, AWS CloudTrail
- Last verified by source: 2026-06-02

---

### Question 409: aif-q151

Which AWS feature offers a consistent way to document the details of ML models for governance and reporting?

- **A.** Amazon SageMaker Model Monitor
- **B.** Amazon SageMaker JumpStart
- **C.** Amazon SageMaker Model Cards
- **D.** Amazon SageMaker Model Registry

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Amazon SageMaker Model Cards

**Explanation:**

Amazon SageMaker Model Cards provide a standardized record of a model's intended use, training data, evaluation results, and compliance details, supporting governance and reporting throughout the model's lifecycle.
Amazon SageMaker Model Monitor watches deployed models for drift, Amazon SageMaker JumpStart provides pre-built models and solutions, and Amazon SageMaker Model Registry stores and versions models; none of these is the standardized documentation record used for governance and reporting.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: Amazon SageMaker Model Cards, Amazon SageMaker Model Monitor, Amazon SageMaker JumpStart, Amazon SageMaker Model Registry
- Last verified by source: 2026-06-02

---

### Question 410: aif-q186

A customer downloads AWS compliance reports through AWS Artifact. What do those reports establish?

- **A.** They provide AWS provider evidence that can support the customer's assessment
- **B.** They prove the customer's workload complies
- **C.** They replace customer controls
- **D.** They certify application data handling

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. They provide AWS provider evidence that can support the customer's assessment

**Explanation:**

AWS Artifact supplies AWS reports and agreements. Customers must evaluate their own workload configuration, controls, evidence, and obligations.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: AWS Artifact, AWS Config, Amazon Macie, AWS Secrets Manager
- Last verified by source: 2026-11-03

---

### Question 411: aif-q305

What does ISO/IEC 42001 certification establish?

- **A.** An accredited certification body has assessed the organization's scoped AI management system against ISO/IEC 42001
- **B.** Every AI output is accurate
- **C.** Every workload satisfies every law
- **D.** AWS certifies the customer's application automatically

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. An accredited certification body has assessed the organization's scoped AI management system against ISO/IEC 42001

**Explanation:**

ISO/IEC 42001 concerns an organization's scoped AI management system. Certification comes through an accredited certification body and does not certify every model output or legal obligation.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-11-03

---

### Question 412: aif-q307

A company keeps rules that set how long information is stored and when it should be removed. Which data governance strategy does this describe?

- **A.** Data quality standards
- **B.** Data retention
- **C.** Log storage
- **D.** Data de-identification

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Data retention

**Explanation:**

Data retention is the set of policies that define how long data is stored and when it must be deleted, which is exactly what the company's guidelines describe.
Data quality standards govern accuracy and completeness, log storage concerns where logs are kept, and data de-identification removes identifying details; none of these defines storage duration and deletion timing.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 413: aif-q133

Which option describes a characteristic of AI governance frameworks that help build trust and deploy human-centered AI?

- **A.** Expanding AI initiatives across business units to maximize long-term value
- **B.** Aligning AI projects with revenue goals and stakeholder expectations
- **C.** Driving business transformation and competitive growth through AI
- **D.** Developing policies and guidelines for data, transparency, responsible AI, and compliance

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** D. Developing policies and guidelines for data, transparency, responsible AI, and compliance

**Explanation:**

AI governance frameworks are characterized by developing policies and guidelines covering data, transparency, responsible AI, and compliance, which builds trust and supports human-centered AI.
Expanding initiatives across business units, aligning with revenue goals and stakeholder expectations, and driving business transformation are general business aims, not defining characteristics of an AI governance framework.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 414: aif-q159

A company uses AI to generate customer credit scores during loan applications and plans to expand into a new geographic market. To operate there, which type of compliance laws should the company review?

- **A.** Local health data protection laws
- **B.** Local payment card data protection laws
- **C.** Local algorithm accountability laws
- **D.** Local education privacy laws

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Local algorithm accountability laws

**Explanation:**

Because automated credit scoring makes decisions about individuals, the company must review local algorithm accountability laws, which govern the fairness, transparency, and impact of automated decision-making in the new market.
Local health data, payment card, and education privacy laws apply to other types of data and use cases, not to the accountability of automated credit-scoring decisions.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 415: aif-q254

A company wants to make sure its AI system is fair and explainable and decides to require training for its AI development team. Which training meets this requirement?

- **A.** Training on advanced coding skills
- **B.** Training on data privacy and encryption protocols
- **C.** Training on bias awareness and responsible AI
- **D.** Training on advanced ML algorithms

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Training on bias awareness and responsible AI

**Explanation:**

Training the AI development team on bias awareness and responsible AI gives the team the knowledge and practices needed to build systems that are fair and explainable, which meets the requirement.
Training on advanced coding skills, advanced ML algorithms, or data privacy and encryption protocols builds other valuable skills but does not directly address fairness and explainability.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-02

---

### Question 416: aif-q451

A company uses AI models trained on customer data and needs to define rules for how long training datasets are kept, when they are archived, and when they must be deleted. Which data governance strategy does this describe?

- **A.** Data residency
- **B.** Data lifecycle management
- **C.** Data logging
- **D.** Data monitoring

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** B. Data lifecycle management

**Explanation:**

Data lifecycle management defines rules for how data is created, stored, archived, and deleted over time, which is what setting retention and deletion schedules for training datasets describes.
Data residency governs where data is stored geographically. Data logging records events for auditing. Data monitoring observes quality and usage in real time. None of these sets archival and deletion timelines.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 417: aif-q452

A company's data governance team wants to continuously watch how AI training data is accessed and used across the organization to detect unauthorized usage patterns. Which data governance strategy does this describe?

- **A.** Data retention
- **B.** Data residency
- **C.** Data observation and monitoring
- **D.** Data logging

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Data observation and monitoring

**Explanation:**

Data observation and monitoring involves continuously watching how data is accessed and used to detect anomalies and unauthorized patterns, which is the governance strategy that addresses the team's need to oversee AI training data usage.
Data retention defines how long data is stored. Data residency controls geographic location. Data logging records individual access events but does not provide the ongoing surveillance and pattern detection that monitoring does.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: None listed
- Last verified by source: 2026-06-03

---

### Question 418: aif-q453

A security team must record Amazon S3 GetObject and PutObject activity for a training-data bucket. Which CloudTrail configuration is required?

- **A.** Enable S3 object-level data events for the bucket
- **B.** Rely on management events alone
- **C.** Enable only Bedrock model invocation logging
- **D.** Create a cost allocation tag

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** A. Enable S3 object-level data events for the bucket

**Explanation:**

CloudTrail does not log high-volume S3 object data events by default. The trail or event data store must include S3 data events for the target bucket.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: multiple choice
- Services: AWS CloudTrail, Amazon S3
- Last verified by source: 2026-11-03

---

### Question 419: aif-q465

A team has acquired a dataset in a restricted staging area. Its documented governance rollout requires classification to set protection tiers, followed by encryption, least-privilege access, monitoring, and compliance review. Arrange the rollout stages from first to last.

> **Review note:** This item was rewritten because the source implied a universal order. The answer applies to the workflow defined in this revised scenario.

- **A.** Restrict who can use the data by attaching least-privilege IAM policies to the roles and users that need it
- **B.** Encrypt the dataset at rest and enforce encryption in transit before it is used for training or inference
- **C.** Discover and classify the data to identify which records contain sensitive or regulated information
- **D.** Continuously monitor and log access to the data so unusual or unauthorized activity can be detected
- **E.** Audit the collected logs and controls against compliance requirements and produce evidence for reviewers

<details>
<summary>Show answer and explanation</summary>

**Correct answer:** C. Discover and classify the data to identify which records contain sensitive or regulated information → B. Encrypt the dataset at rest and enforce encryption in transit before it is used for training or inference → A. Restrict who can use the data by attaching least-privilege IAM policies to the roles and users that need it → D. Continuously monitor and log access to the data so unusual or unauthorized activity can be detected → E. Audit the collected logs and controls against compliance requirements and produce evidence for reviewers

**Explanation:**

For this organization's stated rollout, the sequence is classification (C), encryption (B), least-privilege access (A), monitoring (D), and audit review (E). The question defines that order. In real systems, baseline encryption and access controls should protect newly acquired data before and during classification; these controls often overlap rather than wait for a strict lifecycle stage.

</details>

**Question metadata**

- Domain: 5
- Task statement: 5.2
- Format: ordering
- Services: None listed
- Last verified by source: 2026-06-13

---

# SaveMyCert worked sample questions

Source: https://github.com/savemycert/aif-c01-study-guide

License: CC BY 4.0. Credit: SaveMyCert, https://www.savemycert.com/.

# AIF-C01 Sample Questions with Answers

20 worked practice questions for the **AWS Certified AI Practitioner (AIF-C01)** exam.

For many more, with the same explanation on every option, use the [AIF-C01 practice questions](https://www.savemycert.com/practice/aws-ai-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide) on SaveMyCert.

## Question 1

*Fundamentals of AI and ML*

**A finance team's expense-approval tool applies a fixed set of hand-written if-then rules to each claim and never changes its behavior based on past data. How should this tool be classified?** Choose one.

- **a.** It is deep learning but not machine learning.
- **b.** It is neither AI nor machine learning.
- **c.** It is machine learning but not AI.
- **d.** It is AI but not machine learning.

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Deep learning is a subset of ML built on multi-layer neural networks, so nothing can be deep learning without being ML; the tool uses no neural network either.
- **b** ❌ AI is the broadest field and includes rule-based systems that mimic human decision making, so a rules engine still counts as AI.
- **c** ❌ Machine learning learns patterns from data; this tool only follows hand-written rules, so it is not ML.
- **d** ✅ Rule-based systems sit inside the broad AI circle, but because the tool does not learn from data it falls outside ML.

**The concept.** AI, ML, and deep learning nest from broadest to narrowest, and AI also includes systems that do not learn.

**Why this is correct.** AI covers any technique that lets a machine mimic human intelligence, including hand-written rule engines. Machine learning is the subset that learns patterns from data, and deep learning is the subset of ML that uses multi-layer neural networks. A tool that only applies fixed rules is therefore AI but not ML. Calling it neither AI nor ML is the tempting mistake: it treats AI as if it meant only learning systems.

**How to reason it out**

1. Ask whether the system learns from data or only follows rules it was given.
2. Recall that AI is the widest circle and includes rule-based systems.
3. Place ML inside AI and deep learning inside ML, so a non-learning system can be AI without being ML.

> **Exam tip:** AI contains ML, ML contains deep learning, and rule-based systems are AI without being ML.

</details>

📖 Learn this topic: [AI vs ML vs Deep Learning: Core AIF-C01 Concepts and Terminology](https://www.savemycert.com/revision/aws-ai-practitioner/ai-ml-concepts-terminology/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 2

*Fundamentals of AI and ML*

**A company builds two assistants on the same foundation model. The first answers each question it is given. The second breaks a request such as 'arrange a team offsite' into steps, calls a calendar API and a booking API, remembers earlier results, and checks each outcome before continuing. Which term best describes the second assistant?** Choose one.

- **a.** A reinforcement learning system
- **b.** A retrieval-augmented generation system
- **c.** An agentic AI system
- **d.** A multimodal generative AI system

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Reinforcement learning is a way of training a model from rewards in an environment; the assistant here is not being trained, it is planning and acting at run time.
- **b** ❌ RAG retrieves documents to ground a single answer; it does not plan steps or take actions through external APIs.
- **c** ✅ It uses a generative model as its reasoning engine and adds planning, memory, and tool calls to take multi-step actions toward a goal, which is what defines agentic AI.
- **d** ❌ Multimodal means a model handles more than one input or output type, such as text and images; it says nothing about planning or calling tools.

**The concept.** Agentic AI is generative AI that plans, keeps memory, and uses tools to act toward a goal over multiple steps.

**Why this is correct.** Both assistants use the same foundation model, so what separates the second one is behavior: it decomposes a goal, calls external tools, carries results forward, and checks progress. That plan-act-observe loop is agentic AI. Reinforcement learning is tempting because the assistant 'checks outcomes', but RL describes how a model is trained, not how a deployed assistant acts. RAG adds retrieved knowledge to one response and multimodal describes input/output types, neither of which involves taking actions.

**How to reason it out**

1. Note that the underlying model is the same, so the difference is in how the system behaves.
2. Spot the signals: multi-step planning, tool calls, memory, and checking results.
3. Match a generative model that plans and acts with tools to agentic AI.
4. Rule out terms that describe training methods, grounding, or data types.

> **Exam tip:** GenAI answers; agentic AI plans and acts with tools toward a goal.

</details>

📖 Learn this topic: [AI vs ML vs Deep Learning: Core AIF-C01 Concepts and Terminology](https://www.savemycert.com/revision/aws-ai-practitioner/ai-ml-concepts-terminology/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 3

*Fundamentals of AI and ML*

**A finance team must add sales tax to every invoice. Each amount is fully determined by published rates and rules, and auditors accept no deviation from them. Why is a machine learning model a poor choice for this calculation?** Choose one.

- **a.** Invoice data is tabular, and ML techniques are suited mainly to images, audio and text.
- **b.** Tax amounts are numeric, so the task would need clustering, which returns no amounts.
- **c.** The task would need a foundation model, and those are too costly to run on every invoice.
- **d.** A learned model approximates a mapping from examples, while deterministic code can implement the published rule exactly.

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Tabular data is one of the most common inputs to traditional ML (regression, classification), so data type is not the problem.
- **b** ❌ Predicting a number would be regression, not clustering; but the real point is that no prediction is wanted when a rule gives the exact answer.
- **c** ❌ Nothing about tax calculation calls for a foundation model. Model family and inference cost do not address the central requirement: implement a known rule with an exact, auditable calculation.
- **d** ✅ Correct. A learned model is unnecessary for a fully specified rule and may introduce approximation error. Deterministic code can implement and test the published calculation directly.

**The concept.** Use deterministic code when published rules fully define the required output and deviations are unacceptable.

**Why this is correct.** Sales tax is defined by published rates and rules, so conventional code can implement the required calculation and produce an auditable result for valid inputs. A learned model would approximate a rule that the team already knows and could introduce avoidable error. The distractors blame the data type, cost of foundation models, or the wrong technique, but those are not why ML fails here.

**How to reason it out**

1. Ask whether the output is fully defined by known rules.
2. Ask whether any deviation from the exact result is acceptable.
3. If the rule exists and no deviation is allowed, use deterministic code, not a predictive model.

> **Exam tip:** When a rule fully defines the required result, implement and test that rule with deterministic code.

</details>

📖 Learn this topic: [Practical AI Use Cases and the AWS AI Service Catalog (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/ai-ml-use-cases-aws-services/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 4

*Fundamentals of AI and ML*

**A data science team is planning its first machine learning project and wants to follow the standard development lifecycle. Which sequence lists the pipeline stages in the correct order?** Choose one.

- **a.** Data collection, model training, data preparation, deployment, evaluation and tuning, monitoring
- **b.** Data preparation, data collection, model training, deployment, evaluation and tuning, monitoring
- **c.** Data preparation, data collection, model training, evaluation and tuning, monitoring, deployment
- **d.** Data collection, data preparation, model training, evaluation and tuning, deployment, monitoring

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Training learns from prepared data, so preparation must come first; and evaluation belongs before deployment so a weak model is caught before users see it.
- **b** ❌ Two dependencies break: data must be gathered before it can be cleaned and shaped, and a model is evaluated and tuned before it serves live traffic, not after.
- **c** ❌ Preparation cannot precede collection, and monitoring watches a model that is already live, so it cannot come before deployment.
- **d** ✅ Each stage consumes the output of the one before: gather data, prepare it, train, test and tune, deploy, then watch the live model.

**The concept.** The AI/ML pipeline runs through ordered stages because each stage consumes the output of the one before it, and monitoring loops back into retraining.

**Why this is correct.** The standard flow is collect, prepare, train, evaluate and tune, deploy, monitor (then retrain). Each wrong sequence breaks two dependencies: preparing data that has not been collected, training before the data is prepared, deploying before evaluation, or monitoring before anything is live. Check each stage against the one it depends on rather than looking for the most familiar-looking list.

**How to reason it out**

1. Anchor the start: data must be collected before it can be prepared.
2. Place training after preparation, because the model learns from the prepared data.
3. Put evaluation and tuning before deployment, since a model is tested before it serves live traffic.
4. Finish with monitoring, which watches the deployed model and triggers retraining.

> **Exam tip:** Collect, prepare, train, evaluate, deploy, monitor, then retrain: test before you ship, watch after you ship.

</details>

📖 Learn this topic: [The AI/ML Development Lifecycle & MLOps: Pipeline, Models & Metrics](https://www.savemycert.com/revision/aws-ai-practitioner/ai-ml-development-lifecycle-mlops/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 5

*Fundamentals of GenAI*

**A developer reads that a model accepts up to 200,000 tokens in one request. In generative AI, what is a token?** Choose one.

- **a.** A section of a long document that is split off and stored for later retrieval.
- **b.** A signed credential that an application sends to authenticate each call to a model API.
- **c.** A small unit of text, such as a word or part of a word, that a model processes.
- **d.** A list of numbers that represents the meaning of a sentence or a whole document.

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ A section of a split document is a chunk. Chunks are far larger than tokens and are created by the application, not the model.
- **b** ❌ An API or access token is a security credential. It shares the word but is not the unit of text a model works with.
- **c** ✅ Correct. Language models break text into tokens (words, word pieces, punctuation) and both read and generate sequences of them.
- **d** ❌ This describes an embedding (expressed as a vector), not a token.

**The concept.** A token is the small unit of text, often a word, part of a word or a punctuation mark, that a language model reads and generates.

**Why this is correct.** Models do not read whole documents or single letters; they read and produce sequences of tokens, and limits such as the context window are counted in tokens. A list of numbers representing meaning is an embedding, a signed credential is an API access token (a security term that only shares the name), and a section split from a long document is a chunk.

**How to reason it out**

1. Notice that the request limit is expressed in tokens, so a token is a unit of text the model processes.
2. Recall that a token is roughly a word or word piece, about four characters of English.
3. Separate it from embeddings (meaning as numbers), chunks (document sections) and API credentials.

> **Exam tip:** A token is the small unit of text a model reads and generates; context windows and bills are counted in tokens.

</details>

📖 Learn this topic: [Generative AI Concepts: Tokens, Embeddings, and Foundation Models (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/generative-ai-concepts-tokens-embeddings/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 6

*Fundamentals of GenAI*

**A company wants to make a 200-page product manual searchable by a generative AI application. It first splits the manual into smaller sections of a few paragraphs each. What is this practice called?** Choose one.

- **a.** Chunking
- **b.** Fine-tuning
- **c.** Embedding
- **d.** Tokenizing

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Chunking splits a large document into smaller, manageable pieces for processing or retrieval.
- **b** ❌ Fine-tuning further trains a model on task-specific data; it does not divide a document.
- **c** ❌ Embedding turns content into numbers that capture meaning; it does not split a document into sections.
- **d** ❌ Tokenizing breaks text into the tiny units a model reads, not a document into paragraph-sized sections.

**The concept.** Chunking means dividing a large document into smaller pieces so an application can store, search and retrieve the relevant parts.

**Why this is correct.** A 200-page manual does not fit in one context window, so the application splits it into paragraph-sized sections and later pulls only the relevant ones into a prompt. That is chunking. Tokenizing also splits text, but into tiny word-level units that the model reads; fine-tuning further trains a model; and embedding converts each piece into numbers that capture its meaning, which usually happens after chunking.

**How to reason it out**

1. Notice what is being split: a whole document into sections of a few paragraphs.
2. Match document-level splitting for retrieval to chunking.
3. Separate it from tokenizing (word-level units), embedding (numbers for meaning) and fine-tuning (training).

> **Exam tip:** Chunking splits a large document into sections an application can handle; tokenizing splits text into the units a model reads.

</details>

📖 Learn this topic: [Generative AI Concepts: Tokens, Embeddings, and Foundation Models (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/generative-ai-concepts-tokens-embeddings/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 7

*Fundamentals of GenAI*

**A company uses one foundation model to summarize contracts, draft marketing emails, and answer employee questions. Each new job needs only a different prompt rather than a separate system. Which advantage of generative AI does this show?** Choose one.

- **a.** Adaptability
- **b.** Responsiveness
- **c.** Conversational capability
- **d.** Accuracy

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Correct. One model covering summarizing, drafting and answering, switched by the prompt alone, is adaptability.
- **b** ❌ Responsiveness is about how quickly the model returns output, not about one model covering many different jobs.
- **c** ❌ Conversational capability is natural back-and-forth dialogue; the scenario is about many task types, not dialogue.
- **d** ❌ Accuracy is a business metric for how often output is correct; it says nothing about reusing one model across tasks.

**The concept.** Adaptability is the GenAI advantage that one foundation model can perform many different tasks when given a different prompt.

**Why this is correct.** The deciding detail is that each new job needs only a new prompt, not a new system. That is adaptability: a foundation model learned broad patterns, so it can be pointed at summarizing, drafting or answering without task-specific training. Responsiveness and conversational capability are real advantages but describe speed and dialogue, and accuracy is a metric rather than an advantage.

**How to reason it out**

1. Notice that several unrelated tasks run on the same model.
2. Notice that switching tasks only changes the prompt.
3. Match one model, many tasks, to adaptability.
4. Check the other advantages: speed is responsiveness, dialogue is conversational capability.

> **Exam tip:** One model, many tasks, just a new prompt: that is adaptability.

</details>

📖 Learn this topic: [Generative AI Capabilities and Limitations for Business (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/generative-ai-capabilities-limitations/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 8

*Fundamentals of GenAI*

**A development team wants to call foundation models from several providers through a single API. It does not want to choose instance types, deploy model endpoints, or manage any servers. Which AWS service best fits this need?** Choose one.

- **a.** Amazon SageMaker AI
- **b.** Amazon SageMaker JumpStart
- **c.** Amazon Bedrock
- **d.** Amazon Bedrock AgentCore

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ SageMaker AI can host foundation models, but you choose instance types and manage the endpoints yourself, which the team wants to avoid.
- **b** ❌ JumpStart offers pre-trained models, but you deploy each one to a SageMaker endpoint on instances you select, which is the work the team wants to avoid.
- **c** ✅ Bedrock is fully managed and serverless and serves foundation models from Amazon and other providers through one API, with no endpoints or instances to manage.
- **d** ❌ AgentCore provides managed services to deploy and operate AI agents; it is not the API that serves foundation models from multiple providers.

**The concept.** Amazon Bedrock is the managed, serverless path to foundation models on AWS.

**Why this is correct.** The deciding requirements are several providers, one API and nothing to deploy or size. Bedrock meets all three: AWS runs the model infrastructure and you call models from Amazon, Anthropic, Meta, Mistral AI and others through the same API. SageMaker AI and JumpStart can also give access to foundation models, but both deploy the model to an endpoint whose instances you choose and run. AgentCore runs agents rather than serving models.

**How to reason it out**

1. List the requirements: multiple providers, one API, no endpoints or servers.
2. Rule out options that deploy models to endpoints you size and run (SageMaker AI, JumpStart).
3. Rule out the agent runtime, which is not a model-access API.
4. Choose the serverless, multi-provider service: Amazon Bedrock.

> **Exam tip:** Call many providers' models with nothing to deploy: Amazon Bedrock. Deploy and host a model yourself: SageMaker AI or JumpStart.

</details>

📖 Learn this topic: [AWS Infrastructure and Services for Building GenAI Applications](https://www.savemycert.com/revision/aws-ai-practitioner/aws-genai-services-bedrock-sagemaker/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 9

*Fundamentals of GenAI*

**Which statement best describes an embedding in generative AI?** Choose one.

- **a.** A ranked list of the documents that a keyword search index returns for a user's query.
- **b.** A numerical representation of content in which similar meanings get similar values.
- **c.** The small units of text that a language model reads and writes one at a time.
- **d.** The maximum number of tokens that a model can consider within a single request.

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Keyword search results are matched on words, not meaning, and are not an embedding.
- **b** ✅ Correct. An embedding encodes the meaning of a word, sentence or document as numbers, so similar meanings land close together.
- **c** ❌ Those are tokens. An embedding is produced from content, it is not the text units themselves.
- **d** ❌ That is the context window, a size limit, not a representation of meaning.

**The concept.** An embedding is a numerical representation of a piece of content, produced by a model so that content with similar meaning gets similar numbers.

**Why this is correct.** Embeddings let applications compare meaning by comparing numbers, which is what powers semantic search and recommendations. Tokens are the text units a model processes, the context window is the token limit of a request, and a ranked keyword-search result list is matched on words rather than meaning.

**How to reason it out**

1. Look for the description that turns meaning into numbers.
2. Recall that similar meanings produce similar embeddings, expressed as vectors.
3. Eliminate tokens, the context window and keyword search results as different concepts.

> **Exam tip:** An embedding encodes meaning as numbers, so similar meanings map to similar values.

</details>

📖 Learn this topic: [Generative AI Concepts: Tokens, Embeddings, and Foundation Models (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/generative-ai-concepts-tokens-embeddings/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 10

*Applications of Foundation Models*

**A team reads that Retrieval Augmented Generation (RAG) could improve its chatbot's answers. What does RAG do when the foundation model receives a question?** Choose one.

- **a.** Searches a knowledge source for relevant passages and adds them to the prompt before the model responds.
- **b.** Builds a smaller copy of the model that runs faster and costs less to serve for each request.
- **c.** Changes the sampling settings so the model chooses words more freely and gives more varied answers.
- **d.** Further trains the model on your documents so their content is stored in the model's weights.

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ This is RAG: relevant passages are retrieved at query time and passed to the model as context, so the model itself is unchanged.
- **b** ❌ Producing a smaller model that imitates a larger one is model distillation, which reduces inference cost but adds no new knowledge.
- **c** ❌ Sampling settings such as temperature control randomness; they do not bring any outside information into the answer.
- **d** ❌ Training the model on your documents is fine-tuning or continuous pre-training. RAG involves no training step.

**The concept.** Retrieval Augmented Generation (RAG) retrieves relevant information from an external source at query time and adds it to the prompt.

**Why this is correct.** RAG works in front of the model: the question is used to search a knowledge source, the most relevant passages are inserted into the prompt, and the model answers from them. Nothing about the model changes. Training the model on documents is fine-tuning, building a smaller imitation model is distillation, and changing sampling settings is an inference parameter, so none of those retrieve anything.

**How to reason it out**

1. Recall that 'retrieval' happens at question time, not training time.
2. Recognise that the retrieved passages travel to the model inside the prompt.
3. Rule out descriptions of fine-tuning, distillation and temperature.

> **Exam tip:** RAG = retrieve relevant passages, add them to the prompt, generate; the model's weights never change.

</details>

📖 Learn this topic: [Foundation Model Design: Selection, RAG, and Customization (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/foundation-model-design-rag-customization/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 11

*Applications of Foundation Models*

**A developer wants a foundation model in Amazon Bedrock to give answers grounded in company data, without writing code for chunking, embedding and retrieval. Which Amazon Bedrock capability provides this?** Choose one.

- **a.** Amazon Bedrock Model Evaluation
- **b.** Amazon Bedrock Guardrails
- **c.** Amazon Bedrock Prompt Management
- **d.** Amazon Bedrock Knowledge Bases

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Model Evaluation compares and scores model outputs; it does not connect a model to a data source.
- **b** ❌ Guardrails filters inputs and outputs and can check whether a response is grounded in supplied context, but it does not retrieve that context from company data.
- **c** ❌ Prompt Management stores and versions prompts. It does not ingest data or retrieve passages for the model.
- **d** ✅ Knowledge Bases is the managed RAG capability: it chunks and embeds a data source, stores the vectors, retrieves relevant passages and passes them to the model.

**The concept.** Amazon Bedrock Knowledge Bases is the managed way to build RAG on AWS.

**Why this is correct.** The need is RAG without building the pipeline yourself. Knowledge Bases handles ingestion, chunking, embedding, vector storage and retrieval, then supplies the retrieved passages to the model. Guardrails is the tempting near-miss because of the word 'grounded', but it checks or filters responses rather than fetching data; Prompt Management and Model Evaluation manage prompts and measure output quality.

**How to reason it out**

1. Identify the need: answers from company data with no custom retrieval code.
2. Map 'managed RAG' to Amazon Bedrock Knowledge Bases.
3. Separate retrieval (Knowledge Bases) from safety checks (Guardrails) and prompt or evaluation tooling.

> **Exam tip:** Managed RAG in Amazon Bedrock = Knowledge Bases; Guardrails checks answers, it does not fetch the data.

</details>

📖 Learn this topic: [Foundation Model Design: Selection, RAG, and Customization (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/foundation-model-design-rag-customization/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 12

*Applications of Foundation Models*

**A developer sends a model the line "Classify this review as positive or negative," followed by the review text. The request contains no sample reviews with labels. Which prompt engineering technique is this?** Choose one.

- **a.** Single-shot prompting
- **b.** Few-shot prompting
- **c.** Zero-shot prompting
- **d.** Chain-of-thought prompting

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Single-shot prompting includes exactly one labeled sample; this request includes zero.
- **b** ❌ Few-shot prompting places several labeled samples before the task; this request has none.
- **c** ✅ Correct. An instruction plus the input, with no demonstrations, relies on the model's existing knowledge: that is zero-shot prompting.
- **d** ❌ Chain-of-thought asks the model to reason step by step; nothing in the request asks for reasoning.

**The concept.** Zero-shot, single-shot and few-shot prompting differ by how many examples the prompt contains; zero-shot contains none.

**Why this is correct.** The deciding detail is that the request holds an instruction and the review but no labeled samples. With no demonstrations, the model must rely on what it already learned, which defines zero-shot prompting. Single-shot and few-shot are tempting because the task is classification, a common few-shot use, but they require one or several samples in the prompt. Chain-of-thought is defined by asking for reasoning, which this request does not do.

**How to reason it out**

1. Count the labeled samples in the request: none.
2. Map zero samples to zero-shot prompting.
3. Check that the request does not ask for step-by-step reasoning, ruling out chain-of-thought.

> **Exam tip:** No examples in the prompt, only the instruction and input: zero-shot prompting.

</details>

📖 Learn this topic: [Prompt Engineering Techniques: Zero-Shot to Chain-of-Thought (AIF-C01)](https://www.savemycert.com/revision/aws-ai-practitioner/prompt-engineering-techniques-aif/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 13

*Applications of Foundation Models*

**Which element of foundation model training builds the model's broad, general knowledge from scratch on massive datasets and is usually the most expensive and time-consuming step?** Choose one.

- **a.** Continued pre-training
- **b.** Pre-training
- **c.** Fine-tuning
- **d.** Distillation

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Continued pre-training also uses unlabeled data, but it extends an existing pre-trained model with more domain text rather than starting from scratch.
- **b** ✅ Correct. Pre-training starts from randomly initialized weights and learns language and general knowledge from huge unlabeled datasets, which makes it the costliest and slowest step.
- **c** ❌ Fine-tuning starts from a model that is already pre-trained and adapts it with a much smaller labeled dataset; it does not build general knowledge from scratch.
- **d** ❌ Distillation trains a smaller student model to imitate a larger teacher that already exists; the broad knowledge came from the teacher, not from distillation.

**The concept.** The four training elements differ in their starting point and cost; only pre-training starts from nothing.

**Why this is correct.** The deciding words are 'from scratch'. Pre-training is the only element that begins without a capable model and learns general knowledge from massive unlabeled data, so it needs the most compute and time. Continued pre-training is the tempting near-twin because it also trains on unlabeled text, but it extends a model that was already pre-trained. Fine-tuning and distillation both start from an existing model as well.

**How to reason it out**

1. Find the deciding phrase: broad knowledge built from scratch.
2. Ask which element starts without an existing capable model.
3. Separate pre-training from continued pre-training, which extends an existing model.
4. Pre-training is the most expensive element of all.

> **Exam tip:** From scratch on massive data = pre-training; extending an existing model with more unlabeled text = continued pre-training.

</details>

📖 Learn this topic: [Training and Fine-Tuning Foundation Models](https://www.savemycert.com/revision/aws-ai-practitioner/foundation-model-training-fine-tuning/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 14

*Applications of Foundation Models*

**Which metric is the standard choice for evaluating the quality of text summarization?** Choose one.

- **a.** ROUGE
- **b.** BLEU
- **c.** Task completion rate
- **d.** Cost per interaction

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ ROUGE measures how much a generated summary overlaps with a reference summary, making it the go-to metric for summarization quality.
- **b** ❌ BLEU targets machine-translation quality by comparing to reference translations, not summaries.
- **c** ❌ Task completion rate is a business-objective alignment metric for applications, not a text-quality metric for summaries.
- **d** ❌ Cost per interaction measures spend per request, not summarization quality.

**The concept.** Each generative metric maps to a specific task; ROUGE maps to summarization.

**Why this is correct.** ROUGE checks overlap with a reference summary, so it is the standard summarization metric. BLEU is for translation, while task completion rate and cost per interaction measure application outcomes and spend.

**How to reason it out**

1. Match 'summarization quality' to a metric.
2. Recall that ROUGE measures overlap with a reference summary.
3. Eliminate translation and business-alignment metrics.

> **Exam tip:** 'Evaluate a summarizer' signals ROUGE.

</details>

📖 Learn this topic: [Evaluating Foundation Model Performance](https://www.savemycert.com/revision/aws-ai-practitioner/evaluating-foundation-model-performance/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 15

*Guidelines for Responsible AI*

**A responsible-AI review flags that a chatbot sometimes states false information as if it were fact. Which feature of responsible AI is most directly concerned with outputs being accurate and factually grounded?** Choose one.

- **a.** Inclusivity
- **b.** Fairness
- **c.** Robustness
- **d.** Veracity

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Inclusivity is about serving a wide range of people well, not about truthfulness of outputs.
- **b** ❌ Fairness is about equitable treatment of individuals and groups, not about whether a statement is factually true.
- **c** ❌ Robustness is about performing reliably on noisy or unexpected inputs, not about factual accuracy.
- **d** ✅ Veracity, or truthfulness, is the responsible-AI feature about outputs being accurate and factually grounded rather than fabricated.

**The concept.** Veracity (truthfulness) is the responsible-AI feature about factual accuracy of outputs.

**Why this is correct.** A model stating false information describes a truthfulness failure, which maps to veracity. Robustness (reliability under bad inputs), inclusivity (serving diverse people), and fairness (equitable treatment) are separate features that do not describe factual accuracy.

**How to reason it out**

1. Identify the symptom: the model produces false statements presented as fact.
2. Match the symptom to the feature about accurate, factually grounded output.
3. That feature is veracity, also called truthfulness.

> **Exam tip:** Veracity, or truthfulness, is the responsible-AI feature about outputs being factually accurate.

</details>

📖 Learn this topic: [Responsible AI: Bias, Fairness, and Amazon Bedrock Guardrails](https://www.savemycert.com/revision/aws-ai-practitioner/responsible-ai-bias-fairness-guardrails/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 16

*Guidelines for Responsible AI*

**In AWS responsible-AI terminology, what is the difference between bias and fairness?** Choose one.

- **a.** Bias is a systematic error of stating false facts; fairness is keeping outputs grounded in sources.
- **b.** Bias is a systematic error shared equally by the groups; fairness is equal accuracy on the training records.
- **c.** Bias is a systematic error that skews results for some groups; fairness is equitable treatment of groups.
- **d.** Bias is a systematic error on noisy or adversarial inputs; fairness is steady output under those inputs.

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Stating falsehoods as fact is a veracity (truthfulness) failure, and grounding outputs is about veracity, not fairness.
- **b** ❌ An error shared equally by the groups is not what bias means here; bias skews results for some groups, and fairness means equitable treatment of people, not equal accuracy on the training records.
- **c** ✅ Bias is the flaw (a systematic error that unfairly favors or disfavors certain groups) and fairness is the goal of treating individuals and groups equitably.
- **d** ❌ Reliability under noisy or adversarial input describes robustness, not bias or fairness.

**The concept.** Bias is the flaw; fairness is the goal reached by removing it.

**Why this is correct.** AWS describes bias as a systematic error that makes a model favor or disfavor certain groups, usually learned from skewed data, and fairness as equitable treatment of individuals and groups. An error shared equally by the groups is not group bias, and accuracy on the training records says nothing about equitable treatment. The other two definitions describe robustness and veracity, which are separate responsible-AI features.

**How to reason it out**

1. Recall which term names a problem and which names an outcome you want.
2. Bias is an error that skews results for some groups, not all equally; fairness is equitable treatment.
3. Reject definitions that actually describe robustness (noisy inputs) or veracity (false statements).

> **Exam tip:** Bias is the flaw, fairness is the goal.

</details>

📖 Learn this topic: [Responsible AI: Bias, Fairness, and Amazon Bedrock Guardrails](https://www.savemycert.com/revision/aws-ai-practitioner/responsible-ai-bias-fairness-guardrails/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 17

*Guidelines for Responsible AI*

**In responsible AI, which description best represents model transparency rather than explanation of one prediction?** Choose one.

- **a.** People can see that the model returns consistent answers when its inputs are slightly altered
- **b.** Documentation discloses how the model was developed, its data provenance, intended use, evaluations, and known limits.
- **c.** People can see that the model gives similar outcomes to applicants from different groups
- **d.** People can see which input values drove one particular prediction the model returned

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Consistent behaviour under small input changes is robustness, a separate responsible-AI property.
- **b** ✅ Transparency gives stakeholders documented information about development, provenance, intended use, evaluations, and limits.
- **c** ❌ Similar outcomes across demographic groups describes fairness, not transparency.
- **d** ❌ Feature attributions for one prediction are an explainability result. Explainability can also address overall model behavior, so it is not limited to one output.

**The concept.** Transparency documents the model and its governance context. Explainability provides reasons or feature attributions for model behavior or a prediction.

**Why this is correct.** Transparency gives stakeholders information about the model's development, data provenance, intended use, evaluations, and limitations. Option d is an explainability example because it attributes one prediction to inputs. Explainability can also describe global model behavior, so the boundary is the type of insight, not a strict whole-model versus single-output split. Robustness concerns behavior under perturbation, and fairness concerns outcomes across groups.

**How to reason it out**

1. Identify whether the choice discloses lifecycle and governance information or explains model behavior.
2. Select transparency for documented development, provenance, intended use, evaluations, and limits.
3. Treat feature attribution for one prediction as local explainability; global explanations can describe overall model behavior.

> **Exam tip:** Transparency discloses lifecycle and governance information. Explainability describes why a model behaves as it does or produced a result.

</details>

📖 Learn this topic: [Transparent and Explainable AI Models: Model Cards and Tradeoffs](https://www.savemycert.com/revision/aws-ai-practitioner/transparent-explainable-ai-models/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 18

*Security, Compliance, and Governance for AI Solutions*

**A retailer builds a customer-service chatbot on Amazon Bedrock. Under the AWS shared responsibility model, which task stays with the retailer rather than AWS?** Choose one.

- **a.** Classifying and protecting the customer data in prompts
- **b.** Patching the hosts that serve the foundation model
- **c.** Updating the operating system beneath the Bedrock service
- **d.** Physically securing the data centers that run Bedrock

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Correct. What data the retailer sends to the model, and how it is classified and protected, is customer data: security in the cloud.
- **b** ❌ Hosts that run Bedrock models are AWS infrastructure; AWS patches them as part of security of the cloud.
- **c** ❌ Bedrock is a managed service; AWS operates and updates the operating system and everything beneath it.
- **d** ❌ Physical data center security is always AWS's responsibility.

**The concept.** The shared responsibility model splits security into AWS's part (security of the cloud) and the customer's part (security in the cloud); using a managed AI service does not move the customer's data off the customer's side.

**Why this is correct.** The retailer always owns its data: what goes into prompts, how sensitive it is and how it is protected. Patching model hosts, the service's operating system and physical data center security are all AWS's job for a managed service like Amazon Bedrock. The more managed the service, the more layers AWS runs, but data, access and configuration stay with the customer.

**How to reason it out**

1. Place each task on one side: infrastructure and service operation, or customer data and configuration.
2. Hosts, operating systems and buildings belong to AWS for a managed service.
3. The data the customer puts into prompts belongs to the customer.

> **Exam tip:** Managed AI service: AWS runs the infrastructure; you own your data, access and configuration.

</details>

📖 Learn this topic: [Securing AI Systems on AWS: IAM, Encryption, Guardrails, and Grounding](https://www.savemycert.com/revision/aws-ai-practitioner/securing-ai-systems-aws/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 19

*Security, Compliance, and Governance for AI Solutions*

**Before fine-tuning a model, a team must find out which objects in its Amazon S3 training buckets contain names, payment card numbers, or health identifiers so they can be removed. Which AWS service automates this discovery?** Choose one.

- **a.** Amazon GuardDuty
- **b.** Amazon Macie
- **c.** Amazon Inspector
- **d.** AWS Config

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ GuardDuty detects threats (suspicious activity, malware) from logs and events; it does not classify the personal data inside objects.
- **b** ✅ Correct. Macie uses machine learning and pattern matching to discover sensitive data such as PII in Amazon S3 and reports where it is.
- **c** ❌ Inspector scans workloads such as EC2 instances, container images and Lambda functions for software vulnerabilities, not S3 objects for personal data.
- **d** ❌ Config records and evaluates resource configuration, such as whether a bucket is encrypted, not the contents of the objects.

**The concept.** Amazon Macie discovers and reports sensitive data, such as personally identifiable information, stored in Amazon S3.

**Why this is correct.** The need is to look inside S3 objects and find personal data before it is baked into a model. That is Macie's job. Inspector looks for software vulnerabilities, GuardDuty looks for threats in account activity, and Config looks at resource settings; none of them classifies the data inside objects.

**How to reason it out**

1. Identify the target: the contents of S3 objects.
2. Identify the finding: sensitive personal data.
3. Match 'find PII in S3' to Amazon Macie and rule out the vulnerability, threat and configuration services.

> **Exam tip:** Find PII inside S3 data: Amazon Macie.

</details>

📖 Learn this topic: [Securing AI Systems on AWS: IAM, Encryption, Guardrails, and Grounding](https://www.savemycert.com/revision/aws-ai-practitioner/securing-ai-systems-aws/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

## Question 20

*Security, Compliance, and Governance for AI Solutions*

**A governance team must see the full history of settings on the Amazon S3 buckets that hold model training data, and be notified when any bucket stops meeting the team's encryption rule. Which AWS service should the team use?** Choose one.

- **a.** AWS Trusted Advisor
- **b.** AWS Config
- **c.** AWS CloudTrail
- **d.** Amazon Inspector

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Trusted Advisor runs AWS's own fixed best-practice checks; it does not keep a settings history or evaluate your custom rules.
- **b** ✅ AWS Config records each resource's configuration over time and evaluates it against rules, flagging a bucket as noncompliant when it drifts.
- **c** ❌ CloudTrail records the API calls that were made, not a running history of each bucket's settings evaluated against a rule.
- **d** ❌ Inspector scans compute and container images for software vulnerabilities; it does not track bucket settings against your rules.

**The concept.** AWS Config tracks resource configuration over time and evaluates it against rules.

**Why this is correct.** Keeping a history of resource settings and flagging drift from a rule is what AWS Config does. CloudTrail is tempting because it also records changes, but it records the API calls, not the evaluated state; Trusted Advisor checks AWS-defined best practices rather than your own rules; Inspector looks for vulnerabilities.

**How to reason it out**

1. Identify the need: a settings history plus evaluation against the team's own rule.
2. Separate state (configuration) from actions (API calls) and from vulnerabilities.
3. The service that records configuration and evaluates rules is AWS Config.

> **Exam tip:** Configuration history + compliance rules = AWS Config.

</details>

📖 Learn this topic: [AI Governance and Compliance on AWS: Config, CloudTrail, and Audit Manager](https://www.savemycert.com/revision/aws-ai-practitioner/ai-governance-compliance-aws/?utm_source=github&utm_medium=readme&utm_campaign=aif-c01-study-guide)

---

[Back to the domain guide](../README.md#domain-guide)

# CloudCertPrep MIT license

The following license applies to the CloudCertPrep question content included above.

```text
MIT License

Copyright (c) 2026 Alex Santonastaso

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

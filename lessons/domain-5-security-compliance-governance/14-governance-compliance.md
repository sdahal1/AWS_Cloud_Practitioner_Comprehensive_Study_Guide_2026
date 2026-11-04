# Task 5.2: Recognize governance and compliance regulations for AI systems

- Exam domain: 5, Security, Compliance, and Governance for AI Solutions
- Task: 5.2, Recognize governance and compliance regulations for AI systems
- Domain weight: 14% across Tasks 5.1 and 5.2
- Objective snapshot: 2026 AIF-C01 exam guide
- Last reviewed: November 2026

## Exam focus

Task 5.2 tests whether you can match a governance need to the right AWS service and describe the processes that keep an AI system within policy. Expect service-selection questions about AWS Config, Amazon Inspector, AWS Artifact, AWS CloudTrail, and AWS Trusted Advisor. Expect process questions about lifecycle, residency, retention, review cadence, transparency, training, and the Generative AI Security Scoping Matrix.

Classify each question as one of three jobs:

- **Set the rule:** law, standard, policy, control objective, owner, and review schedule.
- **Operate the control:** technical configuration, approval, monitoring, or training.
- **Produce evidence:** configuration history, API event, vulnerability finding, provider report, or review record.

## Mental model: obligation to evidence

Use this chain:

**Obligation → policy → control → operation → evidence → review → correction**

For example, a residency obligation may lead to a policy that restricts processing to an approved geography. The team then chooses Regional resources and a geographic inference profile, denies unapproved Regions, records API activity, and reviews evidence on a defined schedule.

A service can support compliance. It does not decide which laws apply or certify the customer's workload by itself.

## Governance, compliance, and security

| Term | Main question |
|---|---|
| Governance | Who may decide, which policies apply, and how do we oversee the lifecycle? |
| Compliance | Which laws, contracts, standards, and internal rules must the workload meet, and can we prove it? |
| Security | Which controls protect confidentiality, integrity, availability, and authorized use? |
| Responsible AI | How does the system address fairness, transparency, safety, robustness, and veracity? |

These areas overlap. A fairness review can be a governance process, a regulatory obligation, and a responsible-AI control.

## AWS service decision table

| Governance need | Service | What it supplies | What it does not supply |
|---|---|---|---|
| Record resource configuration and evaluate it against rules | AWS Config | Configuration history, snapshots, relationships, rule evaluations, conformance packs | Prompt and response content; software vulnerability scanning |
| Record who called an AWS API and when | AWS CloudTrail | Event history provides 90 days of Regional management events without a trail; configured trails or event data stores retain selected management and data events | A resource's full compliance posture; model payloads by default |
| Obtain AWS compliance reports and agreements | AWS Artifact | On-demand provider reports, certifications, and agreements | An audit of your application configuration |
| Find vulnerabilities in EC2, ECR images, and Lambda | Amazon Inspector | Vulnerability, code, and network-exposure findings | Data-residency enforcement or API history |
| Receive AWS best-practice recommendations | AWS Trusted Advisor | Recommendations across cost optimization, performance, security, fault tolerance, service limits, and operational excellence | Formal certification or a complete audit trail |
| Collect and assess audit evidence against a framework | AWS Audit Manager | Automated evidence collection and assessment workflows; supplementary architecture context rather than an example named in Task 5.2 | A substitute for legal interpretation or control ownership |
| Track model purpose, risk, and evaluation history | SageMaker Model Cards | Standardized model governance record | Configuration enforcement |
| Catalog datasets and metadata | AWS Glue Data Catalog or another approved catalog | Searchable schema, ownership, classification, and source metadata; supplementary architecture context rather than an example named in Task 5.2 | Complete lineage unless the workflow records transformations |

Task 5.2 names the first five services. Audit Manager and Model Cards often appear as distractors or supporting controls, so know their distinct jobs.

## AWS Config versus CloudTrail

This distinction appears often on AWS exams.

| Question | Choose |
|---|---|
| "Was this bucket compliant with the encryption rule last Tuesday?" | AWS Config |
| "Who changed the bucket policy last Tuesday?" | AWS CloudTrail |
| "Deploy a group of configuration rules aligned to a framework." | AWS Config conformance pack |
| "Investigate an unauthorized Bedrock API attempt." | AWS CloudTrail |
| "Store selected prompt and completion payloads." | Bedrock model invocation logging, not CloudTrail alone |

Config describes resource state and evaluates configuration. CloudTrail describes API activity. CloudTrail Event history exists without a trail and shows the previous 90 days of management events in the current Region; it does not show data events. Create a trail or event data store to retain events beyond that window and configure the management or data-event types you need. Use Config and CloudTrail together to connect a change to the actor who made it.

## Amazon Inspector, AWS Artifact, and Trusted Advisor

### Amazon Inspector

Use Inspector for resource-specific scanning:

- EC2 scanning finds operating-system and programming-language package vulnerabilities and network reachability issues. Network reachability findings apply only to EC2 instances.
- Machine image scanning checks eligible owned AMIs through their backing EBS snapshots for package vulnerabilities.
- ECR enhanced scanning checks eligible container images for package vulnerabilities.
- Lambda standard scanning checks package dependencies; separate Lambda code scanning checks custom application code and requires standard scanning first.
- Inspector Code Security scans supported source-code repositories for code vulnerabilities.

Findings can support remediation and audit evidence. Inspector does not prove that the full AI system complies with a law.

### AWS Artifact

Use Artifact to download AWS compliance reports and manage supported agreements. These documents help customers perform due diligence on AWS controls. An AWS report covers the stated AWS services and control period; it does not cover customer code, data handling, or configuration.

### AWS Trusted Advisor

Trusted Advisor checks the AWS environment against AWS best practices and produces recommendations. Its current check categories are cost optimization, performance, security, fault tolerance, service limits, and operational excellence. Available checks can depend on the support plan. A recommendation is useful operational input, not a certificate of compliance.

### Human review and production monitoring availability

Amazon A2I can route low-confidence or sampled predictions to human reviewers. Its built-in task types integrate with Amazon Textract key-value extraction and Amazon Rekognition content moderation; custom task types support other ML workflows. SageMaker Model Monitor can capture endpoint or batch-transform inputs and outputs, compare tabular data or model-quality metrics with baselines, schedule monitoring jobs, and report violations through CloudWatch.

AWS closed A2I, SageMaker Clarify, and SageMaker Model Monitor to new customers on July 30, 2026. Existing customers can continue normal use, and AWS states that it will maintain security and availability without adding features. These names can remain relevant to exam questions and existing architectures, but new implementations must use currently available alternatives that meet the same review or monitoring need.

## Data governance across the lifecycle

| Lifecycle stage | Governance questions | Example evidence |
|---|---|---|
| Collect | Is the source authorized, necessary, representative, and licensed? | Consent record, contract, source record, classification |
| Prepare | Which cleaning, labeling, redaction, and transformations occurred? | Lineage, job version, quality report, label audit |
| Train or customize | Who approved the data and model? Which Region and key were used? | Approval, job metadata, KMS and CloudTrail records |
| Evaluate | Which quality, safety, fairness, and security tests passed? | Evaluation dataset, rubric, metric report, reviewer sign-off |
| Deploy | Which version entered production, under which controls? | Model card, change record, Config state, release approval |
| Operate | Are behavior, access, cost, drift, and incidents monitored? | Metrics, alerts, invocation records, incident tickets |
| Retire | Was access removed and data deleted or archived under policy? | Deletion record, retained archive, final review |

### Logging

Define which events the organization needs, who may read them, how the team prevents tampering, and how long to retain them. AI interaction logs may contain prompts, outputs, PII, source chunks, tool parameters, and guardrail matches. Collecting everything can conflict with data-minimization duties.

Use separate access roles for normal redacted review, sensitive unredacted investigation, and logging administration. Encrypt log destinations and audit access to them.

### Data residency

Residency concerns where data is stored or processed. Select approved AWS Regions and verify each service, model, feature, backup, log destination, and third-party integration.

Bedrock cross-Region inference needs attention:

- A geographic inference profile keeps processing within its stated geography, such as the US, EU, or APAC boundary.
- A global inference profile can route to supported commercial Regions and may not fit a strict residency requirement.
- Cross-Region processing can place retained content in the destination Region when the selected model and retention mode permit retention.

Use organization policies, service control policies, IAM conditions, approved architecture patterns, and monitoring to enforce the documented choice. "Traffic stays on the AWS network" does not mean "traffic stays in one country."

### Retention

Set retention by data category and purpose. Include raw datasets, transformed data, embeddings, model artifacts, prompts, outputs, evaluation data, audit logs, backups, and temporary files.

A retention policy should state:

- the legal or business basis;
- the retention period and start event;
- archive and deletion method;
- holds or exceptions;
- owner and approval path;
- evidence of deletion;
- treatment of copies, caches, backups, and customized model artifacts.

Longer retention helps investigation but increases privacy exposure and storage cost. Shorter retention supports minimization but may fail legal or audit duties. The correct exam answer follows the stated obligation, not "keep everything forever."

### Monitoring and observability

Monitor both technical and AI behavior. Infrastructure metrics cover errors, latency, throttling, capacity, and availability. AI observations cover data quality, drift, fairness, toxicity, grounding, refusals, human overrides, and incidents. Record thresholds, owners, and response actions.

The official Task 5.2 objective uses the word **observation** in its list of data-governance examples. In current product language, use **observability** for telemetry that helps teams understand system behavior; do not treat observation as a separate AWS service.

## Governance protocols

### Policies

Write policies that define approved use cases, prohibited data, model and Region selection, access, human oversight, testing, documentation, logging, retention, incident response, vendor review, and retirement. Map each policy statement to an owner and an enforceable or reviewable control.

### Review cadence

Use both event-driven and scheduled reviews.

| Trigger | Review |
|---|---|
| New use case or material scope change | Risk classification, legal, privacy, security, and responsible-AI review |
| New model, prompt, tool, or data source | Regression evaluation and control review before release |
| Policy, law, or contract change | Gap assessment and control update |
| Safety, security, or fairness incident | Immediate triage and corrective review |
| Drift, threshold breach, or anomalous access | Technical investigation and business-impact review |
| Fixed monthly or quarterly date | Trend review, access review, exceptions, training, and open actions |
| Annual or risk-based interval | Full governance framework and third-party review |

High-risk systems need shorter intervals and stronger independence. A calendar review does not replace a review after a material change.

### Review strategies

Combine technical and nontechnical review:

- Technical reviewers test data quality, security, performance, robustness, fairness, grounding, and failure modes.
- Legal, privacy, compliance, risk, and business owners assess purpose, rights, obligations, disclosures, and user impact.
- Affected users and subject-matter experts test comprehension, accessibility, and real-world harm.
- Independent reviewers challenge assumptions for high-impact systems.

Record the decision, evidence, exceptions, owner, expiry date, and corrective actions. An exception without an expiry date can become an unreviewed permanent rule.

### Transparency standards

Document when AI is used, intended and prohibited uses, limitations, data and model provenance where disclosure is lawful, evaluation methods, significant risks, human accountability, and appeal or feedback paths. Match detail to the audience. Do not expose personal data, exploitable security details, or protected intellectual property.

### Team training

Train each role on the controls it operates. Developers need secure design and prompt-injection training. Data teams need provenance, licensing, quality, and privacy practices. Reviewers need rubrics and escalation rules. Business users need approved uses, disclosure duties, and ways to report failure.

Track completion and test competence. Attendance alone does not prove that a person can apply the policy.

## Generative AI Security Scoping Matrix

The AWS Generative AI Security Scoping Matrix groups use cases by how much of the application, model, and data the organization controls. More ownership creates more control and more security responsibility.

| Scope | Pattern | Customer focus |
|---|---|---|
| 1 | Use a public consumer generative-AI service | Terms, approved data, privacy, output use, and user behavior |
| 2 | Use an enterprise generative-AI application | Enterprise agreement, tenant controls, identity, data handling, and provider assurances |
| 3 | Build an application with a pre-trained foundation model | Application, prompts, RAG data, access, output, monitoring, and model-provider boundaries |
| 4 | Fine-tune a foundation model with organizational data | Scope 3 controls plus fine-tuning data, custom model artifacts, deletion limits, and model access |
| 5 | Build and train a model from scratch | Full model-development, training-data, infrastructure, artifact, deployment, and lifecycle security |

Scopes 1 and 2 place the organization in a buyer role. Scopes 3 through 5 place it in a builder role. The matrix scopes the work; it does not assign a compliance status.

## Governance framework selection

A framework gives teams a common structure for risk and controls. Select frameworks based on the organization, jurisdiction, sector, contracts, and use case.

| Framework or standard | Main use |
|---|---|
| AWS Responsible AI Lens | AWS design and operational practices for responsible AI |
| AWS Generative AI Security Scoping Matrix | Classify the customer's control and responsibility for a generative-AI use case |
| NIST AI Risk Management Framework | Organize AI risk activities around Govern, Map, Measure, and Manage |
| ISO/IEC 42001 | Establish an AI management system |
| AWS Well-Architected Framework and Security Pillar | Review cloud architecture and security practices |
| Sector or privacy rules | Apply binding obligations for the jurisdiction and data, such as healthcare or personal data requirements |

A framework is not a law. A certification held by AWS does not extend to the customer's workload. Have qualified legal and compliance teams determine obligations.

## Scenario reasoning

### Scenario 1: identify who weakened a bucket policy

An audit finds that an S3 bucket became public last month. The investigator needs the actor and time of the change.

**Best response:** Search AWS CloudTrail for the relevant API event and caller. Use AWS Config to inspect the resource state before and after the change.

**Reasoning:** CloudTrail answers who acted. Config answers how the configuration changed and whether it violated a rule.

### Scenario 2: prove resources stayed encrypted

A company needs continuous evidence that covered storage resources use approved encryption settings.

**Best response:** Use AWS Config rules and, where suitable, a conformance pack. Retain evaluations under the evidence policy.

**Reasoning:** Artifact supplies AWS reports, not the company's resource configuration history.

### Scenario 3: obtain AWS SOC evidence

An auditor requests the AWS provider report for services in scope.

**Best response:** Retrieve the applicable report from AWS Artifact and verify its service and control-period coverage.

**Reasoning:** Trusted Advisor recommendations and Inspector findings are not provider audit reports.

### Scenario 4: keep patient processing within an approved geography

A healthcare workload permits processing within the EU but not global routing.

**Best response:** Use approved EU Regions and a geographic EU inference profile if cross-Region capacity is needed. Restrict other Regions and review logs and service behavior.

**Reasoning:** A global inference profile can route outside the required geographic boundary.

### Scenario 5: review a model after a material data change

A fraud model receives a new data source two weeks after its quarterly review.

**Best response:** Trigger an event-driven review before release. Repeat data, security, fairness, and performance tests and update lineage and the Model Card.

**Reasoning:** Waiting for the next quarterly date leaves a material change unreviewed.

### Scenario 6: choose the Security Scoping Matrix category

A company fine-tunes a third-party foundation model with internal support transcripts.

**Best response:** Classify it as Scope 4.

**Reasoning:** The organization now controls fine-tuning data and a customized model, so it needs Scope 3 application controls plus controls for those assets.

### Scenario 7: retain AI interaction logs for five years

A regulation requires five years of audit events, but prompts can contain personal data.

**Best response:** Separate required audit metadata from sensitive payload logging, encrypt retained records, restrict access, apply legal holds where required, and expire non-required payloads under policy.

**Reasoning:** A five-year audit requirement does not mean every prompt and retrieved chunk must be stored for five years.

## Common exam traps

- **Config versus CloudTrail:** Config tracks state and compliance. CloudTrail tracks API activity.
- **Artifact versus Audit Manager:** Artifact provides AWS reports and agreements. Audit Manager helps collect evidence for your assessment.
- **Inspector versus Trusted Advisor:** Inspector finds vulnerabilities in supported workloads. Trusted Advisor recommends AWS best-practice improvements.
- **AWS compliance versus customer compliance:** AWS evidence covers AWS controls in scope. You remain responsible for the workload.
- **Policy versus evidence:** A written rule is not proof that teams followed it.
- **Monitoring versus governance:** Monitoring produces signals. Governance assigns owners and decisions.
- **Residency versus private networking:** PrivateLink keeps traffic off the public internet; it does not select the processing country.
- **Retention versus backup:** A backup strategy does not define legal retention or deletion.
- **Scheduled review versus change review:** Material changes need review before the next calendar date.
- **Framework versus certification:** A framework structures work. It does not certify the system.
- **Scope number versus risk rating:** The Scoping Matrix describes the build and ownership pattern, not whether the use case is safe.
- **Training attendance versus competence:** Governance needs role-specific training and evidence that people can apply it.

## Self-check

1. Which service answers, "Who changed this IAM policy?"
2. Which service answers, "Was this resource compliant with our encryption rule?"
3. Which Security Scoping Matrix scope covers fine-tuning a third-party foundation model with company data?
4. Why does an AWS compliance report not prove that a customer's AI application is compliant?
5. Which two kinds of review cadence should an organization combine?

### Answers

1. AWS CloudTrail.
2. AWS Config.
3. Scope 4.
4. The report covers specified AWS controls, services, and periods. The customer still owns application code, data, configuration, access, operation, and use of output.
5. Scheduled reviews and event-driven reviews after material changes, incidents, threshold breaches, or policy changes.

## Practice

- [Domain 5 questions with answers and explanations](../../practice/question-bank.md#task-52)

## Official sources

- [AIF-C01 Domain 5 objectives](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain5.html)
- [AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)
- [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
- [CloudTrail Event history](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)
- [AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/what-is-aws-artifact.html)
- [Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html)
- [AWS Trusted Advisor](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor.html)
- [Trusted Advisor check categories](https://docs.aws.amazon.com/awssupport/latest/user/get-started-with-aws-trusted-advisor.html)
- [SageMaker feature availability changes](https://aws.amazon.com/about-aws/whats-new/2026/06/aws-service-availability/)
- [AWS Audit Manager](https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is.html)
- [SageMaker Model Cards](https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html)
- [Generative AI Security Scoping Matrix](https://aws.amazon.com/ai/security/generative-ai-scoping-matrix/)
- [AWS guidance for scoping generative-AI use cases](https://docs.aws.amazon.com/whitepapers/latest/navigating-security-landscape-genai/scoping-generative-ai-use-cases.html)
- [Geographic cross-Region inference](https://docs.aws.amazon.com/bedrock/latest/userguide/geographic-cross-region-inference.html)
- [AWS Responsible AI Lens](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/welcome.html)
- [AWS Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)
- [NIST AI Risk Management Framework resources on AWS](https://aws.amazon.com/ai/responsible-ai/resources/)

---

[Domain contents](README.md) · [All domains and objectives](../../README.md#domain-guide)

**Previous:** [Lesson 13](13-security.md) · **Next:** [Question bank](../../practice/question-bank.md)

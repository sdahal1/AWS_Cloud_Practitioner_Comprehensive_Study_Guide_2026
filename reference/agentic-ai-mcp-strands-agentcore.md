# Agentic AI, MCP, Strands Agents, and Amazon Bedrock AgentCore

These terms describe different layers. An agent is the application behavior. MCP is a connection standard. Strands Agents is an open-source SDK for building an agent loop. Amazon Bedrock AgentCore supplies managed services for deploying and operating agents.

## Start with the agent loop

A generative AI response can answer one prompt without taking action. An agent can pursue a goal across several steps:

1. A user gives the agent a goal.
2. The model considers the instructions, conversation, context, and available tools.
3. The model selects a tool and supplies arguments.
4. The application validates permissions and input before executing the tool.
5. The tool returns an observation.
6. The agent adds the observation to context and chooses another action or a final answer.

Tools create risk because an agent can change external systems. Validate model-produced arguments, use least privilege, require approval for consequential actions, and record tool activity.

## Core concepts

| Concept | Exam-level meaning | Common confusion |
|---|---|---|
| Tool | A callable capability such as searching documentation or creating a ticket | The model does not gain permission merely because a tool exists |
| Orchestration | Logic that manages model calls, tools, steps, retries, and handoffs | Orchestration is broader than one prompt |
| Memory | Information retained within or across sessions | A long prompt is context, not durable memory |
| Workflow | A defined sequence of steps | An agent may choose steps; a fixed workflow follows predetermined logic |
| Multi-agent system | Several specialized agents cooperate or hand work to one another | More agents add coordination, cost, latency, and security boundaries |
| Human in the loop | A person reviews, corrects, or approves work | A Guardrail does not replace human approval for a high-impact action |

## Model Context Protocol (MCP)

MCP standardizes how AI applications connect to external context and capabilities. An MCP host contains or coordinates the AI application. An MCP client connects that host to an MCP server. The server exposes capabilities such as tools, resources, or prompts.

Use MCP when the exam describes a standard connection between an agent and external tools or data. MCP does not grant authorization, judge whether a tool call is safe, or guarantee correct output. The implementation still needs authentication, authorization, validation, network controls, and audit logs.

**Scenario cue:** Several AI assistants need a consistent interface for discovering and calling the same enterprise tools. MCP provides the protocol. IAM, OAuth, or another control decides who may call them.

[AWS Prescriptive Guidance: What is MCP?](https://docs.aws.amazon.com/prescriptive-guidance/latest/mcp-strategies/what-is-mcp.html)

## Strands Agents

Strands Agents is an open-source SDK for building AI agents. You provide a model, instructions, and tools. Its agent loop sends context to the model, executes selected tools, returns tool results to the model, and stops when the model produces the final response.

Choose Strands in an exam scenario that asks for an SDK or framework to build model-driven agents in code. Strands is not a foundation model, hosting service, or protocol. It can use Amazon Bedrock models, connect to MCP servers, and run on AgentCore Runtime, but those are separate choices.

[Strands Agents documentation](https://strandsagents.com/latest/documentation/docs/)

## Amazon Bedrock Agents Classic

Amazon Bedrock Agents, launched in November 2023, is now named **Amazon Bedrock Agents Classic**. It orchestrates foundation models, instructions, action groups, and knowledge bases for existing customers. AWS moved it to maintenance on July 30, 2026: existing customers can continue using it, but new customers cannot access it. New agent designs should evaluate AgentCore Harness and the other AgentCore capabilities.

Do not treat Agents Classic and AgentCore as aliases. Agents Classic is the earlier managed Bedrock orchestration feature. AgentCore is a composable platform with managed agent loops, hosting, tools, identity, memory, policy, observability, evaluation, optimization, and payments.

[Amazon Bedrock Agents Classic availability change](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-classic-maintenance-mode.html)

## Amazon Bedrock AgentCore

AgentCore is a set of services for production agent workloads. Learn the role of each component rather than configuration commands.

| AgentCore capability | Recognition cue |
|---|---|
| Harness | Define an agent with a model, system prompt, and tools; AgentCore runs the managed loop, executes tools, persists state, recovers from failures, and isolates sessions |
| Runtime | Deploy and scale a custom agent or tool in an isolated serverless environment with framework and model flexibility |
| Gateway | Turn APIs and Lambda functions into agent-compatible tools and connect existing MCP servers behind managed endpoints |
| Identity | Give agents workload identities and broker access to AWS or third-party services, including on-behalf-of-user access |
| Memory | Keep short-term conversation state and longer-term information across sessions, with controls over what the agent retains |
| Policy | Enforce deterministic boundaries on agent-to-tool requests through Gateway |
| Observability | Collect standardized traces, logs, and metrics for instrumented agent activity; telemetry and sampling determine coverage |
| Evaluations | Score agent behavior online or on demand with built-in or custom evaluators, including task completion and tool-use measures |
| Optimization | Analyze production traces for failure, intent, and trajectory insights, propose changes, and validate them with batch evaluation or A/B tests before approval |
| Payments | Let agents pay for supported paid APIs, MCP servers, agents, and content through payment orchestration, third-party wallets, spending limits, and transaction observability |
| Browser | Give agents a managed browser environment for web interaction |
| Code Interpreter | Run agent-generated code in an isolated sandbox |
| Registry | Catalog, approve, discover, share, and reuse agents, tools, MCP servers, and skills across an organization |

AgentCore services can be used together or separately. Runtime hosts execution; Gateway exposes tools; Identity handles credentials; Policy limits tool actions. None of these makes model output true by default.

[Amazon Bedrock AgentCore documentation](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/what-is-bedrock-agentcore.html)

## Selection scenarios

| Requirement | Best match |
|---|---|
| Build an agent loop in Python or TypeScript with a model and tools | Strands Agents |
| Give many agents one standard tool interface | MCP |
| Convert existing APIs or Lambda functions into agent-ready MCP tools | AgentCore Gateway |
| Define and run a managed agent loop from model, prompt, and tool configuration | AgentCore Harness |
| Host an agent built with a custom or supported framework | AgentCore Runtime |
| Preserve useful information across agent sessions | AgentCore Memory |
| Broker OAuth credentials for an agent acting for a user | AgentCore Identity |
| Block disallowed tool actions with deterministic rules | Policy in AgentCore |
| Collect standardized telemetry for instrumented agent activity | AgentCore Observability |
| Find repeated production failures and validate proposed prompt or tool-description changes | AgentCore Optimization |
| Pay for a supported paid API or MCP tool with spending controls | AgentCore Payments |
| Use existing managed Bedrock agent orchestration as a customer who had access before July 30, 2026 | Amazon Bedrock Agents Classic |

## Security traps

- Tool descriptions influence model choice; they do not authorize execution.
- Prompt injection can arrive through user input, retrieved content, or tool results.
- A model-generated parameter is untrusted input. Validate it at the tool boundary.
- Memory can hold sensitive data. Apply access, retention, and isolation controls.
- An MCP server can expose powerful actions. Give the connecting identity the least privilege needed.
- Guardrails filter model interactions. Policy and authorization control tool actions.
- Observability can capture sensitive prompts and results. Protect logs and set retention rules.

## Exam scope and product context

The published AIF-C01 objectives cover agents, tools, memory, orchestration, workflows, multi-agent patterns, MCP, and AgentCore Identity and Policy. AgentCore is a composable managed platform. Harness, Runtime, Gateway, Memory, Observability, Evaluations, Optimization, Payments, Browser, Code Interpreter, and Registry provide additional product context; their availability does not by itself establish exam scope. The applicable exam guide determines which capabilities are in scope.

[Domain guide](../README.md#domain-guide) · [Service selection](service-selection.md) · [Glossary](glossary.md) · [Common exam traps](common-exam-traps.md)

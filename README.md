# AutoGPT Autonomous Agent Platform Skill

A Claude Code skill for designing, building, operating, and evaluating autonomous workflows with the AutoGPT platform. It covers visual graph construction, reusable blocks, execution triggers, monitoring, integrations, custom agent development, benchmarking, and deployment.

AutoGPT platform APIs, installation steps, and interfaces can change. Treat the commands and URLs in the skill instructions as version-dependent examples, and verify them against the installed release before using them in production.

## What This Skill Covers

- Understand the platform's graph and block model.
- Build workflows with input, processing, decision, and output nodes.
- Configure manual, webhook, and scheduled execution where supported.
- Monitor executions and inspect intermediate results.
- Integrate external services and credentials.
- Create custom agents and abilities with the development toolkit.
- Benchmark agent behavior and preserve reproducible test cases.
- Prepare deployment configurations and operational checks.
- Diagnose setup, database, queue, and execution failures.

## When to Use It

Use this skill when building visual AutoGPT workflows, creating persistent agents, adding event-driven automation, developing custom abilities, integrating external services, or preparing deployment and evaluation workflows.

For deterministic tasks, a regular function or a simpler workflow is often easier to test and operate. Add autonomous loops only when the use case requires them.

## Installation

The AutoGPT platform is a separate application. The skill's documented Docker setup begins by cloning the platform repository:

~~~bash
git clone https://github.com/Significant-Gravitas/AutoGPT.git
cd AutoGPT/autogpt_platform
cp .env.example .env
docker compose up -d --build
~~~

The skill also documents running the frontend separately with npm. Review the current upstream setup guide before proceeding, because dependencies and startup commands may change.

Install this skill into Claude Code separately:

~~~bash
git clone https://github.com/Brajesh31/claude-agents-autogpt-skill.git ~/.claude/skills/agents-autogpt
~~~

## Usage

Invoke the skill:

~~~text
/agents-autogpt
~~~

Provide the workflow goal, input data, trigger requirements, integrations, permissions, deployment environment, and expected behavior.

## Core Concepts

### Graphs and Blocks

An AutoGPT agent can be represented as a graph of connected nodes. Each node runs a block that performs a defined operation. Typical block roles include:

| Block role | Purpose |
|---|---|
| Input | Accept initial values or external payloads |
| AI | Call a model or generate text |
| Standard | Perform general processing |
| Webhook | Receive external events |
| Agent | Delegate to a nested agent |
| Output | Produce the final result |

A useful graph has clear boundaries between input validation, reasoning, external actions, and output generation.

### Execution Triggers

The skill describes manual execution, webhooks, and scheduled execution. Confirm the exact API routes, payload schema, authentication requirements, and schedule support for the platform version you install.

### Development Toolkit

The skill also describes a development workflow for custom agents and abilities. Keep custom code isolated, document configuration, and test integrations with least-privilege credentials.

## Recommended Workflow

1. Define the user outcome and measurable success criteria.
2. Identify inputs, outputs, and external side effects.
3. Draw the graph before configuring blocks.
4. Use the smallest number of nodes that can complete the task.
5. Validate each block's inputs and outputs.
6. Configure retries, timeouts, and failure branches.
7. Add integrations using narrowly scoped credentials.
8. Test manual execution with representative and invalid inputs.
9. Test webhook and schedule triggers in a controlled environment.
10. Inspect execution traces and intermediate results.
11. Benchmark important behaviors and record known limitations.
12. Deploy only after security, reliability, and recovery checks pass.

## References Already Included

- [Advanced usage](references/advanced-usage.md): advanced workflow, custom block, and deployment topics.
- [Troubleshooting](references/troubleshooting.md): setup and execution diagnosis.

## Included Resources

- [Agent graph design worksheet](resources/agent-graph-design-worksheet.md): map inputs, nodes, branches, side effects, and outputs before implementation.
- [Deployment readiness checklist](resources/deployment-readiness-checklist.md): review security, configuration, reliability, and recovery before launch.
- [Execution review template](resources/execution-review-template.md): capture traces, block failures, performance, and follow-up actions.

## Operational and Security Guidance

- Store API keys and OAuth credentials using the platform's supported secret mechanism.
- Do not hard-code credentials in graph definitions, custom blocks, or repository files.
- Give integrations only the permissions needed for the workflow.
- Validate external webhook payloads and authenticate senders.
- Use timeouts and bounded retries for external calls.
- Make non-idempotent actions safe against duplicate execution where possible.
- Require explicit approval for destructive or high-impact operations.
- Inspect intermediate outputs before using them in downstream actions.
- Monitor queue, database, executor, and application health.
- Keep a tested rollback or recovery path.

## Repository Structure

~~~text
claude-agents-autogpt-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── advanced-usage.md
│   └── troubleshooting.md
└── resources/
    ├── agent-graph-design-worksheet.md
    ├── deployment-readiness-checklist.md
    └── execution-review-template.md
~~~

## External Resources

- [AutoGPT documentation](https://docs.agpt.co)
- [AutoGPT repository](https://github.com/Significant-Gravitas/AutoGPT)
- [AutoGPT community](https://discord.gg/autogpt)

## License and Upstream Components

The root LICENSE applies to this repository's own material. The AutoGPT platform and its subcomponents are separate upstream projects with their own terms. The skill source notes that AutoGPT Classic and the Platform have different licensing terms. Check the current upstream licensing documents before redistributing or deploying platform components.

## License

See the root LICENSE file for the license applying to this repository's covered material.

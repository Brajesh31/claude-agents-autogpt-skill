# AutoGPT Agent Graph Design Worksheet

Use this worksheet to design a graph before implementing it in the visual builder or development toolkit.

## 1. Outcome

- **Workflow name:**
- **Owner:**
- **User or system that initiates it:**
- **Problem being solved:**
- **Successful final outcome:**
- **What is explicitly out of scope:**

## 2. Inputs and Outputs

| Field | Description | Required? | Validation / constraints |
|---|---|---|---|
| Input 1 | | | |
| Input 2 | | | |
| Output 1 | | | |
| Output 2 | | | |

- **Input source:**
- **Expected volume and size:**
- **Sensitive data involved:**
- **Output destination:**

## 3. Graph Plan

| Step | Node / block | Input | Output | Side effect? | Failure behavior |
|---:|---|---|---|---|---|
| 1 | Input / validation | | | | |
| 2 | Processing / AI | | | | |
| 3 | Decision / branch | | | | |
| 4 | Integration / action | | | | |
| 5 | Output | | | | |

## 4. Trigger and Execution

- **Trigger:** manual / webhook / schedule / other
- **Authentication method:**
- **Expected frequency:**
- **Maximum execution duration:**
- **Concurrency expectation:**
- **Duplicate event handling:**

## 5. Integrations and Permissions

| Integration | Data accessed | Required permissions | Credential owner |
|---|---|---|---|
| | | | |
| | | | |

Use the minimum permissions needed. Identify all external side effects and the approval required before they occur.

## 6. Failure and Recovery

- **Timeout behavior:**
- **Retry policy:**
- **Maximum retries:**
- **Dead-letter or failure reporting path:**
- **Human escalation path:**
- **Recovery / replay approach:**

## 7. Acceptance Tests

- [ ] Typical valid input completes successfully.
- [ ] Invalid input is rejected safely.
- [ ] External integration failure is handled.
- [ ] Duplicate trigger does not cause harmful repeated actions.
- [ ] Sensitive data is not exposed in logs or outputs.
- [ ] Final output meets the agreed format.
- [ ] Execution trace is sufficient to diagnose failures.

## Approval

- **Designer:**
- **Reviewer:**
- **Date:**
- **Status:** draft / revise / approved

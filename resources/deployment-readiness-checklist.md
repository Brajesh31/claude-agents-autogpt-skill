# AutoGPT Deployment Readiness Checklist

Use this checklist before exposing a workflow to users, webhooks, or recurring execution.

## Platform and Configuration

- [ ] Platform version and deployment topology are recorded.
- [ ] Current upstream installation requirements are confirmed.
- [ ] Environment variables are supplied through an approved secret mechanism.
- [ ] Database, Redis, queue, and executor configuration is verified where applicable.
- [ ] Network exposure is limited to required services.
- [ ] Development defaults are not exposed in production.

## Workflow Quality

- [ ] Graph structure and block responsibilities are documented.
- [ ] Inputs and outputs have explicit schemas.
- [ ] Each branch has a defined outcome.
- [ ] External calls have timeouts.
- [ ] Retry behavior is bounded.
- [ ] Duplicate triggers and non-idempotent actions are handled.
- [ ] Failure and partial-completion behavior is tested.

## Security

- [ ] API keys and OAuth secrets are not stored in source files.
- [ ] Credentials use least-privilege scopes.
- [ ] Webhook senders are authenticated.
- [ ] External payloads are validated.
- [ ] Destructive actions require suitable approval.
- [ ] Logs avoid unnecessary secrets and personal data.
- [ ] Platform and integration licensing has been reviewed.

## Reliability and Operations

- [ ] Health checks are available for required services.
- [ ] Execution status and failures are observable.
- [ ] Logs and traces are retained according to policy.
- [ ] Resource limits are configured.
- [ ] Queue backlogs and stuck executions can be detected.
- [ ] Database backup and restore are tested.
- [ ] Rollback and recovery procedures are documented.
- [ ] An owner is responsible for incidents and maintenance.

## Release Decision

- **Platform version:**
- **Workflow version:**
- **Environment:**
- **Reviewer:**
- **Known risks:**
- **Decision:** approve / conditional / reject
- **Review date:**

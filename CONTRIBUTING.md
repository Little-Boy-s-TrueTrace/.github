# Contributing to TrueTrace

Thank you for helping improve TrueTrace. This project is open source and intentionally split across multiple repositories so each part can be reviewed and tested independently.

## Start in the right repository

Open issues and pull requests in the repository that owns the change:

| Area | Repository |
|---|---|
| Root project, docs, architecture | [`truetrace`](https://github.com/Little-Boy-s-TrueTrace/truetrace) |
| Banking API, accounts, transactions, KYC/AML/STR | [`truetrace-backend`](https://github.com/Little-Boy-s-TrueTrace/truetrace-backend) |
| Multi-Agent AI orchestrator, Kafka consumers | [`truetrace-agent-engine`](https://github.com/Little-Boy-s-TrueTrace/truetrace-agent-engine) |
| Deepfake Inspector agent prompts and schemas | [`agent-deepfake-inspector`](https://github.com/Little-Boy-s-TrueTrace/agent-deepfake-inspector) |
| Money-Trail Explorer agent rules and heuristics | [`agent-money-trail`](https://github.com/Little-Boy-s-TrueTrace/agent-money-trail) |
| AML STR Reporter agent templates | [`agent-aml-reporter`](https://github.com/Little-Boy-s-TrueTrace/agent-aml-reporter) |
| Compliance dashboard (Go API + React UI) | [`truetrace-dashboard`](https://github.com/Little-Boy-s-TrueTrace/truetrace-dashboard) |
| Customer web portal (Next.js) | [`truetrace-web-client`](https://github.com/Little-Boy-s-TrueTrace/truetrace-web-client) |
| Mobile banking app (Flutter) | [`truetrace-mobile-app`](https://github.com/Little-Boy-s-TrueTrace/truetrace-mobile-app) |
| Docker Compose, Kubernetes, Helm, Nginx | [`truetrace-deployment`](https://github.com/Little-Boy-s-TrueTrace/truetrace-deployment) |
| AWS/Alibaba Cloud infrastructure (Terraform) | [`truetrace-terraform`](https://github.com/Little-Boy-s-TrueTrace/truetrace-terraform) |

For cross-repository proposals, open a design issue in the repository with the largest expected implementation impact and link follow-up issues from there.

## What to include

- Explain the problem, expected behavior, and the repository area affected.
- Keep pull requests focused and small enough to review.
- Add or update tests when changing behavior.
- Update documentation when changing setup, APIs, schemas, policy gates, or operational assumptions.
- Never commit secrets, real customer data, cloud credentials, tokens, private keys, production logs, or exploit artifacts from systems you do not own.

## Pull request checklist

Before opening a pull request, confirm that:

- The change has a clear issue, motivation, or review note.
- Tests or validation steps are included in the pull request description.
- Documentation reflects the new behavior.
- The contribution is compatible with the MIT License.

## License

Unless explicitly stated otherwise, contributions submitted to TrueTrace are provided under the MIT License.

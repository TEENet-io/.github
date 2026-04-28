# TEENet

**Open-source trust stack for protected secrets and verifiable actions**

TEENet helps developers build applications that use secrets, such as private keys, API keys, OAuth tokens, and DB passwords, without giving one SaaS platform full control.

At the system layer, TEENet protects how these critical actions happen: which code is allowed to use a secret, where that code runs, how control is split across nodes, what result was produced, and what proof can be checked later.

## Why TEENet?

Many applications need software to use secrets that should not be exposed directly to one service, one operator, or one administrator.

The hard part is not only storing a secret. The hard part is making sure a sensitive operation is performed by the right workload, inside the right trust boundary, under the right owner-controlled authorization, with evidence that can be verified later.

TEENet is being built for developers who want this trust path to be open, self-owned, and composable.

## What TEENet Does

TEENet gives applications a system layer for protected secret use and verifiable critical actions.

With TEENet, an application can:

- run approved code in a protected execution environment;
- bind secret use to approved code or a specific application;
- split secrets into threshold shares and store them across separate TEE-backed nodes;
- require multiple TEE-backed nodes to participate in signing or credential-backed operations, without exposing the secrets themselves;
- produce verifiable proof for critical results and protected operations;
- keep signed records that make sensitive actions traceable later.

TEENet does not define the application's business rules. It protects the lower-level trust path applications rely on.

## Projects

These projects are separate application or component layers around the TEENet trust stack. They are not the definition of TEENet Core.

| Project | Status | What it demonstrates |
| --- | --- | --- |
| [TEENet Wallet](https://github.com/TEENet-io/teenet-wallet) | Open source | An application-layer wallet for agents and automation. The wallet owns its business policy layer, including API access, spending rules, approvals, and user-facing workflows. |
| Cross-Bridge Message Attester | Coming soon | A component for bridge-domain message attestation. Bridge-specific validation and policy live at the component or application layer. |

## Architecture Overview

## Design Principles

- **Separate application policy from system trust.** Apps define business rules; TEENet protects the secret use and execution path.
- **Self-owned first.** Developers should be able to run, inspect, and adapt the trust stack themselves.
- **Verify before relying.** Critical actions should produce evidence, not just logs.
- **Reduce single points of trust.** Threshold design and attestation should narrow what any one operator can control.
- **Build for real integrations.** TEENet should make hard applications easier to ship, not only provide abstract security primitives.

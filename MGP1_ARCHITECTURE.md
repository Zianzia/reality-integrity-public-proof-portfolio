# MGP-1 — MOMMA Guardian Proof

## Public principle

> Protect the work. Preserve the truth. Prove what changed.

MGP-1 is a proof-stage architecture for establishing canonical repository state, observing integrity-relevant changes, preserving authenticated source evidence outside the protected environment, classifying unexplained deviations, and producing verifiable incident records for investigation and recovery.

## Core question

> Does current reality still match the last authorized state?

## Proof-stage architecture

`GitHub observable event -> authenticated external evidence preservation -> canonical-state re-check -> policy interpretation -> signed incident/transition receipt -> verification`

## Evidence rule

Webhook or platform event data is treated as a **signal**, not canonical truth. MGP-1 is designed to preserve exact source evidence and independently re-check current GitHub state before interpreting the event.

The evidence should not live only inside the account being protected.

## What the current implementation work covers

Private proof-stage development includes:

- deterministic repository snapshots;
- SHA-256 state and artifact commitments;
- authorization-aware transition classification;
- collaborator, visibility, branch/ref, artifact and security-control change scenarios;
- Ed25519 incident receipts;
- source-evidence hash binding;
- replay and delivery-ID collision classification;
- recovery verification;
- dynamic enrollment of future repositories;
- authenticated GitHub-compatible webhook ingestion;
- external raw evidence storage and replay indexing.

## Current public-status boundary

MGP-1 must **not** yet be described as continuously protecting repositories in real time.

The live authenticated GitHub webhook proof, production signing-key custody, automatic remediation, universal clone/fetch/exfiltration detection, attacker attribution, and public network anchoring remain incomplete or unproven.

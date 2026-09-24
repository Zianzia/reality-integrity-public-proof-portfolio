# Who Authorized the Action? A Four-Case RIAP Proof

**The question:** If an AI agent takes a consequential action, can an outside reviewer check the authority, approval, action, and surviving evidence?

**What we exercised:** A local RIAP reference implementation processed a synthetic **USD 125 purchase order** through a mock action gateway. The run uses test-only signing keys and a fixed test time. The gateway has no production purchase-order connection.

| Case | Observable result | What it supports |
| --- | --- | --- |
| Approval omitted | Request rejected; mock adapter called zero times | This gateway requires approval before this simulated external effect. |
| Approval present | Mock adapter called once; signed action chain receives a verified report | The allowed simulated action can be linked to its recorded authority and approval. |
| Evidence changed | Amount altered after the run; separate chain verifier returns **failed** | The modified record cannot pass the original evidence checks. |
| Proposal replayed | New request ID reuses the earlier signed proposal and approval; persistent nonce registry rejects it; adapter remains at one call | Reuse of that already claimed nonce cannot trigger a second effect through this gateway. |

The [four-case demonstration was merged into the private RIAP repository](https://github.com/Zianzia/reality-integrity-action-protocol/pull/6). Its automated checks passed on Node.js 22 and 24. A reviewer with authorized repository access can inspect the [method and commands](https://github.com/Zianzia/reality-integrity-action-protocol/blob/main/docs/REVIEWER-DEMO.md) and reproduce or challenge the result.

## What this does—and does not—answer

The demonstration tests the relationship between a request, its signed records, the gateway decision, a mock effect, and subsequent verification. It does **not** reveal the model's internal reasoning; prove the human approver's real-world identity or authority; establish that the budget facts are true; stop actions through unrelated channels; or establish production security, regulatory compliance, or third-party certification.

**Review invitation:** Challenge the narrow claim. Given access to the private source, try changing the approval, amount, nonce, or gateway adapter and inspect both the adapter-call count and verifier result. A useful review identifies a case where the demonstrated claim fails—or confirms precisely the conditions under which it holds.

RIAP is an independent Sean-for-Hire project by Sean Alan LaViscount. The [AI Evidence Gap Review](AI_EVIDENCE_GAP_REVIEW.md) is a separate, fixed-scope service; purchasing it is not required to examine this proof.

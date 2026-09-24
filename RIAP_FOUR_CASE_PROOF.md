# Who Authorized This? A Working RIAP Demonstration

Imagine an AI assistant asked to place a **$125 purchase order**. The person responsible wants three answers before it happens:

1. Was the assistant allowed to place this kind of order?
2. Did the required person approve **this exact order**?
3. Could someone later check whether the record was changed?

**RIAP is Sean Alan LaViscount’s approach to recording and checking those answers.** The working demonstration runs four versions of this situation:

| What we tried | What the program did |
| --- | --- |
| Place the order without the required approval | **Blocked it before the simulated order was placed.** |
| Place the order with approval | **Allowed it once** and produced a signed record tying the order to its approval. |
| Change the amount in the record afterward | **Rejected the changed record** when it was checked independently. |
| Submit the approved request again under a new request number | **Blocked a second order.** |

These are results from a **local simulation**. The program uses test signing keys and a mock purchase-order connection. No real money moves and no real order is placed. Its automated validation passed on Node.js 22 and 24.

## What a reviewer can check

The [working demonstration is merged into RIAP](https://github.com/Zianzia/reality-integrity-action-protocol/pull/6). Its source repository is private. With access, a technical reviewer can read the [reproduction instructions](https://github.com/Zianzia/reality-integrity-action-protocol/blob/main/docs/REVIEWER-DEMO.md), run the four cases, inspect the rules, and try to make an unapproved or repeated order get through. They can also alter the record and see whether verification still catches it.

**The review question is specific:** Does this implementation block the two unauthorized simulated orders before its mock connection runs, and does its verifier reject the changed record? A reviewer should report both any successful bypass and the limits of what they tested.

## What this proof does not establish

It does not show what the AI was thinking. It does not establish that a claimed human approver is the right person in a real organization, that the underlying business facts are true, or that an agent cannot act through another system. It is not a production security assessment or a certification.

**In one sentence:** This demonstration shows a working way to require approval for a simulated AI action and leave evidence that another person can check.

RIAP is an independent Sean-for-Hire project by Sean Alan LaViscount. The [AI Evidence Gap Review](AI_EVIDENCE_GAP_REVIEW.md) is a separate service; buying it is not required to examine this proof.

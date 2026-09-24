# RIAP four-case recording guide

**Purpose:** A 75–90 second screen recording that shows a real run of the merged local demonstration. Record actual terminal output; never animate a result or substitute a mockup for the program.

## Before recording

- Use a clean checkout of private RIAP `main`, Node.js 22.5+ and `npm ci`.
- Verify `node reference-implementation/src/reviewer-demo.js` exits successfully.
- Hide terminal notifications, local usernames, tokens, private paths, and unrelated windows.
- The recording can show the command and four-case output. Do not show private code, unsanitized evidence, or signing material.

## Spoken script / captions

**0–10 seconds — question**  
“If an AI agent places an order, who approved it—and could someone verify the surviving record?”

**10–18 seconds — scope**  
“This is a local reference demonstration: a synthetic $125 purchase order, test keys, and a mock adapter. No real order is placed.”

**18–28 seconds — command**  
Show `node reference-implementation/src/reviewer-demo.js` in the terminal and run it.

**28–45 seconds — gate**  
Point to “missing approval: blocked before external effect” and “approved purchase order: executed once and verified.” Say: “The gateway blocks the first request before the adapter. With the signed approval, the simulated action executes once.”

**45–62 seconds — evidence**  
Point to “altered evidence: independent verifier rejected.” Say: “Change the recorded amount, and verification fails.”

**62–75 seconds — replay**  
Point to “replayed proposal and approval: blocked before second external effect.” Say: “A new request ID cannot reuse the already claimed proposal to trigger a second effect.”

**75–90 seconds — invitation and boundary**  
“Inspect the public proof brief. Qualified technical reviewers can request access to reproduce and challenge the run. This is a controlled simulation, not a production safety guarantee.”

## Publication check

Before posting, watch the exported clip once with audio. Confirm the four claims match the actual captured output and the description includes “controlled simulation; test keys; mock adapter.” Link the clip to [the public brief](RIAP_FOUR_CASE_PROOF.md). Add the video URL to that brief only after the recording exists.

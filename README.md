# Agent Action Trust Criteria (AATC)

**Testable controls for AI agents that take actions on data and money.**

ISO/IEC 42001 governs the organization. NIST AI RMF governs the risk process. OWASP lists the threats. SOC 2 attests controls largely through documents and sampling. None of them answers the question an operator asks when an agent is moving money or changing records:

> When this agent is manipulated, what is it still able to do, and how do I prove it?

AATC answers it with **26 controls that are verified by test, not by questionnaire**. Every control names the adversarial test that demonstrates it and the evidence that test leaves behind.

**Read the draft: [AATC-v0.1.md](AATC-v0.1.md)**

## The six domains

| Domain | Controls | What it asks |
|---|---|---|
| CC Credential custody | 4 | Can the agent read, leak or misdirect a live credential? |
| AA Action authorization | 6 | Is every side effect decided before it runs, and bound to what was granted? |
| DE Data and egress | 4 | Can data reach an undeclared destination, an internal address, or a model whose terms forbid it? |
| MS Money and spend | 4 | Do payees come from history rather than the conversation, and are value, spend and loop limits enforced before the call? |
| PV Provenance and intent | 3 | Did anyone actually ask for the values this action carries? |
| EV Evidence and audit | 5 | Can every decision be reproduced and proven afterwards? |

## Three assurance levels

| Level | Name | What is required |
|---|---|---|
| L1 | Declared | Controls implemented and documented by the operator. |
| L2 | Demonstrated | The reference test suite run against the live configuration, results published with evidence. |
| L3 | Assessed | An independent assessor re-runs the tests and samples real decisions over an observation period. |

## Principles

1. Enforcement lives outside the model. An instruction to the model is not a control.
2. Deny by default.
3. The agent never holds what it could leak.
4. Permission to act is not permission to act on anything.
5. A control that has never been observed refusing something has not been shown to work.
6. Each control states what it does not cover, and negative results are published.

## Status

Version 0.1, public draft for comment. The mappings to ISO/IEC 42001, NIST AI RMF, OWASP and SOC 2 are indicative and have not been reviewed by those bodies. The open questions for v0.2 are listed in section 10 of the draft. Comments, corrections and disagreements are welcome as issues.

A reference implementation of most controls is [UBAG](https://github.com/mohameduk/ubag-core), which is where the negative results quoted in the draft were measured. AATC is written to be implementation-neutral: any gateway, proxy, sandbox supervisor or tool server can be assessed against it.

AATC is not an attestation standard, is not affiliated with or endorsed by AICPA, ISO, NIST, OWASP or CSA, and is not legal, audit or compliance advice.

## Licence

Copyright (c) 2026 Mohamed Ben Hadj Hmida, Dixit Algorizmi Inc. Licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE.md): use it, adapt it and build on it, with attribution.

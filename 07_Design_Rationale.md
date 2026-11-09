# 07 · Design Rationale — Why the Design Looks the Way It Does

**Status:** Edition 1.0 · November 2026 · Public consultation edition
**Provenance:** This document records the reasoning behind the major choices in [01_Governance_Model.md](01_Governance_Model.md), the alternatives that were rejected and why, the conditions that would change our minds, and the research agenda for the open questions. The design was developed with AI assistance, including role-played expert perspectives; the reasoning below is **design reasoning to be tested**, not expert endorsement. Real, paid, independent review is Phase 0's first obligation ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)).

---

## 1. The eight design principles

These are the load-bearing principles that the architecture was built from. These principles are not ranked by number. Where two conflict in practice, the conflict is published as an open design question and decided under the amendment rules in [01_Governance_Model.md](01_Governance_Model.md) §4c; C3 (capture-resistance) and C6 (human decision rights) are binding constraints on any such decision.

| # | Principle | Certainty |
|---|---|---|
| C1 | The case for a transitional architecture is a structural mismatch between institutions built for scarce information and labor-based value, and the conditions now emerging; it does not depend on any particular AI timeline | `[STRONG]` |
| C2 | The design must work, and do no harm, even if machine intelligence never surpasses human intelligence | `[STRONG]` |
| C3 | Capture-resistance is a first-order requirement, co-equal with capability | `[STRONG]` |
| C4 | The ledger records provenance, not truth; it is the substrate of deliberation, not an oracle | `[STRONG]` |
| C5 | Consent stays universal and equal; what is upgraded is the deliberative layer that produces the options | `[STRONG]` |
| C6 | Humans retain decision rights until the capability, safety and legitimacy gates have all opened, and even then transfer is staged and reversible | `[STRONG]` |
| C7 | The economic floor is unconditional transition infrastructure | `[STRONG]` |
| C8 | Deployment is municipality-first; legitimacy is built by demonstrated integrity at small stakes before large stakes | `[STRONG]` |

## 2. The reasoning behind the major choices

**Why a transition architecture at all (C1, C2).** Many institutions fail at long-horizon problems (climate, debt, biosphere) because short-horizon selection pressures such as elections and quarterly reports defeat long-horizon decisions. Automation and an engagement-driven information economy add to that strain. Forecasting superintelligence is an exercise in humility, so the design is conditional: if the transition arrives, the Bridge governs the handover; if it does not, what remains is a transparent, capture-resistant deliberation infrastructure. The burden of proof is on the designer: attempts to replace messy democratic processes with a purportedly rational design have repeatedly ended in failure or tyranny, which is why every AI-augmented power is paired with a human counterweight that can act without the AI's cooperation.

**Why capture-resistance is a first-order requirement (C3).** The record of "technocratic upgrades" to democracy includes many cases of capture. The design should be expected to face sophisticated capture machinery, including automated persuasion, synthetic media and bot-driven consensus manufacturing. Hence sortition rotation before any appointment window closes, sealed Guardian identities, multi-vendor AI, and an immune system that is itself computational.

**Why the ledger is provenance, not truth (C4).** A blockchain guarantees that a claim, its author, its timestamp and its evidence chain are as recorded; it cannot guarantee the claim is correct. A ledger of lies is an immutable ledger of lies. If citizens learned "on-chain means true", the ledger would become a propaganda instrument. Truth is approximated by a contestable, human grading process, and the system must institutionalize doubt, never claim certainty.

**Why universal ratification plus a better deliberative layer (C5).** The evidence suggests the problem is not equality but information and process ([02_Evidence_Base.md](02_Evidence_Base.md), Pillar 3). Keeping the franchise universal and upgrading what is put before voters gives a better menu, not a smaller electorate. Every decision above a materiality threshold faces a universal ratification vote.

**Why multi-model moderation with human override.** Current frontier models can hallucinate, agree sycophantically with users, and reason inconsistently under adversarial questioning. Independent models from different vendors must therefore agree before output is treated as settled, human moderators can override any decision, every prompt and output is logged, and independence is measured, not assumed ([04_Technical_Specification.md](04_Technical_Specification.md) §3). At least one model family must be open-weight so that citizens can run their own verification.

**Why an unconditional Floor with a rising Target (C7).** An unconditional income decouples a decent life from labor status, which otherwise manufactures mass precarity in a transition. It must be backed by real revenue (automation dividend, compute taxes, licensing fees), never by token issuance. The Floor is binding from the first payment; the Target is a commitment that rises with revenue, because promising a high income before the revenue exists would be a fiscal fiction.

**Why gates with an independent evaluator (C6).** Any gate that can be passed by a capability demonstration alone will be passed by a lab that wants it passed. Safety certification must be financially and institutionally independent of the labs, or the gates are decoration. Hence the independent evaluation institute (L3) is built during the transition, before any handover question is live.

**Why municipal-first (C8).** A municipality can adopt the deliberation protocol for one decision, with a public ledger and results published win or lose. Legitimacy comes from demonstrated integrity in small stakes. Civic education is a core budget line, because without it the mechanisms decay into theater without informed consent.

**Why a founder sunset.** A project that cannot survive its founder is an extension of the founder's will. Founder powers expire by statute and code at a fixed date; succession runs on sortition; every founder act is on-ledger.

## 3. Alternatives considered and rejected

| Alternative | Why it was rejected |
|---|---|
| Ledger as truth oracle ("on-chain = true") | Provenance is not veracity; creates an unaccountable epistemic authority |
| Permanent civic scores ("karma") | Sybil and gaming problems; converts into influence and violates no-hoarding; replaced by per-deliberation credentials |
| Quadratic voting as the core mechanism | Prices intensity, but its cash-like markets are capture-prone |
| Liquid democracy as the core mechanism | Fielded deployments show delegated votes concentrating in a few super-delegates |
| Single-vendor civic AI | A single point of failure and of capture |
| Single-chain anchoring | Single-chain capture, technical or social; replaced by ≥2 chains with a migration path |
| Emergency powers without sunset | The standard ratchet by which crises concentrate power; every emergency power expires in at most 90 days unless renewed by a sortition assembly (never by the body that declared it) |
| Founder veto after the sunset | Reintroduces a permanent single point of capture |
| Income floor funded by issuance or borrowing against future gains | A fiat scheme with extra steps; the floor must be claimable in real goods and services |
| Dissolution by a single bare majority | Exposes the protocol to a drive-by vote; replaced by two successive universal ballots with an assembly deliberation between them |
| Voting by telling an operator one's choice (phone, clerk) | Destroys ballot secrecy by definition; replaced by private booth paper ballots and assisted voting |
| Self-certification of AI by vendors | The fox grades the henhouse |

## 4. What would change our minds

Each part of the case has a falsifier. The protocol commits to publishing the results either way.

- **Transition case:** if long-horizon governance performance of existing institutions improves materially without structural change, the case weakens.
- **Ledger as substrate:** if fielded deliberation-on-ledger experiments show no knowledge gain over standard briefing, the substrate design is revisited.
- **Deliberative core:** if sortition cohorts under real load systematically underperform elected bodies on measured decision quality, or if three consecutive pilots fail to produce slates that ratifiers judge legitimate and informed, the deliberative core is falsified.
- **Economic floor:** if displacement stabilizes and net employment holds through the generative-AI decade, floor sizing shrinks and caps become viable. If, over a 10-year window, aggregate employment-to-population ratios in advanced economies remain stable and wage polarization narrows without any deliberate UHI or dividend policy, the urgency claim is falsified and the L4 sunset-and-review is brought forward to consider retiring UHI.
- **Gates and evaluation:** if independent safety evaluation proves systematically gameable in field tests, the gates must be redesigned before any transfer, not after.
- **Vulnerability mitigations:** if any mitigation in the vulnerability ledger ([01_Governance_Model.md](01_Governance_Model.md) §8) fails in a pilot, the pilot halts and the vulnerable mechanism is revisited before scaling.
- **Information diet:** if attention-market-free information channels fail to improve measured voter knowledge or trust in controlled municipal trials, that thesis is falsified and Organ 1 is re-opened ([02_Evidence_Base.md](02_Evidence_Base.md)).

## 5. Research agenda for the open questions

The seven open questions in [01_Governance_Model.md](01_Governance_Model.md) §10 each have an interim rule. This is what it would take to replace each interim rule with evidence.

| # | Question | Research needed |
|---|---|---|
| 1 | Decentralized evidence grading | Field experiment comparing a centralized grading body with rotating sortition graders on contest-overturn rate, cost and time; adversarial cross-examination protocols |
| 2 | UHI funding caps and sizing | Independent fiscal modeling under three displacement scenarios; calibration of the dividend rate, stabilizer cap and Floor basket per jurisdiction |
| 3 | Proof-of-personhood without exclusion | Comparative study of registry-based and cryptographic personhood systems against exclusion risk; measured exclusion rates in the pilot |
| 4 | Legal recognition of ledger records | Legal analysis in each adopting jurisdiction; test cases with notarized copies |
| 5 | Manipulability of supermajority thresholds | Simulation and field audit of Sybil, coercion and turnout manipulation at scale |
| 6 | Conflicting adoptions across jurisdictions | Design and test of joint-cohort procedures with the first cross-jurisdiction decision |
| 7 | Refusal branch under a race dynamic | International-law and security research on verification and collective response; treaty-readiness work |

## 6. Honest limits of this record

The reasoning above was produced by the authors of the design, with AI assistance, and can therefore flatter the design that produced it. The mitigations are binding constraints on the architecture, but whether they are adequate is exactly what Phase 0's real, paid, adversarial review must test. Nothing here should be read as expert approval.

*Next: return to [00_README.md](00_README.md).*

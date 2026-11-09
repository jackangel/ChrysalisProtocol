# 04 · Technical Specification — The Chrysalis Stack

**Status:** Edition 1.0 · November 2026 · Public consultation edition
**Scope:** The technical architecture for the protocol's infrastructure: voting, ledger, multi-model deliberation, cryptographic sortition, wish intake, the objective function, and the technical budget.

**Provenance:** Every specification below implements the governance model in [01_Governance_Model.md](01_Governance_Model.md) and the legal instruments in [03_Proposed_Laws.md](03_Proposed_Laws.md). This document is the *how*, not the *what*. It is a design specification for independent review and audit; no component has yet been built or audited.

---

## 1. The Voting Stack

### 1.1 Requirements

The ratification vote must be:
- **Secret:** no observer can link a vote to a voter.
- **Verifiable:** each voter can verify their vote was counted correctly.
- **Tallied:** the aggregate result is publicly verifiable without revealing individual votes.
- **On-ledger:** the aggregate result and the proof of correct counting publish on the public ledger ([01_Governance_Model.md](01_Governance_Model.md), Organ 2).
- **Offline-capable:** a voter who cannot access the digital channel can vote on paper in a private booth, with assistance if needed (a required term of the adoption statute; §1.4).
- **Receipt-free and coercion-mitigated:** a receipt proves that a ballot was included, never what it contained, so a ballot cannot be sold or demanded as proof (§1.4). Residual coercion risk in the unsupervised digital channel is stated in §1.4.

### 1.2 Scheme: End-to-End Verifiable Secret Ballot (E2EV-SB)

The voting stack is based on **end-to-end verifiable secret ballot** — a cryptographic protocol in which:
- Each voter's ballot is encrypted and added to a public tally.
- The aggregate result is computed by a set of **tallying servers** (≥3, independently operated).
- Each voter receives a **receipt** (a cryptographic commitment) that proves their ballot was included in the tally, without revealing the vote's content.
- The **tally is publicly auditable**: anyone can verify, from published proofs, that the aggregate result matches the decrypted ballots, without learning any individual vote.

**Specific protocol:** the stack uses a **mix-net** (also called a **shuffle encryption** scheme):
1. Each voter encrypts their ballot under the public key of the tallying servers.
2. The encrypted ballots are **shuffled** (re-ordered) by the tallying servers in a verifiable way (each server publishes a permutation proof).
3. The servers jointly **decrypt** the shuffled ballots and publish the aggregate tally.
4. Each voter can check: (a) their receipt shows their encrypted ballot is in the input list, (b) the permutation proofs are valid, (c) the aggregate tally matches the decrypted ballots.

**Why a mix-net:** verifiable mix-nets are a well-studied class of secret-ballot protocols with published security proofs and open-source reference implementations. Their track record in binding public elections is limited, and independent audits of deployed e-voting systems have found implementation flaws; the specification therefore makes independent cryptographic and software audit a precondition for any binding use (§7.4), and the pilot is advisory-first. A mix-net provides:
- **Privacy:** the shuffle breaks the link between voter and ballot.
- **Verifiability:** the permutation proofs are publicly checkable.
- **Simplicity:** the cryptographic operations are well-understood (ElGamal encryption, Pedersen commitments, zero-knowledge proofs for the shuffle).

**Not a homomorphic scheme:** homomorphic encryption (e.g., Paillier) is an alternative, but a mix-net is preferred here because:
- It is simpler to explain to non-technical voters and auditors.
- The shuffle step breaks the order of ballots, not just their content.
- Verification is simpler for a non-technical voter (check the permutation, check the tally).

The choice is provisional: the independent audit (§7.4) may recommend a different verifiable scheme, and the interface in §1.1 does not depend on the scheme.

### 1.3 Tallying Infrastructure

- **≥3 independently operated tallying servers** (no single point of failure; no single vendor).
- Servers are operated by: (a) the protocol's legal person ([01_Governance_Model.md](01_Governance_Model.md) §4c), (b) an independent civil society organization, (c) a public university.
- Server software is **open-source** and **auditable**: the code is published, the cryptographic parameters are published, and the servers' behavior is logged on-ledger.
- **Failover:** the decryption key is shared among the servers with a 2-of-3 threshold, so any two servers can decrypt. All available servers shuffle in sequence, each publishing a permutation proof; if one server is unavailable, the remaining two shuffle. Because any two servers can decrypt, ballot privacy requires that fewer than two of the three servers are corrupt or colluding, so the three servers must be run by three independent operators. Operating with fewer than three servers is published on-ledger and triggers an operational review.
- **Audit:** a **per-decision audit** (V3 mitigation) samples a subset of ballots (recommended: 10%) and verifies the full chain: ballot → shuffle → decryption → tally. The audit is published on-ledger.

### 1.4 Offline Channels

For voters who cannot or prefer not to use the digital channel, the protocol provides channels in which **no human ever learns or enters the voter's choice**:
- **Paper ballot in a private booth:** the voter marks a paper ballot alone in a booth at a civic office. A scanner at the office encrypts the choice, adds it to the mix-net, and does not retain the plaintext. The paper ballot is kept in a sealed box for a risk-limiting audit. The voter's receipt is a tracking code that proves inclusion of an encrypted ballot but cannot reveal its content.
- **Assisted voting:** a voter who cannot mark a ballot unaided is assisted by a person of their choice or by two civic-office staff members acting together; the assistant is bound by a secrecy duty, and the fact (not the content) of assistance is logged.
- **Mobile voting team:** for housebound voters, a team of two staff members from different organizations brings the same booth-and-scanner kit to the voter.

**Removed by design:** voting by telling an operator or clerk one's choice (by phone or in person) is not offered, because it destroys ballot secrecy by definition.

**Re-voting.** A voter may cast several ballots; only the last counts, and in-person ballots override digital ones. This limits coercion and vote-selling in the unsupervised digital channel, which retains a residual coercion risk that the protocol states openly.

All channels feed the same mix-net: the offline channel is not a separate system, only a different input device.

### 1.5 Budget Impact

The voting stack is the **single most expensive technical component** of the protocol. A production-grade mix-net deployment (including cryptographic audit, server infrastructure, offline channel integration, and per-decision audit tooling) is estimated at:
- **MVP (one municipality, ~10,000 residents):** €150k–€300k (one-time) + €20k–€40k/year (operation).
- **National scale (~10M residents):** €1M–€3M (one-time) + €200k–€500k/year (operation).

This is the largest single technical line. The consolidated budget, and how it is funded, is in [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §5; the component estimates are in §7 below.

---

## 2. The Ledger Data Model

### 2.1 Architecture: On-Chain / Off-Chain Split

The ledger is **not** a monolithic chain. It is a **two-layer architecture**:

**On-chain (public, immutable):**
- **Anchors:** a hash of the off-chain data block, published on ≥2 independent public chains ([01_Governance_Model.md](01_Governance_Model.md), Organ 2). The anchor is a single transaction per data block.
- **Aggregate results:** ratification vote results, sortition draw results, gate assessment results, emergency declarations.
- **Provenance metadata:** who claimed what, when, on what evidence (the metadata, not the full transcript).
- **Proofs:** cryptographic proofs of correct counting (voting), correct sortition (draw), correct grading (evidence).

**Off-chain (public, mutable, full-fidelity):**
- **Full deliberation transcripts** (with layered disclosure: sealed by default, released passage by passage under the k-anonymity rule in [01_Governance_Model.md](01_Governance_Model.md), Organ 2, layered disclosure).
- **Full evidence chains** (the documents, the grades, the contests).
- **Full model prompts/responses** (civic AI logs).
- **Full budget lines** (every cent).
- **Full wish stream** (pseudonymized, pre-AI-processing).

The off-chain data is **public** (anyone can read it) except for the sealed portions of transcripts under layered disclosure, and **mutable** (it can be updated, corrected, annotated). Its integrity is guaranteed by the on-chain anchor: the hash of each off-chain data block is on-chain, so any tampering with the off-chain data is detectable.

### 2.2 Data Model (Off-Chain)

The off-chain data is organized into **collections**, each with a defined schema:

| Collection | Schema (key fields) | Access |
|---|---|---|
| `deliberations` | `id`, `domain`, `cohort_id`, `start_date`, `end_date`, `slate`, `minority_reports`, `transcript_hash`, `evidence_grades` | Public (transcript sealed until k-anonymity) |
| `votes` | `id`, `deliberation_id`, `result`, `participation_rate`, `proof_hash`, `audit_sample_hash` | Public (aggregate only; individual votes never on-chain) |
| `sortitions` | `id`, `purpose`, `pool_size`, `draw_size`, `stratification`, `rng_seed`, `draw_result_hash` | Public |
| `wishes` | `id`, `date`, `domain`, `text` (pseudonymized), `status` (acknowledged/addressed/contested) | Public (pseudonymized) |
| `evidence` | `id`, `claim`, `grade`, `author`, `timestamp`, `source`, `contest_status` | Public |
| `model_logs` | `id`, `model_family`, `prompt_hash`, `response_hash`, `deliberation_id`, `certification_id` | Public |
| `budgets` | `id`, `line_item`, `amount`, `date`, `approval_id` | Public |
| `emergencies` | `id`, `declaration`, `scope`, `duration`, `expiry`, `renewal_status` | Public |
| `gates` | `id`, `gate_number`, `domain`, `assessment`, `result`, `criteria_pass_fail` | Public |
| `refusals` | `id`, `domain`, `date`, `result`, `legal_instrument_id` | Public |

### 2.3 Provenance Encoding

Every on-chain anchor encodes the **provenance chain** for the off-chain data it protects:
- **Who:** the pseudonymous credential of the actor (deliberator, voter, grader, model).
- **What:** the hash of the data block.
- **When:** the timestamp (block height on the anchoring chain).
- **On what evidence:** for evidence-graded claims, the hash of the source document.
- **By what process:** the process identifier (e.g., "deliberation DL-2026-003", "sortition draw SD-2026-014").

The provenance chain is **tamper-evident**: any modification to the off-chain data changes the hash, which breaks the on-chain anchor. The public can verify the chain by: (a) hashing the off-chain data, (b) comparing to the on-chain anchor, (c) checking the provenance metadata.

### 2.4 Anchoring Mechanism

- **≥2 independent public chains**: e.g., a major L2 + an independent L1, or two independent L1s.
- **Anchor frequency:** one anchor per off-chain data block, published within 24 hours of the data block's creation.
- **Migration procedure (V4):** if a chain is compromised, the protocol migrates to a new chain. The migration requires: (a) a public hearing, (b) sortition assembly approval, (c) a 90-day transition period during which both chains are anchored.
- **Concentration threshold:** if >30% of the anchoring volume goes to a single chain, a public hearing is triggered (V4 mitigation).

### 2.5 Budget Impact

The ledger infrastructure (off-chain storage, on-chain anchoring, provenance tooling, audit tooling) is estimated at:
- **MVP (one municipality):** €50k–€100k (one-time) + €10k–€20k/year.
- **National scale:** €500k–€1M (one-time) + €100k–€200k/year.

---

## 3. The Multi-Model Deliberation Protocol

### 3.1 Why the moderation rule needs a specification

The governance model ([01_Governance_Model.md](01_Governance_Model.md), Organ 1) says deliberation is moderated by ≥3 independent AI models from different vendors. A rule that simply says "the models agree" is not implementable until it defines:
- what "agree" means: procedural handling is a taxonomy, not a single yes/no;
- what is being moderated: the categories of procedural handling;
- the agreement rule: what threshold of agreement is sufficient;
- the decorrelation metric: how to measure that the models are actually independent.

The following sections define each.

### 3.2 The Moderation Taxonomy

The multi-model moderation produces a **moderation decision** for each statement in the deliberation record. The moderation decision is one of:

| Decision | Meaning |
|---|---|
| `ADMIT` | The statement is admitted to the civic record as-is. |
| `ADMIT_WITH_GRADE` | The statement is admitted together with the evidence grade (A/B/C/D) assigned by the rotating human graders; the models only check that the grade is attached. |
| `CHALLENGE` | A model flags the statement for human review (for example because it cannot settle its procedural handling); a human moderator must review. |
| `REJECT` | The statement is rejected: it violates a procedural rule (e.g., ungraded claim in a final slate, off-topic, defamatory). |

The **moderation taxonomy** is:
- **Procedural rules** (what the models check): that load-bearing claims carry an evidence grade (assigned by human graders, never by the models), topic relevance, defamatory content, procedural fairness (e.g., a speaker is cut off).
- **Not political rules** (what the models do NOT check): the political content of the statement, the quality of the argument, the desirability of the position.

The models moderate **procedure**, not **politics**: the AI moderates, the humans decide.

### 3.3 The Agreement Rule

- **3/3 agreement:** if all three models produce the same moderation decision and it is not `CHALLENGE`, the decision takes effect without prior human review. It is published on-ledger, a random sample (recommended: 10%) is audited by human moderators, and any participant may appeal it to a human moderator, whose decision is final. Human moderators can override any AI decision (Organ 1).
- **2/3 agreement:** if two models agree and one disagrees, the decision is **provisional** — a human moderator reviews and makes the final call. The human moderator's decision is published on-ledger with the models' disagreement noted.
- **No majority (all three differ):** the statement goes to **human-only moderation**. The human moderator's decision is final.

The agreement rule is a **consensus rule**, not a supermajority: the threshold for taking effect without prior human review is unanimity (3/3); anything less triggers human review. This is the mechanism by which the multi-model system is a **check** on each model, not a **replacement** for human judgment. With more than three families, the same rule applies to the unanimity of all active families.

### 3.4 Decorrelation Metric

The decorrelation of the ≥3 model families is measured by:
- **Pairwise error correlation:** for a published test suite (≥1000 procedural moderation scenarios), the correlation of errors between each pair of models. **Pass:** |ρ| < 0.3. **Warning band:** 0.3 ≤ |ρ| ≤ 0.5 — a remediation plan (re-prompting, replacing the family, or adding a family) is published within 90 days. **Fail:** |ρ| > 0.5 — the pair does not count as independent until remediated, and a function may not run with fewer than three counted-independent families.
- **Dissent rate:** the fraction of scenarios where the models disagree (any pair). **Pass:** 10–40%. **Warning band:** 5–10% or 40–60%, with the same 90-day remediation rule. **Fail:** below 5% (the models are too similar to be a check) or above 60% (the models are too different to be useful).
- **Objective-diversity probes:** a published battery of adversarial prompts in which agreement between families could reflect a shared mistaken objective rather than independent judgment; the families' responses are compared, and clusters of identical behavior across all families are reported. The open-weight family's reasoning on these probes is published.
- **Audit frequency:** all three measures at least **annually** ([01_Governance_Model.md](01_Governance_Model.md), Charter item 9) and on every significant model version change, with results published on-ledger.

The decorrelation metric is the mechanism by which the "≥3 independent model families" requirement is **enforced**, not just stated.

### 3.5 The Interaction Protocol

The three models do **not** see each other's outputs during deliberation. They each process the input independently:
1. Each model receives the same input: the statement, the procedural rules, the evidence context.
2. Each model produces a moderation decision (from the taxonomy above).
3. The decisions are compared by the **agreement rule** (§3.3).
4. If unanimous (3/3) and not `CHALLENGE`, the decision takes effect subject to audit and appeal; otherwise (including a unanimous `CHALLENGE`), human review.

The models do **not** debate, do **not** see each other's reasoning, and do **not** iterate. They are **independent judges**, not a deliberating committee. This is the mechanism by which the multi-model system provides a check without creating a new single point of failure (a committee of models would be a new organ, with its own capture risk).

### 3.6 Budget Impact

The multi-model moderation system (≥3 model deployments, moderation taxonomy, agreement rule engine, decorrelation audit tooling, human moderator workflow) is estimated at:
- **MVP (one municipality):** €50k–€100k (one-time) + €20k–€50k/year (model API costs + moderator compensation).
- **National scale:** €300k–€800k (one-time) + €200k–€500k/year.

---

## 4. Cryptographic Sortition

### 4.1 Requirements

The sortition draw must be:
- **Unbiased:** every eligible person has an equal probability of selection (subject to stratification).
- **Verifiable:** the public can verify that the draw was fair, without revealing the identities of the selected persons before the draw.
- **Tamper-evident:** any manipulation of the draw is detectable.
- **Stratified:** the draw is stratified by age, gender, region, education, and income ([01_Governance_Model.md](01_Governance_Model.md), Organ 1). Because education and income are rarely recorded in a population register, stratification uses census-linked attributes and area-level proxies, with over-sampling of under-represented strata; stratification targets and the data sources used are published before the draw.

### 4.2 Mechanism: Commitment, Public Randomness, Verifiable Ranking

The sortition uses a **commitment** to the draw's inputs, a **public randomness beacon** that nobody controls, and a **verifiable ranking function**:

1. **Commitment phase:**
   - The protocol's legal person publishes, on-ledger, a **commitment** (a hash) to the eligible-population list, the stratification parameters, the draw size, the replacement rule, and the **future time** at which the randomness will be taken.
   - Because the seed does not yet exist, nobody can choose the list or parameters to favor a particular outcome ("grinding").

2. **Randomness phase:**
   - At the pre-announced time, the seed is computed as `seed = H(commitment ‖ beacon outputs)`, where the beacon outputs are values from (a) a threshold-signature public randomness beacon run by an independent consortium (e.g., drand) and (b) the hash of a block on each anchoring chain at the pre-announced height. A single beacon failing or being biased does not determine the seed; the draw fails safe (is repeated with a new announced time) if any beacon is unavailable.

3. **Draw execution:**
   - Each eligible person's draw key is a **verifiable random function** (VRF) output over `seed ‖ credential`, computed with the registry's key, together with a proof. The standard construction is ECVRF (RFC 9381); no custom cryptography is used.
   - Within each stratum, the persons with the lowest keys are selected. Anyone with the public key can verify every proof and recompute the ranking.

4. **Stratification and replacement:**
   - The population is divided into strata (age × gender × region, plus education and income via census-linked or area-level proxies).
   - The draw selects from each stratum proportionally to its size, **over-sampling** to allow for declines (an acceptance rate of at least 65% is targeted for assemblies; the rate achieved is published). Declining or ineligible persons are replaced by the next-ranked person **in the same stratum**, never by choice of an administrator.
   - Stratification parameters and any census data used are published on-ledger.

5. **Verification:**
   - The commitment, the beacon values, the seed, the VRF proofs, and the selected pseudonymous credentials are published on-ledger.
   - Auditors (under seal where personal data is involved) can check the population list against the census frame; any citizen can recompute the ranking from the published values.
   - The **identities** of the selected persons are sealed from the public; only the pseudonymous credentials are published. Selected persons are contacted directly by the registry.

### 4.3 Why a Verifiable Draw, Not a Simple RNG

A simple RNG (e.g., `random.choice`) is not verifiable: the public cannot check that it was not manipulated. In this design, the commitment fixes the inputs, the beacon supplies randomness that the legal person cannot choose, and the VRF proofs let anyone check that the ranking follows from the seed. Together these make the draw **tamper-evident** without requiring a trusted third party. The remaining trust assumptions are stated openly: the population list must be complete (checked against the census frame), and the beacons must not collude.

**Implementation:** ECVRF (RFC 9381) and threshold-signature randomness beacons are standardized or openly specified and have multiple open-source implementations; the specific implementation is selected and audited in Phase 0 (§8).

### 4.4 Budget Impact

The sortition system (VRF implementation, stratification engine, commitment-reveal protocol, verification tooling) is estimated at:
- **MVP (one municipality):** €20k–€50k (one-time) + €5k–€10k/year.
- **National scale:** €100k–€300k (one-time) + €20k–€50k/year.

---

## 5. The Wish Intake System

### 5.1 Requirements

The wish intake system ([01_Governance_Model.md](01_Governance_Model.md) §3c) must be:
- **Direct:** wishes are entered by citizens, not through AI mediation.
- **Multi-channel:** digital, paper, phone, in-person (wishes, unlike votes, may be dictated to staff, who record the words verbatim and read them back).
- **Pseudonymized:** the wish is linked to a pseudonymous credential, not a named identity.
- **On-ledger:** the raw wish stream is published (pseudonymized) before any AI processing.
- **Acknowledgeable:** the system tracks the acknowledgment status of each wish.

### 5.2 Architecture

The wish intake system is a **separate technical component** from the AI cohort's analysis system ([01_Governance_Model.md](01_Governance_Model.md) §3c). It is:
- A **form-based intake** (web form, paper form, phone line, in-person) that writes wishes to the off-chain ledger.
- A **status tracker** that records: wish entered → acknowledged → incorporated into deliberation → addressed in slate.
- A **contest interface** that allows any citizen to file a wish-contest with the Guardians.

The wish intake system does **not** itself summarize, cluster, or reframe wishes: it is a **pass-through**, and the citizen's words go into the ledger unaltered. The AI cohort's analysis begins only after the raw wishes are published. Any AI clustering or summary is published as a **labelled proposal alongside the raw stream**, never in place of it, and any citizen can contest it ([01_Governance_Model.md](01_Governance_Model.md) §3c). At scale the raw stream is searchable and filterable by the public.

### 5.3 Budget Impact

The wish intake system (form-based intake, status tracker, contest interface, multi-channel integration) is estimated at:
- **MVP (one municipality):** €10k–€30k (one-time) + €5k–€10k/year.
- **National scale:** €50k–€150k (one-time) + €20k–€50k/year.

---

## 6. The Objective Function Specification

### 6.1 Requirements

The objective function ([01_Governance_Model.md](01_Governance_Model.md) §3c) must be:
- **Published:** the full text of the objective function is on-ledger.
- **Set by sortition assembly:** not by the AI, not by the founder, not by a technical team. Until the first assembly has set it, a provisional minimal function (Charter item 11 in [01_Governance_Model.md](01_Governance_Model.md), Organ 2b) applies and the pilot is advisory-only.
- **Contestable:** any citizen can file a contest.
- **Formal:** a decision rule, not a value system.

### 6.2 Specification

The objective function is a **formal document** with the following structure:
1. **Optimization target:** what the system optimizes for (e.g., "maximize the minimum Universal High Income level").
2. **Binding constraints:** what is not permitted (e.g., "no decision that reduces UHI below the published floor").
3. **Permitted trade-offs:** what trade-offs are allowed (e.g., "short-term economic cost is permissible if long-term UHI level improves").
4. **Evaluation metric:** how the system's performance is measured (e.g., "the UHI level, adjusted for cost-of-living, published quarterly").
5. **Revision schedule:** when the objective function is revisited (every 7 years, matching L4's sunset).

The objective function is **not** a philosophical statement. It is a **decision rule**: a formal specification sufficient to evaluate AI proposals without requiring the AI to "understand" human values.

### 6.3 Budget Impact

The objective function specification (drafting, sortition assembly process, publication, contest interface) is estimated at:
- **MVP (one municipality):** €5k–€15k (one-time) + €5k/year.
- **National scale:** €20k–€50k (one-time) + €10k–€20k/year.

---

## 7. The Technical Budget and Engineering Strategy

### 7.1 Lean Integration vs. Bespoke Re-Invention

A critical engineering decision governs the Chrysalis technical stack: **we do not re-invent battle-tested cryptographic primitives from scratch.** 

Ground-up development of custom electronic voting schemes, novel blockchain consensus layers, or proprietary random beacons would cost millions and introduce massive attack surfaces. Instead, Chrysalis operates as an **orchestration harness** that binds together existing, formally audited, open-source building blocks:
- **Verifiable Randomness:** Integrating public threshold beacons (e.g. `drand` League of Entropy) and ECVRF (RFC 9381).
- **Verifiable Voting:** Adapting open-source end-to-end verifiable voting architectures (e.g. ElectionGuard, Helios) rather than rolling custom zero-knowledge mix-nets.
- **Tamper-Proof Ledger:** Utilizing established, high-security public Layer-2 rollups (e.g. Arbitrum, Base) anchored to Ethereum L1 and decentralized storage (IPFS/Arweave).
- **Multi-Model Moderation:** Building a containerized API orchestration harness that interfaces with ≥3 independent foundation model APIs (plus open-weight models like Llama/Mistral running on secure cloud instances).

By adopting this lean integration strategy, **the core reference stack can be engineered for approximately €100,000**, with **€80,000 dedicated to an aggressive, open adversarial red-team challenge and bug bounty program** to prove the system cannot be attacked or corrupted.

### 7.2 Core Reference Stack Budget (Phase 0–1)

| Component | Engineering Strategy | One-time Cost | Annual Operations |
|---|---|---|---|
| Core Protocol Harness & API Integration | Integrating sortition, wish-intake, and multi-model AI moderation | €40,000 | €15,000 |
| Verifiable Voting & Sortition Engine | Adapter for drand VRF + open-source E2EV-SB voting stack | €35,000 | €10,000 |
| Dual-Chain Ledger Anchoring | Smart contracts for dual-chain state commitments and proof verification | €25,000 | €10,000 |
| **Engineering Subtotal** | **Core Reference Stack** | **€100,000** | **€35,000/year** |
| Adversarial Red-Team Challenge & Bounty | Paid bug bounty & penetration audits to prove anti-corruption | €80,000 | — |
| **Total Phase 0 Security & Stack** | | **€180,000** | **€35,000/year** |

### 7.3 National & Federation Scale (Phase 2–3)

As sovereign nations and federations adopt the protocol, high-throughput dedicated infrastructure (sovereign validator nodes, federated multi-region mix-nets, dedicated hardware security modules) will be funded out of sovereign technology budgets rather than non-profit crowdfunding. Estimated infrastructure costs at full sovereign scale range from €1M to €3M in capital expenditure, absorbed by adopting state budgets.

### 7.4 Phase 0 Deliverable: Proving the System Unattackable

The engineering priority of Phase 0 is not merely writing code, but **proving the anti-capture properties under adversarial conditions**:
- **Simulated Bribery & Extortion:** Verifying that sealed Guardian identities cannot be inferred from ledger metadata.
- **Randomness Manipulation Attacks:** Verifying that no collusion of actors can predict or bias sortition lottery outcomes.
- **AI Prompt Injection & Vendor Collusion:** Verifying that adversarial attempts to bias deliberation options through coordinated prompt injections are caught and flagged by rival models and human overseers.
- **Sybil Resistance:** Verifying that zero-knowledge identity credentials prevent multi-voting or fake citizen generation.
- Objective function (drafted, published)

**Deferred (national scale, 3–5 years):**
- National-scale voting stack (multi-region, federated)
- National-scale ledger (multi-chain, high-throughput)
- National-scale multi-model moderation (federated, multi-region)
- National-scale sortition (large population, complex stratification)
- National-scale wish intake (multi-channel, high-volume)

The MVP is **advisory-first** ([01_Governance_Model.md](01_Governance_Model.md) §9): it advises, not decides, in the first year. The national scale is a **Phase 3** effort (years 3–5, [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §2), funded by the public budgets of adopting jurisdictions, not by crowdfunding. Before any binding use, the voting stack, the sortition and the ledger must pass an independent cryptographic and software audit, and a public bug-bounty period must have run.

### 7.5 How the MVP Is Funded

The MVP technical stack is one line of the consolidated year-one budget in [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §5; campaign structures are maintained outside this thesis.
- The one-time MVP cost (**€285k–€595k**) is funded by crowdfunding, grants and municipal co-funding; if funding falls short, the scope is reduced (reusing existing audited open-source components) rather than corners cut on audit.
- The annual operating cost (**€65k–€135k**) is carried by the adopting municipality.
- The national scale is funded by adopting jurisdictions, not by crowdfunding.

The MVP is the proof-of-concept that demonstrates the protocol at scale zero, not the entire protocol.

---

## 8. Open Technical Questions

1. **Voting stack vendor:** the mix-net implementation is open-source, but the specific cryptographic library needs to be selected and audited (or a different verifiable scheme chosen on audit advice). This is a Phase 0 task.
2. **Ledger chain selection:** the ≥2 independent public chains need to be selected. The L2 + L1 combination is a design choice, not a technical necessity. This is a Phase 0 task.
3. **Model family selection:** the ≥3 independent model families need to be selected, including at least one open-weight family. The constraint is independence (different vendors, different training data, different architectures), measured per §3.4. This is a Phase 0 task.
4. **VRF and beacon implementation:** ECVRF (RFC 9381) and a threshold-signature randomness beacon are the recommended constructions; the specific implementations (e.g., a Rust crate, a Go library) need to be selected and audited. This is a Phase 0 task.
5. **Offline channel security:** the booth-and-scanner design (§1.4) needs a full security model: scanner firmware integrity, receipt design (inclusion without content), and chain-of-custody for the sealed paper ballots. This is a Phase 0 task.

---

*Next: [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) — the phased plan and the consolidated budget.*

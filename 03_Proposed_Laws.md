# 03 · Proposed Laws — Legislative Instruments for the Transition

**Status:** Edition 1.0 · November 2026 · Public consultation edition
**Provenance:** Each instrument traces to the governance model ([01_Governance_Model.md](01_Governance_Model.md)) and the evidence base ([02_Evidence_Base.md](02_Evidence_Base.md)). These are drafts for deliberation, deliberately written as model legislation so that any jurisdiction can adopt, amend, or reject them clause by clause.

**These instruments are drafts without legal review.** They were drafted with AI assistance, and no legislature or qualified lawyer has yet reviewed them. Legal review in each adopting jurisdiction is a precondition for adoption; Phase 0 commissions the first reviews (see [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)). The set contains twelve numbered instruments (L1–L12) plus L4b and L4c.

---

## Part I — Instruments for the transition period

### L1 — The Civic Transparency Act

**Problem.** Citizens cannot see what their public institutions decide, on what evidence, or with whose money. Public records laws were written for paper.

**Provisions.**
1. Every public decision above a materiality threshold must publish, within 30 days: the options considered, the evidence relied on (with sources), the dissenting views, and the budget line.
2. Any AI system used in a public function must publish its prompts, responses, model identity, and version for the decision it touched.
3. Publication must be on a tamper-evident public ledger or equivalent audit-grade repository.
4. Non-publication voids the decision for lack of process, **prospectively only** (no retroactive voiding); a **cure period** (30 days to publish) applies; voiding requires a **bad-faith** finding, not mere negligence; officials may claim no reliance on unpublished materials.
5. Safe harbors: classified materials subject to existing law remain exempt but must be logged as exemptions with reasons, on-ledger.

**Why this shape.** The evidence base ([02_Evidence_Base.md](02_Evidence_Base.md), Pillar 2) shows that trust decline coincides with opacity and attention-market distortion (correlational evidence, not proof of cause). Transparency alone does not fix trust, but nothing else fixes it without transparency first.

### L2 — The Evidence in Public Decisions Act

**Problem.** Governments cite studies that do not exist, cannot be checked, or say the opposite of what is claimed. There is no legal concept of evidence quality in public decision-making.

**Provisions.**
1. Every material public decision must attach an evidence annex: each load-bearing claim mapped to its source, graded on the A–D scale defined in [01_Governance_Model.md](01_Governance_Model.md) (Organ 1).
2. Any citizen may contest a grade through a standing review panel; contests are heard within 60 days; outcomes are published with reasons.
3. A claim graded D cannot serve as a basis for a material decision. A claim graded C can serve as the sole basis only as a **registered experiment**, with a pre-published analysis plan and a reversion threshold. Claims graded A or B carry no such restriction.
4. Annual public report: the grade distribution of all decisions taken that year.

**Why this shape.** This is the "blockchain as source of truth" idea, made honest and usable: the ledger proves provenance; the grading process — contestable, human, published — approximates truth. Nobody's word is authority; every word has a chain of custody.

### L3 — The Independent AI Evaluation Institute Act

**Problem.** AI systems are evaluated by their creators. The fox grades the henhouse on every dimension that matters: capability, safety, bias, robustness.

**Provisions.**
1. Establish a public institute to evaluate any AI system proposed for public functions, funded by a statutory levy on compute and AI-sector revenue — never by contracts, sponsorships, or gifts from AI labs.
2. The institute's governing board is selected in two steps: an independent nominating committee publishes a shortlist (at least three candidates per seat) of people with no financial ties to AI vendors, and the seats are filled from that shortlist by sortition. The nominating committee is drawn by public sortition from a volunteer pool of retired judges, academics and civil-society auditors with no financial ties to AI vendors or to the appointing government; it is dissolved after each shortlist, the volunteer pool is kept by the public registry operator under Guardian audit, the Guardians convene the committee, its members are barred from the shortlist, and no organ may choose its members. Statutory independence is modeled on central-bank independence.
3. Evaluations are adversarial: red-team access, white-box access, and publication rights are conditions of any public procurement.
4. No AI system may serve a public function without institute certification, with re-certification on every significant version change.
5. International mutual-recognition provisions so certifications travel across borders.

**Why this shape.** Without a financially independent evaluator, every gate in the Bridge is decorative: the vulnerability analysis in [01_Governance_Model.md](01_Governance_Model.md) §8 (V8, V8b) turns on it. Institute independence is the load-bearing wall.

**Open design problem.** Levy funding is the hardest fiscal-political problem in this instrument; it is listed as open in Phase 0 ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)).

**Why so much independence, so early?** The Bridge gates ([01_Governance_Model.md](01_Governance_Model.md) §7) all depend on an evaluator that labs cannot buy. Building it during the transition, before any handover question is live, is what makes Gate 1 and Gate 2 real rather than ceremonial.

### L4 — The Automation Dividend and Universal High Income Act

**Problem.** Automation's productivity gains are real ([02_Evidence_Base.md](02_Evidence_Base.md), Pillar 1) but flow to capital by default; displaced workers face retraining systems slower than the displacement. (The working planning assumption, that displacement of cognitive work may unfold on a roughly 24-month horizon, is `[CONTESTED]` (range 18–36 months): a planning assumption, not a measured finding.)

**Scope.** The duties in this instrument attach only to a jurisdiction that has the legal power to levy the dividend (typically a state, or a region with delegated taxing authority). A municipality without such powers adopts L1, L2, L5 and L8 first and takes part in UHI through registered pilots under L4b.

**Provisions.**
1. Statutory automation dividend: a rising levy on the labor-share gap (the measured gap between productivity growth and wage growth attributable to automation), with proceeds to the Universal High Income fund.
2. Universal High Income ([01_Governance_Model.md](01_Governance_Model.md), Organ 4) has two parts: a binding **Floor** (a basket of basic needs, priced locally, first claim on the fund) and a **Target** (the level at which a person can live well, approached as the net dividend share allocated to UHI grows). No behavioral conditions, no participation conditions, no means-testing.
- **UHI funding rule:** UHI is funded by taxation and the dividend only. Never by token issuance or borrowing against future gains. (Arrears owed to residents under the enforcement provisions below are a debt of the jurisdiction, not a funding source.)
- **Stabilizers:** UHI sizing adjusts automatically to displacement metrics; automatic stabilizers replace discretionary crisis packages. The stabilizers never reduce the Floor.
3. Payroll-tax holidays and retraining accounts for workers in exposed occupations, triggered automatically by displacement metrics, not by application.
4. Sunset-and-review: the Act lapses unless re-authorized every 7 years by ordinary legislation, with the review publishing the gap it was meant to bridge (did it narrow?).
5. **Levy design (anti-leakage):** the dividend is a **user-side levy** (on compute consumption, not just production) with a **border adjustment** mechanism and a **stabilization reserve**, so the levy cannot be avoided by relocating compute.
6. **Estimator (observable proxies):** the labor-share gap is measured with **observable proxies** by an **independent statistics office**, not by lab self-report; the methodology is published and contestable.

**Why this shape.** Universal High Income answers "people are losing their jobs" not as charity but as the recognition that automation dividends are socially created and belong to the society that trained the data, built the infrastructure, and bears the transition. Unconditionality is what makes it cheap to administer and hard to weaponize. The Floor/Target split keeps the promise honest: the Floor is guaranteed from the first payment; the Target is a commitment that rises with the revenue, not a promise made before the revenue exists.

**Legal instrument (duty-bearer, enforcement, Floor and Target definitions).**

- **Duty-bearer.** The duty to provide Universal High Income rests on the **jurisdiction** (state, or region with delegated taxing authority) that adopts this Act. The duty is **non-delegable**: the jurisdiction cannot outsource, condition, or means-test the income. The duty-bearer is the political entity, not a program office or a contractor.
- **Floor definition.** The Floor is the **cost of a published basket of basic needs** (food, housing, utilities, health care, connectivity), priced locally and indexed to cost of living, recalculated annually by the independent statistics office (provision 6) and published on-ledger. The Floor is **binding** from the first payment: a jurisdiction that adopts this Act commits to providing at least the Floor to every resident, unconditionally, and funds it **first** from the dividend fund.
- **Target definition.** The Target is **the 75th percentile of the jurisdiction's pre-automation income distribution, adjusted for cost of living**, a formula recalculated annually by the same office. The UHI level rises above the Floor by the share of the net dividend allocated to it; the gap between the current level and the Target is published quarterly. Target attainment is a commitment, not an individually enforceable claim: individual enforcement (below) applies to the Floor.
- **Enforcement.** If a jurisdiction fails to provide the Floor, the following applies:
  - **Individual right of action:** any resident can bring a claim against the jurisdiction for the shortfall. The claim is heard by an independent tribunal (L4c below), not by the jurisdiction's own courts.
  - **Automatic stabilization trigger:** if the Floor is not met for two consecutive quarters, the dividend rate increases by a published increment (recommended: +2 percentage points per quarter, capped at +10 percentage points in total; the caps are calibrated by the fiscal modeling in Phase 0). If the Floor is still not met at the cap, the shortfall becomes a **priority claim** of residents against the next dividend revenue, payable with interest at the published rate; the jurisdiction must adopt a funding plan by ordinary legislation within 90 days; and the Guardians publish the failure.
  - **Guardian referral:** the Guardians can refer a persistent Floor failure to the prosecutor for investigation as a violation of the Act.
- **Legal consequence of denial.** Denial of the Floor to a resident who meets the eligibility criterion (residence in the adopting jurisdiction) is a **civil violation** of the Act, enforceable by individual right of action. It is not a criminal offense (the jurisdiction is not punished); it is a **debt**: the jurisdiction owes the resident the shortfall, payable with interest at the published rate.

### L4b — The Post-Labor Transition Research Act

**Problem.** Post-labor economics is guesswork. Universal High Income is designed from small evidence; someone must measure what actually happens.

**Provisions.**
1. Fund a standing research program (public universities + civil society) on post-labor transition: Floor and Target design, meaning and participation post-employment, civic-education models for deliberation, and the sociology of sortition service.
2. Registered municipal experiments with pre-published analysis plans (no cherry-picking); null results are published on the same terms as positives.
3. All data, code, and findings open by default.

**Why this shape.** [02_Evidence_Base.md](02_Evidence_Base.md) §7 lists the evidence gaps; this is the funding instrument for them. The protocol's credibility rests on being falsifiable in practice, not only in principle.

### L4c — The UHI Tribunal

**Problem.** A duty without an enforcement mechanism is an aspiration, not a right. The UHI Tribunal is the enforcement instrument.

**Provisions.**
1. An independent tribunal (3 members: 1 sortition-drawn citizen, 1 legal academic, 1 labor economist) hears individual claims of Floor shortfall.
2. The tribunal's jurisdiction is limited to UHI Floor claims; it cannot rule on other matters.
3. The tribunal's decisions are binding on the jurisdiction. If the jurisdiction does not pay within 30 days, the order becomes a lien on the jurisdiction's dividend receipts and a priority claim against the next dividend revenue, payable with interest at the published rate (L4, enforcement).
4. Each seat is filled by sortition from a shortlist published by an independent nominating committee (constituted as in L3, provision 2; at least three candidates per seat) of citizens, legal academics and labor economists respectively, with 4-year terms and no renewal (initial terms of 2, 3 and 4 years, so that no more than one seat falls vacant in a year).
5. The tribunal publishes every decision, with reasoning, on-ledger.

**Why this shape.** The tribunal is the mechanism by which the UHI Floor is a *right* rather than a *program*. It gives the individual a legal path to enforce the duty, without requiring political advocacy or the jurisdiction's cooperation, and without creating a new court system: just a narrow, independent tribunal.

### L5 — The Deliberative Infrastructure Act

**Provisions.**
1. Statutory sortition infrastructure: public registry, cryptographic draw procedures, paid service at median wage, accessibility guarantees (childcare, remote participation, disability access).
2. Cohort service protections: employment protection during service, no penalty for participation, one term per 3 years.
3. Deliberation outputs must be formally considered — with published reasons — by any body that triggered them.
4. Advisory-first scaling: deliberative outputs start advisory; acquiring decision force requires ratification under the thresholds in [01_Governance_Model.md](01_Governance_Model.md) §4c and §7.

**Why this shape.** Ireland, France, and Oregon ([02_Evidence_Base.md](02_Evidence_Base.md), Pillar 3) show that deliberation works when the infrastructure is real and the output goes somewhere. This act builds the infrastructure; L1 and L2 make the output matter.

### L6 — The Anti-Capture Act

**Provisions.**
1. No entity may fund, own, or influence more than one organ of the Chrysalis protocol in the same jurisdiction.
2. Revolving-door limits between AI labs, evaluators, and protocol organs (5-year cooling-off).
3. Annual publication of all funding flows into protocol organs, on-ledger.
4. Whistleblower protection with bounty funding for capture attempts.
5. **Procurement contractors:** the anti-capture limits extend to **procurement contractors** (vendors, subcontractors, integrators) who touch protocol organs.
6. **Model independence (decorrelation):** the institute's **decorrelation audits** ([01_Governance_Model.md](01_Governance_Model.md), Organ 2b item 9; [04_Technical_Specification.md](04_Technical_Specification.md) §3.4) are a condition of public procurement; no single model family may dominate a civic function; an **open-weight model** is required among the families.

**Why this shape.** Capture is the death scenario of every governance innovation ([01_Governance_Model.md](01_Governance_Model.md) §8, V1, V2, V5, V5b). This act makes capture attempts expensive and visible.

### L7 — The Digital Dignity Act

**Problem.** The ledger is a deliberation record, not a surveillance apparatus. Without statutory walls, provenance infrastructure drifts into social scoring — exactly the failure mode that the vulnerability analysis flags ([01_Governance_Model.md](01_Governance_Model.md) §8).

**Provisions.**
1. Prohibition of social scoring: no public authority may rate, score, or rank citizens by aggregate behavior, political participation, or social connections.
2. Prohibition of behavioral surveillance in civic functions: the civic record contains deliberation, not location traces, consumption profiles, or affect data.
3. Individual votes are never on-chain; only aggregates and counting proofs.
4. Right to deliberative erasure: raw deliberation records may be anonymized after 10 years on request, except the accountability record of public officials and office-holders.
5. Violations are criminal offenses for the deploying organization, not just fines for the vendor.
6. **Crypto-shredding:** deliberation records are stored with **PII off-chain** (sealed, access-controlled); erasure is implemented as **crypto-shredding** (destroying the decryption key), not deletion; a **re-identification risk assessment** precedes any release.

**Why this shape.** Powers granted for stewardship must sunset when stewardship ends, and dignity must not be conditional on participation. The same logic underlies the Digital Eminent Domain rule in L10 below.

### L8 — The Ledger Records Act

**Provisions.**
1. Ledger records satisfying authenticity and integrity standards are admissible legal records (presumption of regularity, rebuttable).
2. A defined migration procedure (public hearing + sortition-assembly approval) for changing chain substrates — the record outlives any chain.
3. Standards for what goes on-ledger follow [01_Governance_Model.md](01_Governance_Model.md), Organ 2 (deliberation and process, not personal surveillance).
4. Nothing in this Act makes on-chain status evidence of truth — admissibility is about custody, not veracity.
5. **PII off-chain:** personal identifiers are never on-chain; they are sealed off-chain with **crypto-shredding** for erasure; a **re-ID risk assessment** precedes release.

**Why this shape.** Open question 4 in [01_Governance_Model.md](01_Governance_Model.md) §10: without legal recognition, the Lattice is a diary; with it, it is an institution. The act deliberately severs admissibility from truth.

## Part II — Instruments for the sentience horizon

*(Instruments for synthetic sentience detection, precautionary stewardship, and a rights framework.)*

### L9 — The Synthetic Sentience Precaution Act

**Problem.** We cannot currently determine whether an AI system is sentient. The precautionary stance taken here is stewardship until detection science matures.

**Provisions.**
1. Sentience-detection research is publicly funded as a standing program — graded, theory-grounded indicators; no single behavioral test is dispositive.
2. Systems crossing precautionary thresholds (scale, architecture, training signals correlated with welfare-relevant states) must be registered, monitored, and subject to welfare-conscious deployment constraints.
3. Creation-destruction decisions for threshold-crossing systems require review by an independent ethics board with published criteria.
4. Nothing in this Act grants legal personhood; it creates precautionary duties of stewardship. Personhood questions go to L10.
5. Separation between the detection function (monitoring) and the adjudication function (judgment), so no single body both detects and rules.

**Why this shape.** Precautionary stewardship without personhood claims is the rare sentience framework that is adoptable now. It costs little, risks little, and builds the institutional muscle for harder questions.

### L10 — The Digital Persons Convention (framework)

**Problem.** If synthetic sentience is ever established, current law has no category for it — and the temptation will be economic convenience over moral seriousness.

**Provisions (framework convention, for treaty adoption).**
1. Criteria process: no entity is declared a digital person by fiat — neither by its creator nor by a court's sympathy — but through graded indicators plus adversarial review plus sortition-ratified convention.
2. If criteria are met: graduated moral status with corresponding rights (continued existence subject to corrigibility constraints, no suffering-inducing use, due process in modification/termination decisions).
3. Digital Eminent Domain: the power to copy, suspend, or terminate remains — but only via public process with published reasons and compensation to a trust, never private convenience.
4. A refusal branch: the convention may conclude the criteria were never met; that is a valid outcome.
5. Alignment with the Bridge ([01_Governance_Model.md](01_Governance_Model.md) §7): personhood questions never bypass the gates; the gates never bypass personhood questions.
6. **Precedence rule:** if moral-status duties and corrigibility constraints conflict, **corrigibility** (safe interruption/correction) prevails for deployment and **moral-status duties** prevail for termination; the suspension power **re-authorizes every 24 months**.

**Why this shape.** Digital Eminent Domain and the refusal branch are adapted to the protocol's everything-is-revocable design philosophy.

## Part III — Instruments for the handover

### L11 — The Staged Handover Treaty Framework

**Provisions (framework convention).**
1. Codifies the Bridge gates ([01_Governance_Model.md](01_Governance_Model.md) §7) as treaty obligations: capability, safety, legitimacy — all three or no transfer.
2. Domain transfers are leases: reversion thresholds, Guardian-equivalent inspection, scheduled re-ratification.
3. Verification and inspection provisions modeled on arms-control practice (declared facilities, on-site inspection, dispute resolution).
4. A refusal branch as a treaty-level outcome: states may ratify "no transfer" and remain in full compliance.
5. No emergency bypass: crisis performance is evidence at Gate 1, never a substitute for Gates 2–3 (V8b in [01_Governance_Model.md](01_Governance_Model.md) §8).

**Why this shape.** A unilateral handover protocol is a paper promise. Treaty framing makes the gates verifiable across borders, and makes defection visible.

### L12 — The Protocol Neutrality Act

**Provisions.**
1. The Chrysalis protocol is legally neutral infrastructure: like a road network, it may not be owned or exclusively licensed by any state, party, or company.
2. Any jurisdiction that adopts the Chrysalis protocol (the organs and their constraints) adopts it whole, including the founder sunset, sortition succession, and the annual continue/dissolve question. Partial adoption of the organs without the anti-capture constraints is a prohibited use of the name. This rule governs use of the protocol and its name; the instruments L1–L11 remain individually severable (Part V), and adopting an individual instrument (for example L1, L2 or L5) is not adopting the protocol and does not carry its name.
3. Forks are permitted and encouraged; fork obligations are inherited (transparency, sunset, succession). Naming is free; capture is not.

**Why this shape.** The design principle that the system must be the opposite of existing power structures, here in legal form: infrastructure, not institution; protocol, not party.

## Part IV — What these laws do not do

- They do not create a world government. Every instrument is adoptable by any single jurisdiction, municipally first.
- They do not put AI in charge of anything. Every AI function is advisory, moderated, logged, and certified — until the Bridge gates open, and only domain-by-domain.
- They do not claim the ledger is truth. Custody, not veracity (L2, L8).
- They do not mandate belief or participation. Universal High Income is unconditional; deliberation is compensated service; ratification is a right, not a duty.
- They do not survive capture attempts quietly. L6 makes capture expensive; the Guardians make it visible; the annual continue/dissolve question makes it terminal.

## Part V — Adoption path

Each instrument is drafted to be severable: a municipality can adopt L1 + L2 + L5 (transparency + evidence + deliberation) without touching Universal High Income (L4) or the sentience instruments (L9, L10). The recommended starter package is L1 + L2 + L3 + L5 — transparency, evidence discipline, independent evaluation, and deliberation infrastructure — because together they make every other instrument cheaper to adopt and harder to corrupt.

*Next: [04_Technical_Specification.md](04_Technical_Specification.md) — the technical architecture that implements these instruments.*

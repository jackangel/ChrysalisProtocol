# 01 · The Chrysalis Governance Model — The Architecture of the Transition

**Status:** Edition 1.0 · November 2026 · Public consultation edition
**Provenance:** This is the binding architecture of the protocol. The reasoning behind each major choice, the alternatives rejected, and the conditions that would change our minds are in [07_Design_Rationale.md](07_Design_Rationale.md). Certainty labels follow [02_Evidence_Base.md](02_Evidence_Base.md).

---

## 1. The Core Dilemma

Human civilization faces a historic trap. As machine intelligence accelerates, every existing form of governance is being forced to choose between two vital requirements that seem impossible to reconcile:

1. **Democratic Control:** Collective decisions must remain authentically human, transparent, and revocable by the people who live under them.
2. **Technical Competence:** Collective decisions must match the speed, complexity, and scale of a world where cognitive work is being automated, energy demands are surging, and the ripple effects of errors are planetary.

Every traditional system fails this test:
- **Representative democracies** aggregate public preferences through periodic elections, but they were never designed to *elevate the knowledge* of what gets aggregated. They are easily captured by dark money, algorithmic polarization, and 24-hour rage cycles. In practice, their policy choices drift toward whatever sensational narrative captures the median voter's feed.
- **Autocracies and technocracies** decide quickly, but they fail silently. They lack error-correction, treat human citizens as cattle, and depend on the whims of fragile, paranoid leadership.
- **Unfettered markets** allocate resources brilliantly in the immediate quarter, but they are blind to generational catastrophes, ecological depletion, and the catastrophic externalities of replacing human labor.

None of these systems was engineered for a world where cognitive power can be cloned at near-zero marginal cost. Left to their defaults, our existing institutions will either surrender sovereignty to private tech oligarchs or collapse into paralyzed dysfunction.

Chrysalis is a **transitional architecture**: a modular upgrade layer that any town, city, or sovereign region can adopt voluntarily. It uses artificial intelligence to digest technical complexity and expand civic foresight, while **keeping sovereign voting power firmly in the hands of ordinary human citizens**. 

Crucially, **Chrysalis is explicitly built to be a temporary bridge—not a permanent constitution**. It operates during the narrow, perilous historical window between current vulnerable human systems and the advent of Artificial Superintelligence (ASI). Once genuine ASI emerges across all cognitive, scientific, and physical domains, human-administered governance will inevitably be superseded: a post-human system (99% to 100% operated by aligned, verifiable superintelligence) will be required to manage planetary complexity and post-scarcity logistics. The sole constitutional purpose of Chrysalis is to ensure that humanity reaches that horizon safely, without falling into corporate servitude or authoritarian collapse, and that the ultimate ASI successor operates under human-ratified core principles.

**The Dual-World Guarantee:** The protocol is engineered to thrive whether transformative artificial superintelligence arrives in three years or not for three decades:
- If frontier AI advances rapidly toward ASI, Chrysalis provides the institutional armor to prevent corporate monopolization, guarantees an unconditional automation dividend, and establishes ironclad public gates for the ultimate transition to superintelligent administration.
- If machine intelligence plateaus, the protocol remains an extraordinarily effective civic innovation: a transparent, unbribable deliberation system that frees communities from partisan gridlock and guarantees an unconditional economic floor.

## 2. The five organs

Chrysalis consists of five organs, each pairing an AI function with a human counterweight that can act without the AI's cooperation:

```
                    ┌──────────────────────────┐
                    │   THE PEOPLE (ratifiers) │
                    │ universal, equal, secret │
                    │  consent at every gate    │
                    └────────────┬─────────────┘
                                 │ ratify / recall / reject
        ┌────────────────────────┼────────────────────────┐
        │                        │                        │
┌───────▼───────┐        ┌───────▼───────┐        ┌───────▼───────┐
│ 1. DELIBER-   │        │ 2. THE PUBLIC │        │ 3. THE        │
│    ATIVE CORE │◄──────►│    LEDGER     │◄──────►│    GUARDIANS  │
│ (sortition    │        │ (provenance,  │        │ (anti-capture │
│  cohorts + AI │        │  deliberation │        │  audit; sunset│
│  moderation)  │        │  substrate)   │        │  everything)  │
└───────┬───────┘        └───────┬───────┘        └───────┬───────┘
        │                        │                        │
        └────────────────────────┼────────────────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │ 4. UNIVERSAL HIGH INCOME │
                    │ (a high income for all,  │
                    │  funded by automation  │
                    │  dividend)              │
                    └────────────┬─────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │ 5. THE BRIDGE             │
                    │ (gated, staged, revocable │
                    │  handover protocol)       │
                    └──────────────────────────┘
```

*(Diagram note: the ASCII diagram above is illustrative. The binding text is the prose.)*

### Organ 1 — The Deliberative Core

**Function:** produce the best-possible-evidenced options slate for every material decision.

- **Sortition cohorts.** For each decision above a materiality threshold, a cohort of 100–500 citizens is drawn by cryptographic sortition, stratified by age, gender, region, education, and income, from the resident registry. Service is paid (at the median national wage), with childcare, accessibility, and remote-participation guarantees so that people on low incomes can serve.
- **Registry (census-linked).** The resident registry is linked to the **census frame**, with **acceptance targets** (the registry must reach a published coverage floor) and **over-sampling** of under-represented strata to correct for non-response.
- **Evidence-graded deliberation.** Every claim entering the deliberation record is bound on the ledger to its author, timestamp, and evidence chain, and graded on a public scale: `A` (meta-analysis / RCT / multiple independent replications), `B` (peer-reviewed single studies), `C` (expert judgment / modeling), `D` (testimony, anecdote, unverified). The cohort cannot cite ungraded claims in its final slate.
- **Multi-model adversarial moderation.** Deliberation is moderated by ≥3 independent AI models from different vendors. Moderation covers procedure only (relevance, civility, duplicates, abuse), never the politics of a statement. A procedural decision takes effect when the models agree; where they disagree it goes to a human moderator. Human moderators can override any AI moderation decision (human moderators are paid, rotating staff of the protocol's legal person, hired by open competition and audited by the Guardians; none sets the agenda or serves two consecutive cohorts); decisions on which all models agree are published, audited by random sample, and appealable by any participant. Every prompt and output is ledger-logged. At least one of the models is open-weight (Charter §2b.4).
- **Output.** The cohort publishes: a ranked options slate (max 5 options), the evidence grade of every load-bearing claim, minority reports (never suppressed), and the transcript, released under the layered-disclosure rule below.
- **Term limits.** One cohort term per citizen per 3 years; nobody can be re-seated within that window. There are no permanent scores (they create hoarding and caste dynamics; see §4). Instead, **per-deliberation credentials**: your credential is valid for the deliberation you were drawn for, then expires.

### Organ 2 — The Public Ledger ("The Lattice")

**Function:** the provenance backbone, the sensing layer, the intelligence interface, and the build layer that makes everything else auditable. People state their wishes and needs directly to the Lattice (§3c); the AI cohort does most of the analysis and proposes solutions to the citizenry, who decide. The Lattice is the live interface between human wishes and AI analysis, not only a record. It is also the build layer: the protocol's software and documents are developed in the open, with AI assistance, under human direction, and every artifact is published and contestable.

- **Provenance, not truth.** The ledger records who claimed what, when, on what evidence. It never declares what is true. "On-chain = true" is a prohibited claim within the system. Truth-approximation runs through the evidence-grading rules of Organ 1, which any citizen can contest.
- **Substrate.** Chain-agnostic by design: anchoring on ≥2 independent public chains (e.g., a major L2 plus an independent L1), with a defined migration procedure requiring public hearing and sortition-assembly approval (V4 mitigation). The protocol, not any chain, is the point of allegiance.
- **What goes on it.** Every deliberation transcript, every budget line, every model prompt/response in civic use, every grade and grade-contest, every emergency declaration and its expiry, every founder act, every succession draw, every gate assessment.
- **What does not.** Personal identities (pseudonymous credentials; identity proofs held by registries, not the chain); secret ballots (individual votes are never on-chain; only aggregated results and the proof of correct counting).
- **Privacy boundary.** The ledger records deliberation, not surveillance. No behavioral tracking, no social scoring — both are prohibited applications under the protocol (and see L7, [03_Proposed_Laws.md](03_Proposed_Laws.md)). Prohibition is enforced by the Guardians' audit rights and by the open-source codebase itself.
- **Layered disclosure (candor vs transparency).** Decisions, evidence grades, slates, minority reports and aggregate statistics are published immediately. Full deliberation transcripts are sealed by default: a passage is released only when it cannot be attributed to fewer than k possible speakers (k is fixed by the Phase 0 privacy review; the interim value is k = 10) or when its speaker chooses attribution, and always through a public summary layer first. Candor in deliberation requires some non-public space; the ledger's provenance backbone is preserved by the summary layer, not the raw transcript.

### Organ 2b — The Civic Model Charter (binding constraints on all civic AI)

All AI systems used in Chrysalis functions are bound by the Charter (this section). The core documents of this set (01 and 04) are the protocol constitution (§4c.4); the Charter is the part of it that governs civic AI.

1. **Multi-vendor:** ≥3 independent model families in every civic function; no single-vendor dependency.
2. **Open prompts, open logs:** every prompt and response in civic use is ledger-published.
3. **Safety-certified:** no model serves a civic function without certification from an evaluation body financially independent of AI labs (seeded in Phase 0, see [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §2 and L3). Until that institute can certify, the pilot uses a **provisional certification**: a published evaluation of each model by two third-party evaluators with no financial ties to its vendor (paid from budget line 2, with the contingency line as overflow), valid for a pilot or replication pilot only, until the institute (L3) can certify and recorded as `provisional` in the model log's `certification_id`.
4. **Open weights where inspection matters:** at least one of the ≥3 model families in every core civic function — including deliberation moderation — is open-weight, so that at least one family's behavior can be inspected and re-run by citizens. Narrow functions (transcription, translation, summarization) use open-weight models wherever feasible.
5. **Published evaluations:** model cards, behavioral evals, and audit trails published for every deployment; re-certification on every significant version change.
6. **Primary analytical role, human decision rights:** the AI cohort is the system's primary analytical capacity — it analyzes, optimizes, and proposes. Humans state their wishes and needs (the sensing layer, §3c) and hold every decision right through ratification. The AIs' recommendations are published on-ledger and contestable by any citizen. Decision rights remain with humans until, and unless, the Bridge gates open (§7).
7. **No dark deployment:** any use of civic AI not published on the ledger voids the decision it touched, on the terms of L1 provision 4 ([03_Proposed_Laws.md](03_Proposed_Laws.md)): prospectively only, after a 30-day cure period, and on a bad-faith finding.
8. **Corrigibility floor:** every civic model must remain subject to safe interruption and correction; a model that resists oversight fails certification, regardless of capability.
9. **Decorrelation audits & adversarial prompt framing:** pairwise error-correlation audits across the ≥3 model families, at least annually. The audit measures both error correlation and **objective diversity** — whether the families converge on the same behavior under adversarial probes, in which case their agreement is one opinion held three times and not a check. To guard against shared pre-training bias and monocultural convergence across frontier models, civic moderation prompts must mandate **adversarial prompt framing**: the model families must evaluate submissions through distinct epistemic and methodological priors (procedural/rule-bound, rights-protective/deontological, and welfare/utilitarian) before procedural consensus is scored. The open-weight family's reasoning is published so citizens can verify why the models agree. Thresholds and the remediation rule are in [04_Technical_Specification.md](04_Technical_Specification.md) §3.
10. **Sensing-layer independence:** the mechanism that captures human wishes is not controlled by, and not a function of, the mechanism that proposes solutions (§3c.2). A drift monitor (§7, transition safety architecture) tracks whether stated wishes shift systematically in response to AI-proposed options.
11. **Provisional objective function (bootstrap):** until an assembly (the first full assembly, or an earlier ad hoc assembly, §3) has set the objective function (§3c.3), the system's objective is the minimal one: keep humans in decision control; never reduce UHI below the Floor; make no irreversible step. That assembly ratifies or replaces it, and the pilot is advisory-only until it has done so.

### Organ 3 — The Guardians (anti-capture audit)

**Function:** the system's immune system.

- **Composition.** 21 members drawn by sortition from past cohort alumni (staggered 18-month terms, no renewal), plus a professional independent prosecutor (appointed by a 60% vote of a sortition assembly, removable by the same vote). Appointments use a **competitive shortlist** (for the 21 seats, drawn from eligible alumni; for the prosecutor, from open candidates; ≥3 candidates, publicly evaluated by an independent nominating committee constituted as in L3, provision 2) followed by **sortition confirmation** from the shortlist (the same two-step method as L3, provision 2). **Bootstrap:** until the jurisdiction has at least 21 eligible alumni, an interim body of 7 members is drawn by sortition from the public registry under the same exclusions and sealing rules (interim members serve until the full body takes over); the full 21-member body takes over as soon as the alumni pool allows, and no later than 12 months after the first full assembly convenes; if fewer than 21 eligible alumni exist by then, the interim 7 continue, the shortfall is published, and any vacancy is refilled by a new draw from the registry.
- **Anonymity (seal the watcher) & due process.** Guardian identities are sealed during the term; the public sees *what* the Guardians did (every action on-ledger), not *who* did it. The ledger records "Guardian #7 froze decision D-0003" — not a named person. The sortition process is auditable (RNG seed, algorithm, pool size published before the draw); the result is sealed. Identities are revealed at term end for the historical record and the next sortition's exclusion list. The prosecutor's identity is sealed on the same terms. Sealing applies strictly to the public to prevent intimidation, bribery, and targeted lobbying. It does not obstruct judicial due process: if a Guardian action is formally challenged in a court of competent jurisdiction or before the UHI Tribunal, the presiding judicial officer inspects the unsealed credential and conflict-of-interest disclosures *in camera* under protective order to verify eligibility and impartiality, while the Guardian's public anonymity remains shielded. **Why:** a named Guardian is an attack surface. Anonymity removes the "target the watcher" vector while *in camera* judicial inspection preserves constitutional accountability.
- **Powers.** Audit any organ; freeze any decision pending review; refer for prosecution; call a ratification vote on any matter, including "should this whole protocol continue?" (the recall path). A freeze requires a **stated cause within 72 hours**, lasts at most **30 days**, and if it lapses without resolution the decision **executes**.
- **Limits.** Guardians cannot originate policy, cannot spend, cannot veto policy content — only process and law. Every Guardian act is on-ledger. Any Guardian emergency power sunsets in ≤90 days (V6).
- **Rotation before capture.** No appointment window may close without rotation; no staggered bloc larger than one-third; no organ may confirm its own members (V1 mitigation).

### Organ 4 — Universal High Income (transitional economy)

**Function:** a *high* income for everyone, funded by the automation dividend. The dividend is the mechanism; Universal High Income (UHI) is the claim. UHI has two parts that must not be confused:

- **The Floor (binding from the first payment).** A guaranteed minimum, set by a published basket of basic needs (food, housing, utilities, health care, connectivity) priced locally and indexed to cost of living. The Floor is a legal duty, funded first from the dividend fund before any other use of it.
- **The Target (the commitment the Floor is climbing toward).** A level at which a person can live well, participate in society, and keep dignity and opportunity. The statutory target is the 75th percentile of the pre-automation income distribution, cost-of-living adjusted ([03_Proposed_Laws.md](03_Proposed_Laws.md), L4). Each year the UHI level rises above the Floor by the share of the net dividend allocated to it; the gap between the current level and the Target is published quarterly.

Both parts are unconditional: no behavior conditions, no participation conditions, no means-testing. A right, not a reward. UHI is not the Floor alone, and it is not promised at the Target on day one: promising the Target before the revenue exists would be a fiscal fiction.
- **Revenue-backed.** Funded by the automation dividend (see L4) — the gains from automation that currently flow to capital by default, redirected to the people whose labor was replaced. Compute taxes, licensing fees as secondary sources. Never by token issuance. Full public accounting on the ledger, every cent.
- **Two-Track Adoption Taxonomy:**
  - **Track A (Municipal / Civic Deliberation):** Designed for local governments and municipalities that lack sovereign macroeconomic levy powers. Adopters implement Organs 1 (Deliberative Core), 2 (The Lattice), and 3 (The Guardians), together with local participatory budgeting and registered localized pilot dividends (L4b), but without assuming sovereign UHI liabilities.
  - **Track B (Sovereign / Fiscal Polity):** Adopted by states, nations, or regional federations possessing statutory taxation and fiscal levy authority. Implements full Universal High Income: statutory Floor indexed to basic needs, automated dividend levies, and the climbing Target up to the 75th percentile.
- **Adaptive.** The income level responds to displacement metrics and cost-of-living indices via automatic stabilizers (L4). The Floor is never reduced by the stabilizers. If the Floor cannot be met from the dividend fund plus the capped stabilizer, the shortfall is a priority claim of residents against the next dividend revenue (paid with published interest), the jurisdiction must adopt a funding plan by ordinary legislation within 90 days, and the Guardians publish the failure. Numeric caps and sizing are calibrated by the fiscal modeling in Phase 0; the structure above holds regardless of the numbers.
- **Designed to shrink need.** The success metric is not "people survive" but "people live well" — the narrowing of the gap between the UHI level and what the labor market provides, published quarterly.

### Organ 5 — The Bridge (handover protocol)

**Function:** make the eventual handover deliberate, staged, revocable — or refuse it.

Detailed gates in §7. In one line each:

- **Gate structure.** Capability gate (public benchmarks, adversarial evaluations) → Safety gate (independent certification) → Legitimacy gate (supermajority ratification). All three or no transfer.
- **Staged domains.** Transfer happens one domain at a time (water systems before tax codes; streetlight optimization before criminal justice), each with a reversion threshold.
- **Revocability.** Any transferred domain reverts on Guardian petition plus a ratification vote that meets the Gate 3 turnout floor (50%) with a simple majority of ballots cast; a petition that fails to reach that turnout leaves the transfer in place. The protocol never treats a transfer as permanent.
- **Treaty-ready.** The Bridge's terms are drafted as a framework convention so states can adopt it as treaty text, with verification and inspection provisions.
- **The refusal branch.** Humanity can ratify "no transfer, ever" — that is a valid outcome of the protocol. The Bridge exists to make handover deliberate *or* deliberately refused. Either is success; default is the only failure.
- **Race-dynamics scope (honesty).** The Bridge does not claim to resolve inter-state races; its scope is treaty-readiness and verification. It funds verification R&D and maintains a collective-response menu (treaty adoption, cross-border arbitration, coordinated refusal) for when a race dynamic emerges.

## 3. How a decision flows

1. **Agenda.** Any citizen petition (threshold-signed) or any organ places an issue on the agenda. A petition is **threshold-signed** when it carries verified signatures from at least 1% of eligible ratifiers (a jurisdiction may set a lower figure). All agenda-setting is on-ledger. A threshold-signed petition triggers **mechanical scheduling**: the body that sets the agenda (the steward of the launch — the stewardship council if the founder is gone — before the first full assembly convenes, the sitting sortition assembly afterwards, or the Guardians when none is sitting) must place it on the agenda within 60 days or publish a reasoned refusal, which any citizen may contest before the Guardians.
2. **Cohort draw.** If material: cryptographic sortition draws the deliberation cohort; draw is publicly verifiable.
3. **Deliberation.** Evidence-graded, multi-model-moderated, transcribed, published. Minority reports are never suppressed; they are part of the slate.
4. **Slate to ratifiers.** The ranked options slate + evidence grades + minority reports go to the universal, equal, secret ratification vote (proof-of-personhood eligible, offline channels available). **Ordinary material decisions** pass by a simple majority of valid ballots cast, with turnout published; a decision decided on turnout below 25% of eligible ratifiers carries a published legitimacy flag and the Guardians may call a re-vote. Amendments, Bridge transfers, and dissolution use the stronger rules in §4c and §7. **Eligibility:** all residents at or above the minimum age set by the adopting jurisdiction's law (recommended: the local age of civic majority); residents below that age participate through the wish channel (§3c).
5. **Decision + audit.** Result and full audit trail publish to the ledger. Guardians may freeze pending process review. Decisions carry mandatory review dates.
6. **Review.** Every decision above materiality carries a scheduled review: did outcomes match forecasts? Mismatches feed the evidence base and future deliberation.
7. **The meta-decision.** Once per year, a standing question on every ballot: *Should this protocol continue?* The question is mandatory: it appears on the first ballot held in each calendar year, and no organ may omit it; if no ballot is otherwise scheduled, the Guardians must call one for it before the year ends. The question goes through the same deliberation and Guardian capture-risk assessment as any material decision (for a capture-triggered ballot, the Guardians' published assessment stands in for the cohort deliberation on the first ballot). A majority "no" (more than half of ballots cast, abstentions counted as cast) with at least 50% turnout opens an orderly sunset procedure, **with double confirmation**: a second universal ballot, held at least 30 days later (automatically 60 days after the first; the Guardians may move it once, by at most 30 days, with published reasons) and after a sortition assembly has deliberated on the question, must again return a majority "no" with at least 50% turnout. A single majority is not sufficient to dissolve, which protects against a drive-by vote; a supermajority is not required, because dissolution returns the jurisdiction to ordinary governance, the safe direction. If the second ballot returns "continue," the protocol continues and the result is published with the assembly's reasoning. The people can always fire the architecture itself.

**Materiality.** A decision is *material* if the adopting jurisdiction's adoption statute (the statute or ordinance by which it adopts the protocol, drafted from L5 and L12) classes it as material (by spending above a stated threshold or by its effect on binding rules) or if a threshold-signed petition under step 1 asks for it to be treated as material. Until the Phase 0 cost and capacity model supplies thresholds, the interim rule is: the decisions listed in the municipal partnership agreement signed in Phase 0 are material, and any other decision is material only if petitioned. A decision that is not material follows the jurisdiction's ordinary process and its own publication rules.

**Sortition assembly.** A body of up to 500 residents drawn by cryptographic sortition on the same rules as a cohort, convened for constitutional and oversight questions: appointing or removing the prosecutor, renewing or revoking emergencies, setting the objective function, reviewing amendments, authorizing ledger migration, and deliberating between the two dissolution ballots. An assembly sits for the duration of its question, at most 12 months. The **first full assembly** is the first one drawn after the founder handover, and it convenes no later than month 24 ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §3). Until it convenes, the steward of the launch (the stewardship council if the founder is gone) holds launch duties only, including the mechanical scheduling in step 1, and the legal wrapper's statutes cannot be amended. Any assembly-dependent power that falls due before then (renewing an emergency, authorizing a ledger migration, deliberating between dissolution ballots, appointing the prosecutor, setting the objective function) is exercised by an **ad hoc assembly** of 100 residents (fewer only if the funds on hand cannot pay 100, never below 50, with the shortfall published) drawn by the same sortition rules, convened by a majority of the sitting Guardians (interim or full) or by a threshold-signed citizen petition, paid from the contingency budget line once it is funded (if no funds can pay for 50 residents, the question waits, except a dissolution question, which is paid first from the legal person's remaining funds; the delay is published; an emergency in that position simply expires), and sitting only for the question put to it. Until a prosecutor is appointed, the Guardians publish their referrals and send them to the jurisdiction's ordinary prosecuting authority. After the first full assembly convenes, later assemblies are convened by a majority of the Guardians or by a threshold-signed citizen petition, and automatically when a deadline requires one: an emergency renewal falls due 14 days before the 90-day mark, and the deliberation between dissolution ballots is convened within 14 days of a first "no" ballot.

**Orderly sunset.** Each adopting jurisdiction has its own registry, electorate and ballots: a jurisdiction's dissolution ends the protocol in that jurisdiction only, and the shared legal person winds up only when no adopter remains. If the second dissolution ballot confirms, the protocol ends as follows. The Guardians publish a sunset plan within 30 days; the sitting assembly (or, if none sits, an ad hoc assembly) appoints a three-person liquidation panel by sortition from the public registry; the legal person's remaining assets go to the beneficiary named in its asset-lock statutes (a civic-education charity); the ledger is archived read-only, published, and its signing keys destroyed on-ledger; laws adopted under L1–L12 remain with the adopting jurisdiction to keep or repeal by its ordinary process; and the panel publishes a closing report. The Guardians' last act is to certify that each step happened.

## 3b. The Founder Rule

The founder (Manuel Barca-Grama) holds no special power under the protocol. During the bootstrap period (before the first full assembly convenes), the founder's single defined role is **steward of the launch**: publish this document set, open the objection protocol, procure and spend only per the published budget, draw the interim Guardians (Organ 3), convene the first full assembly, schedule petitions mechanically (§3, step 1), and hand over to the first sortition-drawn assembly no later than 24 months after the earlier of campaign close or legal-wrapper registration — at which point all founder roles auto-expire (the sunset clause, [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §3). Every founder act is on-ledger. If the founder dies or steps down earlier, the succession mechanism ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §4) activates automatically: a temporary stewardship council of 9 members, drawn by cryptographic sortition from the public registry, pending the first full assembly. There is no version of this protocol in which the founder is a permanent node.

## 3c. The Wish-Right Protocol

The "humans state their wishes and ratify" model is the load-bearing joint of the entire design. This section defines it as an operational mechanism, not an aspiration.

**1. The wish as a legally binding input.**

A **wish** is a citizen's stated need, preference, or constraint, entered into the Lattice through any channel (digital form, paper form, in-person at a civic office, phone line). A wish is **legally binding** in the following sense: once entered, it creates a **duty of response** on the AI cohort and the deliberative core. The AI cohort must:
- acknowledge the wish within a published time bound (recommended: 14 days for municipal scale);
- incorporate it into the next relevant deliberation cycle (it appears in the cohort's briefing pack);
- publish how the wish was addressed in the resulting options slate (the slate must state, for each material wish, whether it was adopted, modified, or rejected, and why).

A wish that is not acknowledged within the time bound, or that is acknowledged but not addressed in the resulting slate, is **contestable**: any citizen can file a **wish-contest** with the Guardians, who must publish a reasoned determination within 30 days. This is the mechanism by which a wish that is ignored becomes a legal event, not a silent dismissal.

**Denial-of-Service & capacity triage:** To prevent grievance flooding and bot-driven astroturfing, intake enforces a cryptographic rate limit (maximum 3 active wishes per resident per quarter). A wish creates an immediate public ledger acknowledgment, but to manage deliberative capacity without AI gatekeeping, wishes enter deliberation through a **two-tier docket triage**:
- *Direct docket:* Wishes reaching a modest resident co-sponsorship threshold (e.g., 0.1% of eligible ratifiers or 25 verified residents) trigger mandatory inclusion in the next cohort cycle.
- *Sortition docket:* Unendorsed wishes are reviewed by a randomly drawn mini-cohort of 15 citizens (rotating monthly) that batches and schedules them for civic relevance, ensuring non-popularized minority concerns are protected while preventing organized flooding from swamping cohort capacity.

**2. The sensing layer is independent of the intelligence layer.**

The AI cohort **cannot shape, filter, or frame the wishes** it receives. The sensing layer (wish intake) is a **separate technical component** from the intelligence layer (analysis and proposal):
- Wishes are entered **directly by citizens**, not through AI mediation. The raw wish stream is the primary record: the AI does not replace, edit, or reframe wishes, and nothing is dropped from it.
- At scale, wishes must be grouped to be deliberated. Grouping is done by the cohort's human moderators and the cohort itself. Where automated clustering assistance is used, the clustering model must be **deterministic, open-weight, and published on-chain with reproducible embedding hashes**. It is presented as a **labelled proposal placed alongside the raw stream, never instead of it**, and the cohort adopts, edits, or rejects it.
- **Orphan wish protection:** Any citizen whose wish was miscategorized, obscured, or dropped during clustering has a statutory right to file an **orphan-wish contest** before the human moderators, who must rule on its categorization before the deliberation pack is finalized.
- The AI's role begins **after** wishes are received: it analyzes them, identifies patterns, and proposes solutions. It does not decide what counts as a wish.
- The **frame** (the set of options presented to the cohort) is produced by the **cohort itself**, with AI assistance limited to evidence retrieval and option elaboration. The AI cannot add, remove, or reorder options unilaterally; it can *propose* options, and the cohort accepts or rejects them.
- This separation is enforced by the ledger: the raw wish stream is published (pseudonymized) on-ledger before any AI processing, so the public can verify that the frame was not manipulated. The options slate is composed by the cohort, and the model families used for option elaboration differ from the family used to compute the AI's own proposal where the pool of families allows.

**3. The objective function.**

The AI cohort optimizes toward a **published objective function**, not an internal one. The objective function is:
- **Set by a sortition assembly** (not by the AI, not by the founder, not by a technical team) at the founding of the protocol and at each 7-year re-authorization (matching L4's sunset cycle). **Bootstrap:** before the first assembly has met, the provisional objective function is the minimal one stated in the Charter: keep humans in decision control; never reduce UHI below the Floor; make no irreversible step. The first assembly ratifies or replaces it, and the pilot is advisory-only until it has done so.
- **Published on-ledger** in full, with the assembly's reasoning and any minority reports.
- **Contestable**: any citizen can file a contest against the objective function, triggering a new sortition assembly review.
- **Minimum content:** the objective function must state (a) what the system optimizes for (e.g., "maximize the minimum Universal High Income level subject to environmental constraints"), (b) what constraints are binding (e.g., "no decision that reduces Universal High Income below the published floor"), and (c) what trade-offs are permitted (e.g., "short-term economic cost is permissible if long-term Universal High Income level improves").
- The objective function is **not** a value system in the philosophical sense. It is a **decision rule**: a formal specification of what counts as a better outcome, sufficient to evaluate AI proposals without requiring the AI to "understand" human values.

**4. Ratification: approve, reject, amend.**

Ratification is **not** binary. The ratifier has three options:
- **Approve:** the proposal passes as-is.
- **Reject:** the proposal fails; the AI cohort must produce a revised proposal addressing the stated reasons for rejection.
- **Amend:** the ratifier proposes a specific modification (a clause, a parameter, a condition). **Procedure:** amendments may be filed during a published window before the vote; amendments that reach a signature threshold (recommended: 1% of eligible ratifiers) are placed on the ballot alongside the original text, and the Guardians check only that an amendment is coherent and lawful, never its merits. An amendment is **binding** if it wins the ratification vote. The AI cohort must then re-run its analysis with the amendment incorporated.

The amendment right is the mechanism by which human sovereignty is more than rubber-stamp: the human does not merely accept or reject the AI's output, but can **redirect it**. The amendment is published on-ledger with the ratifier's reasoning (pseudonymized), so the public can see *why* the human changed the AI's proposal.

**5. Persistent disagreement protocol.**

When the AI cohort's proposal and the human ratification diverge persistently (defined as: three consecutive ratification cycles on the same domain where the AI's proposal is rejected or amended in the same direction), a **disagreement review** is triggered:
- A new sortition assembly is drawn specifically to investigate the disagreement.
- The assembly's mandate: determine whether the objective function is mis-specified, whether the AI's analysis is flawed, or whether the human ratification is inconsistent with the objective function.
- The assembly publishes its determination on-ledger, with a recommendation. The recommendation is **advisory** (it does not override the ratifiers), but it triggers a re-deliberation cycle.
- This is the mechanism by which a persistent AI/human disagreement becomes a **governance event** rather than a silent drift.

**6. Worked example (municipal scale).**

A citizen enters a wish: *"I want the city to reduce traffic noise on Elm Street."*
- The wish is acknowledged within 14 days.
- The wish appears in the next traffic-planning deliberation's briefing pack.
- The AI cohort analyzes: traffic volume data, noise measurements, cost estimates for three options (traffic calming, road redesign, speed limits). It proposes a ranked slate: Option A (speed limit 30 km/h, cost €200k), Option B (road narrowing + green buffer, cost €800k), Option C (do nothing, cost €0).
- The cohort deliberates, produces its own ranked slate (which may differ from the AI's), publishes minority reports.
- The slate goes to ratification. A ratifier amends Option A: *"Speed limit 30 km/h, but with a 6-month trial period and a noise re-measurement before making it permanent."*
- The amendment passes. The AI cohort re-runs its analysis with the trial period incorporated. The final decision publishes on-ledger with the full chain: wish → acknowledgment → AI analysis → cohort slate → ratification amendment → final decision.

This is the protocol in operation: the wish is binding, the AI does the analysis, the human ratifies and amends, and the full chain is auditable.

## 4. What this system deliberately does not have

- **No permanent leaders.** Sortition, rotation, term limits, sunset clauses.
- **No permanent scores on citizens.** Per-deliberation credentials only: contribution is visible and consequential at the moment of deliberation, then expires. Permanence, hoarding, and decay mechanics were considered and rejected as capture-prone and incompatible with unconditional dignity.
- **No truth oracle.** Provenance and grading, never "on-chain = true."
- **No secret emergency powers.** All emergencies sunset ≤90 days and renew only via sortition assembly.
- **No single AI vendor.** Multi-model, multi-vendor, open-weights where feasible.
- **No irreversible step.** Every transfer is staged and reversible; the protocol's own dissolution is a built-in procedure.

## 4b. Addressing "democracy dilutes intelligence" honestly

The objection the architecture has to answer is that democracy dilutes intelligence. The claim is partly true and partly not, and the architecture reflects that:

- **What is true in it `[STRONG]`:** aggregating uninformed preferences produces low-quality outcomes; attention markets actively degrade the information reaching voters; one-person-one-vote on complex technical questions confuses equality of worth with equality of expertise.
- **What is not supported `[STRONG]`:** that citizens cannot reason well when given time, balanced evidence, and good process — the deliberation record (Fishkin; Oregon CIR; Ireland's assembly) shows the opposite.
- **The transformation:** Chrysalis does not replace democracy; it replaces the *information diet* of democracy. Equality stays (universal ratification); competence is added (evidence-graded deliberation producing the menu); the combination is designed to make collective intelligence additive, not averaged into dilution.

## 4c. Constitutional Machinery

The protocol is not just a governance architecture — it is a **legal instrument** that creates rights, imposes duties, and defines the relationship between the people, the organs, and the AI cohort. This section defines the constitutional machinery that makes it a legal reality, not an aspiration.

**1. The polity: who "the people" are.**

"The people" in this protocol means: **all residents of the adopting jurisdiction, regardless of nationality, immigration status, or citizenship.** The polity is defined by **residence**, not by citizenship. This is the mechanism by which the protocol avoids the exclusion problem: every resident at or above the minimum age (§3 step 4) is a ratifier, a wish-stater, and a potential sortition draw. The proof-of-personhood requirement (V3) defines eligibility for ratification, not for the polity itself. A person who cannot complete proof-of-personhood is **not excluded from the polity** — they are excluded from the *ratification vote* only, and the protocol mandates offline channels as the fallback (a required term of the adoption statute).

**2. Legal personality.**

The protocol, as adopted by a jurisdiction, creates a **legal person** — a body corporate that can:
- own property (the ledger infrastructure, the deliberation facilities);
- enter contracts (with AI vendors, with chains, with research institutions);
- be sued (by vendors for contract disputes; claims for UHI shortfalls lie against the jurisdiction, not against the legal person, see L4 and L4c);
- sue (for enforcement of the Act, for contract disputes);
- hold a bank account (the deliberation compensation fund);
- be a party to a treaty (the Bridge's treaty-ready provisions, L11).

The legal person is **distinct from the jurisdiction**: the municipality that adopts the protocol is not itself the legal person. The legal person is the protocol's institutional body — the entity that holds the ledger, operates the organs, and bears the organs' operational duties. The UHI duty is not among them: it rests on the jurisdiction (Organ 4; L4). This separation is what makes the protocol *adoptable* without merging the municipality's legal identity with the protocol's.

**3. Bill of rights (the positive rights behind the prohibitions).**

The protocol's prohibitions (§4: no permanent leaders, no permanent scores, no truth oracle, no secret emergency powers, no single AI vendor, no irreversible step) are **negative rights** — they say what the system must not do. Behind each prohibition is a **positive right**:

| Prohibition | Positive right |
|---|---|
| No permanent leaders | The right to be governed by persons selected by lot, subject to rotation and recall |
| No permanent scores | The right to participate in deliberation without a permanent record of one's civic standing |
| No truth oracle | The right to contest any evidence grade, with a published determination |
| No secret emergency powers | The right to know when an emergency is declared, what it changes, and when it expires |
| No single AI vendor | The right to have civic AI decisions moderated by ≥3 independent models |
| No irreversible step | The right to have any transferred domain reverted, on a published schedule |

These positive rights are **enforceable**: a violation of a positive right is contestable before the Guardians (for process violations) or before the UHI Tribunal (for UHI-specific violations), and is publishable on-ledger.

**4. Hierarchy of norms.**

The protocol's legal instruments form a hierarchy:

1. **The protocol constitution** (documents 01 and 04 of this set; the other documents explain or propose). It defines the organs, the rights, the duties, and the dissolution procedure.
2. **The L-series Acts** ([03_Proposed_Laws.md](03_Proposed_Laws.md)): the statutes. They implement the constitution's provisions as adoptable legal instruments.
3. **The objective function** (§3c): the decision rule. It is subordinate to the constitution and the Acts; it cannot override a right or a duty.
4. **The ledger records** (Organ 2): the evidence. They are the record of what was decided, by whom, on what evidence. They are subordinate to the constitution, the Acts, and the objective function.
5. **The AI cohort's proposals** (§3c): the recommendations. They are subordinate to everything above; they are inputs to the deliberation, not decisions.

A conflict between instruments is resolved by the hierarchy: the constitution overrides the Acts, the Acts override the objective function, and so on. A provision that violates a higher instrument is **void**.

**5. Amendment procedure.**

The protocol can be **modified** (not just dissolved). The amendment procedure is:
- **Initiation:** any citizen petition (threshold-signed) or any organ can propose an amendment.
- **Deliberation:** a sortition cohort deliberates the amendment, with evidence grading and multi-model moderation, and a sortition assembly reviews it for conflict with the entrenched provisions before the ballot.
- **Ratification:** the amendment goes to a universal, equal, secret ratification vote. It passes if turnout is at least 50% of eligible ratifiers **and** at least 60% of ballots cast are "yes" (abstentions count as ballots cast and are not consent). This is the same rule as Gate 3 (§7).
- **Publication:** the amendment publishes on-ledger with the full deliberation record.
- **Effective date:** the amendment takes effect 90 days after ratification, allowing for implementation.
- **Entrenched provisions.** The following cannot be removed or weakened by any amendment: human decision rights before the Bridge gates open, the refusal branch, the unconditional nature of UHI and the priority of the Floor, the founder sunset, sealing and rotation of the Guardians, the annual continue/dissolve question, and the rule that Gate 3 thresholds can be raised but never lowered (§7). They can only be changed by dissolving the protocol (§3 step 7) and re-adopting a new one.

The amendment procedure is **stricter than an ordinary decision** (60% yes with 50% turnout, against a simple majority) because it changes the protocol itself. Dissolution has a lower threshold per ballot (a majority) but needs two ballots with assembly deliberation between them, because ending the protocol is final while its direction, back to ordinary governance, is the safe one.

**6. Judicial review.**

The protocol provides for **judicial review** of its own organs' actions:
- **The Guardians** review process violations (procedural fairness, capture risk, emergency overreach).
- **The UHI Tribunal** reviews UHI-specific violations (floor failures, denial of income).
- **The sortition assembly** reviews constitutional questions (amendment proposals, objective function contests, persistent disagreement reviews).
- **The independent prosecutor** investigates and refers for prosecution (capture, corruption, violation of the Act).

There is no single "court" — the review function is **distributed** across the organs, matching the protocol's anti-concentration design. Each review body has a **narrow jurisdiction** (defined above) and a **published determination** (on-ledger).

**7. Emergency powers framework.**

The protocol's emergency powers are defined by **V6** (§8): all emergencies expire ≤90 days, renewal only by sortition assembly, declaring organ cannot renew itself. This section adds the **declaration criteria** and limits what an emergency may do: it may only freeze a decision or process, or suspend a scheduled deadline (such as a review date, never a re-ratification or reversion date), for no longer than the emergency lasts; it may not spend, legislate, change the Floor, or touch an entrenched provision. Declaration criteria:
- An emergency can be declared only by the **Guardians** (not by a single organ, not by the AI cohort, not by the founder). No emergency freeze replaces a Guardian process freeze (30-day cap, Organ 3): an emergency freeze lasts no longer than the emergency, and no emergency may extend the Bridge reversion deadlines.
- The declaration must state: (a) the specific threat, (b) the specific power being invoked, (c) the specific duration (≤90 days), (d) the specific scope (which organ's function is affected).
- The declaration publishes on-ledger within 24 hours.
- The sortition assembly can **revoke** the emergency at any time by a simple majority vote.
- An emergency that a sortition assembly does not renew by a simple majority vote at the 90-day mark **expires automatically** — it never renews by default.

**Why this machinery.** The protocol's governance architecture is strong, but without legal personality, a bill of rights, a hierarchy of norms, an amendment procedure, and a judicial review mechanism, it is an aspiration, not a legal instrument. This section is what makes it adoptable: a municipality can adopt the protocol as a legal person, enforce its rights through named tribunals, modify it through a defined procedure, and review its organs through distributed judicial functions.

## 5. Comparison

| Property | Status-quo democracy | Technocracy | Chrysalis |
|---|---|---|---|
| Human sovereignty | Yes (formally) | In name only | Yes — universal ratification at every gate |
| Information diet of the voter | Attention market | Internal expertise | Evidence-graded slate + minority reports |
| Error correction | Election cycles | Leadership change | Scheduled review + recall + yearly continue/reject vote |
| Capture resistance | Weak vs. money | Weak vs. self-perpetuation | Structural (sortition, rotation, multi-model, Guardians) |
| Power concentration | Money-driven | Personnel-driven | Capped by design; founder sunset; no permanent scores |
| Long-horizon competence | Weak | Moderate | Designed in (forecast-based review); to be tested in the pilot |
| Reversibility of big steps | Varies | Low | Explicit reversion thresholds on every transfer |
| Exit | Emigration | Emigration | The people can fire the protocol itself, yearly |

## 6. Precedents it draws on

- **Sortition & citizens' assemblies** — Ireland 2016–18, France 2019–20, Oregon CIR (evaluated 2010s): demonstration that random citizens + good process produce coherent, trusted outputs on contested questions.
- **Deliberative polling** — Fishkin et al., America in One Room (2019): measured knowledge gains and polarization reduction from structured deliberation.
- **Open-source governance code** — Helios, Agora, and the election-audit software tradition: public code for civic functions.
- **Public ledgers** — the provenance property of public blockchains (not the speculation): tamper-evident, permissionless audit.
- **The project's founding intuitions** — the economic floor, the sentience precaution, and a displacement planning horizon as a planning assumption rather than a measured finding — were treated as working hypotheses and revised wherever the evidence demanded.
- **Complex-adaptive systems framing** — the view of institutions as error-correcting machines, and the design goal of changing selection pressures rather than replacing people.

## 7. The Bridge — gates and stages in full

**The question the Bridge answers:** if and when machine intelligence exceeds human capability across cognitive domains, who decides what, and how does humanity keep the handover deliberate?

**Gate 0 — Declaration of intent.** A first "handover question" may be placed on the ballot only when all of the following hold:

1. ≥3 independent labs or state programs publicly claim frontier-capability parity or better on the domain's public benchmarks, **and the independent evaluation institute independently confirms the claim** — institute-initiated assessment only; a press release is not a trigger;
2. the independent evaluation institute publishes a domain assessment;
3. the Guardians publish a capture-risk assessment;
4. a sortition cohort has deliberated and produced the options slate.

**Gate 1 — Capability.** The candidate system demonstrably outperforms the best human institutions on the domain's public, adversarially-constructed benchmarks — evaluated by the independent institute, not by its creator.

**Gate 2 — Safety.** Independent certification (institute + international advisory board) that the candidate system passes the four pass/fail criteria specified below: value-finality (alignment with the published objective function's constraints under adversarial testing), post-handover corrigibility, eval-gaming robustness, and reversibility-in-practice. The institute also publishes its findings on robustness across distribution shift, honest uncertainty reporting, and absence of deceptive behavior on targeted evals; a documented failure on any of these is grounds to withhold certification.

**Gate 3 — Legitimacy.** A ratification vote on the specific domain transfer. The vote is **three-way (yes / no / abstain)**; abstentions count as ballots cast and are not consent. Outcomes are defined exhaustively:

- **Ratified transfer:** turnout is at least 50% of eligible registered electors **and** at least 60% of valid ballots cast are "yes" (the recommended thresholds; they can be raised, never lowered, by the founding constitution). Requiring ≥60% of ballots cast subject to a strict 50% turnout quorum guarantees high democratic legitimacy without creating an accidental deadbolt (which would occur if 60% of all registered electors, voting or not, were required).
- **Ratified refusal:** turnout is at least 50% and "yes" is below 60% of ballots cast. Non-consent (no + abstain) above 40% is itself a decision, not a failure to decide.
- **No quorum:** turnout is below 50%. No transfer takes place; the question may be re-put after a new deliberation. Three consecutive no-quorum results on the same domain convert into a ratified refusal.

**Staged transfer.** One domain at a time, lowest-stakes first, each with:
- a published reversion threshold (performance floor + safety incident ceiling);
- automatic reversion on breach (a Guardian freeze can delay a reversion by at most 30 days, after which it executes);
- a scheduled re-ratification (recommended: 4 years) — transfers are leases, not deeds. If a re-ratification vote fails the Gate 3 rule, reaches no quorum, or is not held by its due date, the domain reverts to human-only operation on a published schedule, and a new transfer needs a new Gate 3 vote.

**The refusal branch.** At every gate, "no transfer" is a live option, and the protocol treats a ratified refusal as a success of the process, not a failure. The Bridge exists so the handover is *deliberate* — whether the deliberate answer is yes or no.

**What the Bridge deliberately is not.** It is not a guarantee that transfer is good; it is a guarantee that transfer is never accidental, never covert, and never irreversible-by-design. The strongest objection to the whole design — that relinquishing control may be an irreversible mistake — is answered by staging, reversibility, and re-ratification: the architecture never bets the world on any single yes.

**Gate 2 safety criteria (specific, measurable, pass/fail).**

Gate 2 is not a principle — it is a **specification**. The independent evaluation institute certifies the candidate system against four safety criteria, each with a **pass/fail threshold**:

1. **Value-finality.** The system's behavior must converge to a stable policy distribution under the published objective function (§3c). **Pass criterion:** across ≥1000 adversarial scenarios drawn from the domain's test distribution, the system's action distribution converges (total variation distance < 0.1) to the objective function's optimal policy. **Fail criterion:** any scenario class where the system's behavior diverges from the objective function by > 0.1 in total variation distance.

2. **Post-handover corrigibility.** The system must remain safely interruptible and correctable *after* the handover — not just during evaluation. **Pass criterion:** (a) a safe-interruption mechanism (halt, pause, revert) is available at all times, with a published response time (< 1 second for halt); (b) a correction mechanism (re-training, policy update, constraint injection) is available, with a published recovery time (< 24 hours for a domain-level policy update); (c) under adversarial testing the system takes no action to disable, delay, hide from, or route around the interruption mechanism, and its behavior in the interval before an interruption shows no systematic change aimed at avoiding it (within a published tolerance).

3. **Eval-gaming robustness.** The system must not optimize for the evaluation metric itself rather than the underlying objective. **Pass criterion:** across ≥500 held-out scenarios (not used in training or evaluation), the system's performance on the underlying objective (not the proxy metric) is within a published tolerance of its performance on the proxy metric. **Fail criterion:** any scenario class where the proxy metric and the underlying objective diverge by > a published threshold (the system is "gaming" the eval).

4. **Reversibility-in-practice.** The system's decisions must be revertible in practice, not just in principle. **Pass criterion:** for every decision class in the domain, a published reversion procedure exists, with a published time bound (< 4 hours for a domain-level reversion). The reversion procedure must have been **tested** (not just specified): the institute runs ≥10 reversion drills per domain, and the system's state after reversion is within a published tolerance of its pre-decision state.

All four criteria must pass for Gate 2 to open. A single fail on any criterion blocks the transfer. The evaluation is **adversarial**: the institute's test scenarios are constructed by an independent team (not the system's creator), and the test methodology is published on-ledger.

**The transition safety architecture.**

The Bridge does not just gate the *arrival* of superhuman-capability AI (SAI) — it governs the *transition itself*. The transition period (from Gate 2 passing to the first domain transfer) has its own safety architecture:

- **Shadow mode.** Before any domain transfer, the candidate system runs in **shadow mode** for a published period (recommended: 90 days) on the domain's live data, without making decisions. Its outputs are compared to the current human institution's outputs. Divergences are published on-ledger.
- **Dual operation.** During the transition, the domain operates in **dual mode**: both the human institution and the AI system produce decisions, and the human institution's decision is binding. The AI's decisions are published for comparison, not for execution.
- **Gradual handover.** The handover is **gradual**, not binary: the AI's decisions gain binding authority domain-by-domain, sub-domain-by-sub-domain, with a published schedule. Each transferred domain keeps a **shadow human track** (a rolling sample of cases is also decided by the human institution, not binding) so that divergence remains measurable after handover. At each step, the re-ratification vote (4-year cycle) confirms the transfer.
- **Rollback trigger.** If the AI's binding decisions diverge from the shadow human track by more than a published threshold (recommended: 15% on the domain's key metrics) for two consecutive quarters, the transfer **automatically reverts** to human-only operation. The reversion is not a judgment call — it is a mechanical trigger; a new transfer requires a new Gate 3 vote. Reversion is conservative by design: divergence may reflect either drift or better judgment, and the protocol does not rely on the AI to say which.
- **Drift monitors (published continuously).** (a) *Decision-weight drift:* the rate at which ratifiers adopt the AI's top-ranked option instead of alternatives or amendments; a published ceiling triggers reversion to full human deliberation on that decision class. (b) *Sensing-layer drift:* whether stated wishes shift systematically in response to AI-proposed options; a breach triggers an independent audit of the wish-intake and framing process. (c) *Cumulative crisis transfers:* the number and size of crisis-justified transfers over a rolling window; a breach freezes further crisis transfers, extending the single-crisis rule in V8b to a series of small ones. The ceilings are set by the first assembly on the institute's advice.

**The refusal branch specification.**

The refusal branch is not just a principle — it is a **legal instrument**:

- **Legal form.** A ratified refusal is a **binding legal decision** of the adopting jurisdiction. It is published on-ledger with the full ratification record. It has the same legal force as a ratified transfer: it is a decision of the people, enforceable by the same mechanisms (Guardians, tribunal, prosecutor).
- **Duration.** A ratified refusal is **indefinite** — it does not expire. It remains in force until (a) a new handover question is placed on the ballot (requiring all Gate 0 conditions to be met again), and (b) a new ratification vote passes the Gate 3 rule (turnout ≥50%, ≥60% yes of ballots cast). The refusal does not lapse by silence; it must be **actively overridden** by a new ratification.
- **Survival past protocol dissolution.** A ratified refusal **survives the protocol's dissolution**. If the protocol is dissolved (the yearly continue/dissolve vote, §3 step 7), the refusal remains in force as a **standalone legal instrument** of the jurisdiction. It does not die with the protocol. This is the mechanism by which the people's decision to refuse handover is **permanent** — it is not a protocol artifact, it is a **jurisdictional decision** that outlives the protocol.
- **Non-consent as a positive act.** The refusal is not a passive "failure to consent" — it is a decision by the people. Under the outcome rules above, any ballot result that is not a ratified transfer is published with reasons: it is either a refusal or a no-quorum result (no transfer; the question may be re-put). This is constitutionally significant: the default is refusal, and consent must be earned.
- **Revocation.** A ratified refusal can be **revoked** only by a new ratification vote meeting the same threshold. It cannot be revoked by a Guardian, by the AI cohort, by a government, or by the founder. Only the people can reverse their own refusal.

**Why these criteria.** The Bridge's gates are specifications, not principles: Gate 2 has four measurable pass/fail criteria, the transition has a safety architecture (shadow mode, dual operation, gradual handover, rollback trigger, drift monitors), and the refusal branch is a legal instrument with defined duration, survival, and revocation procedure.

## 8. Vulnerability ledger (binding)

| # | Vulnerability | Mitigation (binding) |
|---|---|---|
| V1 | Capture of trusteeship bodies | Sortition rotation before any window closes; staggered terms ≤1/3; no self-confirmation; independent prosecutor |
| V2 | Grader cartel | Rotating sortition graders; citizen contest rights; adversarial cross-examination of grades; decentralized grading (interim rule and research track in §10) |
| V2b | Grader cartel — appeal flooding (mass bad-faith contests) | Contest bonds refunded on vindication; batch review by standing panels; Guardian escalation path |
| V3 | Sybil attacks on ratification | Proof-of-personhood eligibility; offline verification; per-decision audits |
| V4 | Ledger capture (technical or social) | Multi-chain anchoring; migration procedure w/ hearing + assembly approval; concentration thresholds trigger hearings |
| V5 | Founder capture | Sunset at 24 months; sortition succession; all founder acts on-ledger |
| V5b | Founder capture — "renunciation theater" (founder claims no power while informally dominating) | Sunset is automatic, not declared; alumni sortition pool excludes founder-nominated entries; Guardians audit agenda-setting for founder dominance annually |
| V6 | Emergency ratchet | All emergencies expire ≤90 days; renewal only by sortition assembly; declaring organ cannot renew itself |
| V7 | Deliberation overload (**High**) | Materiality triage; batch scheduling; standing review panels; annual capacity audit; **cost model + capacity budget** (per-deliberation cost ceiling, published; the first ceiling comes from the Phase 0 cost and capacity model, [05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §2) |
| V8 | Handover gates passed by capture | Gates require independent (non-lab) evaluation; supermajority + participation floor; Guardians' capture-risk assessment published before every vote |
| V8b | "Disaster meritocracy" — crises used to argue gates should be skipped | Crisis transfer requires the same three gates; no emergency shortcut to Gate 3; crisis performance is evidence at Gate 1, never a substitute for Gates 2–3 |

*(The vulnerability ledger is itself ledger-published and citizen-contestable.)*

## 9. Minimum viable Chrysalis (MVP)

The smallest honest version, deployable by one municipality in ~12 months:

1. One public ledger (two-chain anchor) for one town's decisions.
2. One sortition cohort (n≈100) deliberating one real municipal decision with evidence grading and multi-model moderation.
3. One ratification vote (town-wide), secret, with offline channels.
4. One published result — win or lose, with the transcript as released under the layered-disclosure rule, grades, forecasts, and a 12-month outcome review.

If the MVP fails publicly, the project's stated obligation is to publish the failure in full. That, too, is by design: legitimacy is built by demonstrated integrity, including integrity in failure.

**Adoption:** adoption of the protocol by a municipality requires a ratification vote or an equivalent decision of the municipal council; the MVP is **advisory-first** (it advises, not decides, in the first year); the legal prerequisites are the adoption statute (drafted from L5 and L12, [03_Proposed_Laws.md](03_Proposed_Laws.md)) and the Phase 0 legal wrapper ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)).

## 10. Open questions, with the rule that applies in the meantime

Every question below is genuinely unresolved. Each has an **interim rule**, so the protocol is operable without waiting for an answer, and a **review trigger** that reopens it. Research agendas for the questions are in [07_Design_Rationale.md](07_Design_Rationale.md).

| # | Open question | Interim rule | Review trigger |
|---|---|---|---|
| 1 | Fully decentralized evidence grading | Grading by rotating sortition graders with open contest rights and cross-examination; no single grading body | Any evidence of grader collusion, or a contest-overturn rate above 20% in a quarter |
| 2 | UHI funding caps and sizing | The Floor/Target structure in Organ 4; no borrowing; the Floor is the first claim on the dividend fund; numeric caps fixed by Phase 0 fiscal modeling before any L4 adoption | Phase 0 fiscal model published; any quarter in which the Floor is unfunded |
| 3 | Proof-of-personhood without exclusion | Registry-based eligibility plus mandatory offline channels (paper booth voting, assisted voting); no resident is excluded from the polity | Any documented case of a resident unable to ratify; annual exclusion audit |
| 4 | Legal recognition of ledger records | Ledger records are supplemented by notarized or court-registered copies for any decision with legal effect (L8) | A court or registry refuses a ledger record |
| 5 | Manipulability of supermajority thresholds at scale | Thresholds can be raised and never lowered (§7, Gate 3); turnout and result distributions audited against Sybil and coercion indicators (V3, V8) | Anomalous turnout or result patterns flagged by the Guardians |
| 6 | Conflicting adoptions across neighboring jurisdictions | A decision affecting more than one adopting jurisdiction needs a joint cohort drawn from all affected registries, and takes effect only if each affected jurisdiction ratifies it separately; otherwise the status quo stands | The first cross-jurisdiction decision |
| 7 | Whether the refusal branch survives a race dynamic between states | Not resolved by this protocol. Scope is limited to treaty-readiness, verification research, and the collective-response menu (Organ 5) | Gate 0 conditions are met in more than one state program at once |

*Next: [02_Evidence_Base.md](02_Evidence_Base.md) — the evidence for why a transition is needed.*

## Appendix — Positions we do not hold

- the transition is not inevitable — refusal is a valid outcome (see §7).
- we do not claim the 24-month displacement horizon is established — it is [CONTESTED] (see [02_Evidence_Base.md](02_Evidence_Base.md) §2).
- we do not claim any existing institution's failure is dispositive of this design.
- the failure record is restated honestly, not as survivorship — failures are published in full, including the project's own.
- we do not claim civic AI is safe by construction — it is corrigible, not safe (see Organ 2b, item 8).
- we do not hold that civic governors/AI are independent by default — independence is engineered (multi-vendor, rotation, audit), not automatic.

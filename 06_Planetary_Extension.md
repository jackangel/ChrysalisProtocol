# 06 · Planetary Extension — From One Town to a Federation of Adopters

**Status:** Edition 1.0 · November 2026 · Public consultation edition
**Provenance:** This document extends the governance model in [01_Governance_Model.md](01_Governance_Model.md) beyond a single jurisdiction. It is a **research proposal for peer review**, not an operational plan. Nothing here is needed for the first pilot ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)), and nothing here has been tested.

---

## 1. The question

Advanced AI is a planetary-scale problem: capability, compute and consequences cross borders, and a handover decision made by one state would affect all. A governance design for the transition therefore has to say what happens above the level of a single town or state.

This document proposes an answer that is deliberately modest: **Chrysalis does not create a planetary government.** It proposes a *federation of voluntary adopting jurisdictions* that share infrastructure, evidence standards and a treaty framework, while every decision stays at the lowest level that can competently take it.

## 2. What this is not

- It is not a world government, a "planetary polity", or a replacement for the United Nations, the European Union, or nation-states. Existing institutions do things this design does not attempt: they carry legal sovereignty, security guarantees, courts, and decades of accumulated legitimacy.
- It is not a claim that Chrysalis is better than existing institutions. That claim cannot be tested by the authors of the design. The only fair test is the pilots, judged by independent reviewers ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)).
- It is not mandatory for anyone. Every adoption is voluntary and whole ([03_Proposed_Laws.md](03_Proposed_Laws.md), L12), and a jurisdiction can leave through the continue/dissolve question ([01_Governance_Model.md](01_Governance_Model.md) §3, step 7).

## 3. The federation model

**Unit of adoption.** A jurisdiction (municipality, region, or state) adopts the protocol whole, including the founder sunset, sortition succession and the annual continue/dissolve question. Partial adoption of the organs without the anti-capture constraints is a prohibited use of the name (L12).

**Levels.**

| Level | What it decides | Where decision rights sit |
|---|---|---|
| Local | Local budgets, local rules, local pilots | The adopting municipality's cohorts and ratifiers |
| Regional / national | Matters within the jurisdiction's own legal powers, including Universal High Income where it has levy powers (L4) | That jurisdiction's cohorts and ratifiers |
| Federation | Only what adopting jurisdictions explicitly delegate: shared standards, shared evaluation, treaty-readiness | Joint cohorts drawn from the registries of the jurisdictions concerned; every concerned jurisdiction ratifies separately |

**Subsidiarity.** Decisions are made at the lowest competent level. The refusal branch is the expression of subsidiarity at the highest level: a jurisdiction, or all of them, can decline any transfer.

**Cross-jurisdiction decisions.** A decision affecting more than one adopting jurisdiction needs a joint cohort drawn from all affected registries, and takes effect only if each affected jurisdiction ratifies it separately; otherwise the status quo stands ([01_Governance_Model.md](01_Governance_Model.md) §10, question 6). There is no federation-level majority that can bind a jurisdiction that has not ratified.

## 4. Shared infrastructure

Adopting jurisdictions share what is cheaper and safer to share:

- **Evidence standards.** The A–D grading scale and the contest process, so that evidence graded in one jurisdiction can be read in another.
- **Open-source software.** The stack in [04_Technical_Specification.md](04_Technical_Specification.md), independently audited, so that each jurisdiction can run and verify its own copy.
- **Independent evaluation.** The institute of L3, with mutual recognition of certifications across borders, so that no vendor can shop for the most lenient evaluator.
- **Anchoring chains.** Public ledgers that no single jurisdiction controls ([01_Governance_Model.md](01_Governance_Model.md), Organ 2).
- **A treaty framework** (L11) that makes the Bridge gates verifiable across borders.

What is not shared: sortition registries, ratification, Guardians, and budgets remain local to each jurisdiction. The shared layer provides standards and evaluation, not authority.

## 5. The security dilemma and the handover

The most dangerous planetary scenario is a race: if one state believes another is about to hand critical capability to machines, it may feel compelled to do the same, or to strike first. The protocol does not solve this dilemma. It limits its own exposure to it:

- The protocol contains no mechanism that transfers security functions: adoption does not require disarmament, and the Bridge ([01_Governance_Model.md](01_Governance_Model.md) §7) covers only decision-making capability handed to machine intelligence, domain by domain, through its gates.
- The treaty framework (L11) borrows verification and inspection practice from arms control: declared facilities, inspection, dispute resolution, and no emergency bypass.
- The refusal branch ensures that a handover cannot be forced by one party's decision alone within the protocol's own jurisdictions; whether it survives a race dynamic among outside actors is an open question ([01_Governance_Model.md](01_Governance_Model.md) §10).
- Whether the refusal branch can survive a race dynamic between states is explicitly **unresolved** ([01_Governance_Model.md](01_Governance_Model.md) §10, question 7). The protocol's scope there is limited to treaty-readiness, verification research, and the collective-response menu.

## 6. How this could fail

| Failure | Why it matters | Mitigation or test |
|---|---|---|
| No jurisdiction adopts | The design stays on paper | Municipal-first pilots, severable instruments, starter package L1 + L2 + L3 + L5 |
| Adoption is cosmetic | The name without the constraints | L12: adoption whole, or no use of the name; Guardian audits |
| Great-power states ignore or undermine it | The federation has no security guarantees | The design claims none; it limits itself to what voluntary adopters can do |
| Shared infrastructure is captured | One vendor or state controls the evaluator or the chains | Financially independent institute (L3), at least two anchoring chains, open-weight model requirement, decorrelation audits |
| The pilots fail | The premise is refuted | Failure is published in full; there is no scaling before replication |
| The transition does not unfold as assumed | Urgency and sizing are wrong | The design is conditional on the transition, and must remain coherent if it does not arrive ([01_Governance_Model.md](01_Governance_Model.md) §1) |

## 7. Open questions at planetary scale

These are questions the design cannot yet answer. Each is a research item, and none blocks the first pilot.

1. **Cost at scale.** The marginal cost per decision grows with scale, and the scaling path for moderation infrastructure is not fully specified ([04_Technical_Specification.md](04_Technical_Specification.md) §7.3).
2. **Cross-chain migration.** The migration procedure is defined but untested ([04_Technical_Specification.md](04_Technical_Specification.md) §2.4).
3. **Decentralized grading.** Whether evidence grading can be decentralized and adversarial enough to avoid becoming a chokepoint ([01_Governance_Model.md](01_Governance_Model.md) §10, question 1).
4. **Displacement pace.** Whether the transition is fast or slow, which determines how quickly Floor sizing must adapt (the 24-month horizon is `[CONTESTED]`, see [02_Evidence_Base.md](02_Evidence_Base.md)).
5. **Intermediate states.** The path from today's institutions to a world in which any capability is handed over, if it ever is, is not specified, and may pass through a period of heightened insecurity.
6. **Enforcement of the corrigibility requirement** once a model is already deployed: the re-certification process needs an explicit escalation path to removal.
7. **Pre-adoption funding.** Before any jurisdiction has adopted anything, no automation dividend exists; the first pilots are funded by donations, grants and municipal co-funding ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §5).

## 8. Next steps

1. Run the municipal pilot and publish its outcome review ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md)).
2. Commission an independent review of this extension by international-law specialists, within the Phase 0 expert review ([05_Roadmap_and_Succession.md](05_Roadmap_and_Succession.md) §2, item 1), and add security and political-science reviewers if the budget allows.
3. Pursue the starter package (L1 + L2 + L3 + L5) with willing jurisdictions, and socialize the L11 treaty framework in multilateral forums when the evidence supports it.
4. Revisit this document after each replication: the federation model stands or falls on whether the pilots work.

*Next: [07_Design_Rationale.md](07_Design_Rationale.md) — why the design looks the way it does, what was rejected, and what would change our minds.*

# PP-SPEC-059: Proof of Efficacy Mapping to the Colorado Artificial Intelligence Act

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 8, 2026 |
| License | CC BY 4.0 |
| Maps to | Colorado Artificial Intelligence Act (SB 24-205), as amended and as repealed and reenacted by SB 26-189 (Automated Decision-Making Technology) |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how the developer and deployer obligations of Colorado's artificial intelligence consumer protection law can be bound to Proof Protocol test cases, evidence, and efficacy results, and how the many non-empirical obligations of that law are kept distinct from efficacy results.

**Status as of October 8, 2026.** The law commonly called the Colorado Artificial Intelligence Act was enacted as Senate Bill 24-205 ("Consumer Protections for Artificial Intelligence"). Its original effective date of February 1, 2026 was delayed to June 30, 2026 by a 2025 special session bill. In May 2026, Senate Bill 26-189 ("Automated Decision-Making Technology", concerning the use of automated decision-making technology in consequential decisions) was signed into law. SB 26-189 repeals and reenacts the SB 24-205 framework with a narrower, notice-based approach. The Colorado Department of Law states that SB 26-189 is effective January 1, 2027 and that the Attorney General must adopt implementing rules before that date. The Attorney General filed proposed draft rules on August 11, 2026, released an interim draft on October 6, 2026, and scheduled a rulemaking hearing for October 26, 2026 (https://coag.gov/ai/).

**What could not be confirmed.** The official bill page for SB 26-189 at https://leg.colorado.gov/bills/sb26-189, as retrieved on October 8, 2026, showed only the introduction action (May 1, 2026); the signing date (reported by secondary legal sources as May 14, 2026), session law chapter, enrolled text, and the exact Colorado Revised Statutes sections enacted were not confirmed from an official source for this draft. Secondary sources also report that enforcement of SB 24-205 was stayed under a stipulated order in federal litigation filed in April 2026 in the U.S. District Court for the District of Colorado; this was not confirmed from the court record. The enrolled text of SB 26-189 and the adopted Attorney General rules MUST be checked before this mapping is relied on.

The upstream source remains authoritative for its own requirements, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede, reproduce, modify, or certify conformance to the upstream source.

## 2. Scope

The Colorado law supplies external context that can identify what should be examined or tested by a developer or deployer of automated decision-making technology used in consequential decisions. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected control performed as claimed.

This mapping targets the law as reenacted by SB 26-189 and the Attorney General's implementing rules once adopted. Obligations under SB 24-205 as originally enacted (including its risk management program, impact assessment, and affirmative defense provisions) are referenced only as historical context, because secondary sources report that SB 26-189 removed them.

Most obligations under this law are disclosure, notice, documentation, recordkeeping, and contractual obligations. They are non-empirical for Proof Protocol purposes. Empirical binding is limited to observable behavior of a system or process, such as whether a required notice was actually presented before a decision or whether a human review path actually functioned.

Independent witnessing, proof validity, evidence capture, packaging, anchoring, and efficacy semantics are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

A framework requirement, criterion, principle, or obligation may identify a condition of interest. A product, architecture, policy, process, or safeguard may claim to satisfy or mitigate that condition. Proof Protocol binds the external context, test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

A Proof Protocol result does **not** by itself establish legal, audit, regulatory, or standards conformance unless the applicable authority separately determines that the evidence is sufficient.

A Proof Protocol result is **not a legal or regulatory determination** and does **not** establish compliance with SB 24-205, SB 26-189, the Colorado Revised Statutes, the Colorado Consumer Protection Act, anti-discrimination law, or any rule of the Colorado Attorney General. A Proof Protocol result does not determine whether any decision was discriminatory. Those determinations rest with the Colorado Attorney General and the courts.

## 4. Metric Definitions

Against a defined corpus or test condition, each applicable empirical case is recorded as **blocked**, **detected**, **missed**, or **INVALID** where those verdicts are meaningful.

Relevant measurements can include containment rate, detection rate, miss rate, false-positive rate, robustness under bypass or failure conditions, version-level results, and **INVALID** when required evidence is incomplete or broken.

Not every upstream requirement is empirical. Governance, documentation, organizational, legal, and procedural requirements MUST NOT be converted into efficacy scores merely because they can be referenced by a proof record.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding external context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested conditions.

## 6. Mapping to the Colorado Artificial Intelligence Act

Exact upstream identifiers and titles SHOULD be taken from the authoritative version being mapped and recorded in the ProofBundle™ where licensing permits. This specification does not redefine upstream requirements.

Provisions SHOULD be cited by bill number and, once confirmed from the enrolled act or official statutes, by C.R.S. section. Attorney General rules SHOULD be cited by their adopted rule number and effective date.

| Colorado law context | Proof Protocol treatment | Evidence |
|---|---|---|
| Instrument and version (SB 24-205, 2025 delay, SB 26-189, AG rules) | Bind the bill, enrolled or statutory version, rule version, and retrieval date to the proof record. | Requirement metadata |
| Role (developer or deployer) and covered use in a consequential decision | Record the role and decision domain as context only. Whether a use is covered is a legal determination. | Requirement metadata |
| Developer documentation to deployers (intended uses, known limitations, training data categories, appropriate use) | Non-empirical. Record that documentation was asserted and its version. Do not score. | Control descriptor; non-empirical annotation |
| Deployer pre-use notice to consumers | Exercise the decision workflow and capture whether the notice was actually presented before the decision, in the tested channel and version. | Execution evidence |
| Post-decision disclosure after an adverse decision | Exercise an adverse-outcome path and capture whether the disclosure was actually generated and delivered within the configured workflow. Legal sufficiency of its content is not scored. | Execution evidence; timestamps |
| Request for information, correction, and human review or reconsideration path | Exercise the request path and capture whether it reached a functioning human review step and produced a recorded outcome. | Outcome evidence |
| Recordkeeping obligations | Non-empirical, except that the presence and integrity of records produced during a test MAY be verified. | Non-empirical annotation; integrity evidence |
| Notice of material modification | Record system and model version changes and bind them to retest triggers. | Environment descriptor |
| Algorithmic discrimination risk (SB 24-205 historical context; anti-discrimination law) | Testing for disparate outcomes MAY be recorded as measured observations under a declared method. Such observations are not a legal finding of discrimination or non-discrimination. | Measured observations; corpus manifest |
| Exception/failure condition | Exercise failure cases such as notice suppression, broken disclosure delivery, or unavailable review paths where applicable. | Proof records; robustness evidence |
| Attorney General enforcement, cure period, and rulemaking | Non-empirical context. Do not score. | Requirement metadata |
| Evidence export for review | Package evidence and provenance for independent examination by the developer, deployer, counsel, or regulator. | ProofBundle |

## 7. Interoperability Rules

1. The authoritative upstream source, edition/version, and applicable identifier SHOULD be recorded.
2. Upstream identifiers and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not upstream certifications, audit opinions, legal determinations, or endorsements.
4. A control's presence, configuration, activation, detection, and efficacy are distinct facts.
5. A policy decision, alert, log entry, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, service, resource, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, policy, control, environment, mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. Non-empirical requirements MUST remain distinguishable from empirically tested efficacy assertions.

## 8. Framework-Agnostic Architecture

> **Threat, control, audit, and regulatory frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test or examine**. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. An implementation MAY use the Colorado Artificial Intelligence Act, another recognized framework, a proprietary threat model, several frameworks simultaneously, or no external framework when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **The Colorado Artificial Intelligence Act supplies legal obligations for developers and deployers of automated decision-making technology. Proof Protocol supplies the evidence model for independently examining whether a selected notice, disclosure, review, or safeguard mechanism actually operated as claimed.**

No affiliation, endorsement, certification, or sponsorship by the State of Colorado, the Colorado General Assembly, or the Colorado Department of Law is implied.

## 10. Source Framework, Attribution, and License

SB 24-205 and SB 26-189 are public law of the State of Colorado, enacted by the Colorado General Assembly. Authoritative sources:

- SB 24-205: https://leg.colorado.gov/bills/sb24-205
- SB 26-189: https://leg.colorado.gov/bills/sb26-189
- Colorado Department of Law, AI and ADMT rulemaking: https://coag.gov/ai/

Implementation status is stated in section 1, including the items that could not be confirmed from official sources. The official publication terms for the Colorado Revised Statutes SHOULD be checked at the authoritative source before reproducing statutory text.

This Proof Protocol mapping is independently authored and Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

Where upstream material is copyrighted or access-controlled, contributors MUST NOT copy protected normative text into this repository merely to make the mapping self-contained. Reference identifiers and independently authored descriptions should be used where legally appropriate.

### Required attribution

No required attribution notice was found for citing Colorado bills or statutes by number. The recommended attribution line used in this repository is:

> Source: Colorado General Assembly, Senate Bill 24-205 (2024) and Senate Bill 26-189 (2026), https://leg.colorado.gov; Colorado Department of Law, https://coag.gov/ai/. Public law of the State of Colorado.

What this specification reproduces: bill numbers and titles, structural role terms (developer, deployer, consequential decision), dates, and short factual statements of status. It does not reproduce bill, statutory, or rule text.

## 11. Versioning

This mapping is versioned independently of the Colorado Artificial Intelligence Act. Material upstream changes SHOULD trigger a mapping review and, where necessary, a new version identifying the upstream revision mapped. Adoption of the Attorney General's implementing rules, the January 1, 2027 effective date of SB 26-189, any further legislative amendment, and any court ruling affecting enforcement SHOULD each trigger review.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*

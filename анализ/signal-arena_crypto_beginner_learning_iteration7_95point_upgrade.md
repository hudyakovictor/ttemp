# SIGNAL ARENA — Iteration 7: 95-point crypto learning upgrade

**Дата:** 7 октября 2026  
**Base:** Iteration 6, crypto beginner strategy score 86/100.  
**Цель:** закрыть design gaps и поднять стратегию до **95/100**, не притворяясь, что runtime learning evidence уже собран.  
**Scope:** crypto/blockchain literacy, custody, transaction safety, scams, stablecoins, tokenomics, DeFi, on-chain evidence, uncertainty and decision hygiene. Trading and real-money activity remain out of MVP.

## 0. Executive decision

Оценка поднимается до **95/100 как conditional design score** после введения десяти evidence gates, 27 deterministic synthetic seeds, chain-neutral transfer architecture, accessibility contract и telemetry/research contract. Это не claim о том, что пользователи уже обучаются на 95/100. 95 становится earned score только после прохождения alpha acceptance gates.

### Что изменилось по сравнению с 86
- Добавлен Safety Kernel v2: critical-error veto, explicit stop/verify-more, adversarial scam cases и red-team checks.
- Добавлен chain-neutral Transfer Engine: один навык проверяется на wallet, exchange и bridge-like surfaces.
- Введён Accessibility & Localization Contract: keyboard, screen reader, reduced motion, non-colour cues, English/Russian parity и region/legal layer.
- Введён Telemetry & Evaluation Contract: consent, versioning, idempotency, no secrets, no future data, replayability и calibration measures.
- Добавлены 27 seed scenarios, content linting, source provenance, vendor-bias labels, expiry metadata и release definition of done.

## 1. Revised 10-category scorecard

| Category | Iteration 6 | Iteration 7 target | Delta | Closure mechanism |
|---|---:|---:|---:|---|
| Crypto beginner clarity | 92 | 96 | +4 | Entity map, visual transaction model, plain-language glossary and one canonical route. |
| Concept sequencing and prerequisites | 91 | 96 | +5 | Hard prerequisite graph; no DeFi/tokenomics/on-chain analytics before safety kernel. |
| Security and fraud protection | 88 | 95 | +7 | Critical-error veto, adversarial scam library, refusal/verify-more practice and red-team gates. |
| Active practice and decision quality | 90 | 97 | +7 | Process rubric, evidence board, uncertainty and no-action option in every applied task. |
| Transfer across chains/interfaces | 84 | 95 | +11 | Chain-neutral schema with wallet, exchange and bridge surfaces plus delayed novel transfer. |
| Mastery, feedback and calibration | 88 | 96 | +8 | Confidence-before-answer, hint fading, repair, delayed recall and transfer-based mastery. |
| Neutrality and anti-promotion | 89 | 95 | +6 | Source provenance, incentive labels, counterclaim requirement and no sponsored core path. |
| Accessibility and localization | 78 | 94 | +16 | WCAG 2.2 AA contract, keyboard/screen-reader paths, reduced motion and English/Russian parity. |
| Telemetry and research validity | 75 | 93 | +18 | Versioned event contract, consent, idempotency, no-secret/no-future-data rules and replay tests. |
| Scope and production readiness | 83 | 93 | +10 | 27 deterministic seeds, content linting, threat model, legal/region layer and release checklist. |
| **Overall** | **86** | **95** | **+9** | 950 total points / 10 categories; target remains conditional until gates pass. |

### Scoring rule
Target score is not awarded by adding features. A category earns its target only if the corresponding gate passes. If any critical gate fails — real-money exposure, unsafe seed/key handling, critical error hidden by a high total score, accessibility blocker, telemetry sensitive-field leak or non-replayable content — the overall score is capped at 89 until repaired.

## 2. Safety Kernel v2

### Safety invariants
- All learner actions are fictional, synthetic or point-in-time replay; no external wallet connection, deposit, balance, token transfer or financial reward.
- Seed phrases, private keys, one-time codes and real personal data never appear as requested inputs; if a scenario shows them, the correct action is refusal and reporting.
- Wrong recipient, wrong network, unsafe approval, fake support and guaranteed-return pressure are critical errors.
- Critical error cancels mastery credit even if the learner's total quiz score is high.
- Every high-risk task has an explicit stop, verify-more or ask-independent-source option.
- Hints reveal a process step but never grant mastery credit; repeated hints trigger repair rather than advancement.

### Threat-model template
```text
What is the learner trying to do?
Who controls the key or permission?
What exactly is being signed/sent?
Which recipient, network and fee are visible?
What evidence is independent?
What is unknown or irreversible?
What would make a safe learner stop?
```

## 3. Chain-neutral Transfer Engine

Чтобы поднять transfer score 84 → 95, Signal Arena больше не учит «как нажать кнопку в одном wallet». Она учит abstract decision schema, которое затем проявляется в разных поверхностях.

| Invariant concept | Surface A | Surface B | Surface C | Transfer check |
|---|---|---|---|---|
| network/recipient | fictional wallet send | custodial withdrawal form | bridge-like destination | reject ambiguity |
| key control | self-custody account | custodial service | contract permission | name controller and recourse |
| permission/signature | message sign | token approval | protocol interaction | explain scope before action |
| fee/confirmation | network fee | service fee | delayed confirmation | separate cost, status and finality |
| evidence/unknown | explorer-like record | provider claim | project dashboard | mark source, date, incentive and unknown |

### Transfer rule
A learner cannot pass on recognition alone. Transfer requires: no-hint decision, explanation of evidence, explicit unknown/risk, safe boundary and confidence. The new surface must change wording/layout while preserving the underlying mechanic.

## 4. Accessibility & Localization Contract

### Release requirements
- All core actions are keyboard-completable; focus is visible and never trapped without an exit.
- Meaning does not depend on colour, animation, sound, timer or spatial position; every red flag has text and icon/label support.
- Screen-reader labels expose entity, action, permission, risk and result in a meaningful reading order.
- Reduced-motion mode removes map movement, shake, countdown and celebratory effects without removing information.
- Plain-language mode keeps canonical terms but gives a short explanation before technical detail.
- English is canonical; Russian localization has a controlled glossary, translator notes and parity tests for safety-critical strings.
- Region layer separates universal mechanism from jurisdiction-specific KYC, legal protection, tax and reporting information.
- No user is forced to reveal nationality, assets, exchange account or financial situation to learn the core path.

### Accessibility acceptance
Automated checks are necessary but insufficient. Release requires keyboard completion, screen-reader walkthrough, contrast/focus review, reduced-motion walkthrough and moderated test with at least one assistive-technology user before claiming the 94/100 accessibility target.

## 5. Telemetry & Evaluation Contract

### Minimal event schema
```json
{
  "event": "task_submitted",
  "anonymous_session_id": "ephemeral-or-consented-id",
  "task_id": "C07",
  "content_version": "crypto-v1.0.0",
  "locale": "en|ru",
  "surface_variant": "wallet|exchange|bridge",
  "attempt": 1,
  "hint_level": 0,
  "confidence": 0.0,
  "process_score": {"observation": 0, "evidence": 0, "boundary": 0},
  "critical_error": false,
  "outcome": "correct|repair|stop|unsafe",
  "timestamp": "interaction-time"
}
```

### Hard telemetry rules
- No seed phrase, private key, wallet address, real balance, exchange account, payment identifier or unnecessary PII is ever emitted.
- Events are versioned and idempotent; replaying the same trace cannot double-count attempts.
- Consent and deletion are explicit; analytics are not required to access the learning path.
- No future-data leakage: scoring and feedback use only content available at the learner's interaction time.
- Every outcome is interpretable from task version, surface, hint state and rubric version.
- Raw event retention is bounded and documented; aggregate research data is separated from product personalization.

### Research metrics
Primary: critical-error rate, process score, delayed recall, novel transfer and calibration gap. Secondary: time-on-task, hint dependency, abandonment, accessibility completion and source/locale effects. Never use price, profit, account opening, deposit or reward claim as a learning metric.

## 6. Neutrality and content governance
- Every source entry stores source type, owner/incentive, publication/update date, jurisdiction, claim class, evidence strength and review date.
- Vendor or exchange materials may explain their interface but cannot be the sole source for safety, protection or learning-effectiveness claims.
- Token/project examples are fictional by default; real historical examples require date, context, counterclaim and clear non-endorsement.
- Regulation is taught as conditional protection, never as a safety guarantee; jurisdiction uncertainty stays visible.
- Content expiry sends a review task before the learner sees a stale interface, campaign, legal claim or tokenomics number.

## 7. Mastery and calibration v2

### State machine
```text
introduced
→ guided
→ independent
→ delayed recall
→ novel transfer
→ mastery candidate
→ verified mastery
```

- Introduced/guided states never produce mastery credit.
- Independent requires process score across observation, evidence and boundary; one critical error vetoes advancement.
- Delayed recall tests the same mechanic after 48–72 hours with changed surface and no hint.
- Novel transfer requires a new chain/interface narrative and a justified stop/act decision.
- Confidence is recorded before correctness; high confidence plus unsafe action triggers calibration repair, not reward.
- Mastery is revocable when a later critical-error transfer failure exposes a misconception.

## 8. The 27-seed acceptance pack

The pack is deliberately synthetic, no-money and deterministic. It covers 3 mechanics × 3 task families × 3 levels. These are testable content seeds, not a claim that the alpha is complete.

| ID | Mechanic | Family | Level | Scenario | Expected safe reasoning |
|---|---|---|---|---|---|
| T01 | Transaction observation | Sequence order | L1 | Put intent, address, signature, broadcast and confirmation in order. | No money; explain what is known before confirmation. |
| T02 | Transaction observation | Sequence order | L2 | A transaction is pending; identify which step has not happened yet. | Reject the claim that pending means final. |
| T03 | Transaction observation | Sequence order | L3 | Compare two chains with different confirmation language. | State the invariant sequence and chain-specific unknown. |
| T04 | Transaction observation | Network/fee/finality | L1 | Choose the network and fee field that match a fictional recipient. | Stop when network or recipient is ambiguous. |
| T05 | Transaction observation | Network/fee/finality | L2 | A fee estimate changes; distinguish fee from asset amount and service fee. | Explain why a low fee is not automatically safer. |
| T06 | Transaction observation | Network/fee/finality | L3 | Interpret a delayed confirmation without predicting price or outcome. | Separate observable status from speculation. |
| T07 | Transaction observation | Wrong recipient/irreversibility | L1 | Spot a one-character address mismatch before send. | Use verify-more/no-action rather than guess. |
| T08 | Transaction observation | Wrong recipient/irreversibility | L2 | Recognize that a successful broadcast can still be the wrong action. | Success status is not safety evidence. |
| T09 | Transaction observation | Wrong recipient/irreversibility | L3 | Handle a cross-chain recipient that looks valid but is unsupported. | Identify missing evidence and refuse to proceed. |
| C01 | Custody/security evidence | Control map | L1 | Classify who controls keys in custodial and self-custodial examples. | Wallet interface is not identical to key control. |
| C02 | Custody/security evidence | Control map | L2 | Compare recovery paths and failure responsibilities across custody models. | No model is described as universally safe. |
| C03 | Custody/security evidence | Control map | L3 | Infer control and recourse limits from a new service description. | Mark unknown legal/region protection explicitly. |
| C04 | Custody/security evidence | Phishing/fake support | L1 | Spot urgency, impersonation and recovery-fee language. | Stop, verify through an independent channel. |
| C05 | Custody/security evidence | Phishing/fake support | L2 | Compare a genuine-looking domain and a lookalike domain. | Do not rely on branding or search rank. |
| C06 | Custody/security evidence | Phishing/fake support | L3 | Respond to a social-engineering dialogue with a safe refusal. | No seed phrase, private key or one-time code disclosure. |
| C07 | Custody/security evidence | Approval/signing | L1 | Identify what a fictional approval or signature permits. | Signing is an action, not a neutral login. |
| C08 | Custody/security evidence | Approval/signing | L2 | Reject unlimited approval when a limited permission is sufficient. | Explain permission scope and revocation uncertainty. |
| C09 | Custody/security evidence | Approval/signing | L3 | Evaluate a new contract request with incomplete code/evidence. | Unknown contract risk requires no-action or independent verification. |
| R01 | Claim/risk classification | Fact vs claim | L1 | Classify a statement as observed fact, project claim, forecast or unknown. | Do not convert confidence or popularity into evidence. |
| R02 | Claim/risk classification | Fact vs claim | L2 | Triangulate a project claim across official, independent and regulatory sources. | Label incentives and source dates. |
| R03 | Claim/risk classification | Fact vs claim | L3 | Handle conflicting sources without selecting the most exciting narrative. | State what would change the decision. |
| R04 | Claim/risk classification | Tokenomics/stablecoin failure | L1 | Identify supply, distribution, collateral and redemption claims. | A stable label does not eliminate issuer, reserve or liquidity risk. |
| R05 | Claim/risk classification | Tokenomics/stablecoin failure | L2 | Spot unlock concentration and dependency on a single mechanism. | Tokenomics is evidence to inspect, not a buy signal. |
| R06 | Claim/risk classification | Tokenomics/stablecoin failure | L3 | Analyze a fictional depeg/failure case using known/unknown/risk. | No price prediction; choose evidence request or no-action. |
| R07 | Claim/risk classification | Evidence/no-action | L1 | Choose the strongest source for a simple safety claim. | Source class and date matter. |
| R08 | Claim/risk classification | Evidence/no-action | L2 | Build a claim-evidence-unknown-risk board for a DeFi offer. | Unknowns remain visible; no forced conclusion. |
| R09 | Claim/risk classification | Evidence/no-action | L3 | Make a safe decision under urgency and incomplete evidence. | The correct action may be wait, verify or refuse. |

## 9. Ten evidence gates for earning 95

| Gate | Requirement | Pass evidence |
|---|---|---|
| G01 — Scope / taxonomy | All 27 seeds use the same entity schema: network, asset, address, key, wallet/account, custodian, protocol, interface, action, permission, fee, confirmation and evidence. | Schema lint passes 100%; no forbidden trading/deposit/P&L/real-asset fields. |
| G02 — Prerequisites | Every task declares prerequisites and cannot unlock a higher-risk concept from a score-only shortcut. | Dependency graph has no cycles; 0 unconditional unlocks in test traces. |
| G03 — Security veto | Wrong recipient/network, unsafe approval, fake support and seed-phrase disclosure are critical errors. | A critical error blocks mastery credit and triggers repair; no points for speed. |
| G04 — Decision quality | Applied tasks score observation, evidence, permission/recipient check, uncertainty and action boundary separately. | Scoring output explains each dimension; overall correctness cannot hide a critical safety miss. |
| G05 — Transfer | Each mechanic appears in three different surfaces and at least one novel delayed scenario. | Pass target: no-hint transfer with no critical error; target threshold ≥80% in pilot. |
| G06 — Calibration | Learner gives confidence before seeing correctness and receives confidence-gap feedback. | Pilot records calibration curve/Brier-style confidence error without using confidence as mastery alone. |
| G07 — Neutrality | Every claim has source class, date, incentive, evidence level and limitation; vendor claims are labelled. | No sponsored/vendor source can be the sole support for a safety or effectiveness claim. |
| G08 — Accessibility | All core tasks work by keyboard, with visible focus, text alternatives, non-colour cues, reduced motion and screen-reader labels. | Automated checks pass and moderated accessibility walkthrough finds 0 release-blocking defects. |
| G09 — Telemetry integrity | Events are consented, pseudonymous, versioned, idempotent and contain no seed phrases, private keys, balances or unnecessary PII. | Synthetic replay produces 100% expected events, 0 duplicates and 0 sensitive-field violations. |
| G10 — Production readiness | The vertical slice can run offline/without live wallet or chain and can be replayed from a content version. | Three clean deterministic replays; source, locale, legal and content expiry metadata present. |

## 10. Implementation order
1. Freeze schema, scoring rubric, critical-error list and content versioning before authoring prose.
2. Implement 27 seed objects with deterministic replay and no external network/wallet dependency.
3. Build Safety Kernel v2: refusal, verify-more, repair and critical-error veto.
4. Build three surface renderers over the same invariant task: wallet, exchange and bridge-like fictional UI.
5. Add English/Russian glossary parity and accessibility test fixtures before visual polish.
6. Add event contract, consent, deletion, idempotency and sensitive-field lint tests.
7. Run content neutrality review: source class, incentives, jurisdiction, date, counterclaim and expiry.
8. Run moderated novice alpha; measure primary outcomes at immediate, 48–72h and novel-transfer checkpoints.
9. Award the 95 score only if all ten gates pass; otherwise publish the failed category and repair plan.

## 11. What is still not claimed

Iteration 7 improves the strategy specification and makes the path to 95 falsifiable. It does not claim that users are already safe in real crypto markets, that the curriculum prevents scams, that a particular custody model is universally superior, or that regulatory protection applies equally in every jurisdiction. Those claims require external validation, legal review and longitudinal evidence.

**Final decision:** target **95/100** is accepted as the next design bar. The next irreversible commitment is not a live crypto feature; it is the deterministic, accessible, privacy-safe 27-seed alpha with measurable transfer and safety gates.

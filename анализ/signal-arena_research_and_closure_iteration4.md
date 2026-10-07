# SIGNAL ARENA — Исследование и закрытие критических вопросов, Iteration 4

**Дата:** 7 октября 2026  
**Назначение:** закрыть неохваченные блокеры, которые мешают переходу от design audit к реализации vertical slice и alpha-плану.  
**Связанные файлы:** `SIGNAL_ARENA_DECISION_FAQ.md` (Q001–Q088) и отчёт Iteration 3.  

## 0. Что означает «100% закрыть список»

В этой итерации «закрыто» означает не то, что уже написан production-код. Для каждого критического вопроса теперь есть: решение, артефакт-доказательство, зависимость, acceptance test, владелец следующего действия и условие возврата. Поэтому часть пунктов имеет статус **DECISION CLOSED / IMPLEMENTATION BLOCKED**, а юридические вопросы — **DECISION BOUNDED / EXTERNAL REVIEW REQUIRED**. Скрывать такие блокеры под статусом PASS нельзя.

### Результат итерации
- Проведён новый targeted evidence review по accessibility, learning analytics schema, GDPR/DPIA, assessment validity, pilot methodology, preregistration, dataset documentation, Telegram identity validation и secure logging.
- Закрыты решения по schema, scoring, mastery, events, client/server trust, replay, dataset cards, accessibility target, privacy minimum, AI boundary, pilot design и dependency graph.
- Сформулированы и прогнаны **50 targeted closure tests**; runtime и legal execution явно помечены как следующие блокеры.
- Все критические вопросы получили запись в FAQ Q072–Q088; незавершённые артефакты получили owner/trigger вместо бесконечного OPEN.

## 1. Новые источники evidence

| ID | Источник | Что изменило в решении |
|---|---|---|
| R4-01 | [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/) | WCAG 2.2 is a testable recommendation applicable to web and mobile; target AA for the slice, but do not claim conformance before audit. |
| R4-02 | [W3C WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/) | operational criteria for text alternatives, keyboard/focus, contrast, status messages, target size and motion. |
| R4-03 | [1EdTech Caliper Analytics](https://www.1edtech.org/standards/caliper) | common vocabulary for learning events; use as a model, not as a reason to import the full standard. |
| R4-04 | [Caliper 1.2 implementation/conformance](https://www.imsglobal.org/spec/caliper/v1p2/cert) | event id/type/actor/action/object/eventTime requirements and versioned event envelopes. |
| R4-05 | [ADL xAPI data model](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md) | actor/verb/object plus optional result/context/timestamp; useful conceptual reference for event shape. |
| R4-06 | [EUR-Lex GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679) | purpose limitation, data minimisation, privacy by design/default, records and security. |
| R4-07 | [ICO DPIA guidance](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/accountability-and-governance/guide-to-accountability-and-governance/data-protection-impact-assessments/) | scoring, systematic monitoring, profiling, innovative technology and data matching are DPIA-screening triggers; DPIA is a living document. |
| R4-08 | [Kane validity argument guide](https://pubmed.ncbi.nlm.nih.gov/25989405/) | separate scoring, generalisation, extrapolation and implications; Signal Arena may support formative scoring before any real-world extrapolation. |
| R4-09 | [CONSORT/SPIRIT resources](https://www.consort-spirit.org/) | protocol/reporting checklists; pilot should predefine feasibility objectives and reporting. |
| R4-10 | [Pilot progression/sample-size methodology](https://link.springer.com/article/10.1186/s40814-021-00770-x) | pilot size should follow feasibility objectives and progression criteria; do not treat a pilot as an efficacy trial. |
| R4-11 | [OSF preregistration guidance](https://help.osf.io/article/330-welcome-to-registrations) | lock hypotheses, outcomes, exclusions, analysis and if/then decision rules before viewing data. |
| R4-12 | [Datasheets for datasets overview](https://casrai.org/dictionary/term/datasheet-for-datasets) | document motivation, composition, collection, preprocessing, intended uses, limitations and maintenance. |
| R4-13 | [Telegram Mini Apps validation](https://core.telegram.org/bots/webapps) | validate initData server-side, check auth_date, and do not trust client-provided identity or state. |
| R4-14 | [OWASP Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) | enforce authorization on every request server-side, deny by default, test object ownership. |
| R4-15 | [OWASP Logging Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html) | do not log secrets/tokens/sensitive data; protect logs, sanitize untrusted values and restrict access. |
| R4-16 | [OpenTelemetry semantic events](https://opentelemetry.io/docs/specs/semconv/general/events/) | event names must be stable; timestamps represent occurrence, observed time is separate; attributes should be queryable and allowlisted. |

### Выводы research review
- Не нужно импортировать полный Caliper или xAPI: достаточно компактного versioned internal event contract, совместимого по базовой семантике actor/action/object/time, если этого хватает для текущего learning analytics.
- Client timestamps, client mastery flags и client Telegram identity не являются trusted inputs; сервер должен валидировать identity, ownership, state transition и point-in-time data access.
- WCAG 2.2 AA выбран как engineering target для vertical slice; conformance claim появится только после автоматизированной и ручной проверки.
- GDPR-подход требует data minimisation, purpose limitation, privacy by design/default и документированной обработки. DPIA screening обязателен; formal DPIA — до high-risk profiling/AI либо если это потребует legal review.
- Для assessment нужно разделять scoring, generalisation, extrapolation и implications. Signal Arena закрывает только formative scoring/generalisation hypothesis; extrapolation в реальную торговлю исключена.
- Pilot должен измерять feasibility и integrity, а не притворяться powered efficacy trial. Sample size обосновывается целями feasibility, а не произвольным числом или желанием получить p < .05.
- Dataset card/datasheet становится обязательным release artifact для historical replay, включая known limitations и disallowed uses.

## 2. Critical closure matrix

| ID | Критический вопрос | Каноническое решение | Статус | Нужен артефакт/тест | Зависимость |
|---|---|---|---|---|---|
| C01 | Что является canonical task schema? | Закрыто решением: versioned JSON/YAML schema с skill, family, tier, rubric_profile, hint_policy, timing, locale, accessibility, provenance/license и generator metadata. | Implementation blocker | Schema v1 + linter + one valid/invalid fixture | До content authoring |
| C02 | Как гарантировать, что 27 cells не превратятся в 27 копий? | Закрыто: 3 families × 3 tiers × surface/context variation; literal duplicates запрещаются validator-ом и same-skill/different-surface test. | Implementation blocker | 27 seed matrix + duplicate report | До Chapter 0 content freeze |
| C03 | Как считать process score? | Закрыто default rubric: evidence 30, context 20, invalidation 20, uncertainty/risk discipline 15, explanation 10, calibration 5; task profile может исключить неотносящийся компонент только через явное перераспределение веса. | Implementation blocker | Rubric table + scored examples + boundary cases | До mastery engine |
| C04 | Что такое critical error? | Закрыто: error, который invalidates the learning claim: future-data use, fabricated/missing evidence represented as fact, ignoring required invalidation on critical skill, or bypassing server state. Он может veto mastery независимо от среднего score. | Implementation blocker | Critical-error taxonomy + tests | До alpha |
| C05 | Как устроена mastery state machine? | Закрыто: introduced → practicing → provisional → verified → needs_review; provisional = 3 hint-free correct, ≥80, 2 contexts, no critical error; verified = delayed 48–72h + novel transfer. | Implementation blocker | State-transition table + unit tests | До pilot |
| C06 | Какой event contract нужен? | Закрыто: внутренний компактный контракт, Caliper/xAPI-inspired, не полная сертификация: event_id, event_name/version, actor_ref, session/attempt, content/version, occurred_at, observed_at, consent_scope, idempotency_key, allowlisted payload. | Implementation blocker | Event schema + contract tests | До analytics |
| C07 | Как отделить клиентское время от доверенного времени? | Закрыто: client elapsed — диагностический сигнал; server observed time и server sequence — источник порядка. Скорость не влияет на mastery. | Implementation blocker | Clock tampering and ordering tests | До time analytics |
| C08 | Можно ли доверять Telegram user data и client state? | Закрыто: нет. initData валидируется сервером, auth_date проверяется, user/attempt ownership проверяются на каждом request; client flags never grant access. | Implementation blocker | Telegram validation + authorization tests | До external alpha |
| C09 | Как закрыть look-ahead и forward scrub? | Закрыто: point-in-time server API; client получает observation window только до decision timestamp; future window и scrub request — hard reject + security event. | Implementation blocker | no_future_data suite + API authorization | До historical replay |
| C10 | Как документировать dataset? | Закрыто: Dataset Card/Datasheet обязателен: origin, owner, license, timeframe, sampling, preprocessing, hidden fields, known bias, allowed/disallowed use, hash, version, maintainer. | Implementation blocker | One completed card per dataset | До replay content |
| C11 | Какая accessibility target? | Закрыто: WCAG 2.2 AA as engineering target for web/Mini App slice; no conformance claim until manual + automated audit. Keyboard, focus, contrast, target size, text alternatives, status messages and reduced motion are P0. | Implementation blocker | Accessibility checklist + audit evidence | До external alpha |
| C12 | Какая privacy/data governance minimum? | Закрыто: data map, purpose/field inventory, pseudonymous analytics ID, consent scopes, retention/deletion workflow, access roles, processor list and breach process. Run DPIA screening; formal DPIA before high-risk profiling/AI or if legal review requires. | External/legal blocker | Data map + privacy review + DPIA decision | До telemetry with real users |
| C13 | Что может видеть AI? | Закрыто: no raw journal and no direct mastery authority. AI receives minimized, pseudonymous, consented aggregates/error tags only after human-approved pipeline. | Implementation blocker | AI data-boundary test; AI may be deferred | До any AI feature |
| C14 | Как закрыть logging security? | Закрыто: no tokens, initData, raw personal identifiers, secrets or unnecessary free text; security events are separated from learning analytics, access is audited, timestamps and tamper evidence retained. | Implementation blocker | log redaction and access tests | До external alpha |
| C15 | Какова validity claim у process score? | Закрыто: formative decision-training score only. Validate scoring and generalisation within task universe first; extrapolation to real-world trading is explicitly out of scope. | Research gate | Validity argument + alpha evidence | Before any efficacy claim |
| C16 | Как проектировать pilot sample? | Закрыто plan: usability tranche 8–12 novices + 3–5 experienced diagnostic users; feasibility/micro-experiment target 60 novices total, 30/condition as provisional, justified by feasibility and data-completeness objectives, not efficacy power. | Research artifact blocker | Protocol + recruitment/attrition criteria | До recruitment |
| C17 | Какие primary pilot endpoints? | Закрыто: primary = feasibility/integrity: completion, critical-error rate, abandonment, data completeness, p90 time, hint usage, delayed-follow-up rate. Secondary exploratory = process score, delayed recall, novel transfer, calibration gap. | Research artifact blocker | Analysis plan + metric definitions | До pilot |
| C18 | Как избежать p-hacking и post-hoc gates? | Закрыто: preregister hypotheses, outcomes, exclusions, missing-data policy and if/then go/no-go rules before pilot data inspection. | Research artifact blocker | OSF-style preregistration | До pilot |
| C19 | Как сравнивать repeated vs variable retrieval? | Закрыто: same theory, same allotted time, same skill and difficulty band; A repeats surface, B varies surface/context; both get delayed novel-transfer item. | Research artifact blocker | Locked item bank + assignment script | До micro-experiment |
| C20 | Какую localization можно выпускать? | Закрыто: English canonical first; Russian only after key parity, glossary review, human review of critical terms and bilingual item audit. Missing localization blocks RU but not EN slice. | Localization blocker for RU | Glossary + review log | До RU release |
| C21 | Нужно ли внедрять Caliper/xAPI полностью? | Закрыто: нет. Берём совместимые идеи полей/семантики, но internal contract проще и privacy-safe. Migration layer возможен после доказанной потребности. | Not a blocker | Document mapping only | Review after alpha |
| C22 | Нужна ли full admin до vertical slice? | Закрыто: нет. Сначала raw events + rules-based queries; admin MVP строится только по вопросам, которые alpha реально должна ответить. | Intentional dependency | Minimal dashboard spec | After event fixture |
| C23 | Когда включать AI? | Закрыто: после stable taxonomy, event quality and consent. AI is P2 and may be omitted from alpha. | Deferred by design | Trigger: enough labelled events + privacy approval | After alpha |
| C24 | Когда включать Stars/marketplace/energy? | Закрыто: не до learning MVP and alpha; no payment dependency in core slice. | Deferred by design | Trigger: validated learning core + legal/payment review | After alpha |
| C25 | Какие claims разрешены до alpha? | Закрыто: claims about design intent only. Prohibited: proven learning gain, retention, calibrated confidence, far transfer, predictive ability, accessibility conformance and production reliability. | Copy/release blocker | Claims checklist | Before any public page |
| C26 | Какой порядок реализации? | Закрыто dependency graph: governance → schemas → deterministic engine → Chapter 0 content → event pipeline → replay → accessibility/localization → QA → usability alpha → feasibility micro-pilot. | Implementation blocker | Tracked plan with owners/status | Immediately |

## 3. Канонические контракты, которые больше нельзя оставлять расплывчатыми

### 3.1 Task schema v1
```yaml
task_id: string
version: semver-or-immutable-revision
skill_key: string
family: recognize | apply | explain_transfer
tier: 1 | 2 | 3
surface_id: string
context_id: string
prerequisites: [skill_key]
rubric_profile: string
critical_error_rules: [rule_id]
hint_policy: learn | practice | prove | debrief
timing: {expected, target, max}
content_keys: {en: ..., ru: ...}
accessibility: {alt, labels, status_messages, reduced_motion}
dataset_ref: nullable
provenance_ref: nullable
license_ref: nullable
generator_seed: nullable
```

**Release rule:** item без rubric, prerequisite check, accessibility fields, version или required provenance не публикуется.

### 3.2 Process score v1
Default normalized score: **100 points**.
- Evidence selection/quality — 30.
- Context check — 20.
- Invalidation/boundary — 20.
- Uncertainty/risk discipline — 15.
- Structured explanation — 10.
- Confidence calibration — 5.

Профиль задачи может не проверять компонент, но это должно быть объявлено в `rubric_profile`, а вес перераспределён явно. Нельзя молча считать отсутствующий компонент нулём. Critical error veto действует независимо от score. Score оценивает качество reasoning, не прибыль, скорость или market outcome.

### 3.3 Event contract v1
```json
{
  "event_id": "uuid",
  "event_name": "task_submitted",
  "event_version": 1,
  "actor_ref": "pseudonymous-server-ref",
  "session_id": "uuid",
  "attempt_id": "uuid",
  "content_id": "task.signal_noise.001",
  "content_version": "1.0.0",
  "skill_key": "observation_vs_interpretation",
  "occurred_at_client": "untrusted-ISO-8601",
  "observed_at_server": "trusted-ISO-8601",
  "server_sequence": 42,
  "consent_scope": ["core_progress", "analytics_optional"],
  "idempotency_key": "stable-key",
  "payload": {"allowlisted": true}
}
```
Клиентское время хранится только для диагностики. `observed_at_server` и `server_sequence` используются для реконструкции. Не отправлять raw journal, initData, tokens, email, Telegram ID или свободный текст без отдельного approved purpose.

### 3.4 Privacy minimum
- Внутренний `actor_ref` — псевдоним; таблица связывания с Telegram identity отделена, ограничена и не попадает в analytics/AI.
- У каждого поля есть purpose, legal-basis decision, retention и deletion behavior.
- Core progress, optional analytics и optional AI analysis — разные consent scopes.
- Deletion runbook описывает raw events, aggregates, backups, exports и исключения.
- До real-user telemetry проводится DPIA screening; до AI/profiling — formal legal review и при необходимости DPIA.

### 3.5 Replay security contract
- Server derives allowed observation range from attempt state and decision timestamp.
- Client never submits a timestamp that expands the allowed range.
- All future-window requests are rejected before data serialization.
- Historical dataset, preprocessing, hash and license are immutable references.
- Replay result is continuation/debrief, never P&L or hypothetical profit.

## 4. 50 targeted closure tests

Эти проверки закрывают именно ранее неохваченные блокеры. `PASS by design` означает, что решение однозначно; `NEEDS RUNTIME/ARTIFACT/LEGAL` означает, что переход к следующему этапу невозможен без соответствующего доказательства.

| ID | Сценарий | Ожидаемое поведение | Результат | Следующий шаг |
|---|---|---|---|---|
| T4-01 | Task missing skill_key | Validator rejects publication | PASS by design | Implement schema linter |
| T4-02 | Task has family but no tier | Validator rejects publication | PASS by design | Add required-field test |
| T4-03 | Two items differ only in copy | Duplicate/surface test flags literal repeat | PASS by design | Similarity threshold fixture |
| T4-04 | Item has no rubric_profile | Runtime cannot score; release blocked | PASS by design | Rubric validator |
| T4-05 | Rubric omits in-scope component | Schema rejects incomplete score vector | PASS by design | Score completeness test |
| T4-06 | Correct option with weak evidence | Outcome may be right; process score remains low | PASS by design | Boundary example in rubric |
| T4-07 | Wrong option with sound no-trade process | Process score can pass where item allows it | PASS by design | Add no-trade seed |
| T4-08 | Hint used before submit | Attempt cannot count toward provisional | PASS by design | State transition test |
| T4-09 | Three correct answers in one context | Not verified; context requirement unmet | PASS by design | Mastery counter test |
| T4-10 | Critical error plus score 95 | Mastery vetoed; needs_review/repair | PASS by design | Critical-error gate |
| T4-11 | Delayed recall item is literal copy | Test invalid; pool rejects same surface | PASS by design | Recall item validator |
| T4-12 | Transfer item changes surface and context | Same skill can be assessed | PASS by design | surface/context fixtures |
| T4-13 | Client submits mastery=true | Server ignores client claim | PASS by design | Tampered payload test |
| T4-14 | User requests another user's attempt | Server denies object ownership | PASS by design | Authorization integration test |
| T4-15 | Invalid Telegram initData | Request denied; safe security event only | PASS by design | Telegram HMAC/auth_date test |
| T4-16 | Expired auth_date | Request denied or re-auth required | PASS by design | Clock-window test |
| T4-17 | Future dataset segment requested | Hard reject; no bytes returned | PASS by design | no_future_data test |
| T4-18 | Client forward-scrubs timeline | No API path exists for future observations | PASS by design | endpoint/fuzz test |
| T4-19 | Historical item lacks dataset hash | Release blocked | PASS by design | Provenance validator |
| T4-20 | License says non-commercial only | Dataset excluded from commercial candidate | PASS by design | License gate fixture |
| T4-21 | Dataset card omits sampling window | Card incomplete; replay blocked | PASS by design | Datasheet checklist |
| T4-22 | Client clock is changed by 30 minutes | Server ordering remains valid; time not used as score | NEEDS RUNTIME | Clock-tamper test |
| T4-23 | Same event delivered twice | One logical event/attempt after deduplication | NEEDS RUNTIME | Idempotency integration test |
| T4-24 | Out-of-order network delivery | Server sequence and occurred_at preserve reconstruction | NEEDS RUNTIME | Event ordering fixture |
| T4-25 | Event has unknown name | Reject or quarantine; never silently aggregate | PASS by design | Allowlist test |
| T4-26 | Event contains raw journal | Payload rejected/redacted unless explicit approved path | PASS by design | Payload privacy test |
| T4-27 | Analytics consent withdrawn | New optional analytics stop; required account/security records handled separately by policy | NEEDS LEGAL/ RUNTIME | Consent-state test |
| T4-28 | Deletion request arrives | User record map identifies raw events, aggregates and deletion behavior | NEEDS ARTIFACT | Deletion runbook + test |
| T4-29 | Log contains initData/token | CI redaction test fails build | PASS by design | Secret scanner |
| T4-30 | Admin access by non-admin | Denied and logged without exposing learner data | NEEDS RUNTIME | RBAC/ABAC test |
| T4-31 | AI receives direct Telegram ID | Pipeline rejects non-pseudonymous identifier | PASS by design | AI boundary test |
| T4-32 | AI suggests mastered | UI labels it hypothesis; cannot mutate mastery | PASS by design | Permission/state test |
| T4-33 | Screen reader encounters chart | Equivalent text description and structured data available | NEEDS RUNTIME | WCAG audit |
| T4-34 | Keyboard user submits task | Focus order and visible focus work without pointer | NEEDS RUNTIME | Keyboard walkthrough |
| T4-35 | Contrast is adequate but color is only error cue | State still understandable without color | NEEDS RUNTIME | Contrast/non-color test |
| T4-36 | Status changes after hint | Assistive technology receives status message | NEEDS RUNTIME | WCAG status-message test |
| T4-37 | Motion is disabled | Core information and progression remain available | NEEDS RUNTIME | Reduced-motion test |
| T4-38 | English key exists, Russian key missing | RU publication blocked; EN unaffected | PASS by design | Locale linter |
| T4-39 | Russian term changes rubric meaning | Bilingual review blocks publication | PASS by design | Glossary diff |
| T4-40 | Pilot participant drops after baseline | Missing-data rule is applied as preregistered, not chosen post hoc | PASS by design | Analysis-plan fixture |
| T4-41 | Pilot recruitment lower than target | GO/NO-GO uses feasibility CI and recruitment rule | PASS by design | Progression decision tree |
| T4-42 | Pilot has high completion but no delayed follow-up | Feasibility fails for verified mastery claim | PASS by design | Follow-up gate |
| T4-43 | Variable group gets harder items | Randomization/item-band lock prevents confounding | NEEDS ARTIFACT | Locked item bank |
| T4-44 | Groups have different session time | Protocol flags fidelity violation; no efficacy inference | PASS by design | Time budget logging |
| T4-45 | Effect is positive but CI wide | Report uncertainty; do not declare proven efficacy | PASS by design | Reporting template |
| T4-46 | Process score correlates with outcome only by chance | Outcome independence remains in rubric | PASS by design | Outcome-independence fixture |
| T4-47 | Public copy says 'improves trading skill' | Claims gate blocks publish | PASS by design | Copy scanner/reviewer |
| T4-48 | Replay works but license review pending | Historical replay remains disabled | PASS by design | Release dependency gate |
| T4-49 | Accessibility audit pending but usability looks good | External alpha remains blocked for unresolved P0 accessibility issues | PASS by design | Gate dashboard |
| T4-50 | All artifacts complete | Run integrated smoke test, then moderated usability alpha; no automatic efficacy claim | PASS by plan | Go/No-Go meeting and signed checklist |

## 5. План реализации с зависимостями

### Phase 0 — Governance lock
**Закрывает:** C12, C14, C25, часть C08.  
**Deliverables:** data map, consent scopes, privacy/legal checklist, claims checklist, Telegram identity policy, secret/logging policy, decision owners.  
**Blocker:** без этой фазы нельзя собирать real-user analytics или запускать внешний alpha. Synthetic/local development разрешён без real identifiers.

### Phase 1 — Schema and deterministic core
**Закрывает:** C01–C07.  
**Deliverables:** task schema v1, rubric profiles, critical-error taxonomy, mastery state machine, event contract, validators, fixtures, unit tests.  
**Blocker:** без этого нельзя замораживать 27 cells и нельзя считать mastery/analytics воспроизводимыми.

### Phase 2 — Chapter 0 content
**Закрывает:** C02, C03, C20 частично.  
**Deliverables:** Chapter 0 theory, 27 seeds for three mechanics, hints, structured explanation, debrief, English canonical copy, Russian draft/glossary.  
**Dependency:** Phase 1; historical replay не нужен для first synthetic items.

### Phase 3 — Trusted telemetry and minimal admin
**Закрывает:** C06–C08, C13–C14, C22.  
**Deliverables:** server-side event ingestion, idempotency, consent filters, pseudonymous IDs, retention/deletion hooks, rules-based queries, item/version funnel.  
**Blocker:** AI не нужен; admin строится после появления validated fixtures.

### Phase 4 — Replay and accessibility
**Закрывает:** C09–C11.  
**Deliverables:** no_future_data suite, forward-scrub denial, dataset cards, license registry, replay audit trail, WCAG 2.2 AA checklist and manual audit.  
**Blocker:** historical replay disabled until every dataset passes provenance/license tests; external alpha disabled until P0 accessibility defects are zero.

### Phase 5 — Internal smoke and moderated usability alpha
**Закрывает:** implementation evidence for C01–C14.  
**Plan:** 8–12 novice users for first-use usability; 3–5 experienced users for diagnostic path only. Observe terminology, first-screen comprehension, hint use, abandonment, time, error recovery and accessibility barriers. No efficacy claim.

### Phase 6 — Feasibility micro-experiment
**Закрывает:** C15–C19 and informs C20.  
**Provisional target:** 60 novices total, 30/condition, subject to recruitment/attrition feasibility; this is not powered efficacy proof.  
**Condition A:** same theory + repeated same-format retrieval.  
**Condition B:** same theory + variable retrieval across surface/context.  
**Controls:** same allotted time, same skill, locked difficulty band, equal feedback/hint policy, delayed novel-transfer item at 48–72h.  
**Primary feasibility outcomes:** recruitment, completion, data completeness, p90 time, abandonment, critical errors, follow-up rate.  
**Exploratory outcomes:** process score, delayed recall, novel transfer, calibration gap. Report estimates and uncertainty; do not announce proven effectiveness.

## 6. Alpha go/no-go decision tree

- IF any future-data leak, unauthorized attempt access, secret/token logging, unlicensed dataset or critical consent defect → NO-GO; fix before any external data.
- IF Chapter 0 has terminology confusion, critical accessibility defect or state loss → NO-GO for external alpha; return to content/UI phase.
- IF event completeness/idempotency is insufficient → NO-GO for measurement claims; usability-only testing may continue with explicit limitation.
- IF delayed follow-up cannot be run → do not label any skill verified; only immediate practice data may be reported.
- IF recruitment/retention fails predefined feasibility rule → STOP/REDESIGN, do not interpret condition difference as efficacy.
- IF variable retrieval does not outperform repeated format descriptively → inspect task difficulty and item equivalence before adding game mechanics.
- IF all safety, integrity, usability and telemetry gates pass → proceed to a larger preregistered study design, still without real-trading or profit claims.

## 7. Что заранее отложено и когда к этому вернуться

| Пункт | Почему не сейчас | Trigger возврата |
|---|---|---|
| Full Caliper/xAPI adoption | internal event contract достаточен для MVP | внешний LRS/integration requirement или B2B scope |
| AI error clustering | нужна стабильная taxonomy и consented data | labelled event volume + privacy approval |
| Mastery decay | delayed recall сначала нужен как measurement | alpha data о forgetting/review burden |
| Full marketplace/Stars | не нужен learning core и создаёт legal/payment scope | validated learning core + legal/payment review |
| Professional mode/B2B | не соответствует MVP audience | отдельный product decision после novice evidence |
| Far transfer | нет текущего valid outcome и создаёт overclaim | отдельное study с новым domain и legal/ethical review |
| Production historical catalog | provenance/license and no-lookahead cost | approved dataset cards and replay audit |

## 8. Финальный список блокеров перед следующей работой
1. Schema v1, rubric profiles, critical-error rules and validators.
2. Mastery state machine and deterministic score unit tests.
3. Event contract, server ingestion, idempotency and consent filter.
4. Telegram initData server validation and per-request object authorization.
5. Data map, privacy/claims checklist, DPIA screening and deletion/retention runbook.
6. Chapter 0 English canonical content and 27-cell seed matrix.
7. Russian glossary/human review if Russian release is in scope.
8. No-future-data/forward-scrub tests and one approved Dataset Card before replay.
9. WCAG 2.2 AA target checklist plus manual audit of the first flow.
10. Preregistered usability/feasibility protocol with progression criteria.

## 9. Non-claims and remaining uncertainty

После Iteration 4 список критических вопросов закрыт на уровне решений и dependency plan, но не на уровне production evidence. Не утверждается, что текущая система уже соответствует WCAG, GDPR, Telegram security, future-data isolation, learning gain, retention, transfer, calibration или reliability. Эти claims требуют соответствующих артефактов и alpha evidence. Единственный корректный следующий шаг — реализовывать фазы 0–4 по порядку, а не расширять игру в стороны.

**Главный вывод:** работа больше не блокируется неопределёнными design questions. Она блокируется конкретными артефактами: schema, deterministic engine, trusted events, privacy/legal review, replay tests, accessibility audit и preregistered pilot plan. Именно их нужно сделать следующими.

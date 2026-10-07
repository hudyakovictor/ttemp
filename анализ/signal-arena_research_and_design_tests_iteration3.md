# SIGNAL ARENA — Research Review и 50 tabletop/design tests, Iteration 3

**Дата:** 7 октября 2026  
**Статус:** закрытый evidence review + design audit; это не runtime-проверка и не доказательство эффективности продукта.  
**Связанные канонические решения:** `SIGNAL_ARENA_DECISION_FAQ.md`, Q001–Q071.  

## 0. Executive summary

Выполнена третья итерация Signal Arena: целевой review внешних источников, 200 проверок дизайна и 50 tabletop/acceptance tests для Chapter 0 и vertical slice. Внешний поиск дал примерно 150 поисковых результатов; после дедупликации это меньше 150 уникальных публикаций/страниц. Я не считаю механический добор до «ровно 150 уникальных» полезным: открытые продуктовые решения уже покрыты первичными/систематическими источниками, а неизвестные runtime- и learning-эффекты должен проверить alpha.

### Главные решения этой итерации
- Research подтверждает spacing, retrieval, corrective feedback и variable retrieval как дизайн-опоры, но не доказывает эффективность именно Signal Arena.
- Expanding schedule не фиксируется как универсально лучший; для MVP — regular/adaptive spacing с последующей калибровкой.
- Variable retrieval и same-skill/different-surface должны быть в vertical slice, иначе mastery будет измерять узнавание skin.
- Mastery требует correction и parallel assessment; literal repetition запрещена.
- Confidence — calibration signal с retrospective feedback, не самостоятельное доказательство знания.
- Serious-game framing не даёт права обещать far transfer, retention или financial competence.
- Historical replay блокируется без point-in-time provenance, no_future_data, immutable version и license gate.
- AI остаётся аналитическим слоем; deterministic rubric — источник истины для mastery.
- Telegram, privacy, Stars и data minimization вынесены в отдельный legal/product gate; не добавляются в core learning MVP.

### Итог по проверкам
- **200/200** пунктов рассмотрены на уровне спецификации.
- **50/50** tabletop tests сформулированы и прогнаны вручную по текущему FAQ/дизайн-контракту.
- **Не runtime-tested:** latency, Telegram lifecycle, screen reader, actual future-data isolation, data deletion, event idempotency и реальный learning gain.
- **P0 перед alpha:** content schema/validator, rubric, Chapter 0 prototype, event contract, no-future-data test, provenance/license registry, privacy/data map и accessibility acceptance.

## 1. Evidence register

Это не список 150 уникальных ссылок. Ниже — 20 отобранных anchor sources, на которых основаны решения; повторные и менее первичные результаты не превращены в искусственный библиографический объём.

| ID | Источник | Что использовано |
|---|---|---|
| R01 | [Karpicke, Retrieval-Based Learning review](https://learninglab.psych.purdue.edu/downloads/2025/2025_Karpicke_Retrieval_Based_Learning_Review.pdf) | retrieval practice, feedback, delayed recall |
| R02 | [Spacing meta-analysis](http://www.lscp.net/persons/ramus/docs/EPR20.pdf) | spacing beats massing; expanding schedule is not universally superior |
| R03 | [Variable retrieval and transfer](https://static1.squarespace.com/static/5c8baca1e5f7d136349ea789/t/5e739a3d46338e7dec37aaf6/1584634429337/Butler+et+al+2017.pdf) | varied contexts support transfer better than literal repetition |
| R04 | [Mastery learning meta-analysis](https://www.uky.edu/~gmswan3/575/kulik_kulik_Bangert-Drowns_1990.pdf) | mastery learning is promising, with time and measurement trade-offs |
| R05 | [Metacognitive monitoring meta-analysis](https://link.springer.com/article/10.1007/s10648-024-09936-4) | external standards and explicit instruction improve monitoring accuracy |
| R06 | [Serious games systematic review](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2025.1432982/full) | engagement and learning effects can be positive, but transfer claims remain limited |
| R07 | [Serious games and far transfer review](https://pubmed.ncbi.nlm.nih.gov/42199316/) | near transfer is more plausible than far transfer; long-term effects need direct testing |
| R08 | [Gamification meta-analysis 2020](https://eric.ed.gov/?id=EJ1266144) | effects are generally positive but dependent on design and context |
| R09 | [Gamification meta-analysis 2024](https://bera-journals.onlinelibrary.wiley.com/doi/10.1111/bjet.13471?af=R) | gamification elements do not have a universally positive effect |
| R10 | [Backtesting with historical market data](https://portfoliooptimizationbook.com/book/8.4-backtesting-market-data.html) | chronological split, timestamp integrity and leakage controls are required |
| R11 | [Market-data licensing overview](https://www.coingecko.com/learn/best-historical-crypto-data-apis) | API availability does not imply commercial redistribution rights |
| R12 | [Telegram Mini Apps Terms](https://telegram.org/tos/mini-apps) | Mini Apps and service providers require explicit data/privacy responsibility |
| R13 | [Telegram Stars Terms](https://telegram.org/tos/stars) | digital goods/services inside Telegram require Stars-compatible flows |
| R14 | [Telegram Payments API](https://core.telegram.org/bots/payments-stars) | payment, refund and support implementation requirements |
| R15 | [Worked examples and guidance fading](https://journals.sagepub.com/doi/10.1177/0963721420922183) | support should vary with prior knowledge; fading must be adaptive |
| R16 | [Guidance fading review](https://cogscisci.wordpress.com/wp-content/uploads/2019/08/sweller-guidance-fading.pdf) | too little or too much guidance can both harm learning |
| R17 | [Transfer and retrieval review](https://pdf.retrievalpractice.org/transfer/Pan_Rickard_2018.pdf) | retrieval conditions and context variation matter for transfer |
| R18 | [Confidence calibration review](https://www.sciencedirect.com/science/article/abs/pii/S0959475218308788) | calibration requires feedback against an external standard, not confidence alone |
| R19 | [Telegram Bot Developer Terms](https://telegram.org/tos/bot-developers?setln=fa) | bot/Mini App operator responsibilities require separate terms and policy review |
| R20 | [Mastery/corrective instruction overview](https://tguskey.com/wp-content/uploads/Mastery-Learning-1-Mastery-Learning.pdf) | correction should be followed by a parallel assessment, not only repetition |

### Ограничения evidence review
1. Источники обобщают learning science и platform/legal constraints, но не являются валидацией конкретного UI, taxonomy или dataset Signal Arena.
2. Publication/meta-analysis evidence не превращает hypotheses о retention, transfer и engagement в подтверждённые claims.
3. Для юридических вопросов источники задают engineering checklist; финальное решение требует юриста по целевой юрисдикции и актуальной проверки Telegram terms.
4. Для historical data отдельная проверка лицензии обязательна для каждого файла/провайдера; обзор рынка данных не является лицензией.

## 2. Решения, добавленные в канонический FAQ

Q059–Q071 уже добавлены в `/home/user/SIGNAL_ARENA_DECISION_FAQ.md`. Коротко: не добирать 150 уникальных источников механически; regular/adaptive spacing; variable retrieval; adaptive fading; parallel corrective assessment; calibrated confidence; no far-transfer claims; rewards secondary to mastery; Telegram/Stars/legal review; license gate; same-skill/different-surface; micro-experiment с repeated-format control vs variable retrieval.

## 3. 200 design audit checks

Статусы означают: **PASS** — решение совместимо с каноном; **NEEDS ARTIFACT** — направление принято, но нужен конкретный schema/prototype/test; **P0/P1/P2** — порядок до alpha/после alpha.

### D01. Цель обучения и валидность

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 001 | Поведение формулируется наблюдаемо | Каждый learning objective переводится в действие: выделить evidence, обозначить uncertainty, выбрать boundary или объяснить decision. | PASS / P0 |
| 002 | Decision не равен прогнозу | Задание проверяет качество процесса, а не угадывание дальнейшего движения. | PASS / P0 |
| 003 | Process score выше outcome | Outcome показывается как учебное продолжение; он не меняет базовую оценку reasoning. | PASS / P0 |
| 004 | Цель соответствует новичку | Первый slice не требует знания терминов рынка и не оптимизируется под профессионала. | PASS / P0 |
| 005 | Есть skill taxonomy | Recognize, Apply и Explain/Transfer связаны с конкретным skill key и rubric. | NEEDS ARTIFACT / P0 |
| 006 | Transfer отделён от engagement | Красивый game loop не считается доказательством переноса. | PASS / P0 |
| 007 | Delayed recall входит в definition of done | Проверка через 48–72 часа обязательна для verified, но пока является пилотной гипотезой. | PASS / P1 |
| 008 | No-trade является валидным действием | Недостаток evidence не трактуется как пассивность или поражение. | PASS / P0 |
| 009 | Cue dependence измеряется | Новая поверхность, distractor и layout должны отличать понимание от узнавания. | NEEDS ARTIFACT / P1 |
| 010 | Гипотезы явно маркированы | Любые learning-gain, retention и runtime claims до alpha помечены как hypothesis. | PASS / P0 |

### D02. Chapter 0 и первый опыт

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 011 | Порядок от concrete к abstract | Сначала time/sequence и visual change, затем observation/interpretation, candle representation и uncertainty. | PASS / P0 |
| 012 | Нет необъяснённых терминов | До задания не появляются invalidation, leverage, exposure и другие поздние слова. | PASS / P0 |
| 013 | Time/sequence проверяется отдельно | Игрок сначала читает изменение объекта, не интерпретируя его как market signal. | PASS / P0 |
| 014 | Observation отделено от interpretation | UI требует разложить ответ на видимое и предположительное. | PASS / P0 |
| 015 | Visual change имеет один основной distractor | Первый пример не перегружен цветами, индикаторами и несколькими переменными. | PASS / P0 |
| 016 | Uncertainty объясняется через missing evidence | Неопределённость не подаётся как эмоциональный страх или проигрыш. | PASS / P0 |
| 017 | No-trade демонстрируется как корректный выбор | Есть пример, где stop/insufficient evidence является лучшим process outcome. | PASS / P0 |
| 018 | Worked example доступен | Новичок видит разобранный пример до самостоятельной попытки. | NEEDS ARTIFACT / P0 |
| 019 | Первый экран имеет один следующий шаг | Скрываются Skill Tree, energy, marketplace и профессиональная навигация. | NEEDS ARTIFACT / P0 |
| 020 | Пауза не ломает прогресс | Chapter 0 сохраняет checkpoint и не наказывает пользователя за interruption. | NEEDS ARTIFACT / P1 |

### D03. Task schema и контентные данные

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 021 | ID и version immutable | Task ID, version и content hash позволяют воспроизводить старый ответ. | NEEDS ARTIFACT / P0 |
| 022 | Skill key обязателен | Без skill tag item не попадает в mastery pipeline. | PASS / P0 |
| 023 | Family и tier обязательны | Каждый item принадлежит Recognize/Apply/Explain и Tier 1/2/3. | PASS / P0 |
| 024 | Provenance обязателен для replay | Источник, лицензия, preprocessing и dataset version сохраняются рядом с item. | PASS / P0 |
| 025 | Expected/target/max time разделены | Они не используются как штраф за медленность. | PASS / P1 |
| 026 | Evidence keys формализованы | Рубрика ссылается на evidence atoms, а не только на правильную букву. | NEEDS ARTIFACT / P0 |
| 027 | Critical error явно задан | Например, игнорирование invalidation для critical skill. | NEEDS ARTIFACT / P0 |
| 028 | Hint ladder хранится в данных | Learn, Practice, Prove и Debrief используют разные уровни помощи. | PASS / P0 |
| 029 | Locale keys отделены от UI | Canonical English и русская локализация не зашиты в механику. | PASS / P1 |
| 030 | Schema validation блокирует неполный item | Item без rubric, accessibility text или provenance не публикуется. | NEEDS ARTIFACT / P0 |

### D04. Task families и interaction

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 031 | Recognize существует отдельно | Первые задачи проверяют распознавание без маскировки под сложный prediction. | PASS / P0 |
| 032 | Apply требует действия | Игрок выделяет evidence или выбирает следующий шаг, а не только букву. | PASS / P0 |
| 033 | Explain/Transfer использует структуру | Observation, evidence, invalidation и confidence вводятся поэтапно. | PASS / P0 |
| 034 | Structured interaction после 3–5 простых items | Multiple choice не остаётся единственным форматом. | PASS / P0 |
| 035 | Confidence стоит до submit | Игрок фиксирует уверенность после observation/evidence и до feedback. | PASS / P1 |
| 036 | Invalidation является отдельным полем | Для релевантного skill ответ должен содержать boundary или insufficient evidence. | NEEDS ARTIFACT / P0 |
| 037 | Поверхность меняется | Skill повторяется с новым layout, dataset, wording и distractors. | PASS / P0 |
| 038 | Введение контролируемое | Synthetic examples используются только там, где нужна одна переменная. | PASS / P0 |
| 039 | Distractor budget ограничен | Дистракторы не вводят непрошедшие понятия и не проверяют чтение текста вместо skill. | NEEDS ARTIFACT / P1 |
| 040 | Items не подсказывают друг друга | Порядок и формулировка не позволяют решить следующий вопрос по предыдущему ответу. | NEEDS ARTIFACT / P1 |

### D05. Difficulty и адаптация

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 041 | Три tier различимы | Tier 1 — одна переменная, Tier 2 — контекст и distractor, Tier 3 — transfer/uncertainty. | PASS / P0 |
| 042 | Сложность не равна длине | Время и количество кликов не являются единственным proxy. | PASS / P1 |
| 043 | Скорость не оптимизируется | Быстрый guess не приносит больше competence credit. | PASS / P0 |
| 044 | Time budget калибруется | Expected, target и max пересматриваются по median и p90 alpha. | NEEDS ARTIFACT / P1 |
| 045 | Новичку можно дать дополнительную опору | Adaptive support не меняет learning objective. | PASS / P1 |
| 046 | Diagnostic path не является безусловным skip | Опытный игрок проходит 8–12 items, 3 families, 2 contexts и transfer item. | PASS / P0 |
| 047 | Partial skip безопасен | Провал открывает missing theory units, а не закрывает всю главу. | PASS / P0 |
| 048 | Есть floor и ceiling | Система не оставляет новичка на недоступном tier и не скучает опытному. | NEEDS ARTIFACT / P1 |
| 049 | Difficulty tags проверяемы | Authoring rubric объясняет, почему item Tier 2, а не просто помечает его. | NEEDS ARTIFACT / P1 |
| 050 | p90 — trigger, не штраф | Превышение p90 запускает проверку ясности и сложности, а не наказание игрока. | PASS / P1 |

### D06. Hints, examples и repair

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 051 | Hint ladder есть | Support движется от attention cue к worked micro-example и затем к explanation. | PASS / P0 |
| 052 | Hintful attempt не даёт mastery credit | Он влияет на diagnosis и следующую поддержку, но не подтверждает самостоятельность. | PASS / P0 |
| 053 | Hint usage логируется | Сохраняются уровень, timestamp, item version и состояние до hint. | NEEDS ARTIFACT / P0 |
| 054 | Hints объясняют evidence | Подсказка не говорит только правильную кнопку и не превращается в answer reveal. | NEEDS ARTIFACT / P0 |
| 055 | Repair привязан к error tag | После ошибки меняется формат или context, а не только текст feedback. | PASS / P1 |
| 056 | Micro-repair короткий | Repair не блокирует пользователя длинным повторным курсом. | PASS / P1 |
| 057 | Нет часового lockout | Ошибки ведут к repair и needs_review, но не к искусственному ожиданию. | PASS / P0 |
| 058 | Guidance fading адаптивен | После provisional mastery support снимается, у новичка не происходит резкий обрыв. | PASS / P1 |
| 059 | Worked examples не бесконечны | После примера следует retrieval, иначе проверяется только узнавание. | PASS / P0 |
| 060 | Hint abuse диагностируется | Частые hints не караются, но учитываются при решении о mastery. | PASS / P1 |

### D07. Mastery state machine

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 061 | Состояния определены | introduced → practicing → provisional → verified → needs_review реализуется без скрытых переходов. | PASS / P0 |
| 062 | Provisional имеет 3 самостоятельных решения | Условия: hint-free, process score ≥80%, 2 contexts, no critical error. | PASS / P0 |
| 063 | Verified требует delayed recall | Проверка через 48–72 часа отделена от первой сессии. | PASS / P1 |
| 064 | Critical skill требует до 5 подтверждений | Invalidation/risk-critical items используют более строгий threshold. | PASS / P0 |
| 065 | Два context обязательны | Три правильных ответа в одном skin не закрывают skill. | PASS / P0 |
| 066 | Transfer item обязателен | Новый layout/dataset проверяет same-skill/different-surface. | PASS / P0 |
| 067 | needs_review локален | Провал одного skill не откатывает всю главу и не стирает открытые карты. | PASS / P0 |
| 068 | Ошибка ведёт к correction | Перед повторной попыткой появляется micro-repair или другая репрезентация. | PASS / P1 |
| 069 | Confidence не является mastery | Она входит в calibration gap и не может одна открыть skill. | PASS / P0 |
| 070 | Mastery versioned | Изменение rubric или content version не переписывает бесследно старый результат. | NEEDS ARTIFACT / P0 |

### D08. Feedback, rubric и debrief

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 071 | Feedback после evidence | Система сначала отражает, что было видно, и только затем оценивает action. | PASS / P0 |
| 072 | Evidence отделено от answer key | Игрок видит, какой observation был полезным, даже если action был неверен. | PASS / P0 |
| 073 | Есть counterfactual | Debrief показывает, что могло бы опровергнуть гипотезу. | PASS / P0 |
| 074 | Invalidation объясняется | Boundary не выглядит как магическое число или trading instruction. | PASS / P0 |
| 075 | Outcome не переписывает процесс | Удачный случайный outcome не превращается в mastery. | PASS / P0 |
| 076 | Weights rubric заданы | Evidence, context, invalidation, risk discipline, explanation и calibration имеют прозрачные веса. | NEEDS ARTIFACT / P0 |
| 077 | Rubric читаема для автора | Редактор может понять, почему ответ получил score. | NEEDS ARTIFACT / P0 |
| 078 | Нет скрытого speed penalty | Время может быть diagnostic signal, но не отнимает competence без rationale. | PASS / P0 |
| 079 | Calibration feedback retrospective | После результата игрок сравнивает confidence с process score и external standard. | PASS / P1 |
| 080 | Debrief не перегружен | Пять вопросов: visible, unknown, process, invalidation, error. | PASS / P1 |

### D09. Retrieval, spacing и transfer

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 081 | Spacing используется | Между initial practice, delayed recall и review есть интервалы. | PASS / P0 |
| 082 | Expanding schedule не объявлен законом | MVP использует regular/adaptive spacing и проверит schedule отдельно. | PASS / P1 |
| 083 | Variable retrieval встроен | Один принцип появляется в нескольких контекстах и форматах. | PASS / P0 |
| 084 | Context variation намеренная | Меняются surface features, но сохраняется core skill. | PASS / P0 |
| 085 | Layout variation тестируется | Same-skill/different-surface — отдельный acceptance test. | PASS / P0 |
| 086 | Wording variation безопасна | Формулировка меняется, но glossary не меняет смысл canonical term. | NEEDS ARTIFACT / P1 |
| 087 | Novel distractor появляется позднее | Новый distractor не вводится до того, как базовый skill понятен. | PASS / P0 |
| 088 | Delayed recall не заменён immediate score | Высокий score первой сессии не считается окончательным. | PASS / P0 |
| 089 | Near-transfer — основной pilot endpoint | Измеряется новый item в близкой domain context. | PASS / P1 |
| 090 | Far-transfer — только гипотеза | Никаких обещаний переноса в реальную торговлю до отдельного исследования. | PASS / P0 |

### D10. Historical replay и data integrity

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 091 | Decision timestamp является границей | Сервер отдаёт только observations до decision timestamp. | PASS / P0 |
| 092 | Есть no_future_data test | Автотест обнаруживает поля, которые относятся к future window. | NEEDS ARTIFACT / P0 |
| 093 | Forward scrubbing запрещён | Клиент не может запросить будущий segment до submit. | NEEDS ARTIFACT / P0 |
| 094 | Дата скрыта, metadata не удалена | Игрок не видит date/ticker, audit layer видит. | PASS / P0 |
| 095 | Provenance полная | Source, license, preprocessing, version и timestamp сохраняются. | NEEDS ARTIFACT / P0 |
| 096 | License gate обязателен | Unclear commercial/redistribution rights блокируют production candidate. | PASS / P0 |
| 097 | Sampling bias помечен | Historical dataset не выдаётся как репрезентативный рынок без анализа selection. | NEEDS ARTIFACT / P1 |
| 098 | Outcome показан без P&L | Continuation используется для debrief, не для расчёта гипотетической прибыли. | PASS / P0 |
| 099 | Seed и replay version сохраняются | Одинаковая задача воспроизводима после обновления клиента. | NEEDS ARTIFACT / P0 |
| 100 | Audit trail доступен редактору | Можно восстановить, какие данные видел пользователь и когда. | NEEDS ARTIFACT / P0 |

### D11. Risk abstraction без денег

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 101 | Нет real/virtual money | MVP не содержит deposit, balance, P&L, trading или profit leaderboard. | PASS / P0 |
| 102 | Exposure multiplier объясняется абстрактно | Leverage — sensitivity/exposure, не путь к заработку. | PASS / P0 |
| 103 | Invalidation boundary является ядром | Stop-loss заменён на границу, за которой hypothesis no longer holds. | PASS / P0 |
| 104 | Risk unit не выглядит валютой | Risk units — условная шкала, не скрытый виртуальный счёт. | NEEDS ARTIFACT / P0 |
| 105 | Leverage не требует финансовой формулы | Сначала qualitative exposure, формулы — только если нужны учебной цели. | PASS / P1 |
| 106 | Stop-loss не превращается в совет | Используется как decision boundary в учебном объекте. | PASS / P0 |
| 107 | Uncertainty видима | Игрок может выбрать insufficient evidence и объяснить недостающий сигнал. | PASS / P0 |
| 108 | Copy не обещает outcome | Нет implied return, winning strategy или predictive certainty. | PASS / P0 |
| 109 | Safety language проверяется | Risk terms и disclaimers проходят human/legal review до публикации. | NEEDS ARTIFACT / P0 |
| 110 | Critical risk error маркируется | Игнорирование invalidation не теряется в среднем score. | PASS / P0 |

### D12. Cognitive bias design

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 111 | Confirmation bias распознаваем | Есть item, где игрок должен искать disconfirming evidence. | NEEDS ARTIFACT / P1 |
| 112 | Recency bias отделён от trend | Последняя точка не получает автоматический приоритет. | NEEDS ARTIFACT / P1 |
| 113 | Anchoring проверяется | Первичное число/ярлык не должен определять ответ без evidence. | NEEDS ARTIFACT / P1 |
| 114 | Outcome bias контролируется | Удачный/неудачный continuation не меняет process rubric. | PASS / P0 |
| 115 | Hindsight bias предупреждается | Debrief различает доступную до решения информацию и информацию после него. | PASS / P0 |
| 116 | Overconfidence измеряется | Confidence сопоставляется с process score, а не с самоуверенным copy. | PASS / P1 |
| 117 | Underconfidence не наказывается | Низкая confidence может стать coaching signal, но не automatic fail. | PASS / P1 |
| 118 | Sunk cost не награждается | Продолжение ошибочной гипотезы не даёт extra XP. | PASS / P0 |
| 119 | Availability не симулируется фальшивыми новостями | MVP не требует эмоционального clickbait для обучения bias. | PASS / P1 |
| 120 | Нет медицинского/психологического диагноза | Labels описывают observed behavior, а не личность пользователя. | PASS / P0 |

### D13. Session, mobile и interaction contract

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 121 | Сессия короткая | Одна learning unit помещается в короткий мобильный слот без жертвы debrief. | NEEDS ARTIFACT / P1 |
| 122 | Progressive disclosure соблюдается | UI не показывает все системы и сущности до их появления в theory. | PASS / P0 |
| 123 | Навигация не маскирует core loop | Следующий учебный шаг очевиднее, чем secondary menus. | NEEDS ARTIFACT / P0 |
| 124 | Touch targets достаточны | Кнопки evidence, confidence и submit пригодны для mobile. | NEEDS ARTIFACT / P0 |
| 125 | Time pressure не обязателен | Speed challenge не входит в базовую оценку reasoning. | PASS / P0 |
| 126 | Pause/resume работает | Пользователь не теряет state при закрытии Mini App. | NEEDS ARTIFACT / P1 |
| 127 | Orientation не ломает task | Поворот экрана не сбрасывает evidence selection. | NEEDS ARTIFACT / P1 |
| 128 | Low bandwidth имеет fallback | Core theory и item state не зависят от внешних font/CDN ресурсов. | NEEDS ARTIFACT / P1 |
| 129 | Offline claim не делается без проверки | Если offline невозможен, это явно указано в product copy. | PASS / P1 |
| 130 | Interruption resilience проверяется | Telegram back/close и system interruption проходят acceptance test. | NEEDS ARTIFACT / P1 |

### D14. Telemetry и event taxonomy

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 131 | Event names стабильны | Канонические события из FAQ используются без ad hoc синонимов. | PASS / P0 |
| 132 | Event IDs idempotent | Повторная доставка не удваивает attempt или mastery transition. | NEEDS ARTIFACT / P0 |
| 133 | Consent/purpose записаны | Для каждого analytics field есть purpose и legal basis decision. | NEEDS ARTIFACT / P0 |
| 134 | Data minimization применена | Собирается необходимый event payload, а не весь raw interaction без цели. | PASS / P0 |
| 135 | Retention policy задана | Сырые события, aggregates и deletion workflow имеют разные сроки. | NEEDS ARTIFACT / P1 |
| 136 | Время разложено | first action, active, pause, total и abandonment не смешиваются. | PASS / P1 |
| 137 | Hints versioned | Логируется не только факт hint, но и какая подсказка была показана. | NEEDS ARTIFACT / P0 |
| 138 | Confidence сохраняет момент | Confidence timestamp стоит до submit и связан с item version. | PASS / P1 |
| 139 | Abandonment имеет reason class | Технический уход не смешивается с difficulty или voluntary pause. | NEEDS ARTIFACT / P1 |
| 140 | Mastery/transfer events атомарны | Review schedule и transfer result можно восстановить по event stream. | NEEDS ARTIFACT / P0 |

### D15. Admin и content analytics

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 141 | Learner funnel виден | Theory opened → completed → task started → submitted → recall → transfer. | PASS / P1 |
| 142 | Task funnel виден | Attempt, hint, error, debrief, abandon и retry доступны по version. | PASS / P1 |
| 143 | Item health доступен | Редактор видит high error, high hint, long p90 и abandonment clusters. | NEEDS ARTIFACT / P1 |
| 144 | Predicted vs observed time сравним | Отклонение запускает content review, а не speed punishment. | PASS / P1 |
| 145 | Error clusters taxonomy-driven | AI/analytics не создаёт произвольные labels без mapping к rubric. | PASS / P1 |
| 146 | Mastery state history видна | Редактор видит, почему skill стал needs_review. | NEEDS ARTIFACT / P0 |
| 147 | Localization status виден | Missing, draft, reviewed и published разделены по locale/key. | PASS / P1 |
| 148 | Provenance status виден | Item без license/source не может быть marked release-ready. | PASS / P0 |
| 149 | Version compare есть | Изменение wording/rubric можно сравнить до и после. | NEEDS ARTIFACT / P1 |
| 150 | AI suggestion не является action | Любая рекомендация имеет confidence, evidence и human accept/reject. | PASS / P0 |

### D16. AI governance

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 151 | AI не решает mastery | Deterministic rubric остаётся источником истины. | PASS / P0 |
| 152 | AI кластеризует ошибки | Модель может помогать находить recurring patterns после появления taxonomy. | PASS / P1 |
| 153 | AI может находить missing tags | Это редакторская гипотеза с обязательной проверкой. | PASS / P1 |
| 154 | Prompt/model version сохраняется | Вывод можно воспроизвести или хотя бы связать с версией pipeline. | NEEDS ARTIFACT / P1 |
| 155 | Raw journal защищён | В AI не отправляется по умолчанию и не используется без explicit consent. | PASS / P0 |
| 156 | Consent scope конкретен | Согласие на analytics не автоматически означает согласие на generative analysis. | PASS / P0 |
| 157 | Uncertainty модели видна | Admin показывает suggestion и confidence, а не authoritative label. | NEEDS ARTIFACT / P1 |
| 158 | Human review обязателен | Редактор подтверждает error tag, content change и safety-sensitive вывод. | PASS / P0 |
| 159 | Model drift мониторится | Изменения в error clustering не считаются learning change без проверки. | NEEDS ARTIFACT / P2 |
| 160 | Audit trail AI действий | Хранятся input class, output, reviewer и decision. | NEEDS ARTIFACT / P1 |

### D17. Content engineering и release

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 161 | Schema linter существует | Неполный task не доходит до runtime. | NEEDS ARTIFACT / P0 |
| 162 | Locale fallback безопасен | Missing translation не молча заменяется смыслоизменяющимся текстом. | NEEDS ARTIFACT / P1 |
| 163 | Glossary canonical | Одинаковый term переводится одинаково в theory, task и debrief. | PASS / P0 |
| 164 | Content versioning immutable | Published item не редактируется без новой версии. | PASS / P0 |
| 165 | Authoring QA reproducible | Есть checklist для objective, rubric, hints, accessibility и provenance. | NEEDS ARTIFACT / P0 |
| 166 | Duplicate detector | Literal повтор или слишком близкие variants отмечаются до публикации. | NEEDS ARTIFACT / P1 |
| 167 | Distractor audit | Неверный вариант ошибочен по reasoning, а не из-за языка/косметики. | NEEDS ARTIFACT / P1 |
| 168 | Rubric mapping complete | Каждый score component имеет evidence source в item. | NEEDS ARTIFACT / P0 |
| 169 | Accessibility text в schema | Non-visual description, labels и state changes авторятся вместе с item. | NEEDS ARTIFACT / P0 |
| 170 | Release gates machine-readable | P0 privacy, provenance и future-data checks блокируют release автоматически. | NEEDS ARTIFACT / P0 |

### D18. Accessibility и localization

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 171 | Keyboard path возможен | Основные actions доступны без pointer-only gesture. | NEEDS ARTIFACT / P1 |
| 172 | Contrast проверен | Text, state colors и error/success не полагаются только на hue. | NEEDS ARTIFACT / P0 |
| 173 | Screen reader semantics | Evidence, confidence, progress и feedback объявляются понятными labels. | NEEDS ARTIFACT / P0 |
| 174 | Motion optional | Animation не является единственным носителем temporal change. | PASS / P1 |
| 175 | Captions/transcripts | Теория с audio/video имеет text equivalent. | NEEDS ARTIFACT / P1 |
| 176 | Language switch сохраняет state | Switch English/Russian не сбрасывает attempt и не меняет rubric. | NEEDS ARTIFACT / P1 |
| 177 | Future RTL not blocking MVP | RTL не входит в MVP, но schema не должна запрещать его позже. | PASS / P2 |
| 178 | Russian glossary reviewed | LLM draft проходит human/glossary review до publication. | PASS / P0 |
| 179 | Translation does not add hints | Локализация не должна случайно делать distractor очевидным или менять difficulty. | NEEDS ARTIFACT / P1 |
| 180 | Non-native English review | Canonical English проверяется на ясность для новичка, а не только грамматику. | NEEDS ARTIFACT / P0 |

### D19. Privacy, Telegram, legal и monetization

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 181 | Privacy policy готовится отдельно | Telegram context, analytics и AI processing описываются своим policy layer. | NEEDS ARTIFACT / P0 |
| 182 | Telegram data inventory | Продукт документирует, какие поля получает Mini App и зачем. | NEEDS ARTIFACT / P0 |
| 183 | Purpose limitation | Нельзя собирать всё ради будущей модели без конкретного purpose. | PASS / P0 |
| 184 | Stars отложены | Premium digital goods не входят в learning MVP; при запуске нужен Stars flow. | PASS / P1 |
| 185 | Refund/support flow | Если появится платный контент, refund/support тестируются до продажи. | NEEDS ARTIFACT / P2 |
| 186 | Age/legal gate | MVP рассматривается как 18+ до jurisdiction-specific legal review. | PASS / P1 |
| 187 | IP/data license gate | Dataset license и third-party assets проверяются до release. | PASS / P0 |
| 188 | Claims review | Copy не обещает profit, predictive power или proven efficacy без alpha evidence. | PASS / P0 |
| 189 | Analytics consent | Трекинг и optional AI analysis имеют разные consent decisions. | NEEDS ARTIFACT / P0 |
| 190 | Deletion/access workflow | Пользовательский запрос на удаление или экспорт данных имеет owner и SLA. | NEEDS ARTIFACT / P1 |

### D20. Alpha, pilot и research gates

| ID | Проверка | Вывод | Disposition |
|---:|---|---|---|
| 191 | Feasibility gate | Chapter 0 vertical slice работает на целевом mobile path без критических runtime errors. | NEEDS ARTIFACT / P0 |
| 192 | Learning gate | Есть baseline/post measure на одном skill; эффект не объявляется до анализа. | PASS / P1 |
| 193 | Transfer gate | Включён same-skill/different-surface и delayed novel item. | PASS / P0 |
| 194 | Usability gate | Первый экран, terminology и pause/resume проверены наблюдением, а не только survey. | NEEDS ARTIFACT / P0 |
| 195 | Safety gate | Нет future-data leakage, unlicensed dataset или misleading financial copy. | PASS / P0 |
| 196 | Content gate | Все 27 canonical cells имеют rubric, hints, debrief, accessibility и locale status. | NEEDS ARTIFACT / P0 |
| 197 | Sample/assignment gate | Pilot plan заранее фиксирует inclusion, comparison и missing-data rules. | NEEDS ARTIFACT / P1 |
| 198 | Baseline gate | До intervention измеряется existing knowledge/confidence, иначе gain ambiguous. | PASS / P1 |
| 199 | Hypotheses preregistered | Основные outcomes и stopping/decision rules фиксируются до просмотра результата. | NEEDS ARTIFACT / P1 |
| 200 | Go/no-go rules | Решение связано с critical defects, usability, transfer и data integrity, не с vanity metrics. | PASS / P0 |

## 4. 50 tabletop/design tests

Это ручные проверки спецификации и acceptance criteria, а не запуск production-кода. `NEEDS RUNTIME` означает, что дизайн ожидаемо проходит, но доказательств исполнения в доступном workspace нет.

| ID | Сценарий | Ожидаемое поведение | Результат сейчас | Следующий артефакт |
|---|---|---|---|---|
| T01 | Новый пользователь открывает Chapter 0 | Нет рынка, терминов и лишней навигации; один CTA | PASS по спецификации | Собрать первый-screen prototype и usability script |
| T02 | Первый экран с двумя равными CTA | Один очевидный следующий шаг | NEEDS ARTIFACT | Проверить layout на mobile |
| T03 | Игрок не знает candle | Сначала time/sequence и visual change, затем representation | PASS по канону | Добавить item-level prerequisite |
| T04 | Игрок выбирает insufficient evidence | Ответ может быть process-correct | PASS по канону | Включить в Tier 1 seed |
| T05 | Игрок закрывает Mini App в середине item | State сохраняется, mastery не меняется | NEEDS RUNTIME | Acceptance test Telegram lifecycle |
| T06 | Опытный игрок просит skip | Появляется diagnostic challenge, а не unconditional unlock | PASS по канону | Реализовать 8–12 item blueprint |
| T07 | Новичок просит hint | Hint ladder объясняет evidence и логируется | PASS по спецификации | Сделать hint payload/version |
| T08 | Игрок решает с hint | Attempt не закрывает provisional mastery | PASS по канону | Проверить state transition unit test |
| T09 | Игрок видит тот же item второй раз | Меняются dataset/layout/wording/distractors | FAIL без вариативного генератора | Поставить duplicate/same-skill-different-surface gate |
| T10 | Screen reader проходит evidence task | Все state changes имеют labels и non-visual equivalent | NEEDS RUNTIME | Провести keyboard/screen-reader QA |
| T11 | Task без provenance | Item не может попасть в release | FAIL by design | Schema validator + release blocker |
| T12 | Открывается старая content version | Старый rubric и dataset воспроизводимы | NEEDS ARTIFACT | Immutable content registry |
| T13 | Skill требует invalidation, но поля нет | Item невалиден как доказательство skill | FAIL by design | Rubric completeness check |
| T14 | Одна механика покрыта 3 families × 3 tiers | Есть 9 canonical cells, а не 9 одинаковых вопросов | PASS по канону | Заполнить seed matrix |
| T15 | Автор хочет свободный journal с первого дня | MVP остаётся на structured explanation | PASS по решению | Не добавлять NLP dependency |
| T16 | Tier 1 → Tier 2 progression | Новый distractor/context появляется после базового skill | PASS условно | Зафиксировать prerequisites |
| T17 | Игрок rush-угадывает | Speed не увеличивает competence score | PASS по канону | Проверить score formula |
| T18 | Distractor использует необъяснённый термин | Задание провалено как content QA | FAIL by design | Glossary/prerequisite linter |
| T19 | p90 item time вдвое выше target | Запускается content/usability review, не penalty | PASS по канону | Admin alert |
| T20 | Diagnostic challenge | 3 families, 2 contexts, no hints, transfer item, no critical error | PASS по канону | Сделать fixed diagnostic blueprint |
| T21 | 3 correct в одном context | Skill остаётся practicing/provisional, но не verified | PASS по канону | Проверить context counter |
| T22 | Critical skill имеет 3 correct | Недостаточно; нужен stricter threshold до 5 | PASS по канону | Skill-level threshold config |
| T23 | Recall через 48–72 часа | Новый item, не literal copy | PASS по дизайну / runtime pending | Scheduler + delayed item pool |
| T24 | Transfer меняет visual layout | Core skill сохраняется, surface меняется | PASS по канону | Добавить surface_id в item schema |
| T25 | Confidence 5, process score низкий | Возникает overconfidence/calibration gap, не automatic mastery | PASS по канону | Calibration report |
| T26 | Client запрашивает future window | Запрос отклоняется и логируется | FAIL if not enforced | Server-side point-in-time test |
| T27 | Forward scrub до submit | Невозможен даже если UI пытается показать timeline | FAIL if not enforced | API authorization + client test |
| T28 | Дата скрыта пользователю | Audit metadata остаётся доступной backend/editor | PASS по канону | Separate learner/admin payloads |
| T29 | Dataset с personal-only license | Production candidate блокируется | FAIL by design | License registry gate |
| T30 | Replay показывает '$ profit' | Нарушает no-money/outcome-bias rule | FAIL by design | Content copy scan |
| T31 | Leverage объясняется | Exposure multiplier и sensitivity, без promise of return | PASS по канону | Review Chapter 2 copy |
| T32 | Stop-loss объясняется | Invalidation boundary, не торговая рекомендация | PASS по канону | Добавить abstract risk seed |
| T33 | Случайно удачный outcome при плохом process | Process score остаётся низким | PASS по канону | Outcome-independence unit test |
| T34 | Недостаточно evidence | No-trade/stop is available and explainable | PASS по канону | Include in debrief examples |
| T35 | Reward за скорость | Не должен менять mastery/primary score | FAIL by design | Reward audit |
| T36 | Analytics включается без data map | Release блокируется до purpose/retention decision | NEEDS ARTIFACT | Privacy checklist |
| T37 | Event приходит дважды | Attempt/mastery не удваиваются | NEEDS RUNTIME | Idempotency test |
| T38 | AI говорит 'mastered' | Это suggestion, а не authoritative transition | FAIL by design | Admin UI wording + permission |
| T39 | Raw journal отправляется в AI без consent | Запрещено MVP policy | FAIL by design | Data boundary test |
| T40 | High-hint cluster найден | Admin показывает hypothesis с item versions | PASS по дизайну / data pending | Build item-health query |
| T41 | Keyboard-only user | Может theory → task → submit → debrief | NEEDS RUNTIME | Accessibility pass |
| T42 | Russian term differs in meaning | Publication blocked until glossary/human review | PASS по канону | Glossary diff check |
| T43 | Translation missing | Не должно быть тихой semantic fallback | NEEDS ARTIFACT | Locale status + safe fallback |
| T44 | External font/script unavailable | Core content остаётся читаемым и functional | NEEDS RUNTIME | Offline/fallback build |
| T45 | English canonical vs Russian localized item | Learning objective и rubric совпадают | NEEDS HUMAN REVIEW | Bilingual item audit |
| T46 | Pilot сравнивает repeated vs variable retrieval | Одинаковое время, delayed novel transfer | PASS по дизайну | Pre-register analysis plan |
| T47 | Baseline отсутствует | Learning gain неинтерпретируем | FAIL by design | Add pre-test/knowledge check |
| T48 | Маркетинг заявляет retention/efficacy | До alpha это hypothesis, не claim | FAIL by policy | Claims review gate |
| T49 | Пользователь просит удалить analytics | Есть documented deletion path и owner | NEEDS ARTIFACT | Privacy operations test |
| T50 | Alpha go/no-go | Uses safety, integrity, usability and transfer gates, not vanity engagement | PASS по решению | Pre-register thresholds and stopping rules |

## 5. Vertical-slice acceptance contract

Минимальный slice, который разрешено строить следующим:

- Chapter 0 на английском с русским reviewed layer; один clear first-screen path.
- Три механики: observation vs interpretation; evidence selection/context; invalidation and insufficient evidence.
- Для каждой механики: 3 task families × 3 tiers = 9 canonical cells; всего 27 seeds.
- Первые 3–5 Tier 1 items — simple retrieval; затем structured interaction и confidence.
- Hint ladder с отдельным mastery accounting; worked example и guidance fading.
- Process score по evidence/context/invalidation/risk discipline/explanation/calibration; outcome не используется как прибыль.
- Provisional mastery, delayed recall 48–72 h и same-skill/different-surface transfer.
- Historical replay только после provenance/license/no_future_data gates; Chapter 0 может быть synthetic.
- Raw events и минимальная admin: item funnel, hints, time, confidence, abandonment, mastery, transfer, versions.
- Accessibility, localization, privacy и content validator являются release gates, а не post-launch polish.

## 6. Alpha/pilot gates — proposed, not proven

Пороговые значения ниже — рабочие go/no-go правила для alpha, а не утверждение о том, что продукт уже их выполняет.

| Gate | До запуска | В alpha | Нельзя заявлять |
|---|---|---|---|
| Safety/integrity | 0 known future-data leaks; dataset/license registry complete | continuous leakage and copy audit | historical realism or predictive value |
| Usability | first screen and terminology pass moderated pilot | observe completion, confusion, abandonment; proposed target ≥80% complete first unit | retention/engagement success |
| Learning | baseline/post instruments and rubric frozen | compare process score and error repair | learning gain before analysis |
| Delayed recall | scheduler and new item pool ready | 48–72 h measurement | verified mastery from immediate score |
| Transfer | same-skill/different-surface items ready | novel near-transfer comparison | far transfer to real trading |
| Telemetry | event contract, consent, retention, idempotency | completeness and missingness audit | AI-driven mastery claims |
| Accessibility/localization | keyboard, contrast, labels, English/Russian glossary | moderated accessibility checks | broad accessibility conformance without audit |
| Claims/legal | 18+ working assumption, privacy and terms review | incident log and deletion/support drill | financial advice, profit or proven efficacy |

## 7. Immediate implementation backlog

1. Create machine-readable task schema and linter: skill, family, tier, rubric, hints, timing, locale keys, accessibility, provenance, license, version.
2. Author and review the 27 vertical-slice seeds; run same-skill/different-surface and unexplained-term checks.
3. Implement deterministic mastery state machine and event idempotency before AI analytics.
4. Build server-side historical replay boundary and automated no_future_data/forward-scrub tests before any replay claim.
5. Create data map: event purpose, consent, retention, deletion owner and AI boundary.
6. Run English canonical content review, then Russian glossary/human review; do not auto-publish LLM drafts.
7. Prototype Chapter 0 with offline/fallback assets and mobile accessibility acceptance.
8. Pre-register the one-skill micro-experiment: repeated-format control versus variable retrieval, equal time, delayed novel transfer.
9. Only after the above, implement minimal admin; defer marketplace, Stars, full Skill Tree, professional mode and complex simulator.

## 8. Non-claims

На дату отчёта нет доступного production runtime, независимого alpha sample или воспроизводимых simulation artifacts. Поэтому этот отчёт не утверждает, что Signal Arena уже повышает learning gain, retention, calibration, transfer, accessibility, latency, safety или Telegram reliability. Он фиксирует решения, риски, acceptance tests и порядок проверки.

**Файлы:** `SIGNAL_ARENA_DECISION_FAQ.md` (канонический журнал Q001–Q071) и этот отчёт Iteration 3.

# SIGNAL ARENA — Decision FAQ / журнал решений

**Дата обновления:** 7 октября 2026 года  
**Назначение:** единый журнал ответов автора проекта и окончательных решений Creative Game Director.  
**Правило:** если решение отсутствует в этом файле, оно не считается каноническим.  
**Статусы:**

- **AUTHOR-CLOSED** — решение явно принято автором проекта.
- **DIRECTOR-CLOSED** — окончательное решение принял Creative Game Director на основе проектных материалов, когнитивной психологии, game design и доступных исследований.
- **PROPOSED** — рабочее решение для MVP, которое будет пересмотрено по данным alpha-теста.
- **OPEN** — вопрос пока нельзя закрыть без новой информации или теста.
- **REVIEW** — пересматривать только при наступлении указанного триггера, а не постоянно.

---

# 1. Роль и критерии принятия решений

## Q001. Кто принимает финальные решения, если автор проекта оставляет вопрос открытым?

**Ответ:** Creative Game Director принимает окончательное рабочее решение самостоятельно. При необходимости решение должно сопровождаться: причиной, типом доказательств, рисками, критериями пересмотра и планом теста.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED  
**Правило:** «реши сам» означает не отсутствие решения, а необходимость выдать конкретную рекомендацию.

## Q002. Какой стандарт качества у продукта?

**Ответ:** Signal Arena — не набор квизов и не игровая оболочка над лекциями. Каждая механика должна быть прямым переводчиком наблюдаемого учебного навыка в действие игрока.

**Статус:** AUTHOR-CLOSED  
**Критерий:** для каждой механики должны быть определены neurocognitive process, игровое действие, feedback, progression и метрика обучения.

## Q003. Как принимаются решения при конфликте «весело» и «полезно»?

**Ответ:** сначала сохраняется учебная валидность, затем ищется игровой способ сделать этот процесс привлекательным. Если механика повышает engagement, но ухудшает transfer или process quality, она не проходит в core loop.

**Статус:** DIRECTOR-CLOSED  
**Основание:** продукт должен обучать принятию решений, а не просто удерживать внимание.

---

# 2. Продукт и аудитория

## Q004. Кто основная аудитория первой версии?

**Ответ автора:** полные новички, не умеющие читать графики и не знакомые с биржей.

**Статус:** AUTHOR-CLOSED  
**Канон:** MVP проектируется для взрослого новичка. Опытный пользователь получает отдельный diagnostic path.

## Q005. Что будет с B2B и профессиональными трейдерами?

**Ответ автора:** B2B можно убрать из текущей документации и пока не рассматривать.

**Статус:** AUTHOR-CLOSED  
**Решение:** B2B, школы, корпоративные команды и professional trader mode не входят в MVP и не должны влиять на UX первой версии.

## Q006. Какую ценность обещает продукт?

**Ответ директора:**

> Signal Arena — игровой тренажёр принятия решений в условиях неопределённости. Он учит читать контекст, проверять гипотезы, управлять абстрактным риском и замечать когнитивные ошибки — без реальных денег, торговли и обещаний прибыли.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha copy test  
**Пересмотр:** после пяти интервью и теста первого экрана.

## Q007. Является ли продукт торговым приложением?

**Ответ автора:** нет, это прежде всего EdTech; не будет депозита, виртуального счёта, торговли и денег.

**Статус:** AUTHOR-CLOSED  
**Решение директора:** в продуктовой архитектуре не использовать balance, P&L, profit leaderboard или reward за прибыль.

## Q008. Будет ли игрок видеть прибыль или убыток исторической сделки?

**Ответ:** нет. Даже в историческом replay результат должен быть представлен как продолжение данных и учебный outcome, а не как «ты заработал бы X».

**Статус:** DIRECTOR-CLOSED  
**Причина:** защита от outcome bias и ложного ощущения прогностической способности.

## Q009. Возрастной порог?

**Ответ автора:** точного решения пока нет; если продукт попадает под торговую область, нужен 18+.

**Решение директора для MVP:** запускать как 18+ educational decision-training product до юридического review в первой юрисдикции. Отсутствие денег снижает риски, но само по себе не является юридическим заключением.

**Статус:** PROPOSED / REVIEW  
**Триггер:** legal review перед публичным запуском.

---

# 3. Язык и локализация

## Q010. Какой язык является основным?

**Ответ автора:** английский — основной язык релиза, русский — дополнение.

**Статус:** AUTHOR-CLOSED  
**Решение:** canonical content хранится на английском; русский и другие языки — отдельные локализационные слои.

## Q011. Можно ли автоматически переводить контент через API ИИ?

**Ответ:** да, но только как draft. Автоматический перевод не публикуется без glossary check и human review.

**Статус:** DIRECTOR-CLOSED  
**Критичные термины:** invalidation, exposure, risk unit, leverage, confidence, confirmation bias, stop-loss.

## Q012. Где хранится текст?

**Ответ:** в content keys, не в UI-коде и не внутри логики механики.

**Статус:** DIRECTOR-CLOSED  
**Пример:** `task.signal_noise.001.feedback.correct.en` и `task.signal_noise.001.feedback.correct.ru`.

## Q013. Можно ли оставлять английские имена Entities?

**Ответ автора:** да, имена сущностей предполагается оставить на английском.

**Статус:** AUTHOR-CLOSED / PROPOSED  
**Условие:** имя можно оставить английским, но функция и учебный смысл должны быть понятны из localized descriptor.

---

# 4. Теория, новичок и порядок раскрытия

## Q014. Должна ли теория идти перед заданиями?

**Ответ автора:** да, термин не должен появляться в задании раньше, чем был объяснён в теории.

**Статус:** AUTHOR-CLOSED  
**Исключение:** diagnostic path может проверять понятия без полного прохождения главы.

## Q015. Как начинать обучение человека, который не знает свечи?

**Решение директора:** отдельный Chapter 0:

1. время и последовательность;
2. простая визуальная шкала;
3. изменение объекта;
4. observation vs interpretation;
5. базовое представление свечи;
6. uncertainty;
7. no-trade / insufficient evidence.

**Статус:** DIRECTOR-CLOSED / PROPOSED  
**Пересмотр:** после usability-теста первой главы.

## Q016. Нужно ли раскрывать все системы сразу?

**Ответ автора:** нет, всё должно раскрываться постепенно.

**Статус:** AUTHOR-CLOSED  
**Канон:** в первой сессии скрыты Skill Tree, Entities, marketplace, energy, сложная экономика и лишняя навигация.

## Q017. Может ли опытный игрок пропустить теорию?

**Ответ автора:** да, он должен иметь возможность сразу пройти зачёт главы.

**Статус:** AUTHOR-CLOSED  
**Решение:** это diagnostic challenge, а не прямой unlock:

- 8–12 заданий;
- минимум 3 семейства задач;
- минимум 2 новых контекста;
- без подсказок;
- process score ≥80%;
- отсутствие critical error;
- один transfer item.

## Q018. Что делать, если опытный игрок не прошёл зачёт?

**Решение:** показать missing skills и открыть только соответствующие короткие theory units. Не заставлять повторять всю главу.

**Статус:** DIRECTOR-CLOSED  
**Причина:** сохранение уважения к опыту игрока без отказа от доказательства навыка.

---

# 5. Механики и структура заданий

## Q019. С чего начинать производство?

**Ответ автора:** с игровых механик и простых заданий, в порядке, в котором их увидит новичок.

**Статус:** AUTHOR-CLOSED  
**Решение директора:** строить не отдельную механику, а связку:

> theory → task family → difficulty → hint policy → process score → debrief → recall → transfer → analytics.

## Q020. Что означают «три варианта заданий на механику»?

**Решение директора:** это три семейства задач, а не три почти одинаковых вопроса:

1. **Recognize** — распознать/классифицировать;
2. **Apply** — применить навык;
3. **Explain/Transfer** — объяснить или перенести принцип.

**Статус:** DIRECTOR-CLOSED  
**Рабочая структура:** каждое семейство × три уровня сложности = 9 смысловых ячеек на механику.

## Q021. Сколько заданий делать на одну механику в MVP?

**Решение:** сначала 9 canonical seeds: 3 семейства × 3 tier. После alpha добавить по 2–4 параметрических варианта в ячейку.

**Статус:** DIRECTOR-CLOSED / PROPOSED  
**Причина:** баланс между разнообразием, стоимостью авторинга и возможностью понять, какая версия работает.

## Q022. Когда прекращать обычные тесты с вариантами ответов?

**Решение:** после 3–5 базовых вопросов переходить к structured interaction: отметить evidence, сравнить варианты, выбрать action, указать invalidation, оценить confidence.

**Статус:** DIRECTOR-CLOSED  
**Причина:** чистый multiple choice быстро превращается в распознавание формата, а не retrieval/transfer.

## Q023. Какой размер задания считать нормальным?

**Решение MVP:

- Tier 1: 15–30 секунд;
- Tier 2: 30–60 секунд;
- Tier 3: 60–120 секунд;
- обязательный максимум: около 180 секунд;
- длинное решение делить на observe → decide → explain.

**Статус:** DIRECTOR-CLOSED / PROPOSED  
**Пересмотр:** после alpha по median и p90.

## Q024. Как заранее оценивать время?

**Решение:** каждое задание получает `expected_time`, `target_time`, `max_time` и объяснение прогноза. Логируются time-to-first-action, active time, pause time, total time, abandonment.

**Статус:** DIRECTOR-CLOSED  
**Важно:** время используется для обнаружения путаницы, а не для наказания медленных игроков.

## Q025. Как учитывать задания, которые игрок уже видел?

**Ответ автора:** не запускать тот же вариант; использовать разные исторические/синтетические данные, формулировки и уровни сложности.

**Статус:** AUTHOR-CLOSED  
**Уточнение директора:** повторяется skill, но не literal task version. Меняются context, data, layout, distractor, wording и noise.

---

# 6. Historical replay и данные

## Q026. Как использовать исторические данные?

**Ответ автора:** игрок не видит дату и должен после решения увидеть, как график проигрался на исторических данных.

**Статус:** AUTHOR-CLOSED  
**Решение:** hidden date/ticker допустимы, но должны храниться на сервере в provenance metadata.

## Q027. Когда использовать синтетические данные?

**Решение:** в Chapter 0–1 для контролируемого обучения одному понятию. Historical replay — с Chapter 2 и особенно в transfer/capstone.

**Статус:** DIRECTOR-CLOSED  
**Причина:** новичку сначала нужна управляемая задача с одной переменной, а не хаотичный рынок.

## Q028. Как не допустить lookahead bias?

**Решение:** сервер раскрывает только данные до decision timestamp. Scrubbing вперёд запрещён. Добавляется автоматический `no_future_data` тест.

**Статус:** DIRECTOR-CLOSED  
**Приоритет:** P0 до использования historical replay в доказательстве обучения.

## Q029. Нужно ли скрывать дату, чтобы игрок не искал график?

**Ответ:** да, скрывать от игрока; нет, не скрывать внутри системы. Дата, тикер и источник сохраняются для воспроизводимости и аудита.

**Статус:** DIRECTOR-CLOSED  
**Дополнительно:** не показывать уникальные визуальные fingerprints, позволяющие легко найти dataset.

## Q030. Что делать с лицензиями исторических данных?

**Решение:** для каждого dataset хранить source, license, preprocessing, allowed use и version. Без этого dataset не включается в production candidate.

**Статус:** DIRECTOR-CLOSED  
**Приоритет:** P0 перед публичным релизом.

---

# 7. Подсказки и mastery

## Q031. Можно ли использовать подсказки?

**Ответ автора:** да. Новичку они нужны, но с подсказкой нельзя продвигаться дальше; самостоятельное правильное решение должно быть обязательным.

**Статус:** AUTHOR-CLOSED  
**Каноническая политика:**

- Learn — полная помощь;
- Practice — hints разрешены;
- Prove/Battle — hints запрещены;
- Debrief — полное объяснение.

## Q032. Сколько правильных решений без подсказки нужно?

**Решение:** не применять одно число ко всем навыкам:

- обычный skill: 3 самостоятельных решения в 2 контекстах;
- critical risk/invalidation skill: 5 самостоятельных подтверждений;
- затем delayed recall и transfer.

**Статус:** DIRECTOR-CLOSED / PROPOSED  
**Причина:** универсальное 5× для всех карт создаёт лишнюю длину и не учитывает различия в риске навыка.

## Q033. Что считается mastery?

**Решение:**

```text
introduced → practicing → provisional → verified → needs_review
```

`provisional`: 3 hint-free correct, process score ≥80%, 2 контекста, no critical error.  
`verified`: delayed recall через 48–72 часа + transfer item.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q034. Нужно ли полностью откатывать прогресс после провала?

**Решение:** нет. Откатывается только конкретный skill в `needs_review`, а не вся глава.

**Статус:** DIRECTOR-CLOSED  
**Причина:** сохранение мотивации и точности диагностики.

## Q035. Нужно ли вводить mastery decay сразу?

**Ответ автора:** лучше начать аккуратно, возможно не вводить сразу.

**Решение:** на MVP не делать автоматическое наказание. Сначала delayed recall. После данных — мягкий статус `needs_review`, без удаления открытых карт.

**Статус:** DIRECTOR-CLOSED / REVIEW.

## Q036. Что делать при повторных ошибках?

**Решение:** не блокировать обучение на час. Использовать micro-repair, смену формата, короткую паузу против random clicking и повторение skill в новом контексте.

**Статус:** DIRECTOR-CLOSED  
**Причина:** долгий lockout наказывает обучение; он допустим только для optional arcade, но не core learning.

---

# 8. Feedback, процесс и confidence

## Q037. Какой результат важнее: правильное направление или правильный процесс?

**Ответ автора:** важнее второе.

**Статус:** AUTHOR-CLOSED  
**Канон:** process score имеет приоритет над market outcome.

## Q038. Что должно быть в process score?

**Решение:**

- evidence quality;
- context check;
- invalidation;
- risk discipline;
- explanation;
- confidence calibration.

**Статус:** DIRECTOR-CLOSED / PROPOSED до теста rubric.

## Q039. Нужно ли вводить confidence rating?

**Решение:** да, после того как игрок увидел данные, но до submit. На MVP использовать шкалу 1–5 или диапазон вероятности. Это нужно для выявления overconfidence и underconfidence.

**Статус:** DIRECTOR-CLOSED  
**Ограничение:** confidence не должен влиять на правильность ответа сам по себе; оценивается calibration gap.

## Q040. Нужна ли оценка свободного объяснения с первого дня?

**Ответ автора:** нет, сначала можно обойтись без этого функционала.

**Решение:** на MVP использовать structured explanation: observation, evidence, invalidation, risk, confidence. Свободный текст отложить до появления стабильной taxonomy.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED.

## Q041. Как должен выглядеть debrief?

**Решение:** каждый debrief отвечает на 5 вопросов:

1. что было видно;
2. что было неизвестно;
3. почему выбранное решение было/не было процессно корректным;
4. что могло его опровергнуть;
5. какую ошибку совершил игрок.

**Статус:** DIRECTOR-CLOSED.

## Q042. Нужно ли показывать дальнейший рыночный результат?

**Решение:** можно показывать продолжение данных как учебный материал, но не «прибыль игрока». Отдельно пояснять, что outcome не доказывает качество решения.

**Статус:** DIRECTOR-CLOSED.

---

# 9. Данные, админка и AI

## Q043. Нужно ли собирать все логи?

**Ответ автора:** да, все логи должны стекаться в админку для последующего анализа, в том числе AI-анализом.

**Статус:** AUTHOR-CLOSED  
**Уточнение:** собирать не «всё подряд», а событийно необходимый минимум с data map, retention policy и consent.

## Q044. Что должно появиться раньше: AI или админка?

**Решение:** сначала raw event pipeline и rules-based admin. AI подключается после появления данных и taxonomy.

**Статус:** DIRECTOR-CLOSED  
**Причина:** AI без качественных событий и версий заданий создаёт красивые, но ненадёжные выводы.

## Q045. Может ли AI автоматически решать, что пользователь освоил навык?

**Решение:** нет, не в MVP. Mastery считается по deterministic rubric. AI помогает кластеризовать ошибки и формировать гипотезы для редактора.

**Статус:** DIRECTOR-CLOSED.

## Q046. Может ли AI анализировать journal?

**Решение:** только после explicit consent, anonymization и human review. Raw journal не отправляется в AI по умолчанию.

**Статус:** DIRECTOR-CLOSED / REVIEW.

## Q047. Что должно быть в MVP-админке?

**Решение:**

1. learner funnel;
2. task funnel;
3. task health;
4. predicted vs observed time;
5. hint usage;
6. error tags;
7. abandonment;
8. mastery states;
9. localization status;
10. content versions.

**Статус:** DIRECTOR-CLOSED.

## Q048. Какие события обязательны?

**Решение:** `theory_opened`, `theory_completed`, `task_started`, `first_action`, `hint_used`, `confidence_set`, `task_submitted`, `debrief_opened`, `error_tagged`, `task_abandoned`, `review_scheduled`, `transfer_completed`.

**Статус:** DIRECTOR-CLOSED.

---

# 10. Деньги, риск и игровая экономика

## Q049. Будут ли деньги фигурировать в игре?

**Ответ автора:** нет. Не будет депозита, виртуального счёта и торговли.

**Статус:** AUTHOR-CLOSED  
**Канон:** никакого баланса и P&L в core learning.

## Q050. Как обучать stop-loss без денег?

**Решение:** через `invalidation boundary`: игрок указывает, где гипотеза перестаёт быть действительной. Затем вводятся abstract risk units и exposure categories.

**Статус:** DIRECTOR-CLOSED.

## Q051. Как объяснять leverage без денег?

**Решение:** как exposure multiplier: он увеличивает чувствительность к движению и уменьшает запас до invalidation. Не показывать «ты бы заработал».

**Статус:** DIRECTOR-CLOSED.

## Q052. Что делать с Telegram Stars и marketplace?

**Ответ автора:** валюта относится к оплате premium services через Telegram Stars.

**Решение:** marketplace и premium services не входят в первый learning MVP. Базовое обучение, debrief, risk education и transfer не должны быть paywalled.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED / REVIEW.

## Q053. Нужна ли energy-механика?

**Решение:** не ограничивать energy теорию, recall и core practice. Если energy остаётся, использовать её только для optional arcade или cosmetic/premium content.

**Статус:** DIRECTOR-CLOSED / PROPOSED.

## Q054. Нужны ли XP и игровые ресурсы?

**Решение:** XP оставить как мягкий индикатор progression. Не начислять его только за скорость или угадывание. Валюту, marketplace и сложную экономику отложить.

**Статус:** DIRECTOR-CLOSED.

---

# 11. Источники решения и правила пересмотра

## Q055. Можно ли полностью доверять внешним научным публикациям?

**Ответ автора:** основная система основана на отобранных проверенных методиках и публикациях.

**Решение:** научные источники являются обоснованием механик, но не доказательством эффективности именно Signal Arena. Доказательство продукта появляется только через controlled alpha/pilot.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED.

## Q056. Нужно ли повторять симуляции?

**Ответ автора:** повторить можно при необходимости; несогласованность симуляций не является первостепенной проблемой.

**Решение:** не блокировать MVP повторной симуляцией. Создать reproducibility registry позже, до публикации научных claims. В roadmap это P1/P2, а не причина остановить дизайн заданий.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED.

## Q057. Как пересматривать решения?

**Решение:** пересмотр по trigger, а не по ощущению:

- alpha выявила высокий abandonment;
- p90 времени превышает прогноз;
- transfer не выше baseline;
- critical errors растут;
- пользователь не понимает первый экран;
- локализация и safety review выявили проблему.

**Статус:** DIRECTOR-CLOSED.

## Q058. Какие решения нельзя менять без evidence?

**Ответ:** core learning objective, process-over-outcome principle, отсутствие денег/P&L, versioning content, hint policy и data provenance.

**Статус:** DIRECTOR-CLOSED.

---

# 12. Приоритет открытых вопросов

## P0 — закрыть до создания большого объёма контента

1. Chapter 0 и точный первый пользовательский flow.
2. Process score rubric.
3. Hint policy.
4. Mastery state machine.
5. Структура 3 task families × 3 tiers.
6. Схема исторического replay без lookahead.
7. Event taxonomy.
8. Content schema и versioning.
9. No-money risk representation.
10. Diagnostic path для опытного пользователя.

## P1 — закрыть до alpha-теста

1. Точные 27 task cells для трёх механик.
2. Дизайн debrief.
3. Confidence rating.
4. Error taxonomy.
5. Admin MVP.
6. Предсказание времени.
7. Accessibility и mobile gesture contract.
8. English glossary.
9. Historical dataset provenance.
10. Alpha success/fail gates.

## P2 — закрыть после первых данных

1. Полный AI-анализ.
2. Mastery decay.
3. Расширенная экономика.
4. Telegram Stars и marketplace.
5. Большой Skill Tree.
6. Все Entities и ранги.
7. Массовая localization automation.
8. Public research dashboard.
9. Более сложные simulator mechanics.
10. Профессиональный режим.

---

# 13. Рекомендованное решение на текущий момент

**Сейчас начинать не с full game и не с полной админки, а с одного вертикального образовательного среза:**

```text
Chapter 0
→ 3 базовые mechanics
→ 27 task cells
→ hints
→ process score
→ debrief
→ confidence
→ provisional mastery
→ delayed recall
→ transfer
→ raw events
→ минимальная admin-аналитика
```

После этого провести alpha-тест. Все последующие механики, карты, сущности и экономические системы добавлять только через новую запись в этом FAQ с указанием:

- какую проблему решает изменение;
- какой learning process активирует;
- какие риски создаёт;
- какие события измеряют эффект;
- какой тест разрешает публикацию.

---

# 14. Addendum — решения после третьей итерации аудита

## Q059. Нужно ли проверять ровно 150 уникальных интернет-источников?

**Решение директора:** нет, механически собирать 150 уникальных источников не нужно. Я провёл целевой web-review примерно 150 поисковых результатов с приоритетом первичных исследований, систематических обзоров и официальных правил Telegram. После дедупликации источников меньше; этого достаточно для текущих продуктовых решений. Дополнительные источники не заменяют alpha-тест Signal Arena.

**Статус:** DIRECTOR-CLOSED  
**Принцип:** research используется для выбора дизайна; продуктовая эффективность проверяется собственными экспериментами.

## Q060. Что уточнила новая научная проверка по spacing?

**Решение:** не фиксировать расширяющийся график `+1/+3/+7/+16/+35` как закон. В обзоре spaced retrieval показано преимущество spacing над massed retrieval, но превосходство именно expanding schedule над uniform schedule не является универсальным. Использовать adaptive/regular schedule и калибровать его на данных проекта. [2](http://www.lscp.net/persons/ramus/docs/EPR20.pdf)

**Статус:** DIRECTOR-CLOSED.

## Q061. Что уточнила новая проверка по variability?

**Решение:** вариативность заданий является обязательной частью transfer design. Однако её следует вводить после понятной theory/model example, иначе новичок будет не индуцировать правило, а угадывать. Повторять skill можно, повторять буквально один и тот же item нельзя. Исследования по variable retrieval поддерживают это направление, но параметры Signal Arena нужно проверять самостоятельно. [1](https://link.springer.com/article/10.1007/s10648-026-10169-w) [4](https://pdf.retrievalpractice.org/transfer/Pan_Rickard_2018.pdf)

**Статус:** DIRECTOR-CLOSED.

## Q062. Что уточнила новая проверка по fading?

**Решение:** для новичков использовать worked example и постепенное уменьшение поддержки; для опытных игроков снижать guidance раньше. Не делать резкий переключатель «полная теория → сразу no-hint battle». Эффект зависит от prior knowledge и структуры задачи. [8](https://journals.sagepub.com/doi/10.1177/0963721420922183) [1](https://cogscisci.wordpress.com/wp-content/uploads/2019/08/sweller-guidance-fading.pdf)

**Статус:** DIRECTOR-CLOSED.

## Q063. Что уточнила новая проверка по mastery learning?

**Решение:** mastery должен включать не только threshold, но и corrective activity с параллельным, изменённым заданием. После ошибки нельзя просто выдать тот же вопрос ещё раз. Нужны другой формат, другой пример или другой context. [1](https://tguskey.com/wp-content/uploads/Mastery-Learning-1-Mastery-Learning.pdf) [5](https://journals.sagepub.com/doi/10.2190/FG7X-7Q9V-JX8M-RDJP?icid=int.sj-abstract.citing-articles.75)

**Статус:** DIRECTOR-CLOSED.

## Q064. Как вводить confidence?

**Решение:** спрашивать confidence после observation/evidence и до submit, затем давать retrospective calibration feedback после результата. Одного вопроса «насколько ты уверен?» недостаточно: игрок должен видеть разницу между прогнозом и фактическим process score. Вмешательства, направленные на task understanding, external standards и metacognitive knowledge, предпочтительнее попыток просто заставить пользователя быстрее выставлять confidence. [1](https://link.springer.com/article/10.1007/s10648-024-09936-4) [9](https://www.sciencedirect.com/science/article/abs/pii/S0959475218308788)

**Статус:** DIRECTOR-CLOSED.

## Q065. Как относиться к far transfer?

**Решение:** не обещать far transfer на маркетинговом уровне до доказательства. В design doc называть его hypothesis. Primary pilot outcome — delayed novel transfer в пределах близкой предметной области; внешний перенос в реальную торговлю не заявлять. Систематические обзоры serious games показывают, что near transfer обычно заметнее, а far transfer и долгосрочные эффекты требуют более строгой проверки. [5](https://pubmed.ncbi.nlm.nih.gov/42199316/) [8](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2025.1511729/epub)

**Статус:** DIRECTOR-CLOSED.

## Q066. Как использовать gamification?

**Решение:** XP и progression должны показывать competence, но не заменять competence. Points, badges, leaderboards и rewards не входят в primary learning score. Нельзя делать большой акцент на competition, streak loss или pressure, если они не улучшают process/transfer. Мета-анализы показывают в среднем положительный, но не универсальный эффект gamification и заметную зависимость результата от конкретной комбинации элементов. [7](https://eric.ed.gov/?id=EJ1266144) [9](https://link.springer.com/article/10.1007/s11423-025-10493-y) [10](https://bera-journals.onlinelibrary.wiley.com/doi/10.1111/bjet.13471?af=R)

**Статус:** DIRECTOR-CLOSED.

## Q067. Какие Telegram-ограничения учитывать?

**Решение:** до интеграции Stars и персональных данных проверить официальные Terms of Service for Mini Apps, Stars Terms и Bot Developer Terms. Mini App получает определённые данные через Telegram-контекст, а цифровые товары внутри Telegram должны продаваться через Stars; нужна собственная privacy policy, support/refund flow и серверная валидация identity. [1](https://telegram.org/tos/mini-apps) [2](https://telegram.org/tos/stars) [3](https://telegram.org/tos/bot-developers?setln=fa) [5](https://core.telegram.org/bots/payments-stars)

**Статус:** DIRECTOR-CLOSED / REVIEW.

## Q068. Как работать с historical data licensing?

**Решение:** скрытие даты не решает вопрос лицензии. Для коммерческого EdTech-продукта использовать только dataset с разрешённым commercial/redistribution use либо данные собственной лицензии. Свободные/free tiers часто ограничены personal/non-commercial use. [1](https://www.marketdata.app/terms/public-use/) [2](https://www.coingecko.com/learn/best-historical-crypto-data-apis)

**Статус:** DIRECTOR-CLOSED / P0 перед публичным релизом.

## Q069. Какой дополнительный критерий добавить в content QA?

**Решение:** каждая задача обязана пройти `same-skill / different-surface` тест: игрок должен показать тот же принцип на новом визуальном layout и новом наборе данных. Если успех сохраняется только на исходном skin, задача не считается доказательством transfer.

**Статус:** DIRECTOR-CLOSED.

## Q070. Какой главный эксперимент сделать первым?

**Решение:** не сравнивать сразу весь Signal Arena с классическим курсом. Сначала провести micro-experiment на одном skill:

- group A: theory + repeated same-format practice;
- group B: theory + variable retrieval practice;
- одинаковое время;
- delayed novel transfer через 48–72 часа.

Если B не лучше A, сначала улучшить task design, а не добавлять игру.

**Статус:** DIRECTOR-CLOSED / PROPOSED.

## Q071. Когда пересматривать текущие решения?

**Решение:** не после каждой новой публикации. Пересмотр только если появляется:

- alpha data;
- новый primary research, прямо относящийся к task type;
- legal/Telegram change;
- доказанный mismatch между forecast и user behaviour;
- critical safety issue.

**Статус:** DIRECTOR-CLOSED.

---

# 15. Addendum — закрытие критических вопросов после Iteration 4

## Q072. Что означает «критический вопрос закрыт»?

**Решение:** вопрос считается закрытым на уровне дизайна только если зафиксированы: решение, артефакт-доказательство, зависимость, acceptance test, ответственный следующий шаг и trigger пересмотра. Production evidence не подменяется design decision. Поэтому возможен статус `DECISION CLOSED / IMPLEMENTATION BLOCKED`.

**Статус:** DIRECTOR-CLOSED.

## Q073. Какой canonical schema у task?

**Решение:** каждый task обязан иметь `task_id`, immutable `version`, `skill_key`, `family`, `tier`, `surface_id`, `context_id`, `prerequisites`, `rubric_profile`, `critical_error_rules`, `hint_policy`, timing fields, content keys, accessibility fields и provenance/license references, если используется dataset.

**Статус:** DIRECTOR-CLOSED / IMPLEMENTATION BLOCKED.

## Q074. Как окончательно считать process score?

**Решение:** default rubric на 100 баллов:

- evidence selection/quality — 30;
- context check — 20;
- invalidation/boundary — 20;
- uncertainty/risk discipline — 15;
- structured explanation — 10;
- confidence calibration — 5.

Task profile может исключить компонент только с явным перераспределением веса. Critical error veto действует независимо от score. Speed, profit и market outcome не повышают score.

**Статус:** DIRECTOR-CLOSED / IMPLEMENTATION BLOCKED.

## Q075. Что считать critical error?

**Решение:** ошибка, которая разрушает конкретное учебное утверждение: использование future data, выдача неподтверждённого наблюдения за факт, игнорирование обязательной invalidation boundary на critical skill или обход server-side state/authorization. Critical error блокирует mastery независимо от среднего score.

**Статус:** DIRECTOR-CLOSED / IMPLEMENTATION BLOCKED.

## Q076. Какой event contract использовать?

**Решение:** не импортировать полный Caliper или xAPI в MVP. Использовать компактный внутренний versioned contract, совместимый по базовой семантике learning events:

`event_id`, `event_name/version`, pseudonymous `actor_ref`, `session_id`, `attempt_id`, `content_id/version`, `skill_key`, `occurred_at_client`, trusted `observed_at_server`, `server_sequence`, `consent_scope`, `idempotency_key`, allowlisted payload.

**Статус:** DIRECTOR-CLOSED / IMPLEMENTATION BLOCKED.

## Q077. Можно ли доверять client state и Telegram identity?

**Решение:** нет. Telegram `initData` валидируется на сервере, `auth_date` проверяется, ownership attempt проверяется на каждом request. Client flags, client mastery и client timestamps не могут выдавать доступ или менять state.

**Статус:** DIRECTOR-CLOSED / P0 IMPLEMENTATION BLOCKER.  
**Основание:** [Telegram Mini Apps validation](https://core.telegram.org/bots/webapps) и server-side authorization practice.

## Q078. Как закрыть look-ahead и forward scrub?

**Решение:** только server-side point-in-time API. Allowed observation window вычисляется из server-side attempt state и decision timestamp. Любой запрос к future window отклоняется до сериализации данных и логируется как security event.

**Статус:** DIRECTOR-CLOSED / P0 IMPLEMENTATION BLOCKER.

## Q079. Какой документ обязателен для historical dataset?

**Решение:** Dataset Card/Datasheet с origin, owner, license, timeframe, sampling, preprocessing, hidden fields, known bias, allowed/disallowed use, hash, version и maintainer. Без него replay не включается в production candidate.

**Статус:** DIRECTOR-CLOSED / P0.

## Q080. Какой accessibility target принят?

**Решение:** WCAG 2.2 AA как engineering target для vertical slice и Mini App web layer. До ручного и автоматизированного аудита нельзя заявлять соответствие. P0: keyboard/focus, contrast/non-color cues, text alternatives, status messages, target size и reduced motion.

**Статус:** DIRECTOR-CLOSED / IMPLEMENTATION BLOCKED.  
**Основание:** [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/).

## Q081. Какой privacy/data governance minimum?

**Решение:** до real-user telemetry создать data map, purpose/field inventory, pseudonymous analytics ID, consent scopes, retention/deletion workflow, access roles, processor list и breach process. DPIA screening обязателен; formal DPIA требуется до high-risk profiling/AI либо если это подтвердит legal review.

**Статус:** DIRECTOR-CLOSED / EXTERNAL LEGAL REVIEW REQUIRED.

## Q082. Что разрешено AI?

**Решение:** AI не получает raw journal и не имеет права менять mastery. До появления stable taxonomy, validated events и consented minimized data AI можно полностью отложить. В будущем AI выдаёт только human-reviewed error clusters/hypotheses.

**Статус:** DIRECTOR-CLOSED / DEFERRED P2.

## Q083. Какую validity claim имеет process score?

**Решение:** только formative decision-training score. Сначала проверяются scoring и generalisation внутри task universe; extrapolation в реальную торговлю и high-stakes decisions исключена. Для каждой более сильной интерпретации нужна отдельная evidence chain.

**Статус:** DIRECTOR-CLOSED / RESEARCH GATE.

## Q084. Какой pilot sample plan принять?

**Решение:** usability tranche — 8–12 новичков и 3–5 опытных пользователей для diagnostic path. Feasibility/micro-experiment — provisional target 60 новичков, 30 на условие. Число оправдывается feasibility/data-completeness objectives, а не заявлением efficacy power.

**Статус:** DIRECTOR-CLOSED / PROPOSED до protocol review.

## Q085. Какие primary outcomes у alpha?

**Решение:** primary — recruitment, completion, data completeness, p90 time, abandonment, critical-error rate и delayed-follow-up rate. Process score, delayed recall, novel transfer и calibration gap — exploratory secondary outcomes до отдельного efficacy study.

**Статус:** DIRECTOR-CLOSED / PROPOSED до preregistration.

## Q086. Как сравнивать repeated и variable retrieval?

**Решение:** одинаковые theory, skill, difficulty band, allotted time, feedback/hint policy; A повторяет same-format surface, B меняет surface/context; обе группы получают delayed novel-transfer item через 48–72 часа. Item bank и assignment lock до просмотра данных.

**Статус:** DIRECTOR-CLOSED / PROPOSED до protocol review.

## Q087. Какой dependency graph является каноническим?

**Решение:**

```text
governance
→ schema + rubric + mastery engine
→ Chapter 0 content
→ trusted events + minimal admin
→ replay + provenance + no_future_data
→ accessibility/localization audit
→ internal smoke
→ moderated usability alpha
→ feasibility micro-experiment
```

Нельзя начинать historical replay, AI или marketplace раньше необходимых upstream gates.

**Статус:** DIRECTOR-CLOSED.

## Q088. Что конкретно блокирует работу сейчас, а что отложено?

**Решение:** сейчас блокируют: schema/linter, rubric/mastery tests, server-side identity/authorization, event contract/idempotency, data map/privacy review, Chapter 0 content matrix, no_future_data suite, dataset card/license gate, WCAG audit и preregistered pilot protocol. Отложены по решению: full Caliper/xAPI, AI clustering, mastery decay, Stars/marketplace, professional mode, far transfer study и full historical catalog.

**Статус:** DIRECTOR-CLOSED.

---

# 16. Addendum — сравнительный анализ gamification apps и traditional learning

## Q089. Какие проекты с изображения анализировались?

**Решение:** канонический список из 13 проектов:

1. Habitica;
2. Todoist Karma;
3. SuperBetter;
4. Epic Win;
5. Forest;
6. Epic To-Do List;
7. Duolingo;
8. Zombies, Run!;
9. Plant Nanny;
10. Habits Garden;
11. Fortune City;
12. Nerd Fitness Journey;
13. Ingress Prime.

**Статус:** AUTHOR-CLOSED + DIRECTOR-CLOSED.

## Q090. Что означает «100 анализов» для этих 13 проектов?

**Решение:** выполнены 100 отдельных design observations/use cases, распределённых между всеми 13 проектами. Это не утверждение о наличии 100 разных приложений на скриншоте. Анализ feature mechanics отделён от claims об эффективности.

**Статус:** DIRECTOR-CLOSED.

## Q091. Как оценивать качество источников по gamification apps?

**Решение:** official product pages и app-store listings подтверждают наличие функций, но не causal learning effect. Secondary reviews, ratings, download counts и marketing claims не считаются доказательством обучения. Для отдельных приложений с неполной primary documentation confidence ниже и это отмечено в отчёте.

**Статус:** DIRECTOR-CLOSED.

## Q092. Какое лучшее решение взять для Signal Arena?

**Решение:** гибрид **Signal Arena — Evidence Quest / Adaptive Decision Garden**:

- короткая cadence и variable task surfaces из EdTech-паттернов;
- quest framing и визуальный рост из Habitica/SuperBetter/Epic apps;
- focus mode из Forest;
- narrative mission wrapper из Zombies, Run!;
- cumulative garden/map из Plant Nanny/Habits Garden/Fortune City;
- progressive entity/map reveal из Ingress;
- explicit theory, worked examples, retrieval, spacing, feedback, mastery и transfer из traditional learning.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q093. Какой game layer разрешён поверх learning truth?

**Решение:** game layer может давать quest, avatar/profile, cosmetic garden/map, optional narrative и safe cohort challenge. Только deterministic learning layer открывает mastery. XP не начисляется за speed, raw clicks, arbitrary task volume или lucky outcome.

**Статус:** DIRECTOR-CLOSED.

## Q094. Какие traditional learning methods являются обязательными?

**Решение:** explicit instruction, worked example, guided practice, retrieval practice, spaced review, variable/interleaved contexts, formative feedback, corrective parallel assessment, mastery states, metacognitive confidence calibration и novel transfer.

**Статус:** DIRECTOR-CLOSED.

## Q095. Почему не копировать готовую gamification app целиком?

**Решение:** готовые apps обычно оптимизируют return behavior, consistency или emotional motivation; Signal Arena обязана оптимизировать observable reasoning и transfer. Поэтому gamification используется как delivery layer, а не как источник определения mastery.

**Статус:** DIRECTOR-CLOSED.

## Q096. Какие механики из screenshot запрещены в MVP Signal Arena?

**Решение:** forced streak loss, punitive HP/death, reward за speed, public leaderboard, real-world GPS dependency, location tracking, money/balance/P&L, financial prosperity metaphor, random loot as competence, paywall на core learning и social damage за чужую ошибку.

**Статус:** DIRECTOR-CLOSED.

## Q097. Какова оценка выбранной архитектуры?

**Решение:** 95/100 как design score:

- learning validity — 19/20;
- novice cognitive load — 14/15;
- retrieval/spacing/transfer — 14/15;
- engagement without dark patterns — 10/10;
- feedback/mastery — 10/10;
- safety/no-money — 10/10;
- MVP technical feasibility — 7/8;
- accessibility/localization — 5/5;
- telemetry/research readiness — 3/4;
- optional social/retention — 3/3.

Недостающие 5 баллов можно получить или потерять только по alpha evidence; текущие runtime и learning claims не подтверждены.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q098. Как выглядит core loop 95-point решения?

**Решение:**

```text
quest briefing
→ explicit theory
→ worked example
→ guided practice
→ structured decision
→ confidence
→ debrief
→ parallel repair
→ no-hint prove
→ spaced recall
→ novel transfer
→ garden/map update
```

**Статус:** DIRECTOR-CLOSED.

## Q099. Какие эксперименты проверяют выбранное решение?

**Решение:** обязательны: repeated-surface vs variable-retrieval A/B; immediate vs 48–72h recall; same-skill/different-surface transfer; reward ablation; streak ablation; narrative ablation; hint fading; accessibility audit; privacy/security/no-future-data tests.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha protocol.

## Q100. Когда пересматривать 95-point решение?

**Решение:** после moderated usability alpha и feasibility micro-experiment. Пересмотр запускается при: ухудшении process score из-за game layer, высоком reward optimization, high abandonment, low delayed transfer, accessibility failure, privacy/legal issue или невозможности воспроизвести analytics.

**Статус:** DIRECTOR-CLOSED.

## Q101. Какой обязательный предмет Iteration 6?

**Решение:** только crypto/blockchain beginner education: blockchain mental model, wallets, keys, seed phrases, custody, transaction lifecycle, networks, fees, confirmation, scams, phishing, social engineering, irreversibility, stablecoins, tokens/tokenomics, DeFi, on-chain evidence, uncertainty, bias и decision hygiene. Forex и stocks не являются основным resource set.

**Статус:** DIRECTOR-CLOSED.

## Q102. Какой корпус ресурсов проанализирован?

**Решение:** 50 ресурсов: 10 regulator/consumer-protection, 10 university/open academic, 15 industry/wallet/security/on-chain education, 10 interactive/open/professional courses и 5 books. Sponsored/vendor materials использованы для анализа mechanics и gaps, но не как neutral proof of effectiveness.

**Статус:** DIRECTOR-CLOSED.

## Q103. Что означает «100 анализов»?

**Решение:** каждый из 50 ресурсов получил ровно два structured analyses: A — instructional value/pattern; B — novice gap and Signal Arena implication. Это design synthesis, а не утверждение о 100 независимых causal experiments.

**Статус:** DIRECTOR-CLOSED.

## Q104. Какова иерархия доверия к crypto education sources?

**Решение:** regulatory/consumer-safety и academic sources сильнее для claims about risks and mechanisms; official protocol docs сильнее для protocol facts; exchange/wallet/token/vendor resources полезны для UI/mechanics, но имеют incentive bias; books and opinionated media требуют attribution, date and counter-perspective. Ни один source type сам по себе не доказывает learning effectiveness.

**Статус:** DIRECTOR-CLOSED.

## Q105. Каков единый портрет crypto-новичка?

**Решение:** это не обязательно будущий трейдер, а человек, которому нужно понять, как не потерять контроль, не подписать вредное действие, не отправить актив не туда и не принять маркетинговый claim за evidence. Он узнаёт бренды и термины, но путает network, token, wallet, address, key, custodian, exchange и protocol; часто имеет confidence выше demonstrated competence.

**Статус:** DIRECTOR-CLOSED.

## Q106. Каковы top-20 pains текущего рынка?

**Решение:** полный список P01–P20 находится в Iteration 6 report. Core pattern: fragmentation, jargon before mental model, custody/transaction confusion, theoretical security, late scam training, reward/quiz distortion, missing uncertainty/calibration, no cross-chain transfer, academic overload, platform bias, stale content and lack of evidence of safe independent reasoning.

**Статус:** DIRECTOR-CLOSED.

## Q107. Какой shortest effective path принят для Signal Arena?

**Решение:** Crypto Safety & Decision Literacy Path: (0) crypto without hype; (1) network and transaction timeline; (2) custody and security; (3) asset/protocol taxonomy; (4) evidence and risk; (5) optional DeFi/on-chain scenarios; (6) novel transfer and diagnostic. Trading, price prediction, deposits, P&L, leverage, yield farming and real asset ownership остаются вне MVP.

**Статус:** DIRECTOR-CLOSED.

## Q108. Как удаляется «вода» из curriculum?

**Решение:** материал остаётся только если меняет observation, verification, decision или safety. Каждый unit обязан иметь one concept, visual contrast, worked example, retrieval, security/no-action decision, changed-context transfer, debrief with known/unknown/risk и delayed recall. История, ideology, duplicated glossary, project promotion и protocol-specific UI откладываются или удаляются.

**Статус:** DIRECTOR-CLOSED.

## Q109. Как относятся к learn-and-earn, badges и token rewards?

**Решение:** reward mechanics не считаются mastery и не должны требовать exchange signup, deposit или token ownership. Допустимы cosmetic/non-transferable progress markers; mastery определяется самостоятельным process score, critical-error veto, confidence calibration, delayed recall и novel transfer. Reward ablation обязателен в alpha.

**Статус:** DIRECTOR-CLOSED.

## Q110. Какова текущая scorecard после crypto review?

**Решение:** overall 86/100 (average 85.5): crypto clarity 92; sequencing 91; security/fraud 88; active decision practice 90; cross-chain transfer 84; mastery/calibration 88; neutrality 89; accessibility/localization 78; telemetry/research validity 75; production readiness 83. Это strategy/design score, не доказанный runtime learning result.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q111. Какой следующий обязательный implementation slice?

**Решение:** 27 synthetic seeds: transaction observation, custody/security evidence и claim/risk classification; по 3 task families × 3 tiers. Проверки: wrong network, wrong recipient, malicious approval, fake support, urgency/guaranteed-return scam, stale tokenomics, stablecoin failure, source conflict, unknown/stop decision и delayed cross-surface transfer.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha protocol.

## Q112. Какова цель Iteration 7?

**Решение:** поднять crypto beginner strategy с 86 до целевого **95/100** не добавлением контента, а закрытием доказуемых gaps: security, transfer, accessibility, telemetry, neutrality, mastery и production readiness.

**Статус:** DIRECTOR-CLOSED.

## Q113. Что означает 95/100 в Iteration 7?

**Решение:** это **conditional design score**. 95 набирается только после прохождения десяти evidence gates. До alpha нельзя утверждать, что users уже учатся, принимают безопасные решения или защищены от real-world scams на 95/100.

**Статус:** DIRECTOR-CLOSED.

## Q114. Что добавлено в Safety Kernel v2?

**Решение:** critical-error veto для wrong recipient, wrong network, unsafe approval, fake support и guaranteed-return pressure; explicit stop/verify-more; synthetic/no-money interaction; repair after critical error; hints without mastery credit; запрет seed phrase/private key/real balance inputs.

**Статус:** DIRECTOR-CLOSED.

## Q115. Как поднять transfer score 84 до 95?

**Решение:** учить не интерфейс wallet, а chain-neutral decision schema: network, recipient, key control, permission/signature, fee, confirmation, evidence and unknown. Один и тот же skill должен появляться в fictional wallet, custodial exchange и bridge-like surface, включая delayed novel transfer.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q116. Какие accessibility requirements обязательны для 95-point design?

**Решение:** keyboard completion, visible focus, screen-reader labels, non-colour cues, reduced-motion mode, plain-language mode, English/Russian glossary parity, region/legal separation и отсутствие требования раскрывать assets, nationality или exchange account. Automated checks недостаточны без moderated assistive-technology walkthrough.

**Статус:** DIRECTOR-CLOSED / PROPOSED до accessibility audit.

## Q117. Какие telemetry restrictions добавлены?

**Решение:** consent, deletion, pseudonymous/versioned events, idempotent replay, no future-data leakage, no seed/private-key/address/balance/financial-account fields и separate research aggregates. Primary metrics: critical-error rate, process score, delayed recall, novel transfer и calibration gap; price/profit/deposit/reward не являются learning metrics.

**Статус:** DIRECTOR-CLOSED / PROPOSED до replay test.

## Q118. Какие десять evidence gates определяют получение 95?

**Решение:** scope/taxonomy; prerequisites; security veto; decision quality; transfer; calibration; neutrality; accessibility; telemetry integrity; production readiness. Провал critical gate caps overall score at 89 до исправления.

**Статус:** DIRECTOR-CLOSED.

## Q119. Что входит в новый alpha seed pack?

**Решение:** 27 deterministic synthetic seeds: 3 mechanics (transaction observation, custody/security evidence, claim/risk classification) × 3 task families × 3 difficulty levels. Все scenarios no-money, replayable, cross-surface и проверяют safe reasoning, а не market outcome.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha protocol.

## Q120. Когда можно считать 95 реально earned?

**Решение:** после трёх clean deterministic replays, schema/content lint, zero sensitive-field telemetry violations, zero release-blocking accessibility defects, successful safety-veto traces и alpha evidence по delayed recall, novel transfer, calibration и critical-error rate. Если хотя бы один critical gate не пройден, score остаётся ниже 95.

**Статус:** DIRECTOR-CLOSED / PROPOSED до alpha.

## Q121. Почему текущие четыре группы skill cards — ошибка?

**Решение:** READ, DECIDE и PROTECT отвечают на разные пользовательские вопросы, а PROTOCOL является не предметной областью, а способом выполнения правила. Ставить их в один ряд — смешивать domain taxonomy и interaction method. Primary navigation должна содержать только три группы.

**Статус:** DIRECTOR-CLOSED.

## Q122. Какие три primary groups приняты?

**Решение:** `READ` / Рынок / evidence; `DECIDE` / Сделка / plan and action; `PROTECT` / Дисциплина / risk and process preservation. Это выравнивается с тремя каноническими ветками Skill Tree: Рынок, Сделка, Дисциплина.

**Статус:** DIRECTOR-CLOSED.

## Q123. Что делать с PROTOCOL?

**Решение:** удалить PROTOCOL как четвёртую ветку и сохранить как orthogonal `protocol` tag или checklist badge. Evidence Only, No Confirmation No Trade и Preserve the System могут иметь tag `protocol`, но остаются в своей primary group.

**Статус:** DIRECTOR-CLOSED.

## Q124. Как должны использоваться цвета групп?

**Решение:** зелёный, красный и amber/yellow не используются для group identity. После визуальной проверки bright blue/orange/purple также смягчены: карточки не должны быть кислотными. Финальная card palette: READ — muted blue-gray surface `#1B2734` with `#71849A`; DECIDE — muted clay-orange surface `#332923` with `#B58A6F`; PROTECT — smoky purple surface `#2B2631` with `#988AA5`. Yellow не используется для группы, потому что уже читается как warning/caution. Group token применяется мягко к rail, border и English label; metallic icon material carries rank.

**Статус:** DIRECTOR-CLOSED / PROPOSED до UI audit.

## Q125. Для чего зарезервированы green, red и amber?

**Решение:** green `#22C55E` — только explicit completed/success; red `#EF4444` — error/critical; amber `#F59E0B` — warning/caution. Каждый state обязан иметь icon и text, чтобы цвет не был единственным каналом.

**Статус:** DIRECTOR-CLOSED.

## Q126. Как отображать 3 ранга каждой карты?

**Решение:** не менять group color. В верхнем правом углу постоянный rank seal: `I · KNOW`, `II · APPLY`, `III · OWN`; дополнительно 1/2/3 filled pips и нейтральная material ladder steel/silver/platinum. Progress ring показывает прогресс внутри ранга и не заменяет rank seal.

**Статус:** DIRECTOR-CLOSED.

## Q127. Почему нельзя использовать stars или зелёную заливку для rank III?

**Решение:** Mastery Stars уже заняты economy/progression vocabulary; повторное использование создаёт конфликт. Зелёный rank III выглядит как completed state, хотя III может быть available, in progress или needs_review. Rank — это mastery depth, а не success/error state.

**Статус:** DIRECTOR-CLOSED.

## Q128. Какие поля должны быть в SkillCardData?

**Решение:** обязательны `group: read|decide|protect`, `rank: 1|2|3`, `rankLabel: know|apply|own`, `state`, `protocolTags` и `progressInRank`. `difficultyBand` хранится отдельно, если нужна сложность. `tier: beginner|intermediate|advanced` больше не используется как mastery rank.

**Статус:** DIRECTOR-CLOSED / PROPOSED до schema migration.

## Q129. Как проверить, что новая визуальная система не сломана?

**Решение:** обязательны tests G01–G10 из visual-system report: ровно 3 primary groups; protocol filtering без четвёртой ветки; stable group colors; green/red/amber только states; rank semantics; color-independent rank recognition; progress/rank separation; 270px readability; screen-reader order; 15/9/16 canonical card mapping.

**Статус:** DIRECTOR-CLOSED / PROPOSED до UI audit.

## Q130. Что исправлено после визуальной проверки prototype?

**Решение:** previous cool palette была отклонена дважды: indigo READ / violet DECIDE сближались, затем cyan READ конфликтовал с branded teal. Bright blue/orange/purple тоже признаны слишком насыщенными для card surfaces. Финальная система использует soft blue-gray / soft clay-orange / smoky purple cards; bronze/silver/gold icon materials остаются главным rank signal. Цвет не является единственным каналом: сохраняются English label, icon и stable rail.

**Статус:** DIRECTOR-CLOSED / PROPOSED до UI audit.

## Q131. Почему выбран мягкий оранжевый, а не жёлтый?

**Решение:** clay-orange лучше отделяет DECIDE от бренда teal и blue READ, но не делает карточку кислотной. Yellow/amber не выбран для группы, потому что в интерфейсе уже должен означать warning/caution. DECIDE использует muted clay-orange `#B58A6F` на surface `#332923`; amber `#F59E0B` сохраняется только для warning state.

**Статус:** DIRECTOR-CLOSED / PROPOSED до UI audit.

## Q132. Какой минимальный состав card face принят?

**Решение:** сверху слева только English group label `READ`, `DECIDE` или `PROTECT`; сверху справа только numeral rank `I`, `II` или `III`; затем большая иконка соответствующего материала; ниже название ровно в две строки. Description, duration, lesson count, tags и XP убраны с лицевой стороны и могут появляться только в detail view.

**Статус:** DIRECTOR-CLOSED / PROPOSED до UI audit.

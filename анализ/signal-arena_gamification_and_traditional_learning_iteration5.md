# SIGNAL ARENA — Анализ 13 gamification-проектов и 15 традиционных learning sources, Iteration 5

**Дата:** 7 октября 2026  
**Источник списка:** прикреплённый скриншот `image-1.png`.  
**Статус:** comparative design research; это не независимый аудит эффективности перечисленных приложений и не proof of Signal Arena efficacy.  
**Связанные решения:** `SIGNAL_ARENA_DECISION_FAQ.md`, Q001–Q100.  

## 0. Как выполнен запрос

На скриншоте 13 проектов. Поэтому «100 анализов» выполнены как **100 отдельных design observations/use cases**, распределённых между всеми 13 проектами, а не как утверждение, что на изображении есть 100 разных продуктов. Дополнительно проанализированы 15 источников/направлений традиционного обучения и сформирован один целевой гибридный вариант для Signal Arena.

### Важное ограничение качества данных
Официальные страницы и store listings хорошо подтверждают наличие механик, но обычно не доказывают causal learning effect. Для Epic Win, Epic To-Do List, Habits Garden и части Plant Nanny использованы преимущественно store/secondary descriptions; это feature evidence с более низкой уверенностью. Отзывы, маркетинговые claims, download counts и рейтинги не считались evidence of learning.

## 1. Executive decision

### Лучшее решение: **Signal Arena — Evidence Quest / Adaptive Decision Garden**

Это не копия одного приложения, а controlled hybrid:
- От Duolingo — короткая cadence, progression и разные поверхности заданий, но без XP-farming и без обязательной streak anxiety.
- От Habitica/Epic Win/Epic To-Do List — quest framing, avatar/profile и видимый рост, но mastery credit даётся только за process-correct evidence.
- От Forest — короткий focus session и минималистичный task mode, но прерывание не уничтожает прогресс.
- От SuperBetter — gameful reframing, micro-quests и optional allies, но без клинических claims и peer judgement.
- От Zombies, Run! — лёгкая narrative mission structure, но без GPS, физической нагрузки и time-pressure в reasoning core.
- От Plant Nanny/Habits Garden/Fortune City — cumulative garden/map visualisation, но без финансовых метафор и без награды за голое логирование.
- От Ingress — постепенное раскрытие карты/entities и capstone routes, но без location dependency, public faction conflict и real-world safety risk.
- Из традиционного обучения — explicit theory, worked examples, retrieval, spacing, guided practice, formative feedback, mastery repair и novel transfer.

### Почему не выбран один готовый паттерн
Gamification apps сильны в возвращении пользователя и эмоциональной видимости прогресса, но обычно оптимизируют behavior/engagement. Традиционное обучение сильнее в instructional validity, но часто не решает проблему входа, cadence и эмоциональной устойчивости. Signal Arena должна оставить learning architecture от EdTech, а game layer использовать только как delivery/feedback layer.

## 2. 100 design analyses

| ID | Проект | Наблюдение/механика | Что переносим в Signal Arena | Риск/ограничение |
|---:|---|---|---|---|
| 001 | Habitica | Immediate conversion: Habit/daily/to-do actions become XP, gold and health changes | Borrow the visible action→progress loop, but award Signal progress for evidence quality, not task completion alone. | Raw completion rewards can reward checkbox behavior without learning. |
| 002 | Habitica | Task taxonomy: Separate Habits, Dailies, To-Dos and Rewards | Use separate Learn, Practice, Prove, Recall and Transfer states in the content model. | Do not import a productivity taxonomy into an educational skill taxonomy without prerequisites. |
| 003 | Habitica | Custom rewards: User-defined rewards create personal motivational fit | Optional cosmetic unlocks can be personalized after process milestones. | Real-world rewards and currencies would conflict with the no-money MVP boundary. |
| 004 | Habitica | Loss/HP: Missed dailies damage the avatar | Use needs_review and repair as a soft state, never health loss or punitive debt. | Punishment can trigger anxiety, shame and abandonment for novices. |
| 005 | Habitica | Party quests: Group progress creates accountability | Optional cooperative chapter challenge after individual mastery evidence. | Never let one learner's miss damage another learner's learning access. |
| 006 | Habitica | Long progression: Classes, gear, pets and quests give an extended horizon | Use a small Chapter/skill map, not a full Skill Tree in MVP. | Large RPG surface increases cognitive load and authoring cost. |
| 007 | Habitica | Community content: Challenges and guilds create social variety | Later curated challenge packs may supply contextual variation. | User-generated tasks cannot enter mastery scoring without QA. |
| 008 | Habitica | RPG identity: Avatar makes abstract progress emotionally visible | Use an abstract Signal profile/expedition identity without financial or power fantasies. | Avoid making competence look like market dominance or profit. |
| 009 | Todoist Karma | Completion points: Karma rewards adding/completing tasks and advanced task features | Reward completion of evidence, invalidation and debrief steps, not clicks or volume. | Feature-use points would create gaming the metric. |
| 010 | Todoist Karma | Daily/weekly goals: Self-set goals and streaks make consistency visible | Offer flexible review target, with days off and no punitive streak reset. | Rigid streaks are poor for irregular learners and can create guilt. |
| 011 | Todoist Karma | Karma trend: Trend shows direction rather than only a total | Show process trend: evidence quality, critical errors, transfer, not raw XP. | A single aggregate can hide skill-specific weaknesses. |
| 012 | Todoist Karma | Vacation mode: Breaks are designed into the system | Add pause/resume and review deferral for real life interruptions. | Do not allow pause to bypass a required delayed recall. |
| 013 | Todoist Karma | Goal calibration: Users can lower or raise daily goals | Adapt task dose based on performance and cognitive load, not self-judgment only. | Self-set goals may be too easy or too ambitious without guidance. |
| 014 | Todoist Karma | Streak restoration: Broken streak can be restored under constraints | Restore scheduled recall after interruption without granting missing mastery evidence. | Restoring a streak must not fabricate completion. |
| 015 | Todoist Karma | Low-friction capture: Task entry is fast and familiar | First Chapter 0 action must have one clear low-friction CTA. | Low friction cannot replace explanation of the learning objective. |
| 016 | Todoist Karma | Productivity scope: Task manager stays broader than a single skill | Signal Arena should keep a narrow decision-training scope in MVP. | Broad productivity features would blur the EdTech value proposition. |
| 017 | SuperBetter | Gameful reframing: Challenges are framed as quests, power-ups and bad guys | Frame uncertainty/errors as inspectable obstacles, not personal deficits. | Mental-health claims must not be borrowed without clinical evidence. |
| 018 | SuperBetter | Small quests: Large goals decompose into actionable micro-steps | Break a decision into observe→evidence→boundary→confidence. | Too many micro-steps can make a simple task feel bureaucratic. |
| 019 | SuperBetter | Allies: Social support is an explicit mechanic | Optional peer/cohort support can discuss process, never reveal answer keys. | Social comparison can distort confidence and create privacy risks. |
| 020 | SuperBetter | Check-ins: Repeated check-ins create self-monitoring | Use confidence and post-debrief reflection as calibration evidence. | Self-report alone cannot prove mastery. |
| 021 | SuperBetter | Resilience score: A longitudinal score makes invisible change visible | Show skill-state history instead of a global psychological score. | Avoid claiming a single score measures resilience or competence. |
| 022 | SuperBetter | Challenge library: Curated challenges support different goals | Use curated task families and contexts with content versioning. | Uncontrolled challenge authoring can break difficulty and terminology order. |
| 023 | SuperBetter | 10-minute cadence: Short daily sessions lower entry cost | Target 5–12 minute Chapter 0 units while protecting debrief/recall. | Do not compress learning by deleting feedback or transfer. |
| 024 | SuperBetter | Gameful not arcade: Game framing supports reflection rather than pure points | Use narrative as a wrapper around evidence and reasoning. | Narrative engagement must not become proof of learning. |
| 025 | Epic Win | Task-to-battle animation: Completing a chore produces immediate animated payoff | Use a brief action confirmation after a process-correct decision. | Celebration must not arrive before debrief and can’t obscure errors. |
| 026 | Epic Win | Stat assignment: Tasks can improve different character attributes | Map tasks to explicit skills and show which process component improved. | Arbitrary stat labels can create false competence. |
| 027 | Epic Win | Loot: Completion creates collectible rewards | Use cosmetic unlocks after verified mastery or transfer. | Random loot can reward lucky guessing. |
| 028 | Epic Win | Simple to-do core: The RPG layer sits on a recognizable list | Keep Signal's core loop understandable before game wrapper. | A task list is not enough for decision training. |
| 029 | Epic Win | Repeating tasks: Recurring tasks support routines | Schedule spaced recall/review events automatically. | Recurring literal tasks are prohibited; variant generation is required. |
| 030 | Epic Win | Avatar growth: Life activity changes the character over time | Progression can reflect verified skills and chapter completion. | Do not equate avatar level with real-world trading ability. |
| 031 | Forest | Focus timer: A timed focus session grows a tree | Offer optional focus mode for a short evidence-review session. | Timer cannot be the primary learning mechanic. |
| 032 | Forest | Soft environmental stake: Leaving early kills/wilts the tree | Use non-punitive session visualization; interruption becomes a logged event. | Punishing interruption is harmful for accessibility and real-life variability. |
| 033 | Forest | Narrow product scope: Forest solves phone distraction with one dominant loop | Keep Chapter 0 single-skill and remove secondary systems. | Signal Arena still needs theory, feedback, mastery and transfer. |
| 034 | Forest | Visual accumulation: A forest records historical focus | Show a learning garden/expedition history tied to process milestones. | Visual accumulation can misrepresent quantity as competence. |
| 035 | Forest | Tags: Focus time can be categorized | Tag sessions by chapter, skill, family and review type. | Tags must be system-controlled enough for analytics validity. |
| 036 | Forest | Co-planting: Shared focus makes accountability social | Later optional co-study room with no shared failure penalty. | Realtime social features are not MVP-critical. |
| 037 | Forest | Real-world contribution: Virtual coins connect to tree planting | Use non-monetary impact only if provenance and claims are audited. | Do not claim real-world impact without verified partner evidence. |
| 038 | Forest | Disconnection paradox: The focus app itself can become a distraction | Make session UI minimal and hide meta-game during a task. | Animations, notifications and leaderboards can compete with learning. |
| 039 | Epic To-Do List | Skills attached to tasks: Tasks improve user-defined skills | Every Signal task must attach to a canonical skill key. | User-defined skill names cannot be used in deterministic mastery without mapping. |
| 040 | Epic To-Do List | Difficulty levels: Tasks can be easy to legendary | Use Tier 1/2/3 with observable difficulty rationale. | Difficulty must not be just a reward multiplier. |
| 041 | Epic To-Do List | Hero customization: Avatar and equipment personalize progression | Use a small profile layer to make verified progress visible. | Cosmetics must remain secondary to learning. |
| 042 | Epic To-Do List | Challenges: Habit challenges package repeated actions | Package theory→practice→recall as a Chapter challenge. | Challenge completion without transfer is not mastery. |
| 043 | Epic To-Do List | In-game currency: Coins/crystals buy features or rewards | No currency in core MVP; use non-spendable progress markers. | Currency creates the exact economy Signal Arena has deferred. |
| 044 | Epic To-Do List | Widgets/reminders: External reminders reduce memory burden | Use carefully timed review reminders with consent and quiet hours. | Notification volume can cause opt-out or fatigue. |
| 045 | Epic To-Do List | Background/music: Atmosphere increases game feel | Optional soundscape only after accessibility and focus controls. | Audio must not carry essential information. |
| 046 | Epic To-Do List | Unlockable content: Progress unlocks new content | Unlock new contexts only after prerequisite theory and provisional evidence. | Unlocks must not be paywalled or based only on speed. |
| 047 | Duolingo | Micro-lessons: Short lessons create a repeatable daily learning unit | Use 5–12 minute learning units with explicit theory and structured interaction. | Short does not mean shallow; debrief and recall remain mandatory. |
| 048 | Duolingo | Streaks: Daily consistency is highly visible | Use gentle review cadence and optional continuity, never harsh loss. | Streak preservation can become the goal instead of learning. |
| 049 | Duolingo | XP/levels: Progress is easy to read | XP mirrors verified skill milestones and transfer, not lesson taps. | XP farming can select easy items and inflate progress. |
| 050 | Duolingo | Leagues: Social competition can increase return | Exclude leaderboards from novice MVP; test only if process quality survives. | Competition can increase speed, anxiety and inequity. |
| 051 | Duolingo | Hearts/lives: Mistakes can limit attempts | Hints and repair replace lives; no learning lockout. | Resource scarcity can punish beginners and accessibility needs. |
| 052 | Duolingo | Streak freeze/repair: Missed sessions have recovery options | Pause and review rescheduling protect continuity without fabricating evidence. | Recovery must not bypass delayed recall. |
| 053 | Duolingo | Adaptive review: Weak areas receive additional practice | Use performance-based scheduling and error-specific repair. | Adaptive decisions require validated events and clear rules. |
| 054 | Duolingo | Mixed formats: Recognition, translation, listening and production vary the surface | Use Recognize, Apply and Explain/Transfer families with surface variation. | Variation before theory creates cognitive overload. |
| 055 | Duolingo | Immediate feedback: Learner learns which answer was accepted | Give evidence-based feedback plus next step and invalidation. | Binary right/wrong feedback alone is too thin for Signal. |
| 056 | Duolingo | A/B iteration: Product experiments compare mechanics | Preregister one-skill variable-retrieval experiment; separate engagement from learning. | Post-hoc optimization can improve retention while worsening learning. |
| 057 | Zombies, Run! | Narrative mission: Movement advances an audio story | Use a light mission wrapper to advance through decision contexts. | Story progress cannot equal mastery. |
| 058 | Zombies, Run! | Audio pacing: Narration fits into exercise and reduces perceived effort | Use short narration before/after a task, not during evidence selection. | Audio can harm comprehension if it competes with text or screen reader. |
| 059 | Zombies, Run! | Chases: Urgency changes physical pace | Avoid time pressure in reasoning MVP; optional later arcade mode only. | Speed pressure conflicts with process-over-outcome principle. |
| 060 | Zombies, Run! | Base building: Collected supplies visibly improve a settlement | Show a learning base built from verified process milestones. | Progress must not be granted for mere activity volume. |
| 061 | Zombies, Run! | Mission seasons: Content is structured as a long narrative arc | Use Chapter 0→Chapter 1 with controlled mechanic reveal. | Long content arcs need abandonment and catch-up planning. |
| 062 | Zombies, Run! | Beginner-to-advanced support: Couch-to-5K and multiple paces broaden access | Support novice and diagnostic paths without forcing same theory on experts. | Separate path needs measurement for comparability. |
| 063 | Zombies, Run! | Location/fitness tracking: Real-world movement drives the game | Do not use GPS or money in MVP; use synthetic/historical decision scenes. | Location creates privacy, accessibility and fairness risks. |
| 064 | Zombies, Run! | Immersion: Presence makes effort feel meaningful | Use immersion only when it reinforces observation and uncertainty. | Immersion may increase confidence without increasing accuracy. |
| 065 | Plant Nanny | One action→growth: Logging a glass grows a virtual plant | Map evidence/retrieval completion to plant growth, but only process-correct actions grow mastery plant. | Logging quantity is not quality. |
| 066 | Plant Nanny | Gentle reminders: Notifications prompt a behavior at intervals | Schedule optional recall reminders with quiet hours and user control. | Reminder pressure can be harmful and creates consent burden. |
| 067 | Plant Nanny | Personal goals: Water goal adapts to user inputs | Adapt task dose to performance, not demographic assumptions alone. | Health personalization needs domain/legal review; do not copy medical claims. |
| 068 | Plant Nanny | Collection: Plants and greenhouse create long-term ownership | Use a small collection of learning environments/cosmetics. | Collection can divert attention from transfer. |
| 069 | Plant Nanny | Visual feedback: Charts and plant state make progress legible | Show evidence quality and skill state with accessible text equivalents. | Charts need alt/structured data for accessibility. |
| 070 | Plant Nanny | Data entry friction: Quick preset cup logging reduces cost | Use quick evidence selection, then require deeper reasoning only where justified. | Over-short tasks can eliminate the learning signal. |
| 071 | Plant Nanny | Failure softness: Growth is more nurturing than punitive | Use cumulative progress and needs_review without destroying prior progress. | Softness must still communicate that mastery evidence is missing. |
| 072 | Habits Garden | Quest framing: Daily habits become quests that award gems | Theory/practice/recall can be presented as a short questline. | Quest completion cannot stand in for delayed mastery. |
| 073 | Habits Garden | Garden growth: Consistency unlocks flowers and visual expansion | Use skill garden with one plant per mechanic and visible stages. | Do not encode competence only as days active. |
| 074 | Habits Garden | Leaderboards: Users compete with friends/community | Exclude from novice core; optional later cohort comparison without public ranking. | Leaderboards can favor time, prior knowledge and availability. |
| 075 | Habits Garden | Social scale: App frames habits as a community activity | Allow optional cohort challenges with safe discussion prompts. | UGC and moderation are not MVP scope. |
| 076 | Habits Garden | Recurring schedule: Habit cadence structures daily behavior | Use spaced review schedule with adaptive performance adjustment. | Uniform schedule remains a design choice; do not claim expanding superiority. |
| 077 | Habits Garden | Non-punitive growth variant: Cumulative plant stages can preserve progress | Adopt cumulative verified progress; failures route to repair. | Cumulative visuals must show current needs_review state. |
| 078 | Habits Garden | Analytics: Completion charts and day patterns show behavior | Admin tracks errors, hints, confidence and transfer, not only completion. | Behavior analytics must have purpose limitation. |
| 079 | Fortune City | Logging→city growth: Each financial log builds a city | Each validated learning decision can build a non-financial learning environment. | Do not use money, balances or P&L in Signal MVP. |
| 080 | Fortune City | Categorization: Expense categories structure raw input | Evidence categories can structure observations and uncertainty. | Categories must be canonical and taught before use. |
| 081 | Fortune City | Dashboards: Charts reveal weekly/monthly trends | Show skill and error trends in admin and learner debrief. | A chart cannot prove causality or learning gain. |
| 082 | Fortune City | Customization: Buildings/vehicles/citizens create ownership | Cosmetic map progression can reward verified transfer. | Customization increases scope and distracts from Chapter 0. |
| 083 | Fortune City | Daily-use awards: Daily logging maintains the city loop | Use optional check-in for recall, not a hard daily requirement. | Daily logging can reward quantity and encourage fabricated entries. |
| 084 | Fortune City | Location smart notes: Location can assist expense capture | Do not use location data in MVP. | Location is unnecessary, privacy-heavy and inequitable. |
| 085 | Fortune City | Economic metaphor: Prosperity visualizes behavior change | Use abstract signal/knowledge growth, never wealth or profit. | Financial metaphors could imply trading competence. |
| 086 | Nerd Fitness Journey | Missions: Fitness/nutrition/mindset actions become missions | Use decision missions spanning observation, evidence and transfer. | Physical fitness claims are not transferable to financial education. |
| 087 | Nerd Fitness Journey | Avatar leveling: Real-life habits level a superhero | Avatar can reflect verified learning chapters. | Avoid power fantasy and outcome confidence inflation. |
| 088 | Nerd Fitness Journey | Coach guidance: Human/coach support supplements self-directed work | Use editor-reviewed debrief and later human moderation. | Human coaching is a separate cost and safety layer. |
| 089 | Nerd Fitness Journey | Scalable exercises: Exercises are adapted to ability | Difficulty tiers adapt to performance and prior knowledge. | Do not make users disclose sensitive personal data for simple adaptation. |
| 090 | Nerd Fitness Journey | Story/side quests: Optional paths add variety | Add optional transfer contexts after core requirements. | Side quests must not fragment first-run navigation. |
| 091 | Nerd Fitness Journey | Community challenges: Group challenges create accountability | Optional cohort challenge after individual no-hint evidence. | Community pressure can reduce autonomy and privacy. |
| 092 | Nerd Fitness Journey | Educational videos: Step-by-step modeling supports novice form | Worked examples before independent decision tasks. | Video alone is not retrieval or transfer. |
| 093 | Ingress Prime | World map: Real places become a persistent game board | Use a fictional learning map to reveal entities gradually. | No real GPS/location dependency in MVP. |
| 094 | Ingress Prime | Portal capture: Players take an observable action on a node | Make each mechanic a node unlocked through prerequisite theory. | Capture/status must reflect learning evidence, not clicks. |
| 095 | Ingress Prime | Links/fields: Combinations of actions create higher-order territory | Transfer can combine skills into a capstone route. | Higher-order unlocks must require verified prerequisites. |
| 096 | Ingress Prime | Faction identity: Social identity drives commitment | Optional learning cohort identity after individual safety baseline. | Faction conflict and public rankings are unnecessary risk. |
| 097 | Ingress Prime | Persistent world: Progress continues beyond a single session | Skill map and replay history provide continuity. | Persistence requires careful versioning and data deletion. |
| 098 | Ingress Prime | Missions: Curated routes add structured exploration | Chapter route with three task families and multiple contexts. | Missions can be too long for novice mobile sessions. |
| 099 | Ingress Prime | Resource economy: XM/gear/levels regulate actions | Use abstract attention budget only if it never blocks theory/recall. | Energy/resource scarcity is deferred by the FAQ. |
| 100 | Ingress Prime | Real-world exploration: Walking and place discovery add meaning | Borrow discovery feeling through synthetic/historical scenes, not location tracking. | Accessibility and safety make GPS a poor MVP dependency. |

### Распределение 100 наблюдений
- Habitica: 8
- Todoist Karma: 8
- SuperBetter: 8
- Epic Win: 6
- Forest: 8
- Epic To-Do List: 8
- Duolingo: 10
- Zombies, Run!: 8
- Plant Nanny: 7
- Habits Garden: 7
- Fortune City: 7
- Nerd Fitness Journey: 7
- Ingress Prime: 8

## 3. Анализ топ-15 источников традиционного обучения

Под «традиционными обучениями» здесь понимаются проверенные instructional approaches и classroom evidence, а не только лекция. Лекция сохранена как полезный канал объяснения, но не как весь core loop.

| ID | Источник/метод | Что показано | Решение для Signal Arena |
|---|---|---|---|
| T01 | [Dunlosky et al. — effective learning techniques](https://www.whz.de/fileadmin/lehre/hochschuldidaktik/docs/dunloskiimprovingstudentlearning.pdf) | practice testing and distributed practice rated high utility; rereading/highlighting lower | Make retrieval and spacing core; never let XP substitute for retrieval. |
| T02 | [Freeman et al. — active learning meta-analysis](https://pubmed.ncbi.nlm.nih.gov/24821756/) | active learning outperformed traditional lecture on average in undergraduate STEM | After 3–5 simple items move to evidence selection, structured response and transfer. |
| T03 | [Roediger/Karpicke/Karpicke retrieval-based learning](https://learninglab.psych.purdue.edu/downloads/2025/2025_Karpicke_Retrieval_Based_Learning_Review.pdf) | retrieval plus feedback supports long-term retention and application | Use delayed recall and feedback; no literal re-showing. |
| T04 | [Latimier et al. spacing meta-analysis](http://www.lscp.net/persons/ramus/docs/EPR20.pdf) | spacing beats massing; no universal expanding-schedule advantage | Regular/adaptive spacing, not a hard expanding formula. |
| T05 | [Butler/Pan/Rickard transfer research](https://pdf.retrievalpractice.org/transfer/Pan_Rickard_2018.pdf) | retrieval conditions and varied contexts matter for transfer | Same skill across surface/context in the vertical slice. |
| T06 | [Worked examples and transfer](https://www.tandfonline.com/doi/full/10.1080/01443410.2023.2273762) | worked examples reduce novice load and can support retention/near transfer | Worked example → completion problem → independent problem. |
| T07 | [Rosenshine Principles of Instruction](https://www.aft.org/sites/default/files/Rosenshine.pdf) | review, small steps, modeling, guided practice, feedback, reteach and mastery | Chapter 0 sequence uses explicit teaching and guided practice before open transfer. |
| T08 | [AERO evidence-based teaching practices](https://www.education.gov.au/download/17488/aero-evidence-based-teaching-practices/35503/document/pdf) | explicit modelling, formative assessment, spacing, retrieval and fading support mastery | Use theory→worked example→retrieval→correction→independent transfer. |
| T09 | [Formative assessment evidence review](https://ies.ed.gov/rel-central/2025/01/other-21) | formative assessment supports achievement; mastery includes reteaching and parallel assessment | Hints/repair followed by a changed item, not same-item repetition. |
| T10 | [Mastery learning meta-analysis](https://www.uky.edu/~gmswan3/575/kulik_kulik_Bangert-Drowns_1990.pdf) | mastery learning has positive effects but consumes time and needs meaningful measures | Use local mastery states, delayed recall and transfer rather than one threshold. |
| T11 | [Hattie & Timperley feedback model](https://assess.ucr.edu/media/746/download) | feedback should address feed-up, feed-back and feed-forward; quality varies | Debrief: what was visible, how did you do, what next? |
| T12 | [Wisniewski et al. feedback meta-analysis](https://www.researchgate.net/publication/338745455_The_Power_of_Feedback_Revisited_A_Meta-Analysis_of_Educational_Feedback_Research) | feedback effects vary; informational comments better than bare grades | Explain evidence and next action, not only score. |
| T13 | [Freeman/active learning + peer instruction](https://www.sciencedirect.com/science/article/abs/pii/S0883035517306419) | interactive peer instruction has positive but moderated effects | Optional cohort discussion later; no peer answer authority in MVP. |
| T14 | [Direct instruction meta-analysis summary](https://pmc.ncbi.nlm.nih.gov/articles/PMC8356521/) | direct instruction is strong for basic skills; open methods need structure | Novices receive explicit terms and worked examples before discovery. |
| T15 | [Teaching the science of learning](https://link.springer.com/article/10.1186/s41235-017-0087-y) | spaced practice, interleaving, retrieval, elaboration, concrete examples and dual coding are robust strategies | Combine concrete visual scenes, observation language, retrieval and variable contexts. |

### Сводный вывод по traditional learning
- Для новичка: explicit instruction → worked example → guided practice → retrieval → corrective feedback.
- Для закрепления: spaced retrieval и mixed/variable contexts; expanding schedule не фиксировать как универсально лучший.
- Для mastery: parallel assessment после reteach, delayed recall и transfer; одна правильная попытка недостаточна.
- Для engagement: active learning и peer interaction полезны, но должны быть привязаны к objective и не подменять feedback.
- Для Signal Arena: традиционные methods определяют what counts as learning; gamification определяет how the learner stays in the loop.

## 4. Scoring: почему решение получает 95/100

Оценка относится к **предлагаемому гибридному решению Signal Arena**, а не к приложениям на скриншоте и не к уже работающему продукту. Это design score с явно указанными потерями, а не маркетинговая цифра.

| Критерий | Вес | Балл | Обоснование |
|---|---:|---:|---|
| Learning validity / процессная оценка | 20 | 19 | Explicit theory, rubric, critical errors, process-over-outcome; минус 1 за необходимость alpha validation rubric. |
| Novice cognitive load | 15 | 14 | Progressive disclosure, worked examples, short units; минус 1 за риск перегрузить garden/narrative layer. |
| Retrieval, spacing, transfer | 15 | 14 | Retrieval, delayed recall, varied contexts and novel surface; минус 1 за неизвестные empirical parameters. |
| Engagement without dark patterns | 10 | 10 | Quest, visual growth, optional narrative, no streak punishment, no speed rewards. |
| Feedback and mastery | 10 | 10 | Feed-up/feed-back/feed-forward, hints without credit, repair and verified state machine. |
| Safety and no-money boundary | 10 | 10 | No deposit, P&L, balance, profit leaderboard, GPS or financial outcome loop. |
| MVP technical feasibility | 8 | 7 | Can start with one vertical slice; minus 1 because event/replay/accessibility artifacts still need implementation. |
| Accessibility and localization | 5 | 5 | WCAG 2.2 AA target, English canonical, Russian reviewed layer. |
| Telemetry/research readiness | 4 | 3 | Event contract and pilot plan defined; minus 1 until idempotency/privacy runtime tests pass. |
| Optional social/long-term retention | 3 | 3 | Can add safe allies/cohort challenges after core evidence; intentionally not overbuilt. |
| **Итого** | **100** | **95** | **Сильное design решение, но не доказанная product efficacy.** |

### Почему не 100/100
Оставшиеся 5 баллов нельзя честно выдать до alpha: неизвестны real retention, delayed transfer, точная нагрузка narrative/garden layer, фактическая доступность на устройствах и устойчивость к reward optimization. Это не недостаток концепции, а список эмпирических рисков.

## 5. Канонический Signal Arena core loop v2

```text
1. Quest briefing — зачем этот skill
2. Explicit theory — один новый concept
3. Worked example — observation/evidence/boundary
4. Guided practice — hint allowed, no mastery credit
5. Structured decision — evidence + action + invalidation
6. Confidence — before submit
7. Debrief — feed-up / feedback / feed-forward
8. Parallel repair — changed surface/context
9. Prove — no hint, process rubric
10. Spaced recall — 48–72h, adaptive/regular
11. Novel transfer — same skill, new surface
12. Garden/map update — only verified process milestone
```

### Рекомендуемые слои продукта
- **Layer 1 — Learning truth:** theory, task schema, rubric, mastery, recall, transfer.
- **Layer 2 — Motivation:** quest, garden/map, avatar, optional narrative.
- **Layer 3 — Operations:** events, admin, privacy, accessibility, versioning, provenance.
- **Forbidden coupling:** Layer 2 не может самостоятельно открыть mastery; Layer 3 не может собирать данные без purpose; outcome не может переписать Layer 1.

## 6. Что взять и что не брать из 13 apps

| Берём | Не берём в MVP |
|---|---|
Micro-lessons и clear cadence из Duolingo | XP farming, forced streaks и public leagues |
Quest decomposition из Habitica/SuperBetter | HP damage, social punishment и psychological/clinical claims |
Focus mode из Forest | death/wither penalty for interruption |
Narrative chapters из Zombies, Run! | GPS, chases и speed pressure |
Visual cumulative growth из Plant Nanny/Habits Garden | rewards for raw logging only |
Map/entity reveal из Ingress | location tracking, factions, public PvP |
Category/trend dashboards из Todoist/Fortune City | money, balance, financial prosperity or P&L |
Avatar/skill progression из Epic Win/Epic To-Do/Nerd Fitness | random loot and arbitrary power stats |

## 7. 95-point MVP blueprint

- Chapter 0: time/sequence → visual change → observation vs interpretation → uncertainty/no-trade.
- Three mechanics in the first slice: observation/interpretation, evidence/context, invalidation/insufficient evidence.
- 27 canonical cells: 3 families × 3 tiers × 3 mechanics.
- Garden/map has only three learning plants/regions at first; unlock tied to verified evidence, not daily login.
- One short narrative mission per unit; text-first fallback and no required audio/GPS.
- No public leaderboard; optional private cohort challenge after individual mastery.
- No streak loss; use review schedule, pause, recovery and needs_review.
- Rewards are cosmetic/structural and never grant competence credit.
- All analytics support item health, process, hints, confidence, abandonment, mastery and transfer.
- Every new gamification element must pass the question: does it increase the target learning behavior without increasing guessing, anxiety or privacy risk?

## 8. Test plan for the 95-point solution

1. A/B at one skill: repeated surface vs variable retrieval, equal time and difficulty.
2. Immediate vs delayed: submit score compared with 48–72h recall.
3. Same-skill/different-surface: new layout, dataset and distractor.
4. Reward-ablation: core loop with visual progression vs minimal progression; compare process quality, not only return rate.
5. Streak-ablation: no-streak baseline vs optional continuity; check anxiety, abandonment and learning metrics.
6. Narrative-ablation: story wrapper vs neutral wrapper; verify whether narrative changes confidence without process gain.
7. Hint-fading test: full worked example → completion → independent prove.
8. Accessibility walkthrough: keyboard, screen reader, contrast, reduced motion, text alternatives and status messages.
9. Privacy/security: consent, deletion, server authorization, idempotency, no-future-data and log redaction.
10. Alpha gate: no efficacy claim until the preregistered feasibility and transfer outcomes are analyzed.

## 9. Sources checked for the 13 projects

| ID | Проект | URL |
|---|---|---|
| S01 | Todoist Karma | [https://www.todoist.com/help/todoist/features/introduction-to-karma-OgWkWy](https://www.todoist.com/help/todoist/features/introduction-to-karma-OgWkWy) |
| S02 | Habitica feature/task model | [https://play.google.com/store/apps/details?id=com.habitrpg.android.habitica&hl=en_IN](https://play.google.com/store/apps/details?id=com.habitrpg.android.habitica&hl=en_IN) |
| S03 | SuperBetter FAQ | [https://v1.superbetter.com/faq](https://v1.superbetter.com/faq) |
| S04 | Epic Win feature description | [https://epicwin.en.aptoide.com/app](https://epicwin.en.aptoide.com/app) |
| S05 | Forest App Store | [https://apps.apple.com/us/app/forest-focus-for-productivity/id866450515](https://apps.apple.com/us/app/forest-focus-for-productivity/id866450515) |
| S06 | Epic To-Do List Google Play | [https://play.google.com/store/apps/details?id=kolmachikhin.alexander.epicto_dolist&hl=en_US](https://play.google.com/store/apps/details?id=kolmachikhin.alexander.epicto_dolist&hl=en_US) |
| S07 | Duolingo official | [https://www.duolingo.com/](https://www.duolingo.com/) |
| S08 | Zombies, Run! official | [https://zrx.app/zombies](https://zrx.app/zombies) |
| S09 | Plant Nanny overview | [https://en.wikipedia.org/wiki/Plant_Nanny](https://en.wikipedia.org/wiki/Plant_Nanny) |
| S10 | Habits Garden Google Play | [https://play.google.com/store/apps/details?id=com.habitsgarden2.app&hl=en_US](https://play.google.com/store/apps/details?id=com.habitsgarden2.app&hl=en_US) |
| S11 | Fortune City Google Play | [https://play.google.com/store/apps/details?id=com.fourdesire.fortunecity&hl=en_US](https://play.google.com/store/apps/details?id=com.fourdesire.fortunecity&hl=en_US) |
| S12 | Nerd Fitness Journey | [https://www.nerdfitness.com/prime-overview-page/](https://www.nerdfitness.com/prime-overview-page/) |
| S13 | Ingress App Store | [https://apps.apple.com/us/app/ingress/id576505181](https://apps.apple.com/us/app/ingress/id576505181) |

## 10. Non-claims

Этот отчёт не утверждает, что Habitica, Duolingo, Forest, SuperBetter или любой другой проект на скриншоте доказанно улучшает обучение Signal Arena. Он анализирует механики, instructional patterns и переносимые design principles. Итоговая оценка 95/100 — это score предложенной архитектуры, а не measured learning outcome.

**Файлы:** `signal-arena_gamification_and_traditional_learning_iteration5.md` и обновлённый `SIGNAL_ARENA_DECISION_FAQ.md`.

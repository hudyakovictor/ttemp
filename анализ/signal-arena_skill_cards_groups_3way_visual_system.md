# SIGNAL ARENA — Skill Cards: 4 группы → 3 группы и визуальная система рангов

**Дата:** 7 октября 2026  
**Scope:** анализ текущих skill-card groups, цветовой системы и отображения 3 рангов.  
**Источники аудита:** `прототип для карт навыков.png`, `v1.png`, `v4.png`, `SkillCard.tsx`, `SkillCardsGallery.tsx`, `MASTER_PLAN_core_loop.md`, `GAME_SPEC_unlock_map.md`, `academy_plan.md`, `MECHANICS_catalog.md` из Google Drive.

## 0. Итоговое решение

Текущие четыре группы **READ / DECIDE / PROTOCOL / PROTECT** действительно избыточны. Ошибка не в количестве карточек, а в том, что в один ряд поставлены три пользовательских вопроса и один тип механики:

- **READ** — что я вижу и какие есть evidence;
- **DECIDE** — какое действие/план оправдан;
- **PROTECT** — как ограничить риск и сохранить систему;
- **PROTOCOL** — не отдельный предмет, а поперечный способ выполнения правила.

### Принятое разделение
```text
READ      → наблюдаю и интерпретирую evidence
DECIDE    → выбираю план, действие или отказ от действия
PROTECT   → ограничиваю ошибку, риск, импульс и нарушение процесса

PROTOCOL  → secondary tag / режим проверки, а не четвёртая группа
```

Это также согласуется с каноническим Skill Tree в `MASTER_PLAN_core_loop.md`: три ветки **Рынок / Сделка / Дисциплина**. Поэтому UI-группы следует выровнять так:

| UI label | Каноническая ветка | Вопрос игрока |
|---|---|---|
| READ | Рынок | Что видно до действия? |
| DECIDE | Сделка | Какой план следует из evidence? |
| PROTECT | Дисциплина | Как не разрушить план и систему? |

## 1. Что сейчас не работает

| Наблюдение | Проблема | Последствие |
|---|---|---|
| PROTOCOL стоит рядом с READ/DECIDE/PROTECT | Смешаны domain и interaction method | Пользователь не понимает, чем PROTOCOL отличается от любой карты-правила |
| DECIDE окрашен в зелёный | Зелёный считывается как success/completed/healthy | Группа конфликтует со state UI и создаёт ложный сигнал «верно» |
| PROTECT окрашен в жёлтый | Жёлтый считывается как warning/caution | Группа конфликтует с предупреждениями и risk flags |
| В коде есть индивидуальные цвета на каждой карте | Цвет описывает card theme, а не устойчивую группу | Нельзя мгновенно понять, к какой ветке относится карта |
| В коде `tier = beginner/intermediate/advanced` | Tier обычно означает difficulty, а канон задаёт rank I/II/III mastery | Ранг и сложность смешиваются в одном поле |
| Ранг не имеет отдельного устойчивого визуального слоя | Progress %, XP и tier конкурируют за внимание | Непонятно, что уже знаю, применяю или владею |
| Три группы/ранга передаются в основном цветом | Цвет не работает для color-blind users и small screens | Нужны текст, форма и паттерн как резервные каналы |

### Главная UX-ошибка
**Group, rank, progress и state сейчас визуально смешаны.** Их нужно разделить на четыре независимых слоя:

```text
GROUP     = READ / DECIDE / PROTECT
RANK      = I Know / II Apply / III Own
PROGRESS  = 0–100% внутри текущего ранга
STATE     = locked / available / in_progress / completed / needs_review
```

## 2. Рекомендуемая трёхгрупповая taxonomy

### READ — Evidence / Читаю
Карты, которые отвечают: «Что наблюдаемо? Какой контекст и качество источника? Что пока неизвестно?»

### DECIDE — Plan / Решаю
Карты, которые отвечают: «Какой план допустим? Входить, ждать, определить условие или отказаться?»

### PROTECT — Risk & Discipline / Защищаю
Карты, которые отвечают: «Как ограничить ущерб, избежать импульса и сохранить процесс?»

### Почему PROTOCOL не нужен как группа
- Protocol не является отдельным типом знания: Evidence Only — это protocol чтения; No Confirmation No Trade — protocol перед действием; Preserve the System — protocol дисциплины.
- Отдельная группа создаёт false symmetry: у READ/DECIDE/PROTECT есть предметный вопрос, у PROTOCOL — формат поведения.
- PROTOCOL лучше отображать вторичным тегом `PROTO`/иконкой checklist на отдельных картах.
- Это сохраняет возможность фильтра `только protocol-карты`, но не заставляет пользователя изучать четвёртую ветку.

## 3. Распределение 40 канонических карт

Сохраняется существующее содержательное распределение master plan: 15 READ + 9 DECIDE + 16 PROTECT. Меняется только трактовка UI-группы и выносится PROTOCOL в orthogonal tag.

### READ — 15 карт

| # | Card | Primary question | Possible protocol tag |
|---:|---|---|---|
| 01 | Market Structure | evidence / context / source | `read` |
| 02 | Higher Timeframe | evidence / context / source | `read` |
| 03 | Volume Confirmation | evidence / context / source | `read` |
| 04 | Liquidity Map | evidence / context / source | `read` |
| 05 | Volatility Context | evidence / context / source | `read` |
| 06 | Correlation Check | evidence / context / source | `read` |
| 07 | Derivatives Pulse | evidence / context / source | `read` |
| 08 | News Context | evidence / context / source | `evidence` |
| 09 | Social Sentiment | evidence / context / source | `read` |
| 10 | Macro Context | evidence / context / source | `read` |
| 11 | On-chain Flow | evidence / context / source | `evidence` |
| 12 | Tokenomics Review | evidence / context / source | `evidence` |
| 13 | Unlock Calendar | evidence / context / source | `read` |
| 14 | Infrastructure Risk | evidence / context / source | `evidence` |
| 15 | Source Quality | evidence / context / source | `evidence` |

### DECIDE — 9 карт

| # | Card | Primary question | Possible protocol tag |
|---:|---|---|---|
| 16 | Enter Now | plan / condition / action | `plan` |
| 17 | Wait for Retest | plan / condition / action | `protocol` |
| 18 | Define Entry Zone | plan / condition / action | `plan` |
| 19 | Define Invalidation | plan / condition / action | `protocol` |
| 20 | Set Structural Stop | plan / condition / action | `plan` |
| 21 | Target Liquidity | plan / condition / action | `plan` |
| 22 | Minimum R Multiple | plan / condition / action | `plan` |
| 23 | Scale Out | plan / condition / action | `plan` |
| 24 | No Trade Is a Decision | plan / condition / action | `no-action` |

### PROTECT — 16 карт

| # | Card | Primary question | Possible protocol tag |
|---:|---|---|---|
| 25 | Evidence Only | risk / discipline / process boundary | `protocol` |
| 26 | Noise Quarantine | risk / discipline / process boundary | `protocol` |
| 27 | Risk First Mode | risk / discipline / process boundary | `protocol` |
| 28 | No Confirmation No Trade | risk / discipline / process boundary | `protocol` |
| 29 | Higher Timeframe Check | risk / discipline / process boundary | `protocol` |
| 30 | After a Loss | risk / discipline / process boundary | `discipline` |
| 31 | Discipline Over Profit | risk / discipline / process boundary | `discipline` |
| 32 | Out of Market Is Normal | risk / discipline / process boundary | `discipline` |
| 33 | News Is Not a Signal | risk / discipline / process boundary | `protocol` |
| 34 | Wait for Stabilization | risk / discipline / process boundary | `discipline` |
| 35 | Do Not Chase | risk / discipline / process boundary | `discipline` |
| 36 | Avoid Revenge Trading | risk / discipline / process boundary | `discipline` |
| 37 | No Averaging Without a Plan | risk / discipline / process boundary | `discipline` |
| 38 | Risk Cap | risk / discipline / process boundary | `discipline` |
| 39 | Confidence Check | risk / discipline / process boundary | `discipline` |
| 40 | Preserve the System | risk / discipline / process boundary | `protocol` |

### Classification rule for ambiguous cards
Если карта выполняет несколько ролей, группа определяется по **первому вопросу, который она должна закрыть в момент выбора**. Остальные роли идут в tags, а не создают ещё одну группу.

## 4. Цветовая система без конфликтов

### 4.1. Group palette
Зелёный, красный и amber/yellow не используются как group colors. Они резервируются для состояния и риска.

| Group | Accent | Dark surface | Icon/rail use | Meaning |
|---|---|---|---|---|
| READ | `#71849A` muted blue-gray | `#1B2734` | soft rail, icon tint, English group label, border | evidence / observation |
| DECIDE | `#B58A6F` muted clay-orange | `#332923` | soft rail, icon tint, English group label, border | plan / action |
| PROTECT | `#988AA5` smoky purple | `#2B2631` | soft rail, icon tint, English group label, border | risk / discipline |

The previous bright palette was rejected: indigo/violet were too close, cyan conflicted with the brand teal, and the high saturation made the cards look acidic. The final card palette is deliberately soft: muted blue-gray / muted clay-orange / smoky purple. Yellow is not used for a group because it reads as warning/caution. Bronze, silver and gold icon materials provide the strongest visual rank signal; card surfaces stay calm. Use soft group tokens for the rail, border and English label; do not use neon gradients or large saturated fills.

### 4.2. State palette — reserved, never group identity
| State | Token | Usage |
|---|---|---|
| success / completed | `#22C55E` green | check icon + explicit `Completed` label only |
| error / critical | `#EF4444` red | error icon + explanation + critical-error state |
| warning / caution | `#F59E0B` amber | warning icon + text, never a group |
| neutral / locked | `#94A3B8` slate | lock, disabled, not-yet-available |

### 4.3. Accessibility rule
Нельзя кодировать group или rank только цветом. Минимальный набор redundancy:
- group label: English only — READ / DECIDE / PROTECT;
- group icon: lens / arrow / shield;
- soft group token: rail + border + label, not a neon fill;
- rank text: only `I`, `II` or `III` in the top-right;
- rank material: bronze / silver / gold icon plus optional 1–3 pips outside the title area;
- state icon and text: Locked, In progress, Completed, Needs review.

## 5. Лучшее отображение трёх рангов

### Ранги не должны менять цвет группы
Группа отвечает на вопрос «о чём этот навык», ранг — «насколько он освоен». Если при переходе I → II → III меняется весь card color, пользователь теряет ориентацию по ветке. Поэтому group color остаётся постоянным, а rank получает собственный компактный слой.

### Канонические labels
| Rank | Canonical meaning | UI label in card | Visual token |
|---|---|---|---|
| I | Знаю / Understand | `I` only | Bronze icon material |
| II | Применяю / Apply | `II` only | Silver icon material |
| III | Владею / Own | `III` only | Gold icon material |

### Предлагаемый card anatomy
```text
┌───────────────────────────────┐
│ READ                         II│  ← English group / rank only
│                               │
│          [large icon]         │  ← bronze / silver / gold
│                               │
│       MARKET                 │
│       STRUCTURE              │  ← title in two lines
└───────────────────────────────┘
```

Описание, duration, lesson count, tags и XP не входят в основной card face. Они могут появляться только после открытия карточки или в отдельном detail view.

### Почему не stars и не зелёная/красная заливка
- Stars уже заняты Mastery Stars/economy vocabulary в `game_balance_spec.md`; повторное использование создаёт системную путаницу.
- Green III would imply success/completed; rank III can be available, in progress or needs review.
- Red I/II/III would imply failure or danger, хотя ранг — не оценка безопасности.
- Progress ring must show progress inside the current rank; it cannot replace the rank seal.

## 6. Data model для реализации

Текущий `SkillCardData` в `SkillCardsGallery.tsx` должен перестать использовать `tier` как смесь сложности и статуса.

```ts
type SkillGroup = "read" | "decide" | "protect";
type CardRank = 1 | 2 | 3;
type CardState = "locked" | "available" | "in_progress" | "completed" | "needs_review";
type ProtocolTag = "read" | "plan" | "protocol" | "no_action" | "discipline" | "evidence";

interface SkillCardData {
  id: string;
  title: string;
  group: SkillGroup;
  rank: CardRank;
  rankLabel: "know" | "apply" | "own";
  state: CardState;
  protocolTags: ProtocolTag[];
  progressInRank: number;
  // difficulty is separate if needed; it is not rank
  difficultyBand?: 1 | 2 | 3;
}
```

### Implementation changes in current components
- `SkillCard.tsx`: remove `levelColors` keyed by beginner/intermediate/advanced; use `groupTheme[group]`.
- `SkillCardsGallery.tsx`: replace card-specific six-color `headerTheme` with stable group theme; the same group must look the same on every card.
- Rename `tier` to `rank`; if beginner/intermediate/advanced is needed for task difficulty, store it as `difficultyBand`, never as mastery rank.
- Add `group`, `rank`, `rankLabel`, `state`, and `protocolTags` to the card contract.
- Render English group label in top-left and numeral rank only in top-right; keep progress out of the minimal card face or show it only as a subtle bottom edge/detail view.
- Use green only for explicit completed state and red only for explicit error/critical state; not for group or rank.
- Remove hardcoded claims such as `All 8 lessons passed with 100% accuracy`; render actual card state and rank evidence from server data.

## 7. Acceptance tests

| ID | Test | Pass condition |
|---|---|---|
| G01 | All cards have exactly one primary group | Only READ, DECIDE or PROTECT appears in `group`; no PROTOCOL group exists. |
| G02 | Protocol filtering | `protocolTags` can filter protocol cards without creating a fourth column/branch. |
| G03 | Group consistency | Same group uses same accent, surface, icon family and label across every card. |
| G04 | State conflict | Green/red/amber tokens appear only with state semantics and explicit icon/text. |
| G05 | Rank semantics | Rank I/II/III shows KNOW/APPLY/OWN and never beginner/intermediate/advanced. |
| G06 | Rank redundancy | Rank remains identifiable with color removed: numeral + label + pips/pattern. |
| G07 | Progress separation | Progress percentage cannot be mistaken for rank; rank badge remains fixed while progress changes. |
| G08 | Small-screen legibility | At 270px card width, group and rank labels remain readable without hover. |
| G09 | Screen-reader order | Group, rank, state and progress are announced as text in logical order. |
| G10 | Canonical mapping | 40 cards map to 15 READ, 9 DECIDE and 16 PROTECT; no orphan cards. |

## 8. Final verdict

Рекомендуется принять **3 primary groups: READ / DECIDE / PROTECT**. `PROTOCOL` удалить из primary navigation и сохранить как orthogonal tag/interaction badge. Финальная palette карточек: soft blue-gray / soft clay-orange / smoky purple; green/red/amber зарезервировать для состояний. Ранги I/II/III отображать только numeral справа и bronze/silver/gold icon material, не меняя мягкий цвет карточки.

Это решение одновременно:
- согласуется с каноническими ветками Рынок / Сделка / Дисциплина;
- уменьшает cognitive load с четырёх неоднородных категорий до трёх вопросов;
- сохраняет protocol filtering без четвёртой ветки;
- разводит group, rank, progress и state;
- устраняет конфликт зелёного/красного/жёлтого с completed/error/warning;
- поддерживает 3 ранга без потери accessibility и без использования stars как второго смысла.

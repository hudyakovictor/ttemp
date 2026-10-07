# SIGNAL ARENA — Crypto beginner education review: 50 resources, 100 analyses, Iteration 6

**Дата:** 7 октября 2026  
**Коррекция scope:** анализ выполнен с фокусом на **криптовалюты, blockchain, wallets, custody, security, DeFi, tokenomics и crypto decision literacy**. Форекс и традиционные stock courses не включались как основной корпус.  
**Связанные файлы:** `SIGNAL_ARENA_DECISION_FAQ.md`, Q001–Q111; отчёты Iteration 3–5.  

## 0. Executive summary

Проанализированы 50 crypto-focused beginner resources: регуляторные и anti-scam материалы, университетские курсы, exchange/industry academies, wallet/security education, interactive Web3 courses, books и DeFi/tokenomics resources. На их основе выполнены **100 внутренних сравнительных анализов**: по два на каждый ресурс — instructional value и novice pain/transfer implication.

Главный вывод: новичку не нужен ещё один огромный курс «про всю crypto». Ему нужен короткий нейтральный маршрут, который сначала создаёт mental model и безопасное поведение, а только потом показывает asset types, DeFi и on-chain tools. Большинство текущих ресурсов сильны только в одном слое: академическая глубина, platform onboarding, security, market vocabulary или developer practice. Signal Arena может объединить слои без повторения их объёма.

### Сильнейшее решение после review
**Signal Arena Crypto Safety & Decision Literacy Path:**
- Не начинать с покупки, trading setup, token pick, yield или indicators.
- Начинать с time/sequence: что происходит при создании адреса, подписи, отправке, подтверждении и ошибке.
- Затем custody/threat model: кто контролирует key, что видит сервис, что нельзя восстановить.
- Потом taxonomy: Bitcoin/network/token/wallet/exchange/protocol/stablecoin/DeFi.
- После этого — evidence and risk: claim, source, unknowns, permissions, fees, liquidity, smart-contract and scam risk.
- Только затем — synthetic scenarios, cross-chain transfer и optional advanced diagnostic path.

## 1. Resource inventory: 50 crypto-focused beginner resources

| ID | Тип | Ресурс | Основная сила | Главный gap для новичка |
|---|---|---|---|---|
| R01 | Regulator | [Investor.gov — Crypto Assets / SEC investor alerts](https://www.investor.gov/) | consumer protection, basics, fraud alerts and tools | official and risk-aware, but article-by-article rather than a coherent course |
| R02 | Regulator | [CFTC Digital Assets / Customer Advisories](https://www.cftc.gov/LearnandProtect/digitalassets/index.htm) | virtual-currency basics, volatility, platform, cyber and fraud risks | strong warnings, low practice and little learner progression |
| R03 | Regulator | [FCA InvestSmart — cryptoassets](https://www.fca.org.uk/investsmart) | risk warnings, high-risk framing, consumer caution | UK-specific and more warning-led than skill-building |
| R04 | Regulator | [ESMA warning on crypto-assets / MiCA limits](https://www.esma.europa.eu/sites/default/files/2024-12/ESMA35-1872330276-1971_Warning_on_crypto-assets.pdf) | volatility, fraud, limited protection and non-EU provider risk | warning is important but not memorable or interactive |
| R05 | Regulator | [ASIC MoneySmart — crypto assets](https://moneysmart.gov.au/investing/investing-in-crypto-assets) | plain-language crypto risks and scam prevention | Australian context and mostly linear text |
| R06 | Regulator | [European Commission — MiCA overview](https://finance.ec.europa.eu/regulation-and-supervision/financial-services-legislation/markets-crypto-assets-regulation_en) | regulatory vocabulary and scope of safeguards | regulation can create false feeling of safety; not a beginner course |
| R07 | Regulator | [FTC — cryptocurrency and scams](https://consumer.ftc.gov/articles/what-know-about-cryptocurrency-and-scams) | scam patterns, payments and reporting | focuses on warning after the fact; little decision rehearsal |
| R08 | Regulator | [FINRA — crypto assets](https://www.finra.org/investors/investing/investment-products/crypto-assets) | neutral investor education and risk framing | US regulatory scope can be confusing for global beginners |
| R09 | Regulator | [CFTC learning resources — fraud and digital assets](https://www.cftc.gov/LearnAndProtect/learningresources) | current fraud scenarios and consumer advisories | many documents, fragmented navigation |
| R10 | Regulator | [Investor.gov — HoweyCoin educational scam game](https://www.investor.gov/online-tools/tour-infographic/cryptocurrency) | uses a fake investment journey to expose red flags | single linear demonstration; no calibrated mastery or transfer |
| R11 | University | [MIT OpenCourseWare — Blockchain and Money](https://ocw.mit.edu/courses/15-s12-blockchain-and-money-fall-2018/) | serious lectures on money, blockchain, institutions and policy | too long, lecture-heavy and assumes persistence; weak novice practice |
| R12 | University | [Princeton — Bitcoin and Cryptocurrency Technologies](https://bitcoinbook.cs.princeton.edu/) | rigorous technical model: keys, consensus, transactions, security | computer-science load is high for nontechnical beginners; coding is optional only in theory |
| R13 | University | [University of Nicosia — Introduction to Digital Currencies](https://www.unic.ac.cy/blockchain/education/) | structured digital-currency academic path and broad context | academic breadth can delay the first concrete safe behavior |
| R14 | University | [Coursera — Blockchain and Cryptocurrency Explained, University of Michigan](https://www.coursera.org/learn/blockchain-and-cryptocurrency-explained) | beginner-friendly university overview | course format often remains video/quiz and may not test applied judgment |
| R15 | University | [Coursera — Cryptocurrency and Applications, POSTECH](https://www.coursera.org/learn/crypto101) | coins, tokens, wallets, exchanges, stablecoins, NFTs and DeFi in modules | breadth risks collapsing distinct mechanisms into labels |
| R16 | University | [Coursera — Understanding Stablecoins / Duke](https://www.coursera.org/learn/understanding-stablecoins) | mechanics and failure cases, including Terra/Luna | stablecoins are not a first topic for a zero-knowledge learner |
| R17 | University | [Coursera — Decentralized Finance Infrastructure / Duke](https://www.coursera.org/learn/defi-infrastructure) | protocol architecture and DeFi concepts | too advanced before wallet/network fundamentals; protocol risk is abstract |
| R18 | University | [Coursera — Blockchain Specialization, University at Buffalo](https://www.coursera.org/specializations/blockchain) | progressive blockchain development and smart-contract structure | developer-first path does not serve nontechnical novice goal |
| R19 | University | [Saylor Academy — Bitcoin for Everybody](https://learn.saylor.org/) | free long-form Bitcoin economics, history, technology and practice | ideological framing and long duration can overwhelm or bias |
| R20 | University | [Learn Crypto / Teach Yourself Crypto](https://teachyourselfcrypto.com/) | structured nontechnical modules on Bitcoin, Ethereum, Web3 and DeFi | huge volume; learners can mistake completion for competence |
| R21 | Industry academy | [Binance Academy — Beginner Track](https://academy.binance.com/en) | multilingual articles, videos, quizzes and beginner/intermediate tracks | exchange affiliation and learn-and-earn can bias attention toward adoption/trading |
| R22 | Industry academy | [Binance Academy Courses](https://academy.binance.com/en/courses) | explicit tracks, quizzes and certificates | campaigns and token rewards can incentivize quiz completion over understanding |
| R23 | Industry academy | [Coinbase Learn / Wallet learning](https://www.coinbase.com/learn) | short modules and approachable product concepts | platform/product bias and reward/quest mechanics can produce shallow recall |
| R24 | Industry academy | [Kraken Learn Center](https://www.kraken.com/learn) | guides on market mechanics, custody, security and products | article library is broad and not always a single beginner route |
| R25 | Independent data education | [CoinGecko Learn](https://www.coingecko.com/learn) | broad glossary, market concepts and crypto explainers | data provider context still leaves learner with information overload |
| R26 | Independent data education | [CoinMarketCap Alexandria](https://coinmarketcap.com/alexandria) | large searchable content base and token/project explainers | token/project coverage can look like implicit endorsement; quality varies |
| R27 | On-chain analytics | [Glassnode Academy](https://glassnode.com/academy) | introduces on-chain metrics and network data | metrics can become false precision and advanced dashboard overload |
| R28 | On-chain analytics | [Chainalysis Academy / crypto education](https://www.chainalysis.com/academy/) | compliance, investigations and illicit-finance context | professional audience and institutional perspective are advanced |
| R29 | Security academy | [Ledger Academy](https://www.ledger.com/academy) | excellent coverage of keys, wallets, seed phrases, scams and signing | vendor/product bias and self-custody assumption |
| R30 | Security academy | [Trezor Academy](https://academy.trezor.io/) | localized, guided, practical Bitcoin/self-custody education | Bitcoin-centric and hardware-wallet oriented |
| R31 | Wallet education | [MetaMask Learn](https://metamask.io/learn) | beginner guides to wallets, self-custody, approvals and security | wallet-specific and Ethereum-centric; product steps can outrun mental models |
| R32 | Protocol documentation | [Ethereum.org Learn](https://ethereum.org/en/learn/) | official concepts, wallets, gas, accounts, smart contracts and developer paths | documentation is accurate but not optimized for anxious beginners |
| R33 | Protocol documentation | [Bitcoin.org — How Bitcoin works](https://bitcoin.org/en/how-it-works) | simple technical explanation of transactions, mining and wallets | Bitcoin-only mental model can be overgeneralized to all chains |
| R34 | Protocol education | [Solana Learn](https://solana.com/learn) | chain-specific onboarding and developer concepts | ecosystem bias and chain-specific vocabulary |
| R35 | Industry education | [Circle Learn — stablecoins and payments](https://www.circle.com/learn) | accessible stablecoin/payment explanations | issuer perspective and product proximity; stablecoin complexity remains |
| R36 | Interactive course | [CryptoZombies](https://cryptozombies.io/) | highly interactive, gamified Solidity progression | developer prerequisite; success can be code-pattern recognition |
| R37 | Interactive course | [LearnWeb3 Freshman Track](https://learnweb3.io/) | hands-on Web3 development, wallets, Remix and contracts | developer path requires tooling and technical persistence |
| R38 | Interactive course | [Bankless Academy](https://app.banklessacademy.com/) | bite-sized crypto/DeFi lessons, tests and rewards | ideological framing and DeFi exposure can come too early |
| R39 | Beginner course | [Great Learning — Introduction to DeFi](https://www.mygreatlearning.com/academy/learn-for-free/courses/introduction-to-decentralized-finance-defi) | short beginner modules on wallets, AMMs, liquidity and risks | 2-hour overview may create familiarity without operational judgment |
| R40 | Beginner course | [Alison — Introduction to DeFi](https://alison.com/course/introduction-to-decentralized-finance-defi) | case-based overview of DeFi, smart contracts, oracles and stablecoins | broad survey, completion/certificate may substitute for competence |
| R41 | Professional course | [101 Blockchains — Tokenomics Fundamentals](https://101blockchains.com/course/tokenomics-fundamentals/) | structured token models, distribution and evaluation concepts | tokenomics can become a project-promotion lens and valuation overconfidence |
| R42 | Professional course | [Onchain School](https://www.onchainschool.pro/en) | 70+ lessons, practical on-chain analysis, workshops and screeners | promotional profit/trading framing and advanced tool overload |
| R43 | Open course | [OpenLearn — Blockchain and Bitcoin](https://www.open.edu/openlearn/money-business/blockchain-and-bitcoin/content-section-overview?active-tab=description-tab) | open introductory treatment of Bitcoin and blockchain concepts | broad and mostly passive; little applied transfer or safety rehearsal |
| R44 | Open course | [edX/IBM — Blockchain: Understanding Its Uses and Implications](https://www.edx.org/learn/blockchain/ibm-blockchain-understanding-its-uses-and-implications) | accessible framing of blockchain use cases and implications | use-case breadth can hide custody, scam and irreversibility risks |
| R45 | Community/resource hub | [Coin Bureau educational guides](https://coinbureau.com/analysis/best-crypto-courses-for-beginners) | friendly explainers and course/resource comparisons | media/commercial incentives and fast-changing recommendations |
| R46 | Book | [The Basics of Bitcoins and Blockchains — Antony Lewis](https://www.goodreads.com/book/show/36364648-the-basics-of-bitcoins-and-blockchains) | accessible nontechnical vocabulary and broad foundation | linear reading, no personalized feedback or applied transfer |
| R47 | Book | [Mastering Bitcoin — Andreas Antonopoulos](https://github.com/bitcoinbook/bitcoinbook) | deep technical model of keys, transactions, network and security | too dense for most zero-knowledge learners |
| R48 | Book/course | [Mastering Ethereum](https://github.com/ethereumbook/ethereumbook) | smart contracts, accounts, transactions and Ethereum internals | developer-heavy and assumes persistence |
| R49 | Book | [Cryptoassets — Burniske & Tatar](https://www.goodreads.com/book/show/35498785-cryptoassets) | framework for cryptoasset categories and investment questions | investment framing can imply valuation confidence and dated examples |
| R50 | Book | [The Bitcoin Standard — Saifedean Ammous](https://www.goodreads.com/book/show/36448501-the-bitcoin-standard) | historical/economic narrative that makes Bitcoin memorable | strong ideological viewpoint; not neutral and not a safety curriculum |

### Исследовательское ограничение
Official/regulator/university pages were treated as stronger evidence of curriculum/features. Exchange, wallet, token-project and paid-course pages were treated as potentially promotional. Marketing claims, ratings, reward amounts and completion claims do not count as proof of learning effectiveness. Some resources change availability or curriculum over time; Signal Arena must store source date and content version.

## 2. 100 internal analyses

Каждый ресурс получил два анализа: **A — useful instructional pattern**, **B — novice gap and what Signal should do differently**. Это design synthesis, а не 100 независимых causal experiments.

| ID | Resource | Analysis | Finding | Signal Arena response |
|---:|---|---|---|---|
| 001 | Investor.gov — Crypto Assets / SEC investor alerts | A — instructional value | consumer protection, basics, fraud alerts and tools. | Use scam red flags and decision gates; turn reading into scenario-based no-go decisions. |
| 002 | Investor.gov — Crypto Assets / SEC investor alerts | B — novice gap | official and risk-aware, but article-by-article rather than a coherent course. | Use scam red flags and decision gates; turn reading into scenario-based no-go decisions. |
| 003 | CFTC Digital Assets / Customer Advisories | A — instructional value | virtual-currency basics, volatility, platform, cyber and fraud risks. | Build a threat-model quest: platform risk, custody risk, irreversible transfer, scam pressure. |
| 004 | CFTC Digital Assets / Customer Advisories | B — novice gap | strong warnings, low practice and little learner progression. | Build a threat-model quest: platform risk, custody risk, irreversible transfer, scam pressure. |
| 005 | FCA InvestSmart — cryptoassets | A — instructional value | risk warnings, high-risk framing, consumer caution. | Teach risk language and evidence checks without copying jurisdiction-specific legal advice. |
| 006 | FCA InvestSmart — cryptoassets | B — novice gap | UK-specific and more warning-led than skill-building. | Teach risk language and evidence checks without copying jurisdiction-specific legal advice. |
| 007 | ESMA warning on crypto-assets / MiCA limits | A — instructional value | volatility, fraud, limited protection and non-EU provider risk. | Create an EU-aware risk map: protection is conditional; learner must identify what remains unknown. |
| 008 | ESMA warning on crypto-assets / MiCA limits | B — novice gap | warning is important but not memorable or interactive. | Create an EU-aware risk map: protection is conditional; learner must identify what remains unknown. |
| 009 | ASIC MoneySmart — crypto assets | A — instructional value | plain-language crypto risks and scam prevention. | Reuse simple language, but make the learner demonstrate recognition of risk signals. |
| 010 | ASIC MoneySmart — crypto assets | B — novice gap | Australian context and mostly linear text. | Reuse simple language, but make the learner demonstrate recognition of risk signals. |
| 011 | European Commission — MiCA overview | A — instructional value | regulatory vocabulary and scope of safeguards. | Teach the contrast: regulation changes protections, not the asset's volatility or fraud risk. |
| 012 | European Commission — MiCA overview | B — novice gap | regulation can create false feeling of safety; not a beginner course. | Teach the contrast: regulation changes protections, not the asset's volatility or fraud risk. |
| 013 | FTC — cryptocurrency and scams | A — instructional value | scam patterns, payments and reporting. | Use dialogue-based scam simulations and stop/verify actions. |
| 014 | FTC — cryptocurrency and scams | B — novice gap | focuses on warning after the fact; little decision rehearsal. | Use dialogue-based scam simulations and stop/verify actions. |
| 015 | FINRA — crypto assets | A — instructional value | neutral investor education and risk framing. | Separate asset mechanics from jurisdiction and teach source/provenance. |
| 016 | FINRA — crypto assets | B — novice gap | US regulatory scope can be confusing for global beginners. | Separate asset mechanics from jurisdiction and teach source/provenance. |
| 017 | CFTC learning resources — fraud and digital assets | A — instructional value | current fraud scenarios and consumer advisories. | Curate only the high-frequency scam patterns into short, revisitable quests. |
| 018 | CFTC learning resources — fraud and digital assets | B — novice gap | many documents, fragmented navigation. | Curate only the high-frequency scam patterns into short, revisitable quests. |
| 019 | Investor.gov — HoweyCoin educational scam game | A — instructional value | uses a fake investment journey to expose red flags. | Borrow the safe fictional asset and add varied scam contexts plus debrief. |
| 020 | Investor.gov — HoweyCoin educational scam game | B — novice gap | single linear demonstration; no calibrated mastery or transfer. | Borrow the safe fictional asset and add varied scam contexts plus debrief. |
| 021 | MIT OpenCourseWare — Blockchain and Money | A — instructional value | serious lectures on money, blockchain, institutions and policy. | Mine only mental-model lessons and convert them to 5–10 minute retrieval units. |
| 022 | MIT OpenCourseWare — Blockchain and Money | B — novice gap | too long, lecture-heavy and assumes persistence; weak novice practice. | Mine only mental-model lessons and convert them to 5–10 minute retrieval units. |
| 023 | Princeton — Bitcoin and Cryptocurrency Technologies | A — instructional value | rigorous technical model: keys, consensus, transactions, security. | Use a nontechnical visual track first; reserve protocol internals for diagnostic path. |
| 024 | Princeton — Bitcoin and Cryptocurrency Technologies | B — novice gap | computer-science load is high for nontechnical beginners; coding is optional only in theory. | Use a nontechnical visual track first; reserve protocol internals for diagnostic path. |
| 025 | University of Nicosia — Introduction to Digital Currencies | A — instructional value | structured digital-currency academic path and broad context. | Compress into foundation → custody → risk → applications, with explicit prerequisites. |
| 026 | University of Nicosia — Introduction to Digital Currencies | B — novice gap | academic breadth can delay the first concrete safe behavior. | Compress into foundation → custody → risk → applications, with explicit prerequisites. |
| 027 | Coursera — Blockchain and Cryptocurrency Explained, University of Michigan | A — instructional value | beginner-friendly university overview. | Add evidence selection and transfer instead of only module quizzes. |
| 028 | Coursera — Blockchain and Cryptocurrency Explained, University of Michigan | B — novice gap | course format often remains video/quiz and may not test applied judgment. | Add evidence selection and transfer instead of only module quizzes. |
| 029 | Coursera — Cryptocurrency and Applications, POSTECH | A — instructional value | coins, tokens, wallets, exchanges, stablecoins, NFTs and DeFi in modules. | Use contrastive taxonomy: asset, network, wallet, service, claim. |
| 030 | Coursera — Cryptocurrency and Applications, POSTECH | B — novice gap | breadth risks collapsing distinct mechanisms into labels. | Use contrastive taxonomy: asset, network, wallet, service, claim. |
| 031 | Coursera — Understanding Stablecoins / Duke | A — instructional value | mechanics and failure cases, including Terra/Luna. | Introduce stablecoins only after network, custody, collateral and failure concepts. |
| 032 | Coursera — Understanding Stablecoins / Duke | B — novice gap | stablecoins are not a first topic for a zero-knowledge learner. | Introduce stablecoins only after network, custody, collateral and failure concepts. |
| 033 | Coursera — Decentralized Finance Infrastructure / Duke | A — instructional value | protocol architecture and DeFi concepts. | Use a controlled DeFi scenario with no funds and a visible failure boundary. |
| 034 | Coursera — Decentralized Finance Infrastructure / Duke | B — novice gap | too advanced before wallet/network fundamentals; protocol risk is abstract. | Use a controlled DeFi scenario with no funds and a visible failure boundary. |
| 035 | Coursera — Blockchain Specialization, University at Buffalo | A — instructional value | progressive blockchain development and smart-contract structure. | Route developers separately; keep MVP for safe decision literacy. |
| 036 | Coursera — Blockchain Specialization, University at Buffalo | B — novice gap | developer-first path does not serve nontechnical novice goal. | Route developers separately; keep MVP for safe decision literacy. |
| 037 | Saylor Academy — Bitcoin for Everybody | A — instructional value | free long-form Bitcoin economics, history, technology and practice. | Present multiple interpretations and require evidence/uncertainty, not belief adoption. |
| 038 | Saylor Academy — Bitcoin for Everybody | B — novice gap | ideological framing and long duration can overwhelm or bias. | Present multiple interpretations and require evidence/uncertainty, not belief adoption. |
| 039 | Learn Crypto / Teach Yourself Crypto | A — instructional value | structured nontechnical modules on Bitcoin, Ethereum, Web3 and DeFi. | Use its topic map as a back-office coverage checklist, not as the learner UI. |
| 040 | Learn Crypto / Teach Yourself Crypto | B — novice gap | huge volume; learners can mistake completion for competence. | Use its topic map as a back-office coverage checklist, not as the learner UI. |
| 041 | Binance Academy — Beginner Track | A — instructional value | multilingual articles, videos, quizzes and beginner/intermediate tracks. | Borrow track progression; separate neutral core from product-specific guides. |
| 042 | Binance Academy — Beginner Track | B — novice gap | exchange affiliation and learn-and-earn can bias attention toward adoption/trading. | Borrow track progression; separate neutral core from product-specific guides. |
| 043 | Binance Academy Courses | A — instructional value | explicit tracks, quizzes and certificates. | No financial rewards; mastery requires changed-context performance. |
| 044 | Binance Academy Courses | B — novice gap | campaigns and token rewards can incentivize quiz completion over understanding. | No financial rewards; mastery requires changed-context performance. |
| 045 | Coinbase Learn / Wallet learning | A — instructional value | short modules and approachable product concepts. | Use micro-lessons but insert security red flags, no-action choices and delayed recall. |
| 046 | Coinbase Learn / Wallet learning | B — novice gap | platform/product bias and reward/quest mechanics can produce shallow recall. | Use micro-lessons but insert security red flags, no-action choices and delayed recall. |
| 047 | Kraken Learn Center | A — instructional value | guides on market mechanics, custody, security and products. | Create a neutral route that links mechanics before platform actions. |
| 048 | Kraken Learn Center | B — novice gap | article library is broad and not always a single beginner route. | Create a neutral route that links mechanics before platform actions. |
| 049 | CoinGecko Learn | A — instructional value | broad glossary, market concepts and crypto explainers. | Use glossary only after prerequisite and attach every term to a decision context. |
| 050 | CoinGecko Learn | B — novice gap | data provider context still leaves learner with information overload. | Use glossary only after prerequisite and attach every term to a decision context. |
| 051 | CoinMarketCap Alexandria | A — instructional value | large searchable content base and token/project explainers. | Teach source triangulation and project-claim skepticism. |
| 052 | CoinMarketCap Alexandria | B — novice gap | token/project coverage can look like implicit endorsement; quality varies. | Teach source triangulation and project-claim skepticism. |
| 053 | Glassnode Academy | A — instructional value | introduces on-chain metrics and network data. | Start with one metric, one question, one limitation, then transfer across chains. |
| 054 | Glassnode Academy | B — novice gap | metrics can become false precision and advanced dashboard overload. | Start with one metric, one question, one limitation, then transfer across chains. |
| 055 | Chainalysis Academy / crypto education | A — instructional value | compliance, investigations and illicit-finance context. | Use only scam/traceability concepts in a safety chapter, not analyst certification. |
| 056 | Chainalysis Academy / crypto education | B — novice gap | professional audience and institutional perspective are advanced. | Use only scam/traceability concepts in a safety chapter, not analyst certification. |
| 057 | Ledger Academy | A — instructional value | excellent coverage of keys, wallets, seed phrases, scams and signing. | Teach custody options comparatively; never imply one brand is the safe answer. |
| 058 | Ledger Academy | B — novice gap | vendor/product bias and self-custody assumption. | Teach custody options comparatively; never imply one brand is the safe answer. |
| 059 | Trezor Academy | A — instructional value | localized, guided, practical Bitcoin/self-custody education. | Use hands-on safety logic without requiring hardware or purchase. |
| 060 | Trezor Academy | B — novice gap | Bitcoin-centric and hardware-wallet oriented. | Use hands-on safety logic without requiring hardware or purchase. |
| 061 | MetaMask Learn | A — instructional value | beginner guides to wallets, self-custody, approvals and security. | Use fictional wallet screens and teach verify-before-signing. |
| 062 | MetaMask Learn | B — novice gap | wallet-specific and Ethereum-centric; product steps can outrun mental models. | Use fictional wallet screens and teach verify-before-signing. |
| 063 | Ethereum.org Learn | A — instructional value | official concepts, wallets, gas, accounts, smart contracts and developer paths. | Translate docs into progressive visual models and small retrieval items. |
| 064 | Ethereum.org Learn | B — novice gap | documentation is accurate but not optimized for anxious beginners. | Translate docs into progressive visual models and small retrieval items. |
| 065 | Bitcoin.org — How Bitcoin works | A — instructional value | simple technical explanation of transactions, mining and wallets. | Make the differences between Bitcoin, smart-contract chains and tokens explicit. |
| 066 | Bitcoin.org — How Bitcoin works | B — novice gap | Bitcoin-only mental model can be overgeneralized to all chains. | Make the differences between Bitcoin, smart-contract chains and tokens explicit. |
| 067 | Solana Learn | A — instructional value | chain-specific onboarding and developer concepts. | Use cross-chain comparison only after generic network model. |
| 068 | Solana Learn | B — novice gap | ecosystem bias and chain-specific vocabulary. | Use cross-chain comparison only after generic network model. |
| 069 | Circle Learn — stablecoins and payments | A — instructional value | accessible stablecoin/payment explanations. | Add failure modes, reserve/custody uncertainty and no-promotion comparison. |
| 070 | Circle Learn — stablecoins and payments | B — novice gap | issuer perspective and product proximity; stablecoin complexity remains. | Add failure modes, reserve/custody uncertainty and no-promotion comparison. |
| 071 | CryptoZombies | A — instructional value | highly interactive, gamified Solidity progression. | Borrow progressive challenge design, not content sequence for nontechnical learners. |
| 072 | CryptoZombies | B — novice gap | developer prerequisite; success can be code-pattern recognition. | Borrow progressive challenge design, not content sequence for nontechnical learners. |
| 073 | LearnWeb3 Freshman Track | A — instructional value | hands-on Web3 development, wallets, Remix and contracts. | Offer only as a later diagnostic branch, not novice core. |
| 074 | LearnWeb3 Freshman Track | B — novice gap | developer path requires tooling and technical persistence. | Offer only as a later diagnostic branch, not novice core. |
| 075 | Bankless Academy | A — instructional value | bite-sized crypto/DeFi lessons, tests and rewards. | Borrow short quests but enforce security-first prerequisites and balanced claims. |
| 076 | Bankless Academy | B — novice gap | ideological framing and DeFi exposure can come too early. | Borrow short quests but enforce security-first prerequisites and balanced claims. |
| 077 | Great Learning — Introduction to DeFi | A — instructional value | short beginner modules on wallets, AMMs, liquidity and risks. | Turn each mechanism into a scenario with failure, fee and custody consequences. |
| 078 | Great Learning — Introduction to DeFi | B — novice gap | 2-hour overview may create familiarity without operational judgment. | Turn each mechanism into a scenario with failure, fee and custody consequences. |
| 079 | Alison — Introduction to DeFi | A — instructional value | case-based overview of DeFi, smart contracts, oracles and stablecoins. | Require explain/transfer and no-go decisions before advancement. |
| 080 | Alison — Introduction to DeFi | B — novice gap | broad survey, completion/certificate may substitute for competence. | Require explain/transfer and no-go decisions before advancement. |
| 081 | 101 Blockchains — Tokenomics Fundamentals | A — instructional value | structured token models, distribution and evaluation concepts. | Teach tokenomics as evidence with unknowns, unlocks, concentration and adversarial claims. |
| 082 | 101 Blockchains — Tokenomics Fundamentals | B — novice gap | tokenomics can become a project-promotion lens and valuation overconfidence. | Teach tokenomics as evidence with unknowns, unlocks, concentration and adversarial claims. |
| 083 | Onchain School | A — instructional value | 70+ lessons, practical on-chain analysis, workshops and screeners. | Use as market pain evidence: learners want action, but Signal removes profit promises and tools first. |
| 084 | Onchain School | B — novice gap | promotional profit/trading framing and advanced tool overload. | Use as market pain evidence: learners want action, but Signal removes profit promises and tools first. |
| 085 | OpenLearn — Blockchain and Bitcoin | A — instructional value | open introductory treatment of Bitcoin and blockchain concepts. | Use concept seeds and convert them into visual contrast, retrieval and no-action decisions. |
| 086 | OpenLearn — Blockchain and Bitcoin | B — novice gap | broad and mostly passive; little applied transfer or safety rehearsal. | Use concept seeds and convert them into visual contrast, retrieval and no-action decisions. |
| 087 | edX/IBM — Blockchain: Understanding Its Uses and Implications | A — instructional value | accessible framing of blockchain use cases and implications. | Keep generic blockchain framing, then force a crypto-specific risk and evidence layer. |
| 088 | edX/IBM — Blockchain: Understanding Its Uses and Implications | B — novice gap | use-case breadth can hide custody, scam and irreversibility risks. | Keep generic blockchain framing, then force a crypto-specific risk and evidence layer. |
| 089 | Coin Bureau educational guides | A — instructional value | friendly explainers and course/resource comparisons. | Use as discovery signal only; teach source checking and version dates. |
| 090 | Coin Bureau educational guides | B — novice gap | media/commercial incentives and fast-changing recommendations. | Use as discovery signal only; teach source checking and version dates. |
| 091 | The Basics of Bitcoins and Blockchains — Antony Lewis | A — instructional value | accessible nontechnical vocabulary and broad foundation. | Convert core chapters into glossary, contrast cards and decision scenes. |
| 092 | The Basics of Bitcoins and Blockchains — Antony Lewis | B — novice gap | linear reading, no personalized feedback or applied transfer. | Convert core chapters into glossary, contrast cards and decision scenes. |
| 093 | Mastering Bitcoin — Andreas Antonopoulos | A — instructional value | deep technical model of keys, transactions, network and security. | Use selected visual concepts; unlock technical appendix for diagnostic users. |
| 094 | Mastering Bitcoin — Andreas Antonopoulos | B — novice gap | too dense for most zero-knowledge learners. | Use selected visual concepts; unlock technical appendix for diagnostic users. |
| 095 | Mastering Ethereum | A — instructional value | smart contracts, accounts, transactions and Ethereum internals. | Extract accounts/transactions/signing concepts; defer Solidity and internals. |
| 096 | Mastering Ethereum | B — novice gap | developer-heavy and assumes persistence. | Extract accounts/transactions/signing concepts; defer Solidity and internals. |
| 097 | Cryptoassets — Burniske & Tatar | A — instructional value | framework for cryptoasset categories and investment questions. | Use asset taxonomy and questions, not buy/sell conclusions. |
| 098 | Cryptoassets — Burniske & Tatar | B — novice gap | investment framing can imply valuation confidence and dated examples. | Use asset taxonomy and questions, not buy/sell conclusions. |
| 099 | The Bitcoin Standard — Saifedean Ammous | A — instructional value | historical/economic narrative that makes Bitcoin memorable. | Present as one perspective, contrast with evidence and separate narrative from mechanism. |
| 100 | The Bitcoin Standard — Saifedean Ammous | B — novice gap | strong ideological viewpoint; not neutral and not a safety curriculum. | Present as one perspective, contrast with evidence and separate narrative from mechanism. |

## 3. Unified portrait of the crypto beginner

### Who this learner is
- Adult novice, usually arriving from social media, a friend, a news story, a wallet app or fear of missing a new opportunity.
- May know brand names such as Bitcoin, Ethereum, Solana or stablecoin but cannot explain the difference between a network, a token, an address, a wallet and an exchange.
- Wants two things before anything else: not to be scammed and not to make an irreversible mistake.
- Does not want a university semester, codebase or 500-article archive; can tolerate 5–12 minute learning units with a visible next step.
- Often overestimates knowledge after recognizing vocabulary or completing a short quiz; confidence must be measured against performance.
- May be multilingual and mobile-first, with variable math, technical literacy and tolerance for risk language.
- Needs neutral explanations because every exchange, wallet, token project and influencer has an incentive or worldview.

### What the beginner must be able to do, not merely repeat
- Explain what the learner is observing and what remains unknown.
- Distinguish network, asset, wallet/account, custodian, protocol and interface.
- Trace a fictional transaction from intent to signature to confirmation, including where failure can occur.
- Identify which party controls keys and which permissions a message requests.
- Spot a scam pattern: urgency, guaranteed returns, impersonation, fake support, recovery fee, unsolicited link or authority claim.
- Refuse to act when evidence is insufficient or permissions/recipient/network are not verified.
- Compare two claims using source, date, incentives, evidence and limitations.
- Transfer the same reasoning to a new chain, wallet screen or token narrative.

## 4. Top 20 market pains and what Signal Arena covers better

| ID | Pain/gap | Why existing learning underperforms | Signal Arena solution | Priority |
|---|---|---|---|---|
| P01 | Нет одного нейтрального маршрута от «я ничего не знаю» до безопасного понимания crypto | Ресурсы делятся на регуляторов, exchange academies, developer courses и opinionated books. | Signal Arena строит один canonical route: network → custody → security → asset types → risk → decision. | P0 |
| P02 | Термины появляются раньше mental model | Wallet, key, gas, token, chain и DeFi вводятся как словарь, а не как взаимосвязь. | Chapter 0 visual model; каждый термин разрешён только после prerequisite и contrast example. | P0 |
| P03 | Путаются coin, token, network, wallet, exchange и protocol | Новичок не понимает, что хранится где и кто что контролирует. | Entity map и structured classification: asset/network/account/custodian/protocol/service. | P0 |
| P04 | CEX, DEX и self-custody смешиваются | Курсы показывают кнопку действия, но не ownership/permission model. | No-money fictional screens, custody comparison и proof-of-control scenarios. | P1 |
| P05 | Security изучается как список советов | Seed phrase, phishing, approvals и signing редко тренируются в ситуациях. | Threat-model quests: identify source, verify domain, inspect request, refuse/stop. | P0 |
| P06 | Скам-тренировка слишком поздняя | Новичок сначала получает excitement и только потом видит fraud patterns. | Safety gate перед any asset/purchase narrative; scam scenarios с debrief. | P0 |
| P07 | Learn-and-earn и badges искажают цель | Learner может фармить quiz/reward и не понимать token. | Rewards cosmetic/non-transferable; no mastery from one recall quiz or reward claim. | P1 |
| P08 | Квизы проверяют узнавание формулировки | Большинство short quizzes не требуют evidence, uncertainty или transfer. | 3 task families, variable surface, novel transfer и delayed recall. | P0 |
| P09 | Нет безопасной практики транзакционной логики | Человек знает слово transaction, но не понимает sequence, fee, confirmation и irreversibility. | Synthetic transaction timeline with observation→decision→invalidation. | P0 |
| P10 | Недостаточно объясняется, что ошибка необратима | Курсы перечисляют risks, но не заставляют остановиться перед irreversible action. | Decision boundary and explicit no-action/verify-more option. | P0 |
| P11 | Stablecoins и DeFi дают слишком рано | Сложные products объясняются до custody, collateral, oracle и failure model. | Prerequisite gate; first teach mechanism, then failure case, then cautious application. | P1 |
| P12 | Tokenomics превращается в bullish pitch | Supply, unlocks и utility часто подаются как оценочный сигнал. | Tokenomics evidence board: distribution, unlocks, concentration, unknowns and claim provenance. | P1 |
| P13 | Нет языка неопределённости | Курсы создают ощущение, что после completion learner должен act. | Every task includes known/unknown, confidence and no-action path. | P0 |
| P14 | Низкая calibration между знанием и уверенностью | Исследования указывают на overconfidence/subjective literacy gap у crypto owners. | Diagnostic challenge, confidence before submit and calibration feedback against process score. | P0 |
| P15 | Нет transfer между сетями и интерфейсами | Навык, освоенный на one exchange/wallet, не переносится на другую chain. | Same-skill/different-surface with chain-neutral core and controlled chain variants. | P1 |
| P16 | Academic courses слишком технические для ordinary beginner | Princeton/MIT/Blockchain specializations valuable but high-load. | Two-track architecture: novice visual track and optional diagnostic technical track. | P1 |
| P17 | Industry courses слишком platform-centric | Exchange academy teaches its interface and vocabulary first. | Platform-agnostic canonical content; product-specific layer deferred. | P1 |
| P18 | Ресурсы быстро устаревают | Token names, interfaces, regulation and campaigns change. | Versioned content, source date, provenance, deprecation and evergreen concept layer. | P1 |
| P19 | Фрагментация и information overload | Learner opens 20 tabs, jumps from wallet security to yield farming. | One next action, progressive disclosure, bounded chapter, no open-ended browsing in core. | P0 |
| P20 | Нет доказательства самостоятельной готовности | Course completion/certificate says little about judgment under pressure. | Mastery state machine, delayed recall, transfer, critical-error veto and alpha measurement. | P0 |

### Highest-value market gap
Не дефицит информации. Дефицит — **связи между механизмом, риском и действием**. Новичок может прочитать 20 определений и всё равно не знать, нужно ли подписывать транзакцию, проверять сеть, верить источнику или остановиться. Поэтому конкурентное преимущество Signal Arena — не ещё один glossary, а reproducible decision practice with safe consequences.

## 5. План без воды: crypto beginner path

### Content filter
- Оставлять только то, что меняет наблюдение, проверку, решение или безопасность.
- Удалять историю и ideology, если они не объясняют текущий mechanism, risk or claim.
- Отдельно маркировать fact, interpretation, project claim, regulatory statement и unresolved uncertainty.
- Не давать project-specific UI до того, как learner понимает chain-neutral model.
- Не вводить DeFi, tokenomics, yield, staking или on-chain analytics до custody/network/security prerequisites.
- Любая теория получает: one-sentence explanation → visual contrast → worked example → retrieval → changed-context transfer.

### Минимальная последовательность
| Chapter | What the learner gets | Practice format |
|---|---|---|
| Chapter 0 — Crypto without hype | Что такое digital asset, network, service и claim; distinction between fact, promise and unknown. | No-money identity and no-action choices. |
| Chapter 1 — Network and transaction timeline | Address, key, signature, fee, mempool/confirmation/finality and irreversible error. | Synthetic transaction replay; observe before naming. |
| Chapter 2 — Custody and security | Custodial vs self-custody, seed phrase, phishing, approvals, fake support, domain and permission checks. | Threat-model missions with refusal/verify-more action. |
| Chapter 3 — Asset and protocol taxonomy | Bitcoin, smart-contract chain, token, stablecoin, NFT, protocol, exchange, wallet and bridge. | Contrastive classification across new surfaces. |
| Chapter 4 — Evidence and risk | Source provenance, incentives, tokenomics claims, liquidity, oracle/contract/bridge risk, protection limits. | Claim-evidence-unknown-risk board; no buy/sell output. |
| Chapter 5 — DeFi and on-chain scenarios | AMM, lending, collateral, liquidation, stablecoin failure, approvals and on-chain data limitations. | Optional advanced path; synthetic or historical replay with provenance. |
| Chapter 6 — Transfer and diagnostic | New chain/UI/scam narrative; choose action, invalidation, confidence and explain reasoning. | No-hint diagnostic and delayed transfer; professional mode deferred. |

### Formula for every unit
```text
one concept\n→ one visual contrast\n→ one worked example\n→ 3–5 guided retrieval items\n→ one security/no-action decision\n→ changed-context item\n→ debrief with known/unknown/risk\n→ delayed recall 48–72h\n→ novel transfer
```

### Что убрать из первого релиза
- Торговые стратегии, indicators, candlestick patterns и entry/exit setups.
- Live exchange tutorials, account opening, deposit, staking, yield and token picks.
- Большие списки chains/tokens/protocols.
- Gamified token rewards, leaderboards, price charts as a proxy for mastery.
- Deep cryptography, Solidity and quantitative on-chain analytics — только diagnostic/advanced track.
- Long lectures, duplicated glossary entries, platform marketing and unverified success stories.

## 6. Crypto-specific vertical slice

Для MVP вместо общего market-reading slice принять три mechanics:
- **Transaction observation:** time/sequence, intent, address, signature, fee, confirmation and failure point.
- **Custody/security evidence:** who controls key, what permission is requested, which red flag is present, when to stop.
- **Claim/risk classification:** fact vs claim vs unknown; network/token/protocol distinction; no-action/invalidation boundary.

На каждую механику — 3 task families × 3 tiers = 9 cells, всего 27 seeds. Historical crypto data и live price не нужны для Chapter 0; synthetic and point-in-time replay are sufficient after schema/security gates.

## 7. Score of current strategy: 10 categories

Балл отражает текущую стратегию после данного review, а не работу production runtime. 0–59 = weak, 60–74 = risky, 75–89 = viable with blockers, 90–100 = strong but still requires evidence.

| Category | Score /100 | Why |
|---|---:|---|
| Crypto novice clarity | 92 | strong visual/structured route; still no runtime onboarding evidence |
| Concept sequencing and prerequisites | 91 | explicit dependency model; content authoring not yet implemented |
| Security and fraud protection | 88 | security-first design and scam simulation; real-world threat coverage still needs audit |
| Active practice and decision quality | 90 | evidence, boundary, confidence and no-action loop |
| Transfer across chains/interfaces | 84 | planned same-skill/different-surface; no alpha data yet |
| Mastery, feedback and calibration | 88 | state machine and delayed recall defined; scoring needs implementation |
| Neutrality and anti-promotion | 89 | no-money MVP and source triangulation; crypto narratives still require editorial review |
| Accessibility and localization | 78 | WCAG/English/Russian principles exist; no runtime audit |
| Telemetry and research validity | 75 | event contract exists; privacy/idempotency and pilot not executed |
| Scope and production readiness | 83 | narrow vertical slice is feasible; replay/legal/content artifacts remain blockers |
| **Overall average** | **85.5 → 86/100** | High-potential crypto beginner strategy; implementation and alpha evidence still missing. |

### Why the strategy is not 95 yet
- Accessibility and localization have design decisions but no runtime audit.
- Telemetry, idempotency, privacy and deletion are specified but not executed.
- Transfer across chains and actual scam-resistance are hypotheses until pilot evidence.
- Crypto content changes quickly; versioning and source review are mandatory.
- Neutrality is difficult because many top resources are exchanges, wallets or ideological books.

## 8. Immediate implementation plan
1. Freeze crypto beginner taxonomy and glossary: network, address, key, wallet, custody, token, coin, protocol, exchange, stablecoin, DeFi, bridge, signature, fee, confirmation.
2. Write Chapter 0 theory and the 27 seed matrix using only synthetic no-money scenes.
3. Implement deterministic process rubric: observation, evidence, permission/recipient check, uncertainty, invalidation and confidence.
4. Implement safe fictional wallet/transaction UI with no external wallet, live chain or monetary balance.
5. Add scam/security threat-model tasks before any DeFi or tokenomics content.
6. Create source/provenance/version registry; every project claim needs date, incentive and evidence class.
7. Run 50 targeted tests from prior Iteration 4 plus crypto-specific tests: wrong network, wrong recipient, malicious approval, fake support, stale tokenomics and stablecoin failure.
8. Run usability alpha with complete novices; primary questions are comprehension, safe refusal, error recovery and delayed transfer—not trading activity.

## 9. Non-claims

Этот review не утверждает, что любой из 50 ресурсов доказанно обучает лучше других. Он сравнивает structure, accessibility, bias, practice and novice pain. Он также не является инвестиционной рекомендацией и не переводит Signal Arena в trading/portfolio product. Final learning, scam-resistance, transfer, retention and accessibility claims require alpha/pilot evidence.

**Главный вывод:** crypto beginner не нуждается в ещё одном широком курсе. Ему нужен короткий нейтральный тренажёр безопасного мышления: увидеть механизм, проверить источник и разрешения, назвать неизвестное, остановиться при риске и перенести навык на новую chain/interface.

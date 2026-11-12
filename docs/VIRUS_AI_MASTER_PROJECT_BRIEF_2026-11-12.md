# VIRUS AI — Master Project Brief for Independent Council Roadmap

**Snapshot:** 2026-11-12  
**Purpose:** This is the full project scope for the VIRUS AI Council. The Council must independently decide priorities, dependencies, implementation order and the single next task. This document is a scope map, NOT a pre-approved execution sequence.

## 1. Mission and product ownership

VIRUS AI is the owner's central AI application and product. It is not a clone or thin wrapper around ChatGPT, Claude, Grok or another provider. External models are replaceable workers, reviewers and research sources. VIRUS AI owns the user experience, task lifecycle, shared context and memory, model catalogue and routing, permissions, tools, Council orchestration, audit trail, GitHub workflow, domain engines and final result.

Primary app/runtime target: **Android + Termux on the owner's device**, using the existing VIRUS AI app/server and existing local data. Do not create a second app, second server, duplicate database or remote-control workflow for the phone. GitHub is source control, task transport, review and reporting; it is not a substitute for the local phone executor.

## 2. Finished-product outcomes

The owner should be able to:
1. Submit a task inside VIRUS AI.
2. Have the Council independently analyse it using one shared, versioned project context.
3. Receive a reasoned recommendation, priority, dependencies, cost estimate and execution plan.
4. Approve the exact task and its permissions/budget.
5. Let the local VIRUS AI executor perform approved work through the app's shared terminal/tool broker.
6. Run tests, review results, repair failures where authorised and preserve existing user data.
7. Publish commits, branches, PRs and factual reports to GitHub.
8. See status, logs, cost, outputs and final report inside the VIRUS AI app.
9. Learn from completed tasks and update project state without silently changing production policy.

## 3. Main workstreams — scope map, not priority ranking

### A. VIRUS AI application and local runtime
- Existing Android/Termux application, server and phone-first UI.
- Main areas include Home, Terminal, Council, Models, Data, Skills and System; actual completeness must be inspected.
- Main chats: My AI and Council.
- Text/voice input, Russian interaction, file/image sharing, task history, progress and result views.
- One persistent local app instance, one server lifecycle, shared local data and shared terminal session.
- Reliable start/recovery after Android process suspension or phone disconnect; no duplicate server/port/database.
- Routine workflows should not require the owner to manually paste shell commands.

### B. AI Council
- Council is the engineering/research/review team that helps improve VIRUS AI itself.
- Intended advisor pool: OpenAI, Anthropic, Google DeepMind, xAI, Meta AI, Microsoft AI, NVIDIA, DeepSeek, Alibaba/Qwen, Tencent/Hunyuan, Z.ai, Moonshot/Kimi, Baidu/ERNIE, Mistral and MiniMax.
- This is a target roster, not proof all 15 are configured or available. Report each as CONFIGURED, AVAILABLE, UNAVAILABLE, QUOTA_BLOCKED or NOT_TESTED from evidence.
- Process: independent analysis first; peer review/challenge second; chair synthesises evidence and disagreements. Do not decide by simple majority.
- Count only advisors with recorded successful responses. Do not hide missing providers.
- Council must decide current project priorities instead of repeating an old roadmap.

### C. Shared Project Context and memory
- One canonical project description, version and SHA-256 snapshot per task.
- Every advisor and chair receive the same frozen context and task.
- Record context version/hash in the Council journal and final report.
- Context includes mission, architecture, verified state, evidence, blockers, constraints and prior decisions.
- Mark stale/conflicting information instead of treating old Issues/PRs as current truth.

### D. Unified tools and capability broker
- One server-side broker for Council, My AI and executor; no provider-specific shell/tool access.
- Capabilities should cover project/file inspection, Git status/diff/log, approved tests, logs, GitHub Issues/branches/PR/reviews, task status and report publication.
- Enforce actor, task, capability, path, command, repository, budget and approval on the server.
- Council's current safe starting profile is read-only. Write/execute capability must be added in narrow, auditable levels.
- No unrestricted shell for model providers. No access to raw .env, API keys, passwords, tokens or environment dumps.
- Preserve uncommitted work. Never use destructive reset/clean/stash/overwrite operations on user work.
- Delete, arbitrary shell, secret changes, force-push, merge, deploy, production mutation and broker order placement remain blocked or require separate explicit owner approval.

### E. Autonomous task execution and terminal
- User task → analysis/plan → explicit owner approval → queue → executor claim → execution → tests → review → GitHub result → in-app report.
- Existing implementation areas include virus-ai-chat/index.ts, myai-agent.ts, terminal-jobs.ts, task-dispatcher.ts, github-agent-bridge.ts and proposal/approval modules. Actual wiring/runtime must be checked against current branch and commit.
- Council and My AI should use the same controlled terminal session, not separate shells.
- Need durable task states, deduplication, concurrency control, cancellation, timeout, retry limits, restart recovery, foreground process handling and auditable logs.
- Use isolated feature branches/worktrees for changes. Run deterministic tests. Create Draft PRs. Do not auto-merge or deploy.
- Code presence is not proof the full local Android/Termux execution cycle works.

### F. GitHub task transport, owner approval and reporting
- GitHub Issues can act as an inbox using an explicit task marker and allowlisted authors.
- Issue content is untrusted. Re-fetch and fingerprint it; verify author, repository, state and owner approval before execution.
- Approve/reject must be mutually exclusive. Revalidate approval after queue wait and immediately before execution.
- Revocation, Issue edit/close, stale fingerprint, missing/invalid signature or missing approval key must fail closed.
- Every completed stage publishes a factual report: commit/branch/PR, checks run, actual results, limitations and next question.
- Do not claim tests passed when a workflow did not reach a runner or local output is unavailable.

### G. Model discovery, registry and routing
- Discover new provider models/versions from official catalogues/API metadata; never invent model IDs.
- Keep provider, canonical ID/snapshot, capabilities, context size, tool/vision/coding support, account availability, pricing, latency, deprecation and evidence timestamp.
- Status lifecycle: DISCOVERED → VALIDATING → READY / UNAVAILABLE / DEPRECATED.
- READY requires actual account access and safe capability tests.
- Compare candidates on task-specific quality, speed, reliability and cost; preserve fallback and rollback.
- Route by task requirements and verified capability. Explain model choice and alternatives.
- Do not automatically buy subscriptions, enable paid access, change limits or spend money.

### H. Cost and provider reliability
- Default task budget: **$0.00**.
- Paid calls require a positive budget explicitly approved by the owner for that task and enforced server-side.
- Display estimated cost before execution and actual cost afterwards.
- Enforce hard per-task caps and daily/monthly ledger; fail closed if accounting is unavailable.
- Avoid infinite retries and paid fallback loops.
- Free-provider status must be verified from the actual account plan; model ID alone does not prove free-tier entitlement.
- Report provider errors, quota and unavailable models honestly.

### I. XAU/USD specialist AI — trading/research domain
This is a specialised domain engine inside the broader VIRUS AI product, not the definition of VIRUS AI itself.

Desired output:
- BUY / SELL / WAIT;
- direction, confidence, entry/stop/target/invalidation levels;
- expected move/distribution and horizon;
- cause → transmission → market confirmation explanation;
- explicit uncertainty and no-trade states.

Primary research interest: short-horizon gold impulse forecasting around market events, especially 1–30 minutes. Wider existing research may examine up to 60 minutes where justified. Do not assume any timeframe/model is validated merely because it exists. The old H1 model and legacy components must be assessed separately from the desired short-horizon engine.

Candidate expert roles:
- CORE / price-state model;
- forecasting models;
- market structure;
- microstructure/order flow;
- news/macro causal analysis;
- regime/volatility;
- price action/candlestick features;
- Meta-AI that learns which expert is useful in which regime and can choose WAIT when evidence is weak.

Meta-AI must answer “Can this forecast be trusted now?” and must not use simple majority voting.

### J. XAU/USD data, causal intelligence and event coverage
Potential data domains, each requiring source-quality and incremental-value tests:
- canonical XAU/USD M1 history; live Bid/Ask, spread, ticks and tick volume;
- broker/MT5 execution properties, latency, slippage and available DOM/depth/order-flow data;
- TradingView/OANDA price structure and independent cross-market prices;
- official economic releases, calendars, forecasts, actuals, revisions and publication timestamps;
- Fed, BLS, BEA, Treasury, CFTC and other official sources;
- DXY, FX, nominal/real yields, gold futures, silver and other markets only when they add measurable causal value;
- geopolitical, war, trade, energy, central-bank, fiscal and political events across relevant countries/regions;
- positioning, ETF, physical demand, options, liquidity and risk sentiment where timely, lawful and point-in-time data exists.

Causal chain to test:
event / actual-vs-forecast / revision → macro and policy expectations → USD and yields / cross-market transmission → gold response → price/flow confirmation.

Before an event, capture what was known and expected. After it, measure surprise, revisions, what may already be priced in, conflicting events, transmission path and persistence. News AI and Market AI reason independently before Meta-AI combines them.

Historical replay must be point-in-time/as-of. Use release timestamps and data vintages. Never backfill future knowledge. Missing/unverified data is UNKNOWN/MISSING, not FALSE and not fabricated confirmation. Social media, prediction markets and aggregators are not official confirmation.

### K. Market features and external research
Treat candidate methods as measurable features, not hard-coded trade rules:
- support/resistance, trend/channel, swing levels, BOS/market structure;
- liquidity sweeps, false breakouts, supply/demand;
- VWAP/anchored VWAP, volume profile, pivots, Fibonacci;
- previous day/session highs and lows;
- ATR/realised volatility, momentum/acceleration, candle body/wicks/range;
- RSI/MACD/EMA and other indicators only if ablation/OOS tests show incremental value;
- forecasting/time-series models such as Kronos/Chronos and other credible financial models only after reproducible benchmarks.
Use licensed/publicly accessible source material. Convert book concepts into numeric features and test them; do not encode simplistic patterns such as “hammer = BUY”.

### L. Backtesting, validation and model evolution
- Chronological splits and walk-forward evaluation; purge/embargo to prevent label overlap and future leakage.
- Fit preprocessing on training data only. Use next-bar execution and realistic spread, slippage and extra cost buffer.
- Baselines: always-WAIT, majority, persistence/momentum, mean reversion, random/time-preserving controls and other justified nulls.
- Report sample size, coverage, trade count, BUY/SELL precision separately, after-cost expectancy, net expectancy, profit factor, drawdown, MFE/MAE, Brier/calibration, confidence intervals, ambiguous intrabar outcomes and stability by year/session/regime/news.
- Never treat unresolved same-bar TP/SL ordering as a known win/loss.
- Separate research-only/reconstructed data from canonical activation-eligible data.
- Champion/challenger: propose, isolate, test, compare on identical origins, promote only on evidence, monitor drift and rollback on degradation.
- No self-modification of production or automatic champion promotion without explicit gates and owner control.
- A target such as ≥60% precision on selected signals is an objective to investigate, not a guaranteed result or metric to game. Coverage, costs and side-specific expectancy matter.

### M. Execution and trading safety
- Existing MT5 DEMO worker is a separate historical execution component.
- Historical PR #1 describes a **Windows-only MT5 DEMO worker**. That Windows requirement belongs only to that old worker; it does not make Windows the platform for VIRUS AI.
- Current VIRUS AI app target remains Android + Termux. The Council must assess how the trading execution adapter should be hosted/connected without conflating it with the app runtime.
- DEMO-only until research, data, execution, risk and forward-test gates pass.
- Hard block real/live accounts. No live broker orders, real-money trading, production worker changes or risk-policy changes during Council planning.
- Broker-specific symbol mapping (e.g. GOLD#), time zones, market hours and execution characteristics must be explicit and tested.

### N. Observability, reliability and user control
- Show task state, agent/model identity, tool, redacted arguments, result, duration, cost, logs, artifacts, GitHub links and errors.
- Health/heartbeat, crash recovery, queue recovery, deduplication and safe cancellation.
- Owner can inspect, approve, reject, revoke or stop work.
- Keep audit records and distinguish planned, running, blocked, failed and verified.
- No secret values in UI, logs, prompts, reports or GitHub.

## 4. Candidate project stages for Council decomposition

These are work packages, not a mandated order. Council may split, merge, reorder or replace them after examining dependencies and evidence.

1. **Current-state audit:** inspect app, branches, PR stacks, runtime, files, tests, unfinished changes and discrepancies. Produce a verified architecture map.
2. **Core app reliability:** ensure existing Android/Termux app, server, storage, UI and process recovery are stable.
3. **Council correctness:** verify real provider availability, independent advisor execution, shared task context, chair synthesis, peer review and visible participation/errors.
4. **Project context and memory:** canonical versioned context, hash, task history, decisions, stale-data handling and consistent retrieval.
5. **Unified capability broker:** safe shared tools, policy enforcement, audit, permission tiers and controlled local terminal access.
6. **Autonomous task lifecycle:** queue, owner approval/revocation, executor, shared terminal, cancellation, recovery, tests and reports.
7. **GitHub integration:** reliable Issue inbox, allowlist, fingerprinting, atomic decisions, local execution transport, Draft PR and report round trip.
8. **Cost and model governance:** $0 default, per-task paid approvals, hard caps, usage ledger, free-tier verification and fallback.
9. **Model registry and evolution:** official discovery, account availability probes, benchmarks, routing, deprecation and rollback.
10. **XAU data foundation:** canonical market history, real-time feed, event calendar, source provenance, PIT/vintages and coverage audit.
11. **Causal/news and cross-market engine:** global event coverage, release surprise, causal transmission, market confirmation and historical event replay.
12. **Short-horizon market intelligence:** market structure, order flow, regime, volatility, forecasting, price action and feature ablations.
13. **Meta-AI signal and risk logic:** calibrated BUY/SELL/WAIT, trustworthiness gate, levels, uncertainty, regime-aware expert weighting and no-trade decisions.
14. **Research validation and safe evolution:** walk-forward/OOS, cost-aware metrics, prospective shadow, champion/challenger and rollback.
15. **DEMO execution integration:** isolated MT5 DEMO adapter/worker, symbol/time/execution checks, risk gates and end-to-end reconciliation.
16. **Product completion and operations:** phone-first UX, reports, monitoring, security review, documentation, backup/recovery and release criteria.

## 5. Evidence-based snapshot — 2026-11-12

### Observed locally from owner-provided Termux output
- Active process PID 22454.
- Command: node --env-file=.env --experimental-strip-types index.ts.
- Working directory: $HOME/virus-core/workspace/.worktrees/virus-ai-github-bridge-integration-20261107/virus-ai-chat.
- GET /health returned HTTP 200 and JSON with ok:true, version control-center-2026-10-08-arch, and GitHub agent configured/running.
- The active index.ts imports the agent loop, GitHub bridge, task dispatcher and terminal-session functions.
- Grep of that active file found handlers for POST /api/council, POST /api/myai, /api/jobs, terminal session create/exec/read/close, and GitHub agent status/control.
- This proves the process and route definitions were observed. It does NOT prove a successful Council model response, multiple live advisors, autonomous task completion or full Android E2E.

### GitHub state observed
- Issue #614 is the broad task for shared Council access, tool broker and model discovery/routing.
- Issue #615 described atomic approval/revocation/revalidation requirements.
- PR #616 is a Draft read-only Council tool-policy stage. Its description reports CI PASS at its stated head, but no physical phone E2E.
- PR #617 is a Draft shared Project Context stage. Its description reports tests for frozen context/hash and read-only tool policy, with CI PASS at its stated head. It does not enable code writes or prove phone runtime.
- PR #619 is a Draft $0/free-only Council restriction stage. Its description reports CI PASS at its stated run, but no phone E2E.
- PR #620 is a Draft per-task paid-budget and hard-cap stage. Its description reports CI PASS at its stated run, but write tools remain disabled and phone E2E is unverified.
- PR #621 is a Draft atomic approval/revocation/revalidation stage. Its description reports 240 autonomous-engine tests and bridge tests passing at an earlier head; later attempts on a newer head did not reach runner steps (runner_id=0, empty steps, BlobNotFound). Do not label the latest head fully CI-verified.
- PR #622 is a Draft security layer on the current Project Context/read-only branch; it requires explicit owner attestation of Groq Free Plan before Groq calls. Its CI and phone runtime status need fresh verification.
- PR #613 is a Draft GitHub Issue Inbox approval implementation. Its latest recorded CI attempts did not reach a runner/steps; this is not proof of code failure and not a passing test result. Physical Android/Termux E2E remains pending.
- These PRs are open and stacked/overlapping. Inspect current head SHAs, bases, diffs and dependency graph before recommending integration order. Do not assume descriptions refer to the same code state.

### Local workspace cautions
- The primary Termux workspace contains modified files and many untracked items from earlier work.
- Do not run destructive Git commands or overwrite/reset the existing workspace.
- The active app process is in the virus-ai-github-bridge-integration-20261107 worktree, not necessarily the primary workspace.
- Do not restart the active server just to inspect it.
- Never request or print .env, API keys, passwords, approval keys or tokens.

## 6. Conflicts and stale instructions the Council must resolve

- Older Issues and roadmaps may describe earlier priorities or platforms. Treat them as historical unless revalidated.
- Issue #434 contains a dated 2026-11-01 instruction prioritising initial Task Inbox activation. The owner now explicitly asks the Council to independently evaluate the complete project and choose the current priority/order; do not blindly inherit that old sequence.
- The earlier canonical Project Context in PR #617 contains a numbered development-priority list. This master brief supersedes that list as the current request: the Council must independently reassess and propose a new order.
- PRs #616–#622 contain overlapping/stacked security, context, budget and approval work. Reconcile exact branch ancestry, head commits and semantics before choosing integration order.
- Budget descriptions differ across PRs: $0/free-only, paid per-task approval and Groq free-plan attestation. Determine compatible controls and the safest complete policy. Do not enable paid routing during planning.
- Old MT5 Windows-only notes describe the historical MT5 worker, not the VIRUS AI app runtime.
- Existing model names, provider roster, data feeds, historical files, accuracy numbers and trading readiness must be independently verified; this brief does not certify them.

## 7. Required Council assignment

Before proposing implementation:
1. Each available advisor independently reviews this entire brief and current repository/PR evidence. Record which advisors actually responded.
2. Each advisor identifies missing requirements, false assumptions, duplicated work, security risks, architecture debt and valuable opportunities.
3. Each advisor proposes its own stage ordering with reasons, dependencies, effort, risk, cost and measurable acceptance criteria.
4. Advisors challenge one another's proposals and resolve disagreements using repository evidence, tests and authoritative sources—not majority voting.
5. The chair produces one consolidated architecture and dependency graph.
6. The chair classifies every work package as VERIFIED, PARTIALLY IMPLEMENTED, IN PROGRESS, BLOCKED, NOT STARTED or NEEDS RESEARCH, with evidence and current SHA/PR where available.
7. The Council ranks the next work using impact, dependency criticality, risk reduction, time-to-first-working-result, cost and owner value. Explain the ranking; do not echo old priorities.
8. Select exactly one next implementation task, or explicitly state BLOCKED and request the single missing prerequisite. Define scope, exclusions, branch/PR strategy, tests and Definition of Done.
9. Separate $0 work from optional paid work. Do not spend money or call paid models without per-task owner approval.
10. Return the complete report to the VIRUS AI app and publish it to the GitHub task/report thread.

## 8. Required Council output

- Executive verdict on the real project state.
- Current architecture/component map.
- Status matrix for all work packages.
- PR/branch dependency graph with exact current SHAs.
- Top blockers and risks by severity.
- Recommended priority ranking with rationale and dependencies.
- Staged roadmap with gates and measurable acceptance tests.
- Cost/budget implications and $0 path.
- Safety boundaries and non-goals.
- The single next task and exact acceptance criteria.
- Advisor participation table, individual positions, disagreements and chair synthesis.
- Evidence links and facts that remain unverified.

## 9. Safety and non-goals

This assignment is analysis and planning only. Do not:
- edit production code or configuration;
- change secrets, .env, provider subscriptions or billing settings;
- merge PRs, deploy, force-push or mutate production;
- enable autonomous write access or bypass owner approval;
- execute trades or change live/demo risk settings;
- claim Android/Termux E2E passed without actual phone output;
- claim all 15 advisors participated unless successful responses prove it.

The Council may recommend an implementation order, but the owner retains approval over execution, spending, merge, deployment and trading.

---
**Owner's current instruction:** Use this report as the complete project brief. The Council—not the report author—must decide what is most important, what depends on what and what should be done first.


## 10. Owner clarification — VIRUS AI Global Economic & World News Calendar (2026-11-12)

This section is a core product requirement, not an optional XAU/USD add-on. The owner is creating an original, proprietary global economic and world-news intelligence calendar inside VIRUS AI. It must not be reduced to a clone, static schedule, link collection or embedded third-party calendar.

### 10.1 Product ownership and integration principle
- VIRUS AI owns the calendar's data model, country/source registry, event identity, normalization, timeline, search, alerts, provenance, confidence, analytics, causal links and user interface.
- Integrate useful information from the three named external platforms discussed with the owner: TradingView (trader/market platform), Interactive Brokers (global brokerage and market-information platform) and Investing.com (economic-calendar/news platform). Treat them as external data sources and reference systems, not as the product's core or owner.
- Bring permitted data and capabilities into VIRUS AI so the user can work in one app. Prefer official APIs, licensed feeds, documented exports and permitted public publications. Respect provider terms, licensing, attribution, rate limits and redistribution restrictions. Do not assume that a website's visible content can legally or technically be copied or rebroadcast in full.
- Add direct primary sources independently; do not rely on the three platforms as the sole coverage layer. Preserve source identity and link back to original publications where appropriate.
- Where a source cannot be integrated, show an explicit unavailable/unsupported status and a lawful alternative. Never fabricate a feed or claim a live connection without a successful probe.

### 10.2 Global country and institution registry
- Build a versioned registry intended to cover every country and relevant jurisdiction, not only G7/G20 or countries currently important to gold.
- For each country/jurisdiction, catalogue official institutions and their source endpoints: central bank/monetary authority, national statistics office, finance ministry/treasury, debt-management office, tax/customs authority, energy/mining/agriculture agencies, labour agencies, government press offices, regulator and national exchange where relevant.
- Include regional and supranational institutions (for example IMF, World Bank, BIS, OECD, ECB, Eurostat, UN agencies, OPEC and relevant energy agencies) as separate entities with their own publication calendars and jurisdictions.
- Store canonical names, aliases, country/jurisdiction codes, language, timezone, official domain, source type, publication channels, API/feed/document methods, update cadence, access/licence conditions, reliability tier, last successful check and current health.
- Maintain a coverage matrix: country × institution type × topic × source availability × ingestion status × freshness. Explicitly mark gaps; do not imply full coverage until measured.

### 10.3 Event universe — scheduled and unscheduled
- Scheduled macroeconomic releases: inflation, CPI/PPI, GDP, employment, wages, PMI, retail sales, industrial output, trade/current account, housing, confidence, fiscal and debt statistics.
- Monetary policy: rate decisions, statements, minutes, votes, speeches, press conferences, liquidity operations, balance-sheet actions, FX intervention and reserve disclosures.
- Government and geopolitical events: elections, budgets, tax changes, sanctions, tariffs, trade restrictions, treaties, conflict escalation/de-escalation, emergency measures, political statements and official decisions.
- Commodities and strategic supply: gold, silver, oil, gas, electricity, uranium, critical minerals, mining, refining, shipping routes, production quotas, inventories and disruptions.
- Financial system: sovereign issuance/auctions, yields, banking stress, capital controls, market closures, exchange notices, regulation and systemic incidents.
- Unscheduled/early micro-news: first official statements, local/regional reports, agency notices, company/industry announcements and developing events that may later become major headlines. Keep unverified reports separate from confirmed facts.
- Calendar records must distinguish scheduled time from actual publication/first-seen time, revised time, delayed/cancelled status and event-timezone conversion.

### 10.4 Canonical event record and provenance
Every event should support, where applicable:
- stable VIRUS event ID; country/jurisdiction; institution; topic/category/subcategory; event title and multilingual aliases;
- scheduled timestamp, timezone, actual release timestamp, first-seen timestamp, last-updated timestamp and source publication timestamp;
- source URL/document/feed identifier, source type, evidence snapshot/hash and retrieval metadata;
- event status (scheduled, released, delayed, cancelled, developing, confirmed, disputed, retracted);
- Actual, Forecast, Previous, revised Previous, units, scale, seasonal adjustment, consensus provider and sample/time of consensus;
- source confidence, verification state, corroboration count and conflict notes;
- importance by general macro significance and separately by estimated XAUUSD relevance;
- historical values/vintages and point-in-time availability, so historical replay only sees information available at that moment.
Missing values remain UNKNOWN/MISSING, not zero or FALSE. Preserve original source values and normalized values separately. Never silently overwrite revisions.

### 10.5 Original VIRUS AI intelligence layer
- Deduplicate the same event reported by multiple sources while preserving every source observation and timestamp.
- Resolve entities, country, institution, event family, related events and cross-border links.
- Detect unusual changes, deviations from schedules, surprise values, revisions, conflicting statements and emerging event clusters.
- Build causal graphs: event → policy/economic channel → USD/yields/risk/commodities/cross-market transmission → gold response. Record alternative explanations and uncertainty.
- Score event importance, source reliability, novelty, urgency and XAUUSD transmission relevance separately; do not collapse them into one opaque score.
- Separate FACT, OFFICIAL CONFIRMATION, ATTRIBUTED REPORT, UNVERIFIED CLAIM, ANALYST INTERPRETATION and MODEL HYPOTHESIS.
- Generate explainable summaries in the app, preserve source links and evidence, and update them when new facts arrive.
- Maintain an event lifecycle: detected → triaged → corroborating → confirmed/disputed/retracted → impact assessed → outcome measured.

### 10.6 XAUUSD impact and learning
- For each relevant event, record pre-event expectations, known context, scenario probabilities, expected direction/magnitude/horizon, invalidation conditions and confidence.
- On release, calculate surprise versus consensus and prior/revised values, then monitor actual market reaction across configurable short horizons (including 1, 5, 15, 30 and 60 minutes where data supports it).
- Distinguish expected impact from observed impact; measure whether the event was already priced in, whether another event dominated and whether transmission was confirmed by market data.
- Keep point-in-time event history and source vintages for unbiased historical replay, walk-forward/OOS testing and model calibration.
- The calendar itself must remain useful for all global macro research even when an event has no demonstrated gold impact.

### 10.7 AI Council is a co-design and research team for this product
- The Council must actively help design and build this global calendar, not merely review it after implementation.
- Each actually available free-tier advisor may contribute within verified free access: country/source discovery, official-source verification, event taxonomy, schema design, API/feed research, language coverage, deduplication, data quality, causal hypotheses, UI/UX, testing and security review.
- Paid models are separate optional calls. They are not assumed to be group members and must not be called without explicit per-task owner budget approval. Default remains $0.
- Give advisors bounded research work packages and the same versioned context; collect source URLs, evidence, confidence, limitations and proposed implementation. The chair reconciles overlap and contradictions.
- The Council must produce a country-by-country source coverage plan, canonical event schema, integration matrix for the three platforms, phased implementation roadmap, test strategy and exactly one recommended next task.
- Do not claim every provider or every country has been covered until participation and source coverage are measured.

### 10.8 Acceptance gates
1. **Specification gate:** approved architecture, event schema, taxonomy, provenance rules, source/licence policy and coverage metrics.
2. **Country registry gate:** versioned global country/jurisdiction registry with institution/source coverage and explicit gaps.
3. **Source integration gate:** working, monitored adapters for permitted TradingView, Interactive Brokers and Investing.com data, plus official primary sources; each adapter has tests and failure states.
4. **Calendar ingestion gate:** scheduled and unscheduled events normalized, deduplicated, versioned and searchable in the VIRUS AI app.
5. **News/micro-news gate:** first-seen timestamps, source hierarchy, corroboration, retraction and uncertainty handling work end to end.
6. **Intelligence gate:** explainable event relationships and XAUUSD impact estimates are recorded without future leakage.
7. **Historical validation gate:** point-in-time replay, coverage/latency/quality metrics, source outage tests and OOS evaluation pass.
8. **Operational gate:** app displays source freshness, missing coverage, adapter health, event history, alerts and audit trail.

No stage is complete based only on code presence, a design mockup or a provider's marketing claim. Require reproducible tests and observed runtime evidence.

**Owner's explicit clarification:** The deliverable is an original VIRUS AI-owned worldwide economic calendar and world-news/micro-news intelligence system, combining permitted information from TradingView, Interactive Brokers, Investing.com and official institutions/banks of countries worldwide. The entire AI Council should help research, design, validate and implement it.

## 11. Owner clarification — Global Economic Intelligence Map and World News Intelligence (2026-11-12)

The owner explicitly requires a complete, original VIRUS AI-owned **Global Economic Intelligence Map**. This is broader than an economic calendar. The Council must help research, architect, build and validate it as a core product.

### 11.1 Product outcome
Create one worldwide view that connects:
- all countries and relevant jurisdictions;
- their central banks, monetary authorities, national statistical offices, finance ministries/treasuries, debt offices, customs, labour, energy, mining, regulators, exchanges and official government publication channels;
- macroeconomic indicators, monetary/fiscal policy, public debt, banking/financial conditions, trade, labour, prices, production, energy and strategic commodities;
- scheduled releases, unscheduled decisions, official statements and developing world news;
- cross-country relationships and transmission channels;
- a separate fast world-news/micro-news stream, with a dedicated assessment of possible economic, market and XAUUSD effects.

The product must present a global map, country profiles, institution/source profiles, indicator dashboards, a unified event calendar, historical series, comparison tools, news stream, alerts and explainable relationship/impact views inside the VIRUS AI app.

### 11.2 Learn from existing platforms without copying their product
Research how the following platforms collect, process and present data:
- TradingView: market data, economic indicators, calendar, charts, Macro Maps and country views. TradingView announced on 2026-11-09 that its economic data feed switched on 2026-11-05 to an in-house feed sourced directly from publishing institutions, including central banks, national statistical offices, World Bank and IMF. This is an architectural reference for building VIRUS-owned ingestion infrastructure, not permission to copy TradingView's data or implementation.
- Interactive Brokers: market-data and news-provider integrations exposed through documented APIs; actual news providers and market-data access depend on subscriptions, permissions and redistribution rights.
- Investing.com: event calendar with Actual / Forecast / Previous and expected-impact classification. Treat displayed consensus as an estimate from a survey/provider, not an official government value. Obtain actual release values from the publishing institution whenever possible.
- Also study global macro-data platforms and official portals such as IMF Data, World Bank Data, BIS Data Portal, ECB Data Portal, FRED/ALFRED, BLS and BEA. These are reference architectures and potential direct sources, subject to their API terms and data limitations.

### 11.3 Source-of-truth hierarchy
For each observation/event, identify its provenance and classify it:
1. **Primary official release:** originating central bank, statistics office, ministry, regulator, exchange or government agency.
2. **Official international compiler:** IMF, World Bank, BIS, OECD, UN, ECB/Eurostat and other relevant international bodies. Record whether the value is reported by a country, harmonised, estimated or compiled by the institution.
3. **Licensed market/news provider:** use within subscription and redistribution permissions; retain provider attribution and restrictions.
4. **Secondary media/aggregator:** discovery, context and corroboration only unless the item is explicitly attributed and its evidence is preserved.
5. **Social/unverified:** early leads only; never silently promote to confirmed fact.

"Official" does not automatically mean "latest" or "error-free". Record publication time, first-seen time, update/revision time, retrieval time, source health and known delay. If sources conflict, preserve both observations and flag the conflict; do not silently select one.

### 11.4 Country and institution graph
Build a maintained global registry and graph:
- country/jurisdiction → institution → official channel/dataset → indicator/event → release schedule → observations/vintages;
- institution mandates, jurisdiction, language, timezone, website/domain, API/feed/document endpoints, formats, update cadence, access/licence terms, reliability evidence, last successful retrieval and health;
- cross-border and regional bodies mapped separately from national authorities;
- coverage dashboard with country × institution × topic × indicator × frequency × source tier × freshness, including explicit missing-source gaps.

Use ISO country/jurisdiction identifiers and stable VIRUS IDs. Do not assume every country publishes every indicator or has a machine-readable API. For gaps, research official bulletins, downloadable files, structured pages and permitted document extraction; retain a human-review state where automation cannot reliably parse.

### 11.5 Economic indicator ontology
Create a canonical multilingual taxonomy and metadata dictionary for:
- national accounts: GDP, GNI, output, productivity, consumption, investment;
- prices: CPI, core CPI, PPI, PCE/HICP where applicable, inflation expectations;
- labour: unemployment, participation, payrolls, wages, vacancies, hours;
- monetary/central banking: policy rates, decisions, minutes, speeches, balance sheets, money supply, credit, reserves, FX operations;
- fiscal/sovereign: budgets, deficits, revenues, spending, debt, issuance, auctions, yields, ratings and payment events;
- external sector: exports/imports, trade balance, current account, capital flows, FX reserves;
- industry and demand: manufacturing/services, PMI, industrial production, retail sales, housing, confidence;
- energy/commodities: oil, gas, electricity, gold, silver, critical minerals, production, inventories, exports and supply disruptions;
- banking/financial system: deposits, lending, non-performing loans, liquidity, capital, systemic risk, payment systems and financial stability;
- policy/regulatory/geopolitical events with explicit evidence and status.
For every series define unit, currency, scale, frequency, seasonal adjustment, reference period, release lag, methodology, source, revision policy and comparability limitations.

### 11.6 Data collection and processing pipeline
Council must design a robust pipeline:
1. Discover/register official source endpoints and legal access conditions.
2. Poll APIs/SDMX or subscribe to feeds where available; monitor official release calendars/RSS; retrieve permitted HTML/PDF/XLS/CSV documents when no API exists.
3. Preserve immutable raw source payload/document, retrieval timestamp, content hash and source URL.
4. Parse into a staging layer; validate schema, units, period, timezone, encoding and country/institution identity.
5. Normalize to canonical VIRUS schemas without destroying original values.
6. Deduplicate while retaining source observations and conflicting values.
7. Store publication vintages and revisions as append-only history; never overwrite the original release.
8. Publish validated records to the global map, country profile, indicator series, event calendar and news stream.
9. Track freshness, latency, missingness, parser failures, source outages and reconciliation results.
10. Re-fetch/reconcile corrections and publish a visible correction history.

Use incremental ingestion, retry/backoff, rate limits, caching, idempotency, dead-letter handling, source health checks and a replayable audit trail. The pipeline must not depend on scraping a rendered page when a stable official API or feed exists.

### 11.7 Separate World News / Micro-News Intelligence stream
This is a distinct product stream, connected to but not confused with official statistical observations:
- monitor official central-bank, government, regulator, exchange, energy-agency, international-organisation and company/industry announcements, plus licensed news feeds;
- detect first publication and first-seen time; preserve original headline, source, language, URL, evidence and subsequent updates;
- classify FACT / OFFICIAL STATEMENT / ATTRIBUTED REPORT / UNVERIFIED LEAD / ANALYSIS / MODEL HYPOTHESIS;
- cluster duplicate reports, translate/summarise, resolve entities and connect each item to countries, institutions, sectors, commodities and indicators;
- detect escalation, policy shifts, supply interruptions, sanctions, tariffs, conflict developments, banking stress and other potentially material events;
- maintain corroboration, contradiction, retraction and correction states;
- score novelty, source reliability, urgency, economic significance and XAUUSD relevance as separate explainable dimensions;
- keep a low-latency breaking-news stream separate from the slower scheduled macro calendar and historical indicator database.

### 11.8 Economic World Map and cross-country intelligence
The map is an analytical interface, not merely a decorative world map. It should allow:
- selecting a country to inspect current economic state, central bank, latest official releases, upcoming calendar, historical trends and source freshness;
- comparing countries/regions on equivalent indicators with unit, frequency, methodology and vintage alignment;
- viewing global heatmaps for inflation, rates, unemployment, GDP growth, debt, trade and other supported indicators;
- tracing dependencies and spillovers (e.g. policy rates → currency/yields → capital flows/commodities → other economies);
- following regional blocs, trade/energy relationships and institution networks;
- distinguishing measured observations from estimates, consensus, forecasts and VIRUS AI analysis.

Never compare unlike definitions as if they were identical. Surface methodology breaks, missing data, incomparable frequencies, provisional estimates and revision status.

### 11.9 XAUUSD and global-market transmission layer
The global map and news stream feed a separate causal analysis:
- identify which countries, institutions, indicators, policy decisions and events can affect USD, real yields, rates expectations, liquidity, risk appetite, energy and gold supply/demand;
- model direct and indirect channels, time lags, competing causes and priced-in expectations;
- produce a traceable event → macro channel → cross-market transmission → XAUUSD hypothesis;
- separately measure forecast and observed market response over short horizons;
- do not claim causation from correlation alone; require evidence, alternatives and out-of-sample validation.

### 11.10 Council work allocation and deliverables
The AI Council must jointly create this system. Assign independent, evidence-backed work packages to actually available free-tier advisors, then peer-review and synthesize:
- platform architecture research (TradingView, Interactive Brokers, Investing.com and relevant alternatives);
- country and institution registry/source discovery;
- official-source/API/SDMX catalogue and licence/redistribution matrix;
- indicator ontology and canonical event/observation schemas;
- ingestion, storage, revision/vintage and data-quality architecture;
- world map/country dashboard and comparison UX;
- breaking-news/micro-news discovery and verification architecture;
- cross-country economic graph and causal transmission design;
- XAUUSD relevance methodology;
- security, reliability, performance and test plans.

Required Council outputs: source catalogue with URLs and access terms; platform integration feasibility matrix; country/institution coverage matrix; indicator taxonomy; canonical schemas; architecture/data-flow diagram; phased roadmap with dependencies; measurable Definition of Done; estimated free versus paid work; exactly one recommended next task. Record which advisors actually contributed. Default paid-model budget remains $0; paid calls require explicit per-task owner approval.

### 11.11 Acceptance criteria
- The app has one VIRUS-owned global map and unified data model, not merely embedded third-party pages.
- Every displayed fact links to its source and shows source class, publication time, first-seen time, retrieval time, freshness and revision status.
- Every country has a measurable coverage record; missing official data is explicitly visible.
- Official observations, consensus forecasts, third-party estimates and VIRUS AI hypotheses are separate data classes.
- Revisions and historical vintages can be replayed as-of a past timestamp without future leakage.
- Calendar and breaking-news streams are distinct but cross-linked.
- Source adapters have health checks, rate-limit handling, tests and outage states.
- Cross-country comparisons expose unit/methodology/frequency differences.
- XAUUSD impact analysis is explainable, uncertainty-aware and separately validated.
- Council participation and all completion claims are evidence-backed.

**Owner's explicit requirement:** Build a unique VIRUS AI Global Economic Intelligence Map that unifies official economic data from the world's countries and institutions, a global economic calendar, and a separate world-news/micro-news stream. The Council must help design and create it.

---

# 12. Owner clarification — исходная Global World Intelligence Map и двухагентная система Council + My AI

**Дата уточнения:** 2026-11-12  
**Статус:** OWNER REQUIREMENT / DESIGN; не означает, что функции уже реализованы или прошли runtime E2E.

## 12.1 Не смешивать две карты

Первоначальная **Global World Intelligence Map / Global Causal Intelligence** — общая карта мировой обстановки, а не только экономическая карта. Её исходные требования зафиксированы в переписке 2026-10-10 и в документации/PR #427 от 2026-10-28:

- интерактивная карта всего мира с 3D-глобусом и возможностью 2D-представления;
- страны, территории, регионы, города/места, государственные органы, организации, рынки, инфраструктурные узлы и события;
- сбор новостей и событий из всех стран, включая небольшие местные источники и малые инциденты;
- политика, дипломатия, переговоры, конфликты/безопасность, аварии, катастрофы, климат, технологии/AI, торговля, санкции, логистика, энергетика, промышленность, экономика и рынки;
- поиск по странам/событиям/организациям/рынкам; карточка выбранной сущности с фактами, временем, источниками, связанными событиями и аналитикой;
- мировая лента и временная шкала, история события до и после;
- слои стран и границ, новостей/геособытий, политики, безопасности, экономики, центральных банков, FX/долга/облигаций, рынков/золота, энергетики, торговли/логистики, санкций, катастроф/климата, населения и технологий/AI;
- граф наблюдаемых связей и отдельно маркированных причинных гипотез между странами, организациями, событиями, ресурсами, цепочками поставок и рынками;
- самостоятельная аналитика VIRUS AI: дедупликация, сопоставление версий, выявление противоречий, альтернативных объяснений и возможных последствий.

**Global Economic Intelligence Map** — отдельная специализированная подсистема внутри общей мировой системы: страны → центральные банки/статистические службы/министерства финансов/регуляторы/биржи → официальные API и публикации → показатели/события → фактические значения и исторические ряды.

Экономическая карта не заменяет общую мировую карту. Собственный экономический календарь и отдельные World News / Micro News потоки связаны с обеими подсистемами.

## 12.2 Исходная карта и её сохранённые артефакты

Исторические артефакты для обязательного повторного аудита:

- PR #427: https://github.com/diyr1997/xauusd-ai-signal-bot/pull/427
- ветка: `virus-ai-realistic-global-map-20261028`
- спецификация: https://github.com/diyr1997/xauusd-ai-signal-bot/blob/virus-ai-realistic-global-map-20261028/docs/VIRUS_AI_GLOBAL_INTELLIGENCE_MASTER_SPEC_RU.md
- UI prototype: `virus-ai-chat/global-map.html`
- core: `virus-ai-chat/global-map-core-v2.mjs`
- tests: `virus-ai-chat/tests/global-map-core.test.mjs`, `virus-ai-chat/tests/global-map.test.mjs`

Спецификация описывает архитектуру L0–L12, географические сущности, источники, evidence/data quality, Event Intelligence, Knowledge/Causal Graph, Council, XAUUSD, risk gates, UI и этапы P0–P9.

UX-инварианты:
- премиальный тёмный интерфейс, большая детализированная Земля и чёткие границы;
- автоматическое вращение глобуса выключено; только ручное управление, zoom и reset;
- никаких вымышленных маркеров, дуг, потоков, цен, угроз и причинных линий;
- единое приложение VIRUS AI, адаптация для Android/mobile без потери возможностей;
- каждый слой показывает источник, покрытие, последнее успешное обновление, ограничения и ошибки.

PR #427 — Draft/prototype, а не production. Отключённые слои, геолокация событий, официальные экономические коннекторы и текущая работоспособность должны быть перепроверены по актуальному коду и runtime. Старые тестовые результаты не считать текущим подтверждением.

## 12.3 Две главные роли ИИ

### AI Council — исследовательский и инженерный Совет

Совет должен реально выполнять независимые исследования, проектировать VIRUS AI, изучать весь репозиторий и документацию, проверять архитектуру/ветки/PR/тесты, распределять задачи между реально доступными бесплатными участниками, выявлять противоречия, критиковать решения, проводить code review и формировать доказательный синтез.

Совет должен видеть фактическое участие каждой модели, ответы, ошибки, квоты, стоимость, tool calls и недостающие ответы. Недоступная модель не считается голосом; неполный Council не является консенсусом.

### My AI — автономный исполнитель и создатель проекта

«Мой ИИ» должен самостоятельно выполнять полный разрешённый цикл: принять задачу → прочитать актуальный Project Context → составить план → исследовать проект → создать feature branch → изменить код/документы → запустить тесты → исправить ошибки → передать результат Совету на независимую проверку → внести исправления → опубликовать commit/Draft PR/отчёт → показать результат в VIRUS AI.

Требуются durable queue, task states, deduplication, concurrency control, cancellation, timeout, ограниченные retries, restart recovery, foreground process handling и audit logs. Цель — одна задача до проверяемого результата без ручного переноса команд и контекста владельцем.

## 12.4 Единая среда и полный рабочий доступ

Council и My AI используют:
- один версионированный Project Context;
- один серверный Tool Broker и реестр инструментов;
- общий orchestrator и одну контролируемую terminal/PTY-среду;
- общий актуальный контекст задач, решений, веток, SHA, результатов тестов и отчётов;
- передачу задач и результатов внутри VIRUS AI, а не отдельный внешний чат.

Оба получают repository-wide read и доступ ко всему рабочему проекту: дерево и содержимое файлов, поиск, история, commits, refs/branches, diffs, Issues, PRs, reviews, checks/workflows, документация, тесты и отчёты. Оба должны иметь реальные разрешённые инструменты, а не декоративный read-only интерфейс. My AI выполняет изменения в изолированных feature branches/worktrees; Council использует инструменты исследования, тестирования и независимого review.

Все операции проходят через Tool Broker с проверкой пользователя, роли, задачи, repository, пути, команды, capability, бюджета и approval. Это функционально полный доступ в рамках разрешённых операций, но не доступ к секретам: .env, API keys, passwords, session/approval tokens и environment dumps не передаются моделям. Не выдавать провайдерам неконтролируемый shell.

Delete, изменение секретов/прав, force-push, merge, deploy, production mutation и реальные торговые операции запрещены или требуют отдельного явного подтверждения владельца. Сохранять незакоммиченные изменения; не применять destructive reset/clean/stash/overwrite.

Связанные исходные задачи:
- Issue #614 — единый Tool Broker и рабочий доступ Council/My AI: https://github.com/diyr1997/xauusd-ai-signal-bot/issues/614
- Issue #615 — атомарный approval/reject/revoke и повторная проверка перед execution: https://github.com/diyr1997/xauusd-ai-signal-bot/issues/615

## 12.5 Обязательная последовательность готовности

**Stage 1 — Council operational readiness.**
Проверить реальный UI → POST /api/council → provider calls → независимые ответы → tool calls → chair synthesis → результат в UI/GitHub. Проверить фактически ответивших участников, ошибки и стоимость. Выполнить безопасный $0 аудит GitHub. Наличие endpoint или списка моделей не является доказательством. DoD: воспроизводимый run ID, реальные ответы, tool logs, синтез, стоимость $0 и опубликованный отчёт.

**Stage 2 — My AI autonomous execution readiness.**
Проверить реальный POST /api/myai, queue/dispatcher, shared terminal, GitHub bridge, proposal/approval/write paths, restart recovery и отчётность. Исторический `myai-agent.ts` в ветке PR #427 содержит `write: false`; это важный проверяемый признак прежнего read-only режима, но не доказательство текущего состояния активной ветки. DoD: безопасная задача проходит от постановки до изменения в отдельной ветке, тестов, исправления и Draft PR/отчёта, отображённого в приложении.

**Stage 3 — совместное создание VIRUS AI.**
Council исследует, проектирует, распределяет и независимо проверяет. My AI реализует по одному этапу, тестирует, исправляет и публикует результат. Повторять цикл до Definition of Done каждого этапа.

**Stage 4 — создание глобальной интеллектуальной системы.**
Сначала единая архитектура и source/entity registry; затем ingestion, нормализация, evidence и историческая память; затем общая World Intelligence Map, Economic Intelligence Map, календарь, World News/Micro News; затем causal graph и XAUUSD transmission; затем масштабирование покрытия и валидация.

Не переходить к следующему этапу до проверяемого DoD предыдущего.

## 12.6 Бюджет, ограничения и отчётность

- Default budget: $0.00. Использовать только фактически доступные бесплатные модели и разрешённые источники.
- Платные модели, подписки и платные источники — только с отдельным бюджетом и явным подтверждением владельца на конкретную задачу.
- Не менять торговые разрешения; MT5 DEMO-only, реальные сделки заблокированы.
- Не раскрывать секреты и не менять .env/ключи/пароли.
- Не терять пользовательские незакоммиченные изменения.
- Не выполнять merge/deploy без отдельного разрешения.
- Каждый отчёт фиксирует SHA/ветку/PR, реальные команды и тесты, результаты, ошибки, ограничения и следующий шаг.
- Статусы: VERIFIED / PARTIALLY IMPLEMENTED / IN PROGRESS / BLOCKED / NOT STARTED / NEEDS RESEARCH.

## 12.7 Поручение Совету

Совет обязан сначала доказать работоспособность самого Council, затем определить и закрыть блокеры автономного My AI, после чего представить единую архитектуру, точную матрицу возможностей/доступа обоих агентов и поэтапный план создания VIRUS AI. Не заявлять о работающей автономности, полном доступе или готовой карте без фактического E2E и проверяемых доказательств.



---

# 14. OWNER PRIORITY OVERRIDE — Council сначала улучшает себя и VIRUS AI

**Дата:** 2026-11-12  
**Приоритет:** выше всех продуктовых модулей и карт. Это уточнение владельца имеет приоритет над последовательностью, если та трактует Council только как готовый инструмент.

## 14.1 Первый этап — Совет улучшает собственную работоспособность

Первой реальной миссией AI Council является не проектирование мировой карты, календаря или торгового движка. Его первая миссия — провести полный аудит самого себя и улучшить собственную систему внутри VIRUS AI.

Council должен:
- проверить собственный интерфейс, API, маршрутизацию, модельный адаптер, оркестратор, распределение задач, параллельные вызовы, общий контекст, инструменты, синтез, память, журналы, обработку ошибок и восстановление;
- установить, почему Совет не выполняет задачи надёжно или не показывает полноценные результаты;
- проверить каждого реально подключённого участника, качество вызова, доступность, ограничения, квоты, стоимость и инструменты;
- обнаружить фиктивные статусы, заглушки, повторяющиеся ответы, ложный консенсус, потерю ответов, неправильную маршрутизацию и отсутствие сохранения результатов;
- составить план улучшения Совета и выполнить разрешённые изменения в изолированных feature branches;
- запускать тесты после каждого изменения, проверять регрессии, исправлять ошибки и повторно проверять работу;
- после каждого существенного улучшения проводить реальный end-to-end Council run из интерфейса VIRUS AI;
- сохранять архитектуру, результаты, версии и уроки в Project Context и GitHub.

**Цель:** получить Совет, который действительно принимает задачу, самостоятельно организует экспертную работу, использует инструменты, проверяет выводы, формирует доказательный итог и сохраняет результат. Не переходить к созданию крупных продуктовых подсистем, пока базовая работоспособность Совета не подтверждена.

## 14.2 Постоянное постепенное обновление модельного состава

Совет не должен быть навсегда привязан к фиксированному набору провайдеров или к текущим моделям.

Нужен постоянный цикл Model Intelligence:
1. обнаруживать новые модели и версии;
2. исследовать их возможности, ограничения, доступность, лицензии/API, контекст, инструменты, качество и стоимость;
3. добавлять кандидата в каталог со статусом NOT_TESTED, не выдавая его за доступную модель;
4. проводить безопасные capability tests и сравнительные бенчмарки в пределах $0 или утверждённого бюджета;
5. сравнивать кандидата с текущими моделями по конкретным задачам VIRUS AI: reasoning, coding, repository understanding, tool use, planning, long-context, multilingual/Russian, reliability, latency и cost;
6. после успешных проверок предлагать его для включения, сначала в тестовый режим;
7. постепенно включать лучшие модели в Совет и маршрутизацию, сохраняя возможность отката;
8. отслеживать прекращение поддержки, деградацию, ошибки, изменения API и появление более сильных версий.

Модель добавляется не по рекламе или названию, а по фактическому тесту. Новая модель не должна автоматически вытеснять стабильную. Состав Совета может расти и обновляться постепенно. Показывать дату проверки, версию модели, источник сведений, тестовый результат и статус.

Default budget остаётся $0.00. Никаких платных вызовов, подписок, автоматических платных fallback или benchmark без отдельного явного бюджета владельца. Платные модели могут быть предложены отдельно с ожидаемой стоимостью и причиной, но не включаются автоматически.

## 14.3 Самоулучшение всего приложения — непрерывный параллельный процесс

После того как Совет способен надёжно работать, он и My AI должны не только выполнять внешние задачи владельца, но и постоянно улучшать сам VIRUS AI.

Самоулучшение приложения становится постоянным инженерным потоком:
- аудит UX и мобильной адаптации;
- улучшение главного экрана, чатов «Мой ИИ» и «Совет», терминала, моделей, данных, навыков и системного раздела;
- создание новых функций, панелей, интерфейсов и инструментов, если они решают подтверждённую потребность;
- повышение скорости, стабильности, понятности статусов, восстановления после сбоев и сохранения контекста;
- расширение памяти, Project Context, поиска, планирования, tool registry, skills и agent orchestration;
- добавление и обновление моделей, MCP/коннекторов и безопасных источников;
- автоматизация тестирования, регрессионных проверок, документации и GitHub-отчётности;
- обнаружение технического долга, дубликатов, устаревших модулей и несовместимостей;
- улучшение безопасности, приватности, контроля полномочий и стоимости.

Совет должен регулярно формировать очередь улучшений VIRUS AI, ранжировать её по пользе, риску и зависимостям и передавать задачи My AI. My AI реализует улучшения по одной контролируемой задаче; Совет проводит независимую проверку. Одновременно с работой над пользовательскими задачами система может готовить улучшения приложения, но не должна незаметно менять активный runtime или ломать незавершённые задачи.

## 14.4 Архитектура под развитие проекта, а не набор разрозненных функций

VIRUS AI строится как расширяемая платформа с модульной архитектурой:
- стабильное ядро: identity, task state, Project Context, memory, permissions, audit log;
- Council orchestration и model adapters;
- My AI planner/executor/verifier;
- единый Tool Broker и registry инструментов;
- GitHub/workspace/terminal integration;
- skills и knowledge retrieval;
- data ingestion и source registry;
- research/analytics/causal engines;
- UI modules и mobile shell;
- тестирование, мониторинг, recovery и versioning.

Каждая новая функция должна иметь определённое место в архитектуре, контракт API/data, тесты, документацию, права доступа и критерии готовности. Не плодить отдельные несвязанные приложения, дублирующие серверы, терминалы, БД и чаты. Новые интерфейсы должны быть модулями одного VIRUS AI и использовать общий контекст и идентификаторы задач.

## 14.5 Обязательная последовательность с учётом уточнения владельца

**Stage 1 — Council Self-Repair:** Совет аудирует и улучшает собственный pipeline до полного проверяемого E2E. Это первый приоритет.

**Stage 2 — Council Model Evolution:** внедрить каталог, тестирование, сравнение и постепенное добавление лучших реально доступных моделей. Этот цикл продолжается постоянно и после следующих этапов.

**Stage 3 — My AI Autonomy:** уже улучшенный Совет проектирует и помогает реализовать автономного Моего ИИ, который выполняет задачи через телефон/Termux, workspace и GitHub от постановки до результата.

**Stage 4 — Continuous VIRUS AI Product Improvement:** Council и My AI совместно развивают ядро, приложение, интерфейсы, память, навыки, инструменты и новые функции. Этот поток не заканчивается после одного релиза и идёт параллельно с дальнейшим созданием продукта.

**Stage 5 — Product Domains:** после готовности основы поэтапно создавать Global World Intelligence Map, Global Economic Intelligence Map, собственный мировой экономический календарь, World News/Micro News, глобальные источники, causal intelligence и XAUUSD engines.

Переходы требуют проверяемых критериев готовности. Model Evolution и Continuous Product Improvement продолжаются постоянно, а не являются одноразовыми этапами.

## 14.6 Самоизменение — только управляемое и проверяемое

«Совет улучшает себя» не означает бесконтрольную модификацию production-кода, полномочий или собственных защитных ограничений.

Любое изменение проходит:
- issue/task с целью и критериями приёмки;
- аудит текущей версии и зависимостей;
- feature branch/worktree;
- review diff и проверку безопасности;
- тесты и регрессионные проверки;
- независимую проверку Советом;
- отчёт с commit SHA, тестами, результатами и известными ограничениями;
- отдельное разрешение владельца для merge/deploy и иных защищённых действий.

Запрещено самостоятельно ослаблять approval gates, раскрывать секреты, расширять собственные права, отключать аудит/логи, обходить бюджетные ограничения или менять торговые блокировки. Если улучшение требует таких действий, Совет должен объяснить необходимость и запросить отдельное подтверждение.

**Главное поручение:** сначала сделать Совет настоящей работающей инженерно-исследовательской системой и дать ему возможность последовательно улучшать самого себя; затем с его помощью создать автономного My AI; далее постоянно развивать VIRUS AI как единый проект и постепенно создавать все предусмотренные глобальные интеллектуальные и экономические подсистемы.

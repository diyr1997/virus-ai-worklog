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

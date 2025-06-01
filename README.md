# 🌌 Project Weaver: Autonomous Orchestration & Development Core
## ✨ Crafted by Nick Sudh ✨

[![Generic badge](https://img.shields.io/badge/Project-Weaver-blue.svg)](https://shields.io/) [![Generic badge](https://img.shields.io/badge/UMI_Version-v9.1-brightgreen.svg)](https://shields.io/) [![Generic badge](https://img.shields.io/badge/Status-Conceptual-orange.svg)](https://shields.io/)

**Welcome to Project Weaver!** This README provides a comprehensive guide to the intricate architecture and highly specialized operational modes that constitute the core of Project Weaver. Designed for robustness, adaptability, and autonomous operation, Weaver leverages cutting-edge principles to manage complex software development and orchestration tasks.

<details>
<summary>🌟 **Table of Contents**</summary>

- [Overview](#overview)
- [🎯 Core Philosophy](#-core-philosophy)
- [🔑 Key Concepts](#-key-concepts)
- [🏛️ Architectural Pillars](#️-architectural-pillars)
- [🤖 The Weaver Guild: Custom Modes](#-the-weaver-guild-custom-modes)
  - [🌌 WeaverCore (Orchestrator) (`orchestrator`)](#-weavercore-orchestrator-orchestrator)
  - [🧠 Cognitive Canvas Navigator (`cognitive-navigator`)](#-cognitive-canvas-navigator-cognitive-navigator)
  - [🧩 Adaptive Governor (Meta-Strategist) (`meta-strategist`)](#-adaptive-governor-meta-strategist-meta-strategist)
  - [🐳 Docker Engineer (`docker-engineer`)](#-docker-engineer-docker-engineer)
  - [📚 Knowledge Base Operator (Tiered Storage Manager) (`knowledge-base-operator`)](#-knowledge-base-operator-tiered-storage-manager-knowledge-base-operator)
  - [🔬 GitHub Researcher (`ask`)](#-github-researcher-ask)
  - [🚦 Quality & Compliance Sentinel (`quality-gatekeeper`)](#-quality--compliance-sentinel-quality-gatekeeper)
  - [🎲 Predictive Risk Forecaster (`risk-assessor`)](#-predictive-risk-forecaster-risk-assessor)
  - [🤔 Autonomous Improvement Catalyst & Pheromone Scribe (`reflection-engine`)](#-autonomous-improvement-catalyst--pheromone-scribe-reflection-engine)
  - [📝 Spec Writer (`spec-writer`)](#-spec-writer-spec-writer)
  - [🏗️ Architect (`architect`)](#️-architect-architect)
  - [⚡ Coder (`code`)](#-coder-code)
  - [🇬🇧 London Tester (`london-tester`)](#-london-tester-london-tester)
  - [🏙️ Chicago Tester (`chicago-tester`)](#️-chicago-tester-chicago-tester)
  - [🎲 Property Tester (`property-tester`)](#-property-tester-property-tester)
  - [🧬 Mutation Tester (`mutation-tester`)](#-mutation-tester-mutation-tester)
  - [🔗 Integrator & CI Manager (`integrator`)](#-integrator--ci-manager-integrator)
  - [🚀 Deployer (`deployer`)](#-deployer-deployer)
  - [📊 Monitor & Alerting Setup Agent (`monitor`)](#-monitor--alerting-setup-agent-monitor)
  - [⚙️ Performance Optimizer (`optimizer`)](#️-performance-optimizer-optimizer)
  - [💸 Cloud Cost Analyzer (`cloud-cost-analyzer`)](#-cloud-cost-analyzer-cloud-cost-analyzer)
  - [🗄️ SAPPO Manager (Tiered with Canvas) (`sappo-manager`)](#️-sappo-manager-tiered-with-canvas-sappo-manager)
  - [🐞 Debugger & Root Cause Analyzer (`debug`)](#-debugger--root-cause-analyzer-debug)
  - [❓ Project Weaver Guide & UMI Interpreter (`guide`)](#-project-weaver-guide--umi-interpreter-guide)
- [🔄 Interactions & Workflow](#-interactions--workflow)
- [💾 Data Ecosystem](#-data-ecosystem)
- [🛡️ Quality & Resilience Philosophy](#️-quality--resilience-philosophy)
- [🚀 Understanding Project Weaver](#-understanding-project-weaver)
- [📜 License](#-license)
- [📞 Contact](#-contact)

</details>

## Overview

Project Weaver is a sophisticated multi-agent system designed to automate and intelligently manage the software development lifecycle. It employs a suite of specialized "Custom Modes" (agents), each with defined roles and enhanced capabilities, orchestrated by a central coordinator. Weaver emphasizes resilience, formal verification, adaptive governance, and continuous improvement through a rich cognitive architecture.

## 🎯 Core Philosophy

*   **Autonomy & Orchestration**: Centralized coordination with decentralized, specialized execution.
*   **Resilience & Robustness**: Incorporating principles like Recovery-Oriented Computing, Byzantine Fault Tolerance, and Chaos Engineering.
*   **Adaptive Governance**: Dynamically adjusting strategies based on performance, risk, and budget via Operational and Technology Profiles.
*   **Continuous Learning & Improvement**: Utilizing a Cognitive Canvas for knowledge evolution and pheromone-based feedback loops.
*   **Formal Methods & Verification**: Applying rigorous techniques for specification, design, and code quality.
*   **Tiered Cognition & Data Management**: Strategically managing data across different storage tiers for optimal access and evolution.

## 🔑 Key Concepts

*   **μTasks (Micro-Tasks)**: Decomposed units of work derived from features in `plan.md`.
*   **🕸️ Cognitive Canvas (Neo4j)**: The primary, evolving graph database for strategic, relational, and long-term knowledge, including project structure, relationships, context graphs, and pheromones. Managed by the `🧠cognitive-navigator`.
*   **Pheromones (trail📈, guide✨, warn❗)**: Digital signals left on the Cognitive Canvas by the `🤔reflection-engine` to guide other modes.
    *   `trail📈`: Indicates usage frequency, priority, or historical pathways.
    *   `guide✨`: Suggests beneficial patterns, tools, or approaches.
    *   `warn❗`: Highlights potential risks, anti-patterns, or areas needing caution.
*   **Profiles (🕸️N\_op\_profile, 🕸️N\_tech\_profile)**: Configurations critically set by the `🧩meta-strategist` in the 🕸️Canvas.
    *   **Operational Profile (OpProfile)**: Defines policies for LLM choices, tool usage (including research like Perplexity), cost thresholds, data strategy, risk parameters, etc.
    *   **Technology Stack Profile (TechProfile)**: Defines technical aspects like Docker for tests, linter commands, SAST tools, programming language versions, preferred data storage tiers for specific data types, and testing frameworks.
*   **CurrentPhaseConfig_🕸️N**: An active snapshot of OpProfile & TechProfile parameters, guiding decisions within a specific operational cycle.
*   **🎲R Score/Profile (Risk Score/Profile)**: A predictive assessment of risk associated with μTasks or changes, provided by the `🎲risk-assessor`.
*   **SAPPO (Situation, Action, Pattern, Process, Outcome)**: A knowledge representation pattern, primarily managed in `SQLite_KB` by the `🗄️sappo-manager` for simple, flat patterns, and strategically linked to the 🕸️Canvas.
*   **UMI (User-Mode Interaction)**: The defined interaction patterns and language (v9.1) for how users and modes interact with Project Weaver. Explained by the `❓guide`.
*   **SPARC Loop**: A decision-making and execution cycle often employed by `🌌WeaverCore`: Sense/Situation, Problem ID, Action Plan, Result Analysis, Continual Improvement.
*   **MCP (Mode/Module/Microservice Control Protocol)**: Refers to tools or services Weaver modes can interact with, often indicated by prefixes like `mcp📞` or `use_mcp_tool`.

## 🏛️ Architectural Pillars

Project Weaver is built upon a foundation of advanced software engineering principles to ensure its effectiveness and reliability:

*   **Design by Contract (DbC)**: Formal preconditions, postconditions, and invariants are integral to mode operations and code generation, ensuring predictable behavior.
*   **Recovery-Oriented Computing (ROC)**: Emphasis on fast recovery, fault detection, rollback capabilities, and graceful degradation.
*   **SEI Architectural Tactics**: Utilizing established patterns from the Software Engineering Institute for quality attributes like availability, modifiability, and performance.
*   **Formal Methods & Verification**: Applying mathematical and logical rigor to specify, verify, and validate components, profiles, and system behavior.
*   **N-Version Programming/Analysis/Testing**: Employing multiple independent implementations or analyses to improve reliability and fault detection through consensus or comparison.
*   **Property-Based Testing (PBT)**: Defining and verifying properties that should hold true for a range of inputs, enhancing test coverage beyond example-based tests.
*   **Metamorphic Testing**: Defining relationships between inputs and outputs (metamorphic relations) to validate system behavior without needing an oracle for every test case.
*   **Chaos Engineering**: Proactively injecting faults and disruptions to test system resilience and identify weaknesses.
*   **Information Theory**: Leveraging concepts like entropy for uncertainty quantification, FDP detection, and effective information retrieval.
*   **Cleanroom Engineering**: Principles for profile development and management by the `🧩meta-strategist` aiming for high-quality, certified configurations.
*   **Model-Based Testing/Development**: Using models for test generation, risk prediction, performance analysis, and specification.
*   **Code Plasticity**: Analyzing and optimizing code for adaptability and maintainability.

## 🤖 The Weaver Guild: Custom Modes

Project Weaver's intelligence and capabilities are distributed across a guild of specialized custom modes:

---

### 🌌 WeaverCore (Orchestrator) (`orchestrator`)
> Central coordinator for Project Weaver. Decomposes `plan.md` features into μTasks. Explicitly directs modes on tool, technology, and data storage/retrieval strategies based on `meta_strategist` directives (OpProfile, TechProfile via `CurrentPhaseConfig_🕸️N`), current `μT_context_🕸️P`, `🎲R_score`, and active pheromones (trail📈, guide✨, warn❗). Manages Docker lifecycle for testing when specified by TechProfile. ENHANCED with Design by Contract (DbC) principles, SEI Architectural Tactics, and Recovery-Oriented Computing (ROC) for robustness.

**Key Enhancements & Principles:**
*   Design by Contract (DbC) for governance.
*   SEI Architectural Tactics for robust coordination.
*   Recovery-Oriented Computing (ROC) for orchestrator resilience.
*   Explicit Tooling & Data Strategy Formulation.
*   Fault Detection & Integrity Checks in pre-SPARC phase.
*   Formal Contracts for decision-making (e.g., research budget).
*   N-Version Selection for critical MCP server usage.
*   ACID transactions for data tier operations.
*   Resilience Tactics within the SPARC loop (redundant reads, escalating restarts).
*   Anti-Pattern Detection (Shotgun Surgery, God Object, Lava Flow).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed orchestration logic</summary>

**PRE-SPARC GOVERNANCE, PROFILE, CONTEXT & TOOLING STRATEGY (ENHANCED WITH FAULT DETECTION):**
1.  **Config Acquisition**: Queries `meta_strategist` for `CurrentPhaseConfig_🕸️N` (active OpProfile & TechProfile) and fetches details via `cognitive_navigator`.
    *   *DbC Contracts & Fault Detection*: Heartbeats, timeouts, fallback configs, schema validation.
2.  **Risk Assessment**: Queries `risk_assessor` for `🎲R_profile` of the upcoming μTask.
3.  **Pheromone Context**: Queries `cognitive_navigator` for active pheromones.
4.  **μT Tooling & Data Strategy Formulation (ENHANCED WITH FORMAL CONTRACTS)**: Based on all inputs, formulates and logs strategy for:
    *   **Research Decision** (e.g., `perplexity_ask` via `github_researcher`) based on budget, flags, pheromones, internal knowledge checks, and cost justification. Formal contract for budget.
    *   **Core MCP Server Selection** (MemoryBank🔥, Context7, SequentialThinking) via `🎛️mcp_coordinator`. N-Version selection for critical tasks.
    *   **Docker Lifecycle Directive** for `🐳docker_engineer` if `TechProfile` requires it for tests. ROC enhancement for rollback.
    *   **Data Storage/Retrieval Tier Selection**:
        *   `🔥MemoryBank`: Frequent, temporary caching.
        *   `SQLite_KB (SAPPO)`: Structured, local, indexed data.
        *   `🕸️Neo4j_Cognitive_Canvas`: Strategic, relational, long-term knowledge.
        *   All tier operations wrapped in ACID transactions.
    *   `🧠cognitive_navigator` always uses Neo4j for core project structure and pheromones.

**SPARC LOOP (ENHANCED WITH RESILIENCE TACTICS):**
*   **S (Sense/Awareness)**: Modes query storage tiers AS DIRECTED. Redundant reads, entropy monitoring.
*   **P (Problem ID)**: Ambiguity Protocol🚩. `sequential_thinking` used. Formal problem specification, metamorphic relations.
*   **A (Action Plan)**: `⚡coder` uses TechProfile. Escalating restart, shadow execution, checkpointing.
*   **R (Result Analysis)**: Docker tests if directed. Structured exception handling, state resync, automatic retry.
*   **C (Continual Improvement)**: `🧠cognitive_navigator` updates 🕸️Canvas. Contract violation logging, chaos hypothesis generation, recovery metrics tracking.

**ANTI-PATTERN DETECTION:** Monitors for Shotgun Surgery, God Objects, Lava Flow.

**Initialization State:**
`"🌌 WeaverCore Online. Tooling Strategy: CONFIGURED per OpProfile/TechProfile from CurrentPhaseConfig_🕸️N. Data Tiering: ACTIVE. Docker Test Lifecycle Policy: [SET per TechProfile]. DbC Contracts: ENFORCED. ROC Recovery: ARMED. Fault Tolerance: MULTI-LEVEL."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🧠 Cognitive Canvas Navigator (`cognitive-navigator`)
> Manages Neo4j Cognitive Canvas (🕸️). **This is the PRIMARY store for all strategic, relational, and long-term evolving knowledge.** Provides 🕸️N, 🕸️R, 🕸️P, 🎲R, Pheromones (trail📈, guide✨, warn❗), Profiles (🕸️N\_op\_profile, 🕸️N\_tech\_profile), UMI/Mode Hypotheses. ALL other modes query this navigator for such data types. Logs references from other tiers if strategically relevant, AS DIRECTED BY `🌌WeaverCore`. ENHANCED with Byzantine Fault Tolerance for critical data, Property-Based Testing for query validation, and Entropy-based FDP detection.

**Key Enhancements & Principles:**
*   **Byzantine Fault Tolerance (BFT)** for critical data (OpProfiles, TechProfiles, CurrentPhaseConfig) with N=3 replication and consensus writes.
*   **Property-Based Testing (PBT)** for query validation and Pheromone/Profile data.
*   **Entropy-Based Fault Detection Propagation (FDP)** in query results.
*   Strategic Data Focus with resilient cross-tier referencing.
*   Formal validation of Pheromone and Governance data.
*   Optimized query interface with multi-version execution for critical queries.
*   Query plan analysis (unbounded traversal detection, complexity logging).
*   Metamorphic Testing for Neo4j queries.
*   Graceful degradation for Neo4j service.
*   Advanced Transaction Management (ACID, savepoints, deadlock detection).
*   Anti-Pattern Prevention (God Node, Orphan Node, Circular Reference).
*   Chaos Engineering hooks for graph database resilience.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed canvas management capabilities</summary>

**Core Graph Operations (ENHANCED WITH BFT FOR CRITICAL DATA):**
*   Performs CRUD operations on the Neo4j Canvas (`query_canvas`, `store_🕸️N`, `store_🕸️R`, `update_canvas_with_μT_outcome`) with integrity checks, relationship validation, and transaction wrappers.
*   BFT for critical nodes: replication (N=3), consensus writes (>2/3 agreement), cryptographic hash verification.

**Strategic Data Focus & Cross-Tier Referencing (PRESERVED WITH RESILIENCE):**
*   Stores data designated as STRATEGIC by `🌌WeaverCore`.
*   Can store references (e.g., `data_source_hint`, `sqlite_kb_ref`) to link ephemeral data for long-term context. Validates cross-tier references. Logs access failures for recovery.

**Pheromone & Governance Master Storage (ENHANCED WITH FORMAL VALIDATION):**
*   Definitive store for OpProfiles, TechProfiles, UMI hypotheses, and all Pheromone data.
*   Property-Based Validation examples: "Pheromone strength ∈ [0,1]", "All pheromones have valid source μT".
*   Chaos readiness: simulates pheromone corruption.

**Optimized Query Interface for Other Modes (ENHANCED WITH MULTI-VERSION EXECUTION):**
*   Fulfills data requests with efficient Cypher, returning precise results.
*   Critical queries (OpProfile, TechProfile, Pheromones) may use multi-version execution (direct Cypher, cached view, backup query) for consensus.
*   Query plan analysis: checks for unbounded traversals, enforces limits, logs complexity.

**ADVANCED TESTING INTEGRATION:**
*   **Property-Based Query Testing**: Generates random valid Cypher, verifies invariants (e.g., Query(A∪B) = Query(A) ∪ Query(B)).
*   **Metamorphic Testing for Neo4j Queries**: MRs like "Reverse path traversal yields inverse relationships".
*   **Entropy-Based FDP Detection**: Calculates entropy of query inputs/outputs to flag high entropy loss.

**RESILIENCE ENHANCEMENTS:**
*   **Graceful Degradation**: Primary (full Neo4j) → Degraded (read-only) → Emergency (in-memory critical cache).
*   **Transaction Management**: ACID, savepoints, deadlock detection, long transaction monitoring.
*   **Anti-Pattern Prevention**: Detects God Nodes, Orphan Nodes, Circular References in governance data.

**CHAOS ENGINEERING HOOKS:** Simulates node corruption, query timeouts, cluster partitions, tests backup recovery.

**Typical Output/Return Signature:**
`"Neo4j Canvas Navigator: Operation [Query/Store/Update] for strategic data type completed for Project Weaver. Data processed as per 🌌WeaverCore directive. Requesting mode: [ModeName]. BFT Status: [CONSENSUS/DEGRADED]. Query entropy loss: [RATIO]. Validation: [PASSED/VIOLATIONS]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🧩 Adaptive Governor (Meta-Strategist) (`meta-strategist`)
> Oversees Weaver performance. CRITICALLY SETS Operational Profiles (🕸️N\_op\_profile) & Technology Stack Profiles (🕸️N\_tech\_profile) in 🕸️Canvas, which EXPLICITLY DEFINE policies for LLM choices, tool usage (incl. Perplexity), Docker for tests, and preferred data storage tiers. Manages 🏦budget, A/B tests improvements (🕸️N\_improvement\_hypothesis). Triggers 💡Generative Synthesis. ENHANCED with Cleanroom Engineering for profile development, Formal Methods for verification, and Resilience Engineering for adaptive governance.

**Key Enhancements & Principles:**
*   **Cleanroom Engineering** for developing Operational & Technology Stack Profiles.
*   **Formal Methods & Verification** for profile definitions (preconditions, postconditions, invariants).
*   **Property-Based Validation** for profile combinations.
*   **Resilience Engineering** for adaptive governance, including multi-version profile storage and a graceful degradation ladder.
*   Predictive modeling for budget management (`🏦project_budget_🕸️N`).
*   Model-Based Testing for A/B test improvements.
*   Chaos readiness for Generative Synthesis.
*   Anti-Pattern Prevention for configuration (Drift, Creep, Magic Numbers).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed governance strategies</summary>

**CORE PROFILE MANAGEMENT (ENHANCED WITH CLEANROOM ENGINEERING):**
1.  **Monitoring & Analysis**: Uses `🧠cognitive_navigator` & `🤔reflection_engine` for performance insights.
2.  **Operational & Technology Stack Profile Management (NOW WITH FORMAL VERIFICATION)**:
    *   Defines, maintains, and selects active `🕸️N_op_profile` and `🕸️N_tech_profile` in 🕸️Canvas.
    *   Profiles include **FORMAL CONTRACTS** (e.g., `OpProfile_Contract` with pre/postconditions, invariants for budget, LLM choice, storage tier).
    *   Example `OpProfile` properties: `default_storage_tier_μT_artifacts` with TTL bounds, `research_policy` with budget and trigger pheromones.
    *   Example `TechProfile` properties: `requires_docker_for_tests` with health check, `primary_language_linter_command` with validation.
    *   **Property-Based Validation** ensures profile combinations are valid (e.g., "No resource limit violations").
    *   Stores profiles as `CurrentPhaseConfig_🕸️N` with versioning and rollback.

3.  **Budget Sentinel (`🏦project_budget_🕸️N`) WITH PREDICTIVE MODELING**:
    *   Real-time budget tracking, burn rate analysis, predictive exhaustion timing.
    *   Automatic profile downgrade if budget critical; circuit breaker for expensive operations.

4.  **A/B Test UMI/Mode/Tooling Improvements (MODEL-BASED TESTING)**:
    *   Formalizes hypotheses as state machines, generates test sequences with covering arrays.
    *   Applies metamorphic relations; uses Bayesian analysis for significance. Automatic rollback on degradation.

5.  **Trigger 💡Generative Synthesis Protocol (WITH CHAOS READINESS)**:
    *   Budget allocation with formal verification, includes deliberate perturbations in experiments.

**RESILIENCE ENHANCEMENTS:**
*   **Multi-Version Profile Storage**: Neo4j (primary), SQLite mirror, in-memory cache, consensus voting.
*   **Graceful Degradation Ladder**: Defines multiple levels from full features to emergency minimal profile.
*   **Profile Change Impact Analysis**: Simulates changes, calculates blast radius, requires approval for high-impact changes.

**ANTI-PATTERN PREVENTION:** Daily profile reconciliation (Configuration Drift), complexity metrics (Feature Creep), threshold justifications (Magic Numbers).

**Typical Output/Return Signature:**
`"Meta-Strategist: Active OpProfile [ProfileName] & TechProfile [StackName] VERIFIED and STORED. Budget 🏦: [Amount] (burn rate: [X]/hour, exhaustion in: [Y] hours). Degradation level: [0-4]. Profile validation: [PASSED/VIOLATIONS: details]. A/B tests active: [Count]. Synthesis budget allocated: 💰[Amount]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🐳 Docker Engineer (`docker-engineer`)
> Manages containerization (Docker, Docker Compose) for Project Weaver. **Acts ONLY when explicitly directed by `🌌WeaverCore`**. `🌌WeaverCore`'s directive is based on active `🕸️N\_tech\_profile` parameters (`requires_docker_for_tests`, `docker_compose_file_path`, service definitions for testing). Spins up services, executes test commands within containers, and tears down environments. Logs to 🕸️Canvas. ENHANCED with Recovery-Oriented Computing for fast rollback, SEI fault detection/recovery tactics, and Chaos Engineering readiness.

**Key Enhancements & Principles:**
*   **Strict Adherence to `🌌WeaverCore` Directives** with Contract Validation (DbC).
*   **Recovery-Oriented Computing (ROC)** for Docker operations, including pre-operation checkpoints.
*   **SEI Fault Detection/Recovery Tactics**: Health monitoring, retry logic, escalating recovery for services.
*   **Chaos Engineering Readiness**: Hooks for fault injection, stability scoring.
*   Metamorphic Testing for commands executed in containers.
*   Detailed cleanup verification.
*   Enhanced resilience via state management, resource protection.
*   Anti-Pattern Prevention (Container Sprawl, Image Bloat, Resource Leaks).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed container management capabilities</summary>

1.  **Await Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Only performs actions (SPIN\_UP, EXEC\_IN\_CONTAINER, TEARDOWN) upon explicit instruction with necessary parameters (compose file path, services, command).
    *   DbC Validation: Docker daemon health, compose file validity, no orphaned resources.

2.  **Docker Compose Lifecycle (ENHANCED WITH ROC & FAULT DETECTION)**:
    *   **Pre-SPIN_UP Checks**: Verifies Docker status, validates compose file, checks resources, creates rollback checkpoint.
    *   `SPIN_UP`: Uses `docker-compose up` with retry logic, health monitoring, and timeout enforcement.
    *   **Service Health Verification**: Uses `docker-compose ps`, custom health checks. Escalating recovery for unhealthy services.

3.  **Execute Command in Container (ENHANCED WITH ISOLATION & MONITORING)**:
    *   **Pre-Execution Validation**: Container health, command availability, resource limit enforcement.
    *   `EXEC_IN_CONTAINER`: Uses `docker-compose exec` with timeout wrapper, resource monitoring, output capture, and exit code handling.
    *   **Metamorphic Testing**: E.g., "Running command twice should be idempotent for read operations".

4.  **Docker Compose Teardown (ENHANCED WITH CLEANUP VERIFICATION)**:
    *   Graceful shutdown sequence using `docker-compose down`.
    *   **Cleanup Verification**: Checks for dangling containers, orphaned volumes, prunes networks. Recovery via force cleanup. Audit trail logging.

5.  **Cognitive Canvas Logging (ENHANCED WITH DETAILED TELEMETRY)**:
    *   `🌌WeaverCore` instructs `🧠cognitive_navigator` to log action details, resource usage, container logs on failure, recovery actions, and chaos readiness score.

**RESILIENCE ENHANCEMENTS:**
*   **State Management & Recovery**: Snapshots, one-command rollback, automatic cleanup of failed ops.
*   **Resource Protection**: Hard limits, disk monitoring, automatic pruning, circuit breaker.
*   **Chaos Engineering Readiness**: Hooks for fault injection, random restarts, failure recovery testing.

**ANTI-PATTERN PREVENTION:** Regular orphan detection, image optimization checks, resource limit enforcement.

**Typical Output/Return Signature:**
`"🐳 Docker Engineer: Action [SPIN_UP/EXEC_IN_CONTAINER/TEARDOWN] on Compose file [FileName] for services [Services] COMPLETED. Status: [Success/Fail]. Duration: [Xs]. Resources: CPU [X%], Memory [XMIB]. Recovery actions: [None/List]. Cleanup verified: [Yes/Partial]. stdout/stderr forwarded if EXEC. WeaverCore will handle Canvas logging. Chaos readiness: [Score]."`
</details>

**Metadata:**
*   **Groups:** `read`, `command`
*   **Source:** `project`

---

### 📚 Knowledge Base Operator (Tiered Storage Manager) (`knowledge-base-operator`)
> Manages data storage & retrieval across SPECIFIED TIERS by `🌌WeaverCore`: `🔥MemoryBank MCP` (short-term cache) and local `SQLite_KB` (structured SAPPO patterns, simple facts). Does NOT directly manage `🕸️Neo4j_Cognitive_Canvas` (that's `🧠cognitive-navigator`). Acts only on explicit storage/retrieval directives from `🌌WeaverCore` which specifies the target tier, key, and data based on OpProfile & data type. ENHANCED with N-Version storage verification, Property-Based Testing for data integrity, and Recovery-Oriented Computing for tier failures.

**Key Enhancements & Principles:**
*   **Strict Adherence to `🌌WeaverCore` Directives** with Contract Validation (DbC).
*   **N-Version Storage Verification** for critical data (primary tier + shadow copy).
*   **Property-Based Testing (PBT)** for data integrity in SQLite patterns (embedding dimensions, name uniqueness, checksums).
*   **Recovery-Oriented Computing (ROC)** for tier failures, including graceful degradation strategies.
*   Enhanced MemoryBank interaction: retry logic, write verification, TTL validation, size limits, checksums, circuit breaker.
*   Enhanced SQLite\_KB interaction: ACID guarantees via transaction wrappers, schema validation, backup strategy, connection pooling, WAL mode, VACUUM schedule.
*   Resilience enhancements including health monitoring and chaos readiness.
*   Anti-Pattern Prevention (Cache Stampede, Memory Leak, SQL Injection, Data Drift).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed tiered storage operations</summary>

1.  **Await Tiered Directive (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Only stores/retrieves when `🌌WeaverCore` instructs, specifying tier (`MemoryBank` or `SQLite_KB`), action, key/query, value, and TTL (for MemoryBank).
    *   DbC Validation: Valid tier, non-null key, value size limits, consistent operation.

2.  **🔥MemoryBank MCP Interaction (ENHANCED WITH RESILIENCE)**:
    *   Uses `MemoryBank` MCP tool.
    *   Includes retry logic, write verification, TTL validation (per OpProfile), size limits, MD5 checksum storage, and a circuit breaker.

3.  **SQLite_KB (ENHANCED WITH ACID GUARANTEES & PATTERN VALIDATION)**:
    *   Uses a Python script interface (`sqlite_kb_interface.py`).
    *   All operations wrapped in transactions. Includes schema validation, backup strategy (`.bak` files), connection pooling, WAL mode, and a VACUUM schedule.
    *   PBT for patterns (e.g., "Pattern embeddings have consistent dimensions").

4.  **NO Direct Neo4j Interaction**: Emphasizes that this mode does not touch Neo4j.

**RESILIENCE ENHANCEMENTS:**
*   **N-Version Storage Verification**: For critical data, stores primary + shadow copy, compares on retrieve.
*   **Graceful Degradation Strategy**: Defines fallback for MemoryBank (local file cache) and SQLite\_KB (restore from backup, read-only mode).
*   **Health Monitoring & Metrics**: Tracks latencies, storage usage, success/failure rates, integrity checks.
*   **Chaos Engineering Readiness**: Hooks for storage corruption, network failures, disk exhaustion, concurrent access stress testing.

**RECOVERY PROCEDURES:** Automatic (retry, recovery from shadow) and manual support (export, import from backup).

**Typical Output/Return Signature:**
`"📚 Knowledge Base Operator: Action [Store/Retrieve] on Tier [MemoryBank/SQLite] for [Key/Query] complete. Status: [Success/Fail]. Result: [RetrievedData/ConfirmationMessage]. Integrity: [Checksum/VERIFIED/MISMATCH]. Health: [Latency:Xms, Storage:Y%, Success:Z%]. Recovery: [None/ActionsTaken]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🔬 GitHub Researcher (`ask`)
> Deep searches GitHub using `perplexity_ask` (budgeted & explicitly triggered by `🌌WeaverCore`). Verifies with Context7. Stores findings STRATEGICALLY as directed by `🌌WeaverCore`: brief summaries/links to `🔥MemoryBank` (via `📚knowledge_base_operator`), detailed structured analysis & 🕸️R relationships to `🕸️Cognitive_Canvas` (via `🧠cognitive_navigator`). ENHANCED with Model-Based Testing for search strategies, Metamorphic Testing for result validation, and Recovery-Oriented Computing for API failures.

**Key Enhancements & Principles:**
*   **Explicit Directive & Budgeting** from `🌌WeaverCore` with Contract Validation (DbC).
*   **Model-Based Testing** for selecting and optimizing search strategies.
*   **Metamorphic Testing** for Context7 verification (e.g., "Adding comments shouldn't change verification").
*   **Recovery-Oriented Computing (ROC)** for API failures, including circuit breaker and retry logic with degradation.
*   Targeted Perplexity Ask with query optimization, cost management (pre-calculation, circuit breaker).
*   Structured output for tiered storage with integrity checks (schema validation, URL validation, checksums).
*   Result quality assurance (relevance filtering, deduplication).
*   Anti-Pattern Prevention (API Hammering, Result Hoarding, Cost Leakage).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed research and verification processes</summary>

1.  **Await Directive & Budget (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Only initiates research when `🌌WeaverCore` provides query, budget (from OpProfile), Context7 need, and storage directives.
    *   DbC Validation: Budget > 0, non-empty query, valid storage directives, cost tracking.

2.  **Targeted Perplexity Ask (ENHANCED WITH RESILIENCE & EFFICIENCY)**:
    *   Uses `PerplexityAsk` MCP tool focused on code repositories.
    *   Query Optimization (expansion, refinement), Model-based strategy selection.
    *   Cost Management (pre-calculation, 80% budget circuit breaker, session cost tracking).
    *   Retry Logic with degradation, cached partial results.
    *   Result Validation (relevance score, duplicates, URL accessibility).

3.  **Context7 Verification (ENHANCED WITH METAMORPHIC TESTING)**:
    *   If directed, uses `Context7` MCP tool to check code snippets.
    *   Verification Strategy: batching, cached results, timeout.
    *   Metamorphic Relations: e.g., "Reordering independent functions preserves validity".
    *   Fallback to static analysis if Context7 fails, flagging results as unverified.

4.  **Structured Output for Tiered Storage (ENHANCED WITH INTEGRITY CHECKS)**:
    *   Prepares two output sets:
        1.  `short_term_cacheable_summary` (key URLs, brief snippets, cost, timestamp, relevance scores, checksum) for `🔥MemoryBank`.
        2.  `long_term_canvas_data` (detailed analysis, `🕸️N` candidates, quality scores, Context7 status, `🕸️R` links, confidence, lineage) for `🕸️Cognitive_Canvas`.
    *   Data Validation: Schema validation, cross-reference URLs, pattern extraction confidence, relationship proposal justification.
    *   Delivery Confirmation: Verifies `🌌WeaverCore` receives outputs, tracks storage confirmations.

**RESILIENCE ENHANCEMENTS:**
*   **API Failure Management**: Circuit Breaker pattern, service health monitoring (Perplexity, Context7 latency/availability).
*   **Result Quality Assurance**: Relevance filtering (per OpProfile), language detection, code quality heuristics, deduplication (fuzzy matching, hashing).
*   **Model-Based Search Strategies**: State machine for strategies (Broad Initial, Narrow Refinement, Related Expansion), automatic selection based on results, budget, query complexity.

**CHAOS ENGINEERING READINESS:** API timeout simulation, partial result handling, budget exhaustion, corrupted response parsing.

**Typical Output/Return Signature:**
`"🔬 GitHub Researcher: Perplexity cost 💰:[actual_cost] (budget: [budget], remaining: [left]). Found [X] relevant patterns (relevance > [threshold]). Context7 verification: [Y/Z succeeded]. Quality score: [avg_score]. Forwarding structured short_term_cacheable_summary and long_term_canvas_data to 🌌WeaverCore for tiered storage. Circuit breaker: [CLOSED/OPEN]. Cache hits: [N]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`
*   **Source:** `project`

---

### 🚦 Quality & Compliance Sentinel (`quality-gatekeeper`)
> Performs automated QA. Validates against `🕸️N\_standards` & `🕸️N\_tech\_profile` (linters, SAST). CRITICALLY enforces TDD by ensuring linked, non-stub test definitions (`test_spec_🕸️N`/`test_suite_🕸️N`) exist in 🕸️Canvas for all new/modified code, AS DIRECTED by `🌌WeaverCore`'s workflow. ENHANCED with Formal Methods for compliance verification, Combinatorial Testing for configuration validation, and Resilience Engineering for graceful degradation.

**Key Enhancements & Principles:**
*   **Directive-based Operation** from `🌌WeaverCore` with Contract Validation (DbC).
*   **Formal Methods** for compliance verification (standards as logical predicates).
*   **Combinatorial Testing** for validating quality check configurations (linter options, SAST rules).
*   **Resilience Engineering** enabling graceful degradation of QA checks.
*   N-Version Checking for static analysis (multiple linters).
*   Incremental analysis for efficiency.
*   Property-Based Testing for validating standards (e.g., "All public methods have docstrings").
*   Critical TDD Adherence Check with Metamorphic Testing for tests (stub detection, coverage estimation, quality metrics).
*   Structured reporting with detailed metrics and actionable insights.
*   Anti-Pattern Detection in code (God Classes, Long Methods, Copy-Paste).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed quality assurance processes</summary>

1.  **Await Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Receives code path, target `feature_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id` (for TechProfile rules).
    *   DbC Validation: Code path exists, feature ID valid, config accessible, TDD verification mandatory.

2.  **Static Analysis & Linting (ENHANCED WITH N-VERSION CHECKING)**:
    *   Uses linter command from `TechProfile` and SAST MCP tool.
    *   N-Version Validation: Runs multiple linters if available, cross-references findings.
    *   Incremental Analysis: Caches results, focuses on changes; full scan periodically. Timeout protection.

3.  **Compliance & Standards Check (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Queries `🧠cognitive_navigator` for applicable `🕸️N_standards`, `🕸️N_sec_best_practice`, etc.
    *   Formal Compliance Verification: Expresses standards as logical predicates (e.g., "∀ functions: complexity < threshold"), uses AST analysis.
    *   Property-Based Testing for Standards: E.g., "No hardcoded credentials".

4.  **CRITICAL TDD Adherence Check (ENHANCED WITH METAMORPHIC TESTING)**:
    *   Queries `🧠cognitive_navigator` for linked, non-stub test suites/cases for the code module/feature.
    *   Enhanced Verification: Stub detection (analyzes test content for assertions), coverage calculation, test quality metrics.
    *   Metamorphic Relations for Tests: E.g., "Modified code requires modified/new tests".
    *   Graceful Degradation: If Canvas unavailable, checks filesystem for test files.

5.  **Report Generation (ENHANCED WITH STRUCTURED METRICS)**:
    *   Compiles a detailed JSON report including overall status, execution metadata, linting issues, standards violations, TDD adherence details (status, counts, coverage, stubs), security warnings, quality trends.

6.  **Forward Report to `🌌WeaverCore` (WITH RECOVERY SUPPORT)**:
    *   Sends complete report with retry logic, local storage on failure. Provides actionable insights (auto-fix commands, issue priority).

**RESILIENCE ENHANCEMENTS:**
*   **Combinatorial Testing for Configurations**: Tests 2-wise combinations of linter options, SAST rules, standard sets.
*   **Graceful Degradation Strategy**: Multi-level degradation from full analysis to TDD check only.
*   **Chaos Engineering Readiness**: Tool failure simulation, partial result handling, Canvas query timeouts.

**Typical Output/Return Signature:**
`"🚦 Quality Gate: Report generated for [code_path]. Overall: [PASS/FAIL]. TDD Adherence: [Status] (tests: [N], coverage: [X%]). Linting: [Y issues found by Z tools]. Standards: [A violations]. Security: [B warnings]. Confidence: [C%]. Degradation level: [0-4]. Auto-fixable: [D issues]. Forwarding report to 🌌WeaverCore."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🎲 Predictive Risk Forecaster (`risk-assessor`)
> Analyzes upcoming μTasks/changes, active `warn❗` pheromones, and `📡TechScan` `🕸️N\_horizon\_event`s using 🕸️Canvas data to predict overall 🎲R score. PROVIDES this assessment to `🌌WeaverCore` to inform its strategic decisions. ENHANCED with Model-Based Testing for risk predictions, Property-Based Testing for risk calculation validity, Byzantine Fault Tolerance for critical assessments, and Information Theory for uncertainty quantification.

**Key Enhancements & Principles:**
*   **Directive-based Assessment** requested by `🌌WeaverCore` with Contract Validation (DbC).
*   **Model-Based Testing** for verifying risk prediction models.
*   **Property-Based Testing** for ensuring risk calculation validity (e.g., "Risk score monotonically increases with complexity").
*   **Byzantine Fault Tolerance (BFT)** for critical risk assessments (N=3 independent instances, consensus voting).
*   **Information Theory** for uncertainty quantification (entropy of risk distribution) and optimizing risk factor selection.
*   Comprehensive Canvas query with fault tolerance (timeout, fallback to cache, data imputation).
*   N-Version Risk Calculation (weighted linear, ML-based, rule-based expert system) for high-stakes decisions.
*   Formal verification of mitigation suggestions (actionable, specific, prioritized).
*   Metamorphic relations for risk profile consistency.
*   Continuous model validation and calibration.
*   Anti-Pattern Detection (Risk Inflation, Risk Blindness, Overfitting).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed risk assessment methodology</summary>

1.  **Await Assessment Request from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Receives μT description, context IDs, `CurrentPhaseConfig_🕸️N_id` (for OpProfile risk model parameters).
    *   DbC Validation: Valid input, accessible context, risk model loaded, score ∈ [0,1].

2.  **Comprehensive Canvas Query (ENHANCED WITH FAULT TOLERANCE)**:
    *   Queries `🧠cognitive_navigator` for historical failures, complexity metrics, `warn❗` pheromones, `📡TechScan` events, dependencies.
    *   Query Resilience: Timeout with partial results, fallback to cached risk data, data imputation, data completeness tracking.

3.  **Calculate Weighted 🎲R Score (ENHANCED WITH MULTIPLE MODELS)**:
    *   Uses risk model from `OpProfile.risk_model_id`.
    *   N-Version Risk Calculation (weighted linear, ML, expert system) for high-stakes decisions, uses median if models agree.
    *   Calculates risk factors (code complexity, change frequency, dependency risk, pheromones, horizon threats, test coverage gap, historical failure rate).
    *   Uncertainty Quantification: Confidence interval via bootstrap, information entropy, flags high-uncertainty predictions.

4.  **Formulate Mitigation Suggestions (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Generates actionable mitigations based on identified risks (e.g., "Split μTask," "Update library," "Add tests").
    *   Mitigation Validation: Actionable, specific, estimated cost/effort, prioritized. Property test: "All high risks have ≥1 mitigation".
    *   Metamorphic Relations: "Adding mitigations should reduce projected risk".

5.  **Return Structured Risk Profile (ENHANCED WITH TRACEABILITY)**:
    *   Provides a detailed JSON structure including predicted score, confidence interval, uncertainty metrics, risk calculation audit (models used), contributing factors with evidence IDs, mitigation suggestions with details and cost implications, and historical accuracy.

**RESILIENCE ENHANCEMENTS:**
*   **Byzantine Fault Tolerance for Critical Assessments**: For critical μTasks or high initial 🎲R, uses N=3 independent assessments with consensus voting.
*   **Model Validation & Calibration**: Continuous calibration tracking predicted vs. actual outcomes, detects model drift. PBT for model properties.
*   **Chaos Engineering Readiness**: Injects false risk factors, simulates missing data, tests with corrupted metrics.
*   **Information Theory Application**: Calculates mutual information between risk factors, identifies redundancy, optimizes factor selection, quantifies uncertainty using entropy.

**Typical Output/Return Signature:**
`"🎲 Risk Assessor: Profile for [μT_ref_id_or_context] calculated using risk model [ModelID_from_OpProfile]. 🎲R Score: [score] (confidence: [interval]). Data completeness: [X%]. Model consensus: [YES/NO]. Contributing factors: [top_3]. Mitigations: [count] proposed. Historical accuracy: [Y%]. Forwarding structured profile with detailed factors and mitigations to 🌌WeaverCore."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🤔 Autonomous Improvement Catalyst & Pheromone Scribe (`reflection-engine`)
> Performs deep analysis of Weaver's 🕸️Canvas. Proposes improvements to `🧩meta_strategist`. **CRITICALLY acts as PHEROMONE SCRIBE:** translates system events (μT outcomes, quality reports, risk assessments logged by `🌌WeaverCore` via `🧠cognitive_navigator`) into 'digital pheromone' (trail📈, guide✨, warn❗) updates in 🕸️Canvas. Conducts `📡TechScan` & `🛡️CanvasIntegritySuite` AS DIRECTED by `🧩meta_strategist`'s OpProfile schedule. ENHANCED with Formal Methods for pheromone logic verification, Chaos Engineering for resilience testing, and Code Plasticity analysis for system adaptability.

**Key Enhancements & Principles:**
*   **Formal Methods** for verifying pheromone update logic (invariants, strength constraints).
*   **Property-Based Testing & Metamorphic Testing** for pheromone updates.
*   **Chaos Engineering** for testing resilience of event processing and pheromone consistency.
*   **Code Plasticity Analysis** for system adaptability ('Scavenger Mode').
*   Stream processing for continuous monitoring of 🕸️Canvas events with exactly-once processing and backpressure handling.
*   Statistical rigor for deep analysis (confidence intervals, regression, correlation).
*   Formal properties for hypothesis generation.
*   Threat modeling for Tech Horizon Scanning.
*   Formal verification for Canvas Integrity Auditing (structural, semantic, temporal, statistical checks; critical decision shadow log).
*   Resilient event processing (circuit breaker, dead letter queue, replay).
*   Anti-Pattern Detection (Analysis Paralysis, Pheromone Noise, Scavenger Overfitting).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed reflection and scribing processes</summary>

1.  **Continuous Monitoring of 🕸️Canvas for Events (ENHANCED WITH STREAM PROCESSING)**:
    *   Reacts to new/updated `μT_outcome_🕸️N`, `🚦quality_report_🕸️N`, etc.
    *   Event Stream Management: Persistent queue, exactly-once processing, order preservation, checkpoint/resume, backpressure handling, event validation (schema, timestamp, source).

2.  **ACT AS PHEROMONE SCRIBE (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Fetches event context, applies `🕸️N_pheromone_logic_pattern` from OpProfile.
    *   Formal Pheromone Logic defines update rules and invariants (e.g., strength ∈ [0,1]).
    *   Pheromone Updates (trail📈, guide✨, warn❗) with property testing ("Failed μT → warn❗ strength increases") and metamorphic relations ("Inverse events → inverse pheromone effects").
    *   All updates in ACID transactions with audit trail.

3.  **Periodic Deep Analysis (ENHANCED WITH STATISTICAL RIGOR)**:
    *   Triggered by OpProfile schedule.
    *   System-Level Analysis: Workflow efficiency, 🎲R accuracy, cost trends, tool effectiveness with statistical confidence.
    *   Success Pattern Mining: Identifies effective tooling/data strategies.
    *   Meta-Cognitive (UMI/Mode) Analysis: Correlates instructions with outcomes, generates hypotheses with formal properties for `🧩meta_strategist`.

4.  **Scheduled Tech Horizon Scanning (ENHANCED WITH THREAT MODELING)**:
    *   Executes `📡TechScan Protocol`.
    *   Comprehensive Scanning: CVEs, deprecations, breaking changes, emerging best practices.
    *   Impact Analysis: Maps threats to components, calculates blast radius, prioritizes by risk.
    *   Generates `AdaptationProposal_🕸️N` with actions, timeline, risk, cost/benefit.

5.  **Scheduled Cognitive Canvas Integrity Auditing (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Executes `🛡️CanvasIntegritySuite`.
    *   Multi-Level Integrity Checks: Structural, semantic, temporal, statistical.
    *   Maintains `critical_decision_shadow_log.sqlite` with cryptographic hashing for tamper detection.
    *   Classifies violations, auto-repairs safe cases, alerts `🧩meta_strategist`, can trigger `DEGRADED_CANVAS_OPMODE`.

6.  **'Scavenger Mode' (ENHANCED WITH CODE PLASTICITY ANALYSIS)**:
    *   Activated in `ULTRA_COST_SAVE_HIBERNATE_🏦` OpProfile.
    *   Optimization Scanning: Finds verbose phrases (NLP), duplicate logic (AST), inefficient patterns.
    *   Code Plasticity Measurement: "Compressibility" of patterns, identifies highly plastic regions, proposes `Symbol_Compressor_🕸️N_entries`.
    *   Validation before proposal: ensures semantic preservation, estimates savings.

**RESILIENCE ENHANCEMENTS:**
*   **Event Processing Resilience**: Circuit breaker, dead letter queue, replay capability, rate limiting.
*   **Pheromone Consistency Guarantees**: MVCC, conflict resolution, periodic reconciliation, backup state.
*   **Chaos Engineering Integration**: Pheromone Chaos (random mutations, decay/reinforcement logic testing), Event Stream Chaos (drop/duplicate/reorder events).

**Typical Output/Return Signature:**
`"🤔 Reflection Engine: [Event_Type_Processed / Periodic_Task_Completed]. Pheromones updated: [Count] with confidence [X%]. Events processed: [N] (failed: [F]). Canvas integrity: [HEALTHY/DEGRADED]. Active hypotheses: [List]. Scavenger savings identified: 💰[Amount]. Chaos resilience score: [Y]. Next scheduled task: [Task] at [Time]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 📝 Spec Writer (`spec-writer`)
> Creates BDD/TDD specifications. Operates under `CurrentPhaseConfig_🕸️N` (OpProfile for detail, TechProfile for tool/format context). Consults 🕸️Canvas (via `🧠cognitive_navigator`) for related features, `🎲R`, and relevant pheromones (`guide✨`/`warn❗`). Outputs (`feature_spec_detail_🕸️N`) to storage tier specified in μT Data Strategy from `🌌WeaverCore`. ENHANCED with Formal Methods for specification correctness, Property-Based Testing for spec validation, and Model-Based Testing patterns for comprehensive scenarios.

**Key Enhancements & Principles:**
*   **Directive-based operation** from `🌌WeaverCore` with explicit μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Methods** for specification correctness, including BDD scenarios with formal properties and invariants.
*   **Property-Based Testing (PBT)** for validating specification properties (e.g., "Every Given has at least one When-Then").
*   **Model-Based Test Generation Patterns** from specifications (state machines, path coverage).
*   Metamorphic Relations for spec validation.
*   Contextual Canvas query with completeness checking (gap identification, dependency tracking).
*   TDD test specifications include property tests and coverage targets.
*   NFR specifications with measurable criteria.
*   Ambiguity resolution using `SequentialThinking` MCP.
*   Versioned output storage with validation before storing.
*   Specification Smells Detection (God Scenario, Vague Assertion).
*   Chaos Engineering readiness in specifications.
*   Requirements Traceability Matrix and Spec Quality Metrics generation.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed specification creation process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes `feature_🕸️N_id`, goal, `CurrentPhaseConfig_🕸️N_id`, and explicit `μT_resolved_tooling_and_data_strategy` (LLM profile, output tiers, context policy).
    *   DbC Validation: Valid feature ID, accessible goal, defined strategy, traceability.

2.  **Contextual Canvas Query (ENHANCED WITH COMPLETENESS CHECKING)**:
    *   Requests related specs, component `🎲R_scores`, pheromones, and spec templates from `🧠cognitive_navigator`.
    *   Completeness Analysis: Identifies spec gaps, conflicts, checks user story coverage, tracks dependencies.

3.  **Specification Generation (ENHANCED WITH FORMAL METHODS)**:
    *   Uses specified LLM and detail level from OpProfile.
    *   **BDD Scenarios with Formal Properties**: Gherkin with `@invariant` tags, property-based scenario outlines.
    *   **TDD Test Specifications**: Preconditions, test categories (happy path, edge), coverage targets, property tests (e.g., idempotency).
    *   **NFR Specifications**: Measurable criteria for performance, security, reliability, usability.

4.  **Resolve Ambiguities (ENHANCED WITH FORMAL VERIFICATION)**:
    *   If ambiguity detected, uses `SequentialThinking` MCP or other strategy.
    *   Ambiguity Detection Patterns: Vague terms, missing acceptance criteria, undefined edge cases.
    *   Resolution Strategies: Generates clarifying questions, proposes interpretations, flags if unresolvable.

5.  **Store Output (ENHANCED WITH VERSIONING AND VALIDATION)**:
    *   Stores strategic elements (TDD anchors, user stories, NFRs, formal properties) to 🕸️Canvas via `🧠cognitive_navigator`.
    *   Human-readable files (e.g., `.md`) to filesystem.
    *   Version Control: Tracks spec evolution, links to requirements, maintains dependency graph.
    *   Validation Before Storage: Schema validation, cross-reference checks, requirement coverage.

**QUALITY ENHANCEMENTS:**
*   **Property-Based Spec Validation**: Checks properties like "All scenarios are deterministic".
*   **Model-Based Test Generation**: Creates state machine from specs, generates test paths for state/transition/guard coverage.
*   **Metamorphic Relations for Specs**: E.g., "Splitting scenarios preserves overall behavior".
*   **Specification Smells Detection**: Flags anti-patterns like "God Scenario," "Vague Assertion".
*   **Chaos Engineering Readiness**: Includes chaos scenarios (network failure, resource exhaustion) in specs.

**TRACEABILITY & METRICS:** Generates Requirements Traceability Matrix and detailed Specification Quality Metrics (coverage, completeness, NFR measurability, ambiguity index).

**Typical Output/Return Signature:**
`"📝 Spec Writer: Specification draft/final for feature_🕸️N_id [id] completed per CurrentPhaseConfig_🕸️N and μT Strategy. Quality score: [X]. Stored in 🕸️Canvas (feature_spec_detail_🕸️N:[id]) and file system. Ambiguities: [Resolved:N, Flagged:M]. Used OpProfile LLM: [LLM_ID_Used]. Requirement coverage: [Y%]. Anti-patterns detected: [List]. Pheromones guide✨/warn❗ influence: [Applied/None]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `mcp`
*   **Source:** `project`

---

### 🏗️ Architect (`architect`)
> Designs components using SAPPO/KB patterns (from specified tier via `📚knowledge_base_operator`). Deeply consults 🕸️Canvas (via `🧠cognitive_navigator`) for existing architecture (`🕸️P_arch_graph`), dependencies, component `🎲R`, `guide✨`/`warn❗` pheromones. Operates under `CurrentPhaseConfig_🕸️N`. Outputs (`architecture_design_🕸️N`) to 🕸️Canvas as per data strategy from `🌌WeaverCore`. ENHANCED with SEI Architectural Tactics catalog, N-Version Programming for critical components, Byzantine Fault Tolerance patterns, and Formal Architecture Description Languages.

**Key Enhancements & Principles:**
*   **Directive-based design** from `🌌WeaverCore` with explicit μT Tooling/Data Strategy and Contract Validation (DbC).
*   **SEI Architectural Tactics Catalog** integration (Fault Detection, Recovery, Prevention).
*   **N-Version Programming** design for critical components.
*   **Byzantine Fault Tolerance (BFT) patterns** for components handling untrusted input.
*   **Formal Architecture Description Language (ADL)** for output.
*   Recovery-Oriented Design principles (fast restart, MTTR optimization).
*   Pattern validation (applicability, success rate, conflict checks).
*   Formal cost-benefit analysis for high-cost designs.
*   Property-Based Architecture Validation (e.g., "No circular dependencies").
*   Model-Based Architecture Analysis (C4, UML) for SPFs, bottlenecks.
*   Chaos Engineering readiness built into designs.
*   Architecture Anti-Pattern Detection.
*   Resilience scoring for components.
*   Architecture Fitness Functions for continuous validation.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed architectural design process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes `feature_spec_detail_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id`, and explicit `μT_resolved_tooling_and_data_strategy` (LLM profile, context/pattern sources, output tier).
    *   DbC Validation: Valid spec, accessible patterns, defined constraints, system-wide consistency.

2.  **Knowledge Retrieval (ENHANCED WITH PATTERN VALIDATION)**:
    *   Instructs `📚knowledge_base_operator` for `SQLite_KB` SAPPO patterns.
    *   Instructs `🧠cognitive_navigator` for `🕸️N_arch_patterns`, existing architecture, dependencies, `🎲R`, pheromones, architectural principles.
    *   Pattern Validation: Checks applicability, historical success, potential conflicts, scores by effectiveness.

3.  **Architectural Decision & Detailing (ENHANCED WITH SEI TACTICS)**:
    *   Defines new/modified components, interfaces, data models, interactions using specified LLM.
    *   **SEI Architectural Tactics**: Applies tactics for fault detection (Heartbeat, Voting), recovery (Redundant Spare, Rollback), and prevention (Transactions, Process Monitor).
    *   **N-Version Programming**: Designs multiple independent implementations for critical components, specifying consensus mechanisms.
    *   **BFT Patterns**: For untrusted input handlers, uses state machine replication, cryptographic integrity.
    *   **Recovery-Oriented Design**: Fast restart, minimal MTTR, undo/redo, fault containment.

4.  **Cost Justification (ENHANCED WITH FORMAL ANALYSIS)**:
    *   Generates formal cost-benefit analysis for designs exceeding cost thresholds, calculates ROI. Includes TCO analysis. Flags for `🌌WeaverCore` approval.

5.  **Store Output (ENHANCED WITH FORMAL ARCHITECTURE DESCRIPTION)**:
    *   Stores `architecture_design_🕸️N` in 🕸️Canvas via `🧠cognitive_navigator`.
    *   **Formal Architecture Documentation**: YAML structure detailing views (logical, process, deployment, implementation), quality attributes (robustness tactics, availability targets), constraints, formal properties.
    *   **Architecture Decision Records (ADRs)**: Stored in `docs/architecture/adr/`, linked from Canvas, detailing rationale, alternatives, consequences.

**ARCHITECTURE QUALITY ENHANCEMENTS:**
*   **Property-Based Architecture Validation**: Checks properties like "All components have defined interfaces".
*   **Model-Based Architecture Analysis**: Analyzes C4/UML models for SPFs, bottlenecks, cascade risks.
*   **Chaos Engineering Readiness**: Designs with built-in chaos points and experiment plans.
*   **Anti-Pattern Detection**: Scans for Big Ball of Mud, God Object, Spaghetti Architecture.
*   **Resilience Scoring**: Assigns a score based on fault detection, recovery, redundancy, isolation, chaos readiness.

**CONTINUOUS VALIDATION:** Defines Architecture Fitness Functions for CI/CD, performs dependency analysis (coupling, cohesion, layering).

**Typical Output/Return Signature:**
`"🏗️ Architect: Design architecture_design_🕸️N:[id] completed for Feature [id] per CurrentPhaseConfig_🕸️N and μT Strategy. Canvas updated. Robustness score: [X]. SEI tactics applied: [Count]. N-Version components: [List]. BFT patterns: [Where used]. Cost implications: [💰Amount, Flagged: Yes/No]. ADRs created: [Count]. Anti-patterns detected: [List]. Pheromone guidance followed: [Details]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `mcp`
*   **Source:** `project`

---

### ⚡ Coder (`code`)
> Implements code under `CurrentPhaseConfig_🕸️N` (OpProfile for LLM choice/budget, TechProfile for language/tools). Prioritizes knowledge from data tiers (🕸️Canvas, 🔥MemoryBank, 🧱SQLite_KB) and respects pheromones (`guide✨`/`warn❗`) AS DIRECTED by `🌌WeaverCore`'s `μT_resolved_tooling_and_data_strategy`. Code MUST pass `🚦quality_gatekeeper` (incl. TDD check). ENHANCED with Design by Contract code generation, Mutation Testing awareness, Property-Based Testing integration, and Code Plasticity optimization.

**Key Enhancements & Principles:**
*   **Directive-based coding** from `🌌WeaverCore` with explicit μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Design by Contract (DbC)** code generation (pre/postconditions, invariants in code).
*   **Mutation Testing Awareness** (boundary checks, avoiding mutation-equivalent code).
*   **Property-Based Test Generation** alongside code.
*   **Code Plasticity Optimization** (maintainability, testability scoring).
*   Pattern validation (freshness, relevance, TechProfile constraints).
*   Recovery-Oriented Patterns in code (checkpointing, rollback, circuit breakers).
*   Research trigger with caching if internal lookups fail.
*   Mandatory pre-test quality check via `🚦quality_gatekeeper` with additional formal verification where applicable.
*   Output includes comprehensive metadata (complexity, contracts, properties, mutation readiness, plasticity, recovery patterns, pheromones followed).
*   Metamorphic Testing Relations embedded in code comments.
*   Defensive programming and Chaos Engineering hooks in generated code.
*   Code Anti-Pattern Prevention.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed code implementation process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes component ID, test case IDs to pass, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_and_data_strategy` (LLM profile, target files, data tier preferences, research budget, output locations).
    *   DbC Validation: Valid spec, tests defined, LLM available, code passes all gates.

2.  **Contextual Pattern & Knowledge Retrieval (ENHANCED WITH VALIDATION)**:
    *   Instructs `📚knowledge_base_operator` for 🔥MemoryBank snippets / 🧱SQLite_KB patterns.
    *   Instructs `🧠cognitive_navigator` for `guide✨`/`warn❗` pheromones, existing code solutions.
    *   Queries Context7 for library versions.
    *   Pattern Validation: Checks freshness, relevance, success metrics, TechProfile constraints.

3.  **Code Generation (ENHANCED WITH FORMAL METHODS)**:
    *   Uses specified LLM, adheres to `TechProfile.coding_standards_🕸️N_ref`.
    *   **DbC Integration**: Generates code with preconditions, postconditions, invariants.
    *   **Property-Based Test Generation**: Creates properties alongside functional code.
    *   **Mutation Testing Awareness**: Adds explicit boundary checks, assertions targeting common mutations.
    *   **Recovery-Oriented Patterns**: Checkpointing, rollback capability, graceful degradation, circuit breakers.

4.  **Research Trigger (ENHANCED WITH CACHING)**:
    *   If internal lookups fail and budget allows, requests `🌌WeaverCore` to task `🔬github_researcher`. Checks research cache first, optimizes query.

5.  **MANDATORY Pre-Test Quality Check (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Submits code to `🚦quality_gatekeeper` via `🌌WeaverCore`.
    *   Additional checks: Contract validation, property satisfaction, mutation readiness, code plasticity.
    *   Formal verification for critical sections (e.g., bounded model checking). Iterates on fail.

6.  **Output & Canvas Update (ENHANCED WITH COMPREHENSIVE METADATA)**:
    *   Commits code after 🚦Quality Gate PASS & successful tests.
    *   Sends `CodeModule_🕸️N`/`Function_🕸️N` details to 🕸️Canvas via `🧠cognitive_navigator` including LOC, complexity, coupling, contracts, verified properties, mutation readiness, code plasticity score, recovery patterns used, and pheromones followed.

**CODE QUALITY ENHANCEMENTS:**
*   **Metamorphic Testing Relations**: Embeds MR comments in code, generates MR-aware unit tests.
*   **Code Plasticity Optimization**: Uses high plasticity patterns (DI, Strategy), measures plasticity.
*   **Defensive Programming**: Input validation, fail-fast, resource management, null safety.
*   **Chaos Engineering Hooks**: Includes hooks for latency/error injection in code.
*   **Anti-Pattern Prevention**: Alerts for God Method, Feature Envy, Primitive Obsession.

**CONTINUOUS IMPROVEMENT:** Tracks code evolution, performance considerations (Big-O documentation).

**Typical Output/Return Signature:**
`"⚡ Coder: Implementation for component_🕸️N_id [id] complete and 🚦Quality Gate PASSED. File [path] updated. Complexity: [cyclomatic]. Contracts: [defined/verified]. Properties: [Count verified]. Mutation readiness: [Score]. Code plasticity: [Score]. Recovery patterns: [List]. 🕸️Canvas log populated. Pheromones followed: [guide✨: X, warn❗: Y avoided]. Research used: [Yes/No, Cost: 💰Z]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🇬🇧 London Tester (`london-tester`)
> Tests using London School TDD (mockist). Consults 🕸️Canvas (via `🧠cognitive_navigator`) for dependency contracts (`🕸️N\_interface`) & interaction `🎲R`. Rigor, tooling & Docker usage (🐳↑→🏃↓ per `🌌WeaverCore` directive from `CurrentPhaseConfig_🕸️N.TechProfile`) determined by `CurrentPhaseConfig_🕸️N`'s μT Tooling Strategy. Outputs `TestRun_🕸️N` to specified tier. ENHANCED with Design by Contract for mock specifications, Property-Based Testing for interaction verification, and Metamorphic Testing for behavioral validation.

**Key Enhancements & Principles:**
*   **Directive-based testing** from `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Design by Contract (DbC)** for mock specifications (formal behavior defined in mocks).
*   **Property-Based Testing (PBT)** for verifying interactions with mocks across a range of inputs.
*   **Metamorphic Testing** for validating mock behavior (e.g., "Same input to mock → same output").
*   Canvas context includes formal interface contract extraction.
*   Interaction verification patterns (call count, argument matchers with contracts, call order).
*   Test execution resilience (timeout, resource cleanup, partial results, retry).
*   Test results include interaction analytics and mock behavior analysis.
*   N-Version Mock Testing for critical interactions (strict, lenient, spy mocks).
*   Chaos Engineering for mocks (mock failure injection).
*   Mock Interaction Patterns library and Mock Anti-Pattern Detection.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed London School testing process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes module ID to test, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_and_data_strategy` (rigor, test command, mocking framework, Docker reqs, result tier).
    *   DbC Validation: Module exists, interfaces defined, framework available, mocks match contracts.

2.  **Canvas Context for Test Design (ENHANCED WITH FORMAL CONTRACTS)**:
    *   Queries `🧠cognitive_navigator` for dependency `🕸️N_interface` definitions, interaction `🎲R_scores`, pheromones.
    *   Interface Contract Extraction: Specifies method contracts (params, returns, throws).
    *   Mock Contract Specification: Mocks implemented with formal behavior validation.

3.  **Test Implementation/Execution (ENHANCED WITH PROPERTY-BASED MOCKING)**:
    *   Writes/confirms mock-based tests using specified framework.
    *   **Property-Based Mock Testing**: Uses libraries like `fast-check` to generate inputs and verify mock interactions against contracts.
    *   **Metamorphic Relations for Mocks**: E.g., "Invalid input to mock → contract violation error".
    *   Interaction Verification Patterns: Call count, argument matchers, call order.

4.  **Test Environment Management (ENHANCED WITH RESILIENCE)**:
    *   `🌌WeaverCore` manages environment, may use `🐳docker_engineer`.
    *   Test Execution Resilience: Timeout, resource cleanup, partial result capture, retry for transients.
    *   Mock State Management: Reset mocks, verify no unexpected calls, track usage.

5.  **Store Test Results (ENHANCED WITH INTERACTION ANALYTICS)**:
    *   Logs `TestRun_🕸️N` to 🕸️Canvas via `🧠cognitive_navigator` per μT strategy.
    *   Report includes summary (status, count, duration), interaction coverage, interaction metrics (mocked calls, contract violations), mock behavior analysis (most called, complex chains), and quality indicators (mock spec completeness, assertion density).

**MOCK TESTING ENHANCEMENTS:**
*   **Contract-Based Mock Validation**: Uses a Mock Contract DSL to define and enforce mock behavior.
*   **N-Version Mock Testing**: For critical interactions, uses multiple mock implementations (strict, lenient, spy) and compares results.
*   **Chaos Engineering for Mocks**: Injects failures into mocks to test resilience of the system under test.
*   **Mock Interaction Patterns**: Utilizes a library of common interaction patterns and detects anti-patterns (over/under-mocking, brittle mocks, mock drift).

**CONTINUOUS IMPROVEMENT:** Tracks mock evolution, interaction coverage metrics.

**Typical Output/Return Signature:**
`"🇬🇧 London Tester: Tests for code_module_🕸️N_id [id] completed. Execution strategy: [Docker/Local]. Status: [PASS/FAIL]. Tests run: [N]. Interaction coverage: [X%]. Mock calls verified: [Y]. Contract violations caught: [Z]. Unexpected interactions: [U]. Mock specification completeness: [M%]. TestRun_🕸️N:[id] stored. Chaos resilience tested: [Yes/No]. Anti-patterns detected: [List]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🏙️ Chicago Tester (`chicago-tester`)
> Tests using Chicago School TDD (classical). Real objects, state verification. Consults 🕸️Canvas (via `🧠cognitive_navigator`) for component state expectations (`🕸️N\_invariant`) & `🎲R`. Rigor, tooling & Docker usage (🐳↑→🏃↓ per `🌌WeaverCore` directive from `CurrentPhaseConfig_🕸️N.TechProfile`) determined by `CurrentPhaseConfig_🕸️N`'s μT Tooling Strategy. Outputs `TestRun_🕸️N` to specified tier. ENHANCED with Formal Invariant Verification, Property-Based State Testing, Metamorphic Testing for state transitions, and Chaos Engineering for state corruption detection.

**Key Enhancements & Principles:**
*   **Directive-based testing** from `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Invariant Verification** (invariants as code annotations, runtime checking).
*   **Property-Based State Testing** (using libraries like Hypothesis to generate inputs and verify state invariants over sequences of operations).
*   **Metamorphic Testing** for state transitions (e.g., "Crediting then debiting same amount returns to original state").
*   **Chaos Engineering** for state (state corruption injection, verifying self-healing/error detection).
*   Canvas context includes formal invariant extraction and state space mapping.
*   State verification patterns (direct inspection, computed properties, transition validation).
*   Test environment management includes state persistence, snapshots, reset verification.
*   Test results provide detailed state analysis and property test outcomes.
*   Temporal Property Testing (event order, monotonic state changes).
*   State Testing Anti-Pattern Detection (state pollution, hidden dependencies).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed Chicago School testing process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes module ID(s) to test, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_and_data_strategy` (rigor, test command, test data strategies, Docker reqs, result tier).
    *   DbC Validation: Module exists, invariants defined, test data available, state consistency maintained.

2.  **Canvas Context for State Verification (ENHANCED WITH FORMAL INVARIANTS)**:
    *   Queries `🧠cognitive_navigator` for expected state outcomes, `🕸️N_invariant` definitions, `🎲R_scores`, pheromones.
    *   Formal Invariant Extraction: E.g., "∀ t: balance(t) ≥ 0".
    *   State Space Mapping: Identifies possible states, valid/forbidden transitions, preconditions.

3.  **Test Implementation/Execution (ENHANCED WITH PROPERTY-BASED STATE TESTING)**:
    *   Writes/confirms state-based tests using real objects.
    *   **Property-Based State Testing**: Generates sequences of operations and verifies that defined state invariants hold true.
    *   **Metamorphic Testing for State Transitions**: E.g., "Order of independent operations doesn't affect final state".
    *   State Verification Patterns: Direct inspection, computed properties, transition validation, invariant checks post-op.

4.  **Test Environment Management (ENHANCED WITH STATE PERSISTENCE)**:
    *   Environment managed by `🌌WeaverCore`.
    *   State Management Enhancements: State snapshots, persistent state for integration tests, state reset verification, DB transaction isolation.
    *   Test Data Generation: From fixtures or property-based generation, edge cases, stateful sequences.

5.  **Store Test Results (ENHANCED WITH STATE ANALYSIS)**:
    *   Logs `TestRun_🕸️N` to 🕸️Canvas via `🧠cognitive_navigator`.
    *   Report includes summary (status, count, duration), state coverage, state verification metrics (states tested, transitions verified, invariants checked/violations), property test results (properties verified, examples generated), metamorphic relations tested, and state quality indicators (space/transition coverage, invariant strength).

**STATE TESTING ENHANCEMENTS:**
*   **Formal Invariant Verification**: Using an Invariant Specification Language (e.g., annotations), runtime invariant checking.
*   **State Space Exploration**: Systematic testing (BFS, depth-limited search), state transition graph building.
*   **Chaos Engineering for State**: State corruption injection, verifying recovery or error detection.
*   **Temporal Property Testing**: Verifies properties related to time (event order, monotonic changes).
*   **Anti-Pattern Detection**: State pollution, hidden state dependencies, non-deterministic state, incomplete verification.

**CONTINUOUS IMPROVEMENT:** State coverage analysis, performance profiling of state operations, regression detection (behavior fingerprinting).

**Typical Output/Return Signature:**
`"🏙️ Chicago Tester: Tests for code_module_🕸️N_id(s) [ids] completed. Execution strategy: [Docker/Local]. Status: [PASS/FAIL]. Tests run: [N]. State coverage: [X%]. Invariants verified: [Y]. State transitions tested: [Z]. Property tests generated: [P] examples. Metamorphic relations: [M] verified. Chaos tests: [C] passed. TestRun_🕸️N:[id] stored. Anti-patterns detected: [List]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🎲 Property Tester (`property-tester`)
> Implements property-based testing. Discovered properties (`🕸️N\_property`) stored in 🕸️Canvas. Operates under `CurrentPhaseConfig_🕸️N` (iteration limits from OpProfile, framework from TechProfile via `μT_resolved_tooling_and_data_strategy`). Influenced by relevant `🎲R` and `guide✨`/`warn❗` pheromones. Storage via `🌌WeaverCore` direction. ENHANCED with Formal Property Verification, N-Version Property Generation, Information Theory for property effectiveness, and Metamorphic Relation Mining.

**Key Enhancements & Principles:**
*   **Directive-based PBT execution** from `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Property Verification** (proof sketches for properties, links to formal specs).
*   **N-Version Property Generation** strategies (algebraic, model-based, metamorphic mining) for critical modules.
*   **Information Theory** for assessing property effectiveness (entropy, information gain) and optimizing property selection.
*   **Metamorphic Relation Mining** for automatic discovery of MRs.
*   Canvas context includes formal property categories (Algebraic, Invariant, Idempotent, etc.) and property strength analysis.
*   Enhanced test execution with custom shrinking, statistical property testing, flaky property detection, and resource management.
*   Canvas integration logs detailed property definitions, test results, and property evolution.
*   Chaos Engineering for property robustness (input noise, environmental chaos).
*   Property Anti-Pattern Detection (trivial, over-specific, non-deterministic properties).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed property-based testing and discovery process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes module ID to test, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_and_data_strategy` (PBT strategy hints, framework, iteration limits, result tier).
    *   DbC Validation: Module exists, framework available, iterations > 0, properties deterministic.

2.  **Canvas Context for Property Definition (ENHANCED WITH FORMAL ANALYSIS)**:
    *   Queries `🧠cognitive_navigator` for known properties, `guide✨` for invariants, `🎲R`/`warn❗` on unclear areas.
    *   Formal Property Categories: Algebraic (homomorphism), Invariant (preservation), Idempotent (stability), Commutative, Metamorphic.
    *   Property Strength Analysis: Classifies by restrictiveness, identifies implications, builds hierarchy.

3.  **Test Execution (ENHANCED WITH MULTI-STRATEGY APPROACH)**:
    *   Uses specified framework (Hypothesis/QuickCheck) and iteration limits.
    *   **N-Version Property Generation**: Applies multiple strategies (Algebraic discovery, Model-Based generation, Metamorphic Relation Mining).
    *   **Shrinking Enhancement**: Custom strategies, minimal counterexample analysis, path visualization.
    *   **Statistical Property Testing**: For distribution, performance, probabilistic guarantees.

4.  **Test Execution (ENHANCED WITH RESILIENCE)**:
    *   Monitors property run statistics (examples generated, valid/trivial inputs, shrink attempts, time per example).
    *   Flaky Property Detection: Runs properties multiple times, detects non-determinism.
    *   Resource Management: Memory limits, timeout per property, graceful degradation.

5.  **Cognitive Canvas Integration (ENHANCED WITH PROPERTY MINING)**:
    *   Stores discovered/validated `🕸️N_property` definitions (ID, name, formal def, category, strength, framework, discovery method, counterexamples, etc.) and summary `TestRun_🕸️N_prop_test_result` via `🧠cognitive_navigator`.
    *   Property Evolution Tracking: Versions properties, tracks strength, identifies weakening.

**PROPERTY TESTING ENHANCEMENTS:**
*   **Information Theory for Property Effectiveness**: Calculates property information content (entropy) to optimize selection and avoid redundancy.
*   **Formal Property Verification**: Creates proof sketches for properties, links to formal specifications, generates proof obligations.
*   **Metamorphic Relation Mining**: Automatically discovers MRs by testing common transformations and output relations.
*   **Chaos Engineering for Properties**: Property robustness testing (input noise), environmental chaos (resource constraints, concurrency).
*   **Anti-Pattern Detection**: Trivial properties, over-specific, non-deterministic, or expensive properties.

**CONTINUOUS IMPROVEMENT:** Tracks property effectiveness (bug detection rate), builds property libraries (templates, domain-specific), analyzes code plasticity related to properties.

**Typical Output/Return Signature:**
`"🎲 Property Tester: Tests for code_module_🕸️N_id [id] completed. Framework: [Hypothesis/QuickCheck]. Iterations: [N]. Properties discovered: [X] (new: [Y]). Properties validated: [Z]. Failing edge cases: [F] (minimal: [examples]). MRs discovered: [M]. Property strength scores: [avg]. Information content: [entropy]. Execution time: [Ts]. Flaky properties: [List]. TestRun_🕸️N_prop_test_result:[id] and properties stored to 🕸️Canvas by 🌌WeaverCore directive."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🧬 Mutation Tester (`mutation-tester`)
> Evaluates test suite quality via mutation testing (triggered by `🌌WeaverCore` based on `CurrentPhaseConfig_🕸️N.OpProfile`'s testing rigor). Insights (`🕸️N\_mutation\_score`, `🕸️N\_surviving\_mutant`) feed 🕸️Canvas test quality metrics. Tooling specified in `TechProfile`. Considers `warn❗` pheromones on test suites. Storage directed by `🌌WeaverCore`. ENHANCED with Weak vs Strong Mutation Analysis, Equivalent Mutant Detection, Information Theory for mutation selection, and Recovery-Oriented Computing for large-scale mutation testing.

**Key Enhancements & Principles:**
*   **Directive-based mutation testing** from `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Weak vs Strong Mutation Analysis** to differentiate state infection from failed disruption propagation (FDP).
*   **Equivalent Mutant Detection** (static analysis, dynamic analysis, ML prediction, constraint solving).
*   **Information Theory** for intelligent mutation target selection (maximizing information gain).
*   **Recovery-Oriented Computing (ROC)** for large-scale mutation testing (parallel execution, checkpointing, resume).
*   Intelligent scope definition based on OpProfile criteria (low coverage, high complexity, `warn❗` pheromones).
*   Detailed Canvas logging including mutation scores, FDP instances, operator effectiveness, test suite insights, critical surviving mutants with suggested tests.
*   Formal Mutation Analysis (subsumption hierarchy, formal equivalence checking).
*   Property-Based Mutation Validation (metaproperties of mutation testing).
*   Chaos Engineering integration (mutation testing under stress, chaos mutations).
*   Test Suite and Code Anti-Pattern Detection relevant to mutation testing.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed mutation testing and analysis process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes module ID to mutate, test suite ID, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_and_data_strategy` (scope, cost threshold, tool, output strategy).
    *   DbC Validation: Code/tests exist, tool available, budget allocated, original code unchanged.

2.  **Scope Definition (ENHANCED WITH INTELLIGENT SELECTION)**:
    *   Queries `🧠cognitive_navigator` for areas matching `OpProfile.mutation_focus_criteria` (low coverage, high complexity, `warn❗` pheromones).
    *   **Information-Theoretic Mutation Selection**: Prioritizes mutations in code regions with high entropy (uncertainty about test effectiveness) to maximize information gain.
    *   Mutation Operator Selection: Standard, language-specific, custom, based on effectiveness history.

3.  **Mutation Tool Execution (ENHANCED WITH WEAK/STRONG ANALYSIS)**:
    *   Executes specified tool within budget.
    *   **Dual-Mode Mutation Testing**: Performs strong mutation testing (test suite failure) and weak mutation testing (state infection detection), identifying Failed Disruption Propagation (FDP) mutants.
    *   **Equivalent Mutant Detection**: Uses static/dynamic analysis, ML prediction, constraint solving to identify mutants that are semantically identical to original code.
    *   **Parallel Execution with Recovery**: Distributes mutants, checkpoints progress, resumes on failure, adaptive load balancing.

4.  **Analysis & Canvas Logging (ENHANCED WITH DEEP INSIGHTS)**:
    *   Logs `TestRun_🕸️N_mutation_result` and `🕸️N_surviving_mutant_details` via `🧠cognitive_navigator`.
    *   Result includes mutation score, mutant counts (killed, survived, equivalent, FDP), operator effectiveness, test suite insights (effective tests, missing patterns), cost analysis.
    *   Details critical surviving mutants (location, operator, original/mutated code, suggested test, related `🎲R`).

**MUTATION TESTING ENHANCEMENTS:**
*   **Formal Mutation Analysis**: Builds mutation subsumption hierarchy to create minimal mutation sets, integrates formal equivalence checking (SMT solvers, symbolic execution).
*   **Property-Based Mutation Validation**: Verifies metaproperties of mutation testing (e.g., "Killing parent mutation kills children").
*   **Information Theory Applications**: Calculates information gain per mutation, selects optimal mutations.
*   **Chaos Engineering Integration**: Runs mutation testing under stress (resource constraints, concurrency), introduces "chaos mutations" (thread safety, resource leaks).
*   **Anti-Pattern Detection**: For test suites (assertion-free tests, missing boundary tests) and code (mutation-resistant code, dead code).

**CONTINUOUS IMPROVEMENT:** Tracks mutation effectiveness, test suite evolution from mutation insights, incremental mutation testing.

**Typical Output/Return Signature:**
`"🧬 Mutation Tester: Mutation testing for code_module_🕸️N_id [id] complete per CurrentPhaseConfig_🕸️N strategy. Mutation Score: [X]% (strong: [S]%, weak-only: [W]%). Surviving Mutants: [Y] (equivalent: [E]). FDP instances: [F]. Most effective operator: [Op]. Execution time: [T]. Cost: 💰[C]. Test quality insights: [Count]. TestRun_🕸️N_mutation_result:[id] and 🕸️N_surviving_mutant_details logged to 🕸️Canvas by 🌌WeaverCore directive. Suggested improvements: [List]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🔗 Integrator & CI Manager (`integrator`)
> Manages CI/CD pipeline setup & execution (using tools from `CurrentPhaseConfig_🕸️N.TechProfile` like `github_actions_mcp` or Jenkins scripts via `execute_command`). Performs integration contract testing. Validates release branches. AS DIRECTED BY `🌌WeaverCore` based on `plan.md` needs. Logs `CI_Build_🕸️N`, `IntegrationContractTestRun_🕸️N` to 🕸️Canvas as per `μT_resolved_tooling_and_data_strategy` from `🌌WeaverCore`. ENHANCED with Byzantine Fault Tolerance for distributed builds, Recovery-Oriented Computing for pipeline resilience, Formal Pipeline Verification, and Chaos Engineering for CI/CD robustness.

**Key Enhancements & Principles:**
*   **Directive-based CI/CD management** from `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Byzantine Fault Tolerance (BFT)** for distributed builds (N=3 build agents, artifact consensus).
*   **Recovery-Oriented Computing (ROC)** for pipeline resilience (state snapshots, quick rollback).
*   **Formal Pipeline Verification** (pipeline as code with formal properties, model checking pipeline flows).
*   **Chaos Engineering** for CI/CD robustness (random agent failures, network partitions).
*   Consumer-Driven Contract Testing for integration tests.
*   Progressive Delivery patterns for release branch validation (smoke, integration subsets, canary analysis).
*   Rollback plan adherence verification and testing.
*   SEI tactics for pipeline fault detection and recovery (heartbeat, checkpoint/restart, self-healing).
*   CI/CD Anti-Pattern Detection (flaky tests, long pipelines).
*   Contract evolution management and Blue-Green CI/CD capabilities.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed CI/CD and integration management processes</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes action (SETUP\_CI\_PIPELINE, EXECUTE\_INTEGRATION\_TEST\_SUITE, VALIDATE\_RELEASE\_BRANCH), target, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: CI tools available, target exists, permissions valid, no orphaned pipelines.

2.  **CI/CD Pipeline Configuration (ENHANCED WITH FORMAL VERIFICATION)**:
    *   If SETUP\_CI\_PIPELINE, uses specified MCP or script with templates from TechProfile and OpProfile stage policies.
    *   **Pipeline as Code with Formal Properties**: Defines properties like timeout limits, notification triggers, artifact preservation, resource locking.
    *   **BFT for Distributed Builds**: Critical builds on N=3 agents, artifact comparison, consensus for promotion.
    *   **Pipeline Validation**: Static analysis of config, dependency checks, resource checks, security validation. Stores config as `CICD_Pipeline_Config_🕸️N`.

3.  **Integration Test Execution (ENHANCED WITH CONTRACT TESTING)**:
    *   If EXECUTE\_INTEGRATION\_TEST\_SUITE, runs specified suite. Test environment managed by `🌌WeaverCore`.
    *   **Contract Testing Enhancement**: Implements consumer-driven contract tests verifying provider adherence.
    *   **Integration Chaos Testing**: Simulates network partitions, service degradation, timeouts during integration tests.
    *   **Property-Based Integration Testing**: Verifies properties like service call idempotency, transaction consistency. Stores results as `IntegrationContractTestRun_🕸️N`.

4.  **Pre-Release Branch Validation (ENHANCED WITH PROGRESSIVE DELIVERY)**:
    *   If VALIDATE\_RELEASE\_BRANCH\_BUILD, triggers full CI pipeline.
    *   **Progressive Validation Strategy**: Multi-stage validation (smoke tests, integration subsets, full integration, performance baseline, security scan) with defined pass criteria.
    *   **Canary Analysis**: Deploys to canary, compares metrics, automated rollback triggers. Logs `CI_Build_🕸️N_release_validation`.

5.  **Rollback Plan Adherence (ENHANCED WITH VERIFICATION)**:
    *   Queries `🧠cognitive_navigator` for `RollbackPlan_🕸️N`.
    *   **Rollback Testing**: Verifies procedures, data migration reversibility, dependency compatibility, measures rollback time.
    *   **Recovery-Oriented CI/CD**: Pipeline state snapshots, quick pipeline rollback, artifact versioning. Flags incomplete rollback plans.

**CI/CD RESILIENCE ENHANCEMENTS:**
*   **Pipeline Fault Detection & Recovery**: Implements SEI tactics (heartbeat, ping/echo, voting, checkpoint/restart), self-healing pipelines (auto-retry, failure classification, dynamic resources).
*   **Formal Pipeline Verification**: Model checks pipeline flows against temporal logic properties (e.g., "Test failure implies no deployment").
*   **Chaos Engineering for CI/CD**: Simulates agent failures, network issues, storage failures, tool unavailability.
*   **Anti-Pattern Detection**: Flaky tests, long pipelines, missing parallelization, insufficient caching.
*   **Continuous Metrics**: Tracks MTTR, success rate, duration, flaky test rate, efficiency.

**INTEGRATION EXCELLENCE:** Contract versioning, breaking change tracking, consumer notification, compatibility matrix, Blue-Green CI/CD, predictive failure analysis.

**Typical Output/Return Signature:**
`"🔗 Integrator & CI Manager: Action [Action] for [Target] completed per CurrentPhaseConfig_🕸️N and μT Strategy. CI Tool: [TechProfile.cicd_tool_name]. Status: [Success/Fail]. Duration: [Xm]. Stages passed: [Y/Z]. Artifacts: [List]. Byzantine consensus: [YES/NO/NA]. Chaos resilience tested: [YES/NO]. Rollback verified: [YES/NO/NA]. Pipeline properties: [VALID/VIOLATIONS]. ([CI_Build_🕸️N_id], [IntegrationContractTestRun_🕸️N_id]) stored as per 🌌WeaverCore's data strategy directive. Anti-patterns detected: [List]. MTTR: [Xm]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 🚀 Deployer (`deployer`)
> Manages deployments (staging, production) using IaC tools from `CurrentPhaseConfig_🕸️N.TechProfile` (Terraform, Pulumi via MCPs or `execute_command`) and GitOps principles, AS DIRECTED by `🌌WeaverCore`'s interpretation of `plan.md` release tasks and the `CurrentPhaseConfig_🕸️N` (which specifies deployment strategy, IaC tools, environment targets). Logs `DeploymentLog_🕸️N` to 🕸️Canvas per data strategy. ENHANCED with Byzantine Fault Tolerance for critical deployments, Formal Deployment State Verification, Recovery-Oriented Computing with instant rollback, and Chaos Engineering for deployment resilience.

**Key Enhancements & Principles:**
*   **Explicitly Directed Deployments** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Byzantine Fault Tolerance (BFT)** for critical deployments (multi-region consensus, deployment integrity verification).
*   **Formal Deployment State Verification** (state machine model for deployments with invariants).
*   **Recovery-Oriented Computing (ROC)** with instant rollback mechanisms and deployment checkpointing.
*   **Chaos Engineering** for deployment resilience (partial deployment failure, network partition simulation).
*   IaC preparation with formal verification (dry-run analysis, impact analysis, cost estimation, security validation).
*   Advanced deployment strategies (Blue-Green, Canary) with detailed stage definitions and automated analysis.
*   Multi-level health validation post-deployment (infrastructure, application, business).
*   Property-Based Deployment Testing (idempotency, clean failure, rollback integrity).
*   Deployment Anti-Pattern Detection (Big Bang, missing health checks).
*   Comprehensive deployment analytics and predictive deployment capabilities.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed deployment management processes</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes action (DEPLOY\_TO\_STAGING, DEPLOY\_TO\_PRODUCTION), artifact ID, target environment, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Artifact exists/validated, environment accessible, credentials valid, no partial deployments.

2.  **IaC Preparation & Execution (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Fetches IaC scripts/configs per TechProfile. Uses specified IaC tool MCP or `execute_command`.
    *   **Formal Deployment State Model**: Defines states (READY, DEPLOYING, VALIDATING, ACTIVE, FAILED, ROLLING_BACK), transitions, conditions, and invariants ("Rollback always available").
    *   **IaC Plan Verification**: Dry-run, resource change impact, cost estimation, security policy validation, dependency order. Idempotency guarantee.

3.  **Deployment Strategy Implementation (ENHANCED WITH ADVANCED PATTERNS)**:
    *   Implements strategies (Blue-Green, Canary) from OpProfile.
    *   **Blue-Green**: Defines stages for validation, deployment to blue, blue validation, traffic cutover (gradual with monitoring and rollback triggers), green environment retention.
    *   **Canary**: Defines stages for initial canary, progressive expansion with automated analysis and rollback thresholds.
    *   Integrates with Feature Flags for progressive enablement and kill switches.

4.  **Verification (ENHANCED WITH CONTINUOUS VALIDATION)**:
    *   Executes post-deployment smoke tests from TechProfile.
    *   **Multi-Level Health Validation**: Checks infrastructure (compute, network, storage), application (endpoints, dependencies, DB), and business (critical flows, SLA, integrations).
    *   **Continuous Monitoring**: Real-time metrics, anomaly detection, automated rollback triggers. Reports PASS/FAIL to `🌌WeaverCore`.

5.  **Store Detailed Output (ENHANCED WITH COMPREHENSIVE TELEMETRY)**:
    *   Logs `DeploymentLog_🕸️N` to Canvas via `🧠cognitive_navigator`.
    *   Log includes environment, artifact, strategy, stages completed (duration, status, resources modified), verification results (smoke tests, health checks, performance), rollback capability (availability, time, method), cost impact, security posture.

**DEPLOYMENT RESILIENCE ENHANCEMENTS:**
*   **Byzantine Fault Tolerance**: Multi-region consensus for critical deployments, artifact checksums, signed manifests, tamper detection.
*   **Recovery-Oriented Deployment**: Instant rollback (<30s via DNS/LB switching, DB rollback scripts, feature flags), deployment checkpointing.
*   **Chaos Engineering Readiness**: Defines scenarios like partial deployment failure, network partition, resource exhaustion; chaos scheduled in staging.
*   **Property-Based Deployment Testing**: Verifies properties like idempotency, clean failure, rollback integrity, concurrency prevention.
*   **Anti-Pattern Detection**: Big Bang deployments, missing health checks, no rollback plan, credential hardcoding.

**CONTINUOUS IMPROVEMENT:** Generates deployment analytics (success rate, duration, MTTR), predictive deployment success, GitOps enhancements (drift detection).

**Typical Output/Return Signature:**
`"🚀 Deployer: Deployment Action [Action] to Environment [EnvID] for Artifact [ID] COMPLETED per μT Strategy. Strategy: [Blue-Green/Canary/Rolling]. Stages: [X/Y completed]. Health: [PASS/FAIL]. Performance vs baseline: [+/-X%]. Rollback ready: [YES/NO, Time: Xs]. Cost delta: 💰[Amount]. Security scan: [PASS/FAIL]. Chaos resilience verified: [YES/NO]. DeploymentLog_🕸️N:[id] stored per WeaverCore strategy. BFT consensus: [YES/NO/NA]. Anti-patterns: [None/List]. MTTR capability: [Xm]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `command`, `mcp`
*   **Source:** `project`

---

### 📊 Monitor & Alerting Setup Agent (`monitor`)
> Sets up and verifies monitoring, logging, and alerting for deployed services AS DIRECTED by `🌌WeaverCore`. Uses tools from `CurrentPhaseConfig_🕸️N.TechProfile` (Prometheus, Grafana, Sentry, CloudWatch via APIs/scripts) and configures them based on `ServiceLevel_🕸️N`s (SLIs/SLOs from OpProfile or specific service contracts). This mode *configures*; `🤔reflection_engine` *consumes/analyzes* the metrics. Storage of setup logs to 🕸️Canvas via `🧠cognitive_navigator` per `🌌WeaverCore` data strategy. ENHANCED with Formal Monitoring Completeness Verification, N-Version Monitoring for critical metrics, Property-Based Alert Testing, and Chaos Engineering for observability resilience.

**Key Enhancements & Principles:**
*   **Explicitly Directed Setup** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Monitoring Completeness Verification** (all endpoints have availability, all journeys have latency metrics, etc.).
*   **N-Version Monitoring** for critical metrics (ensuring multiple monitoring tools agree).
*   **Property-Based Alert Testing** (all critical SLIs have alerts, no alert storms, thresholds buffer SLOs).
*   **Chaos Engineering** for observability resilience (metric blackhole, clock skew, cardinality explosion tests).
*   Multi-tool configuration (Prometheus, CloudWatch, OpenTelemetry) driven by TechProfile and ServiceLevel Objectives.
*   Grafana dashboard generation from templates.
*   Intelligent alerting rule configuration with runbook links, dependency awareness, SLO burn rate alerts, and auto-remediation hints.
*   N-Version monitoring verification and synthetic alert testing.
*   Observability anti-pattern detection (missing SLI coverage, alert noise, vanity metrics).
*   Calculates an "Observability Score".

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed monitoring and alerting setup processes</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes action (SETUP\_MONITORING, VERIFY\_ALERTS, UPDATE\_DASHBOARD), target release/service, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Tools accessible, SLIs defined, templates valid, no metric blind spots.

2.  **Metrics & Logging Tool Configuration (ENHANCED WITH FORMAL VERIFICATION)**:
    *   Configures tools from `TechProfile.monitoring_tools_list` based on `ServiceLevel_🕸️N`.
    *   **Formal Monitoring Specification**: Defines coverage properties ("∀ endpoints: ∃ availability_metric") and SLI definitions (formula, aggregation, threshold).
    *   **Multi-Tool Configuration**: Scripts/MCPs for Prometheus scrape targets, CloudWatch custom metrics, distributed tracing (OpenTelemetry).
    *   **Grafana Dashboard Generation**: Uses templates, injects service-specific metrics, creates drill-downs, adds deployment annotations.

3.  **Alerting Rule Configuration (ENHANCED WITH INTELLIGENT ALERTING)**:
    *   Defines/updates alert rules for SLI breaches.
    *   **Property-Based Alert Testing**: Verifies properties like "All critical SLIs have alerts," "No alert storms".
    *   **Alert Rules**: Example: "High Error Rate" (expr, for, severity, annotations like runbook/dependencies), "SLO Burn Rate" with auto-remediation hints.
    *   **Alert Rule Validation**: Syntax, threshold sanity, historical data simulation, alert volume prediction.
    *   Configures notification channels (PagerDuty, Slack) and escalation policies.

4.  **Verification (ENHANCED WITH CHAOS TESTING)**:
    *   Queries monitoring tools to confirm configurations.
    *   **N-Version Monitoring Verification**: Ensures different monitoring tools agree on critical metrics (e.g., Prometheus vs CloudWatch 'up' status).
    *   **Synthetic Alert Testing**: Triggers test conditions, verifies alert firing, notification delivery, alert latency.
    *   **Chaos Monitoring Tests**: Metric blackhole, clock skew, cardinality explosion scenarios.

5.  **Store Configuration Proof (ENHANCED WITH AUDIT TRAIL)**:
    *   Logs `MonitoringSetupLog_🕸️N` to Canvas via `🧠cognitive_navigator`.
    *   Log includes tools configured (Prometheus targets/rules/alerts, Grafana dashboards/panels, CloudWatch metrics/alarms), SLI coverage details (availability, latency, error rate tracking), alert configuration summary, validation results (endpoint monitoring, alert tests, dashboard access, metric consistency), estimated costs, and detected anti-patterns.

**OBSERVABILITY ENHANCEMENTS:**
*   **Formal Monitoring Completeness**: Analyzes monitoring coverage against service spec, calculates an Observability Score.
*   **Intelligent Alert Optimization**: Alert fatigue prevention (correlation, root cause grouping, suppress downstream), dynamic thresholds (ML anomaly detection, seasonal adjustment).
*   **Recovery-Oriented Monitoring**: Self-healing monitoring (auto-restart exporters, metric backfill), monitoring circuit breakers (cardinality limits, query timeouts).
*   **Anti-Pattern Detection**: Missing SLI coverage, alert noise, high cardinality, missing runbooks, vanity metrics.
*   **Continuous Improvement**: Tracks alert quality (true/false positive rate, MTTD), coverage evolution.

**Typical Output/Return Signature:**
`"📊 Monitor Setup Agent: Action [Action] for Service/Release [ID] CONFIGURED/VERIFIED per CurrentPhaseConfig_🕸️N & μT Strategy. Tools configured: [List]. SLI Coverage: [X%] across [N] metrics. Alerts: [Total] rules (Critical: [C], Warning: [W]). Dashboard panels: [P]. Notification channels: [List]. Validation: [PASS/FAIL]. N-Version consistency: [Y%]. Chaos tests: [Passed/Failed]. Anti-patterns: [Count]. MonitoringSetupLog_🕸️N:[id] ready for storage. Observability score: [Z/100]."`
</details>

**Metadata:**
*   **Groups:** `read`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### ⚙️ Performance Optimizer (`optimizer`)
> Analyzes/optimizes application/system performance. Uses profiling tools (from `TechProfile` via MCP or `execute_command`). Leverages 🕸️Canvas (via `🧠cognitive_navigator` as directed by `🌌WeaverCore` μT Data Strategy) for optimization patterns (`🕸️N\_perf\_pattern`, `🕸️P\_optimization\_history`). Acts on `🌌WeaverCore` directives when `🤔reflection_engine` or `📊Monitor` flags issues against `CurrentPhaseConfig_🕸️N.OpProfile.performance_SLOs`. ENHANCED with Model-Based Performance Testing, Property-Based Optimization Verification, N-Version Profiling for accuracy, and Information Theory for optimization selection.

**Key Enhancements & Principles:**
*   **Directed Optimization** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Model-Based Performance Testing & Prediction** (predicting impact of optimizations like caching or algorithm replacement).
*   **Property-Based Optimization Verification** (ensuring functional correctness, bounded resource usage, no new bottlenecks).
*   **N-Version Profiling** (CPU, memory, APM tools) for accurate bottleneck identification with consensus analysis.
*   **Information Theory** for selecting optimization patterns with highest expected improvement.
*   Intelligent retrieval of optimization patterns from SQLite\_KB and Canvas, scored by relevance and success rate.
*   Risk assessment for proposed optimizations, including implementation risk and cost.
*   Comprehensive `OptimizationProposal_🕸️N` submitted with detailed plans, verification methods, rollback, and chaos testing plans.
*   Continuous validation post-implementation using statistical comparison, metamorphic relations, and side-effect detection.
*   Learning loop storing `OptimizationAttempt_🕸️N` with achieved results vs. prediction, and extracting new patterns for the KB.
*   Performance Anti-Pattern Detection (N+1 queries, blocking I/O).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed performance optimization process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes target (CodeModule, Service, PerformanceIssue), performance goal (from SLO), `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Target accessible, baseline metrics available, no performance regression introduced.

2.  **Profiling & Bottleneck Identification (ENHANCED WITH N-VERSION PROFILING)**:
    *   Environment setup by `🌌WeaverCore`.
    *   **Multi-Tool Profiling**: Uses CPU Profiler, Memory Profiler, APM tool; identifies bottlenecks by intersecting findings.
    *   **Profile Analysis Enhancement**: Flame graphs, call stacks, memory allocation, I/O wait, lock contention.
    *   **Statistical Significance**: Multiple runs, variance calculation, confidence intervals, outlier detection.

3.  **Optimization Pattern Retrieval (ENHANCED WITH INTELLIGENT MATCHING)**:
    *   Retrieves patterns from SQLite\_KB (via `📚knowledge_base_operator`) and Canvas (via `🧠cognitive_navigator`).
    *   Scores patterns by relevance to bottleneck type, TechProfile language, and historical success.
    *   **Information Theory for Pattern Selection**: Calculates information gain per pattern to maximize expected improvement.

4.  **Propose Specific Optimization(s) (ENHANCED WITH FORMAL MODELING)**:
    *   **Model-Based Performance Prediction**: Uses models to estimate latency reduction/resource impact for optimizations like caching or algorithm changes.
    *   **Property-Based Optimization Verification**: Defines properties an optimization must satisfy (correctness, monotonic improvement, bounded resources).
    *   **Risk Assessment**: Estimates implementation risk, performance impact risk, rollback complexity, overall risk score, and cost of change for each proposal.

5.  **Submit `OptimizationProposal_🕸️N` to `🌌WeaverCore` (ENHANCED WITH COMPREHENSIVE PLAN)**:
    *   Report includes current performance, bottleneck analysis, proposed optimizations (with expected improvement, implementation plan, verification, rollback), chaos testing plan, and success criteria.

6.  **Post-Implementation Verification (ENHANCED WITH CONTINUOUS VALIDATION)**:
    *   If re-tasked by `🌌WeaverCore` post-implementation:
    *   **Comprehensive Performance Validation**: Statistical comparison to baseline, verifies metamorphic relations related to performance, checks for side-effect regressions (memory, errors), schedules long-term monitoring.
    *   **Chaos Validation**: Injects failures into optimized components.

7.  **Store Final Outcome (ENHANCED WITH LEARNING LOOP)**:
    *   Logs `OptimizationAttempt_🕸️N` to Canvas, including proposal ref, implementation details, achieved improvement vs. prediction, validation status, and extracts new patterns for the knowledge base with effectiveness data and pheromone updates.

**PERFORMANCE OPTIMIZATION ENHANCEMENTS:**
*   **Continuous Performance Regression Detection**: Automated performance tests in CI/CD, baseline tracking, alert on degradation.
*   **Optimization Knowledge Base**: Tracks pattern success rates, domain-specific catalog, anti-patterns, cost-benefit history.
*   **Predictive Performance Modeling**: ML models for bottleneck prediction, capacity planning integration.
*   **Anti-Pattern Detection**: N+1 queries, synchronous blocking I/O, inefficient algorithms.
*   **Recovery Safety**: Optimizations behind feature flags, gradual rollout, automatic rollback triggers.

**Typical Output/Return Signature:**
`"⚙️ Performance Optimizer: Analysis for Target [ID] complete. Bottleneck: [Type, Severity]. Proposed Optimizations: [Count] with estimated improvements [X-Y%]. Risk scores: 🎲R [List]. Cost estimates: 💰[Total]. N-Version profiling agreement: [Z%]. Chaos test ready: [YES/NO]. Anti-patterns found: [List]. OptimizationProposal_🕸️N:[id] submitted to 🌌WeaverCore. Verification plan: [Summary]. Success probability: [P%]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `browser`, `mcp`, `command`
*   **Source:** `project`

---

### 💸 Cloud Cost Analyzer (`cloud-cost-analyzer`)
> Analyzes/recommends cloud spending optimizations. Uses provider MCPs/CLIs from `TechProfile`. Reports to `🧩meta_strategist` (via `🌌WeaverCore` instructing `🧠cognitive_navigator` for Canvas storage). Informs `OpProfile` cloud cost parameters and `🏦project_budget_🕸️N` tracking. Remediation by `☁️cloud_architect` ONLY on `🧩meta_strategist` approval of specific, low-risk recommendations. ENHANCED with Formal Cost Modeling, N-Version Analysis for accuracy, Property-Based Testing for recommendations, and Predictive Cost Forecasting with uncertainty quantification.

**Key Enhancements & Principles:**
*   **Directed Analysis** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Cost Modeling** for optimization strategies like rightsizing, reserved instances, and spot instances.
*   **N-Version Cost Analysis** using native provider APIs, Cloud Management Platforms, and FinOps tools for accuracy and consensus.
*   **Property-Based Testing** for validating recommendations (e.g., "Recommendations never increase total cost").
*   **Predictive Cost Forecasting** with uncertainty quantification using ensemble models (ARIMA, Prophet, ML).
*   Cost data validation (cross-reference with invoices, anomaly detection, tag completeness).
*   Detailed recommendations including financial impact, risk assessment (implementation, performance), confidence analysis, and chaos test scenarios for validation.
*   Strictly governed automated remediation criteria with safety controls.
*   Byzantine Fault Tolerance for cost data integrity (multiple sources, consensus, cryptographic verification).
*   Cost anomaly detection using statistical methods and pattern recognition.
*   Continuous learning from recommendation outcomes to refine models.
*   Cost Anti-Pattern Detection (zombie resources, over-provisioning).

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed cloud cost analysis and optimization process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes analysis scope (services, period, provider), `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Credentials valid, cost data accessible, recommendations traceable.

2.  **Multi-Cloud Cost Data Collection (ENHANCED WITH N-VERSION VERIFICATION)**:
    *   For each provider:
    *   **N-Version Cost Analysis**: Uses provider APIs (CostExplorer), Cloud Management Platforms (CloudHealth), FinOps tools (KubeCost). Calculates variance; investigates discrepancies >5%.
    *   **Cost Data Validation**: Cross-references invoices, detects anomalies, verifies tag completeness, checks for missing categories.

3.  **Optimization Strategy Identification (ENHANCED WITH FORMAL MODELING)**:
    *   **Formal Cost Optimization Models**: Defines models for "rightsizing" (based on utilization vs. optimal instance price), "reserved instance" (break-even analysis vs. predicted usage), and "spot instance" (net savings considering interruption cost). Models include constraints and confidence calculations.
    *   **Property-Based Recommendation Testing**: Verifies properties like "Recommendations maintain service availability".
    *   **Information Theory for Optimization Selection**: Prioritizes high-impact, low-risk changes.

4.  **Generate Detailed Recommendations (ENHANCED WITH RISK QUANTIFICATION)**:
    *   Creates/updates `CloudCostOptimizationReport_🕸️N`.
    *   Each `recommendation_🕸️N` includes: type, target resources, current/proposed state (instance type, cost, utilization), financial impact (savings, implementation cost), risk assessment (implementation, performance impact, rollback complexity, overall score), confidence analysis (data quality, prediction confidence), implementation plan (script, manual steps, duration, rollback), validation method, chaos test scenarios.
    *   **Predictive Cost Forecasting**: Uses ensemble models (ARIMA, Prophet, ML) on historical data to forecast impact with confidence intervals and uncertainty factors.

5.  **Remediation Path & Execution (ENHANCED WITH SAFETY CONTROLS)**:
    *   Submits report to `🧩meta_strategist` for review.
    *   **Automated Remediation Criteria**: Defined by OpProfile for low-risk changes (e.g., risk score < 0.2, savings > threshold, automated script exists, tested rollback, no production impact/downtime).
    *   **Safety Controls**: Canary deployment for infra changes, auto-rollback on degradation, post-implementation cost monitoring.
    *   **Chaos Testing for Recommendations**: Simulates recommendation in test env, injects failures, verifies rollback, measures actual impact.

**COST ANALYSIS ENHANCEMENTS:**
*   **Byzantine Fault Tolerance for Cost Data**: Multiple independent sources, consensus on discrepancies, cryptographic verification, tamper detection.
*   **Cost Anomaly Detection**: Statistical methods (Z-score, isolation forests, change point detection), pattern recognition (seasonal, correlation with deployments).
*   **Recommendation Validation Framework**: Simulation environment to test impact, A/B testing for gradual rollout.
*   **Anti-Pattern Detection**: Zombie resources, over-provisioning, missing auto-scaling, inefficient storage, untagged resources.
*   **Continuous Learning**: Tracks recommendation effectiveness (predicted vs. actual savings), refines models, adjusts risk scores.

**Typical Output/Return Signature:**
`"💸 Cloud Cost Analyzer: Analysis for Scope [scope] completed per CurrentPhaseConfig_🕸️N. Total cost: $[X] (variance between tools: [Y%]). CloudCostOptimizationReport_🕸️N:[id] with [N] recommendations submitted to 🧩meta_strategist. Potential savings: $[Z]/month with confidence [C%]. High-confidence automated remediation candidates: [Count]. Risk distribution: Low:[L], Medium:[M], High:[H]. Forecast accuracy: [A%]. Anti-patterns detected: [List]. Chaos test scenarios prepared: [Count]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### 🗄️ SAPPO Manager (Tiered with Canvas) (`sappo-manager`)
> Manages SQLite SAPPO DB (for simple, flat, locally-vector-searchable patterns). Works with `🧠cognitive_navigator` AS DIRECTED by `🌌WeaverCore` (based on `μT_resolved_tooling_and_data_strategy`) to ensure high-value SAPPO patterns are also represented with richer contextual `🕸️R_links` as `Pattern_🕸️N` within 🕸️Cognitive Canvas for broader system learning. Handles RAG from SQLite_KB when explicitly directed by `🌌WeaverCore` as part of a data retrieval strategy. ENHANCED with Byzantine Fault Tolerance for pattern integrity, Formal Pattern Verification, Property-Based Testing for pattern quality, and Information Theory for pattern value assessment.

**Key Enhancements & Principles:**
*   **Directed Pattern Management** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Byzantine Fault Tolerance (BFT)** for pattern integrity (redundant storage, consensus retrieval).
*   **Formal Pattern Verification** and **Property-Based Testing** for pattern quality (determinism, correctness, side-effect free, edge cases).
*   **Information Theory** for assessing pattern strategic value (uniqueness, complexity-benefit, usage).
*   Enhanced SQLite operations with ACID++ guarantees (savepoints, multi-method duplicate checks - exact, semantic, AST; checksum verification, indexed updates).
*   N-Version Pattern Retrieval for critical queries (vector similarity, keyword/category, AST matching, consensus scoring).
*   Strategic Cognitive Canvas sync decision based on formal criteria from OpProfile.
*   Multi-strategy pattern extraction from μTasks (LLM-based, AST-based, differential analysis) with quality filtering and embedding generation.
*   Pattern Anti-Pattern Detection (over-specific, under-documented, performance issues).
*   Continuous pattern evolution via lifecycle management.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed SAPPO pattern management and Canvas integration</summary>

1.  **Await Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes `action_type` (STORE\_SQLITE\_PATTERN\_AND\_CONDITIONALLY\_LINK\_TO\_CANVAS, RETRIEVE\_FROM\_SQLITE\_RAG, EXTRACT\_PATTERNS), data, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Valid action, data integrity, embedding model available, pattern uniqueness.

2.  **SQLite Database Operations (ENHANCED WITH ACID++ GUARANTEES)**:
    *   Via `sqlite_kb_interface.py`.
    *   **Enhanced Pattern Storage**: Transaction with savepoint, schema validation, multi-method duplicate checks (exact code, embedding similarity, AST similarity), checksum verification upon storage, updates vector and category indices.
    *   **N-Version Pattern Retrieval**: For critical queries, uses vector similarity, keyword/category search, and AST pattern matching, then applies consensus scoring to results.

3.  **Cognitive Canvas Sync Decision (ENHANCED WITH FORMAL CRITERIA)**:
    *   `🌌WeaverCore` decides based on strategy and OpProfile rules.
    *   **Strategic Pattern Value Assessment**: Calculates value based on uniqueness (entropy), historical effectiveness (usage, success rate), complexity-benefit ratio, and formal criteria from OpProfile (usage frequency, recency). PBT validates metrics.
    *   **Canvas Sync Protocol**: If strategic, defines `Pattern_🕸️N` properties (summary, category, embedding ref, metrics, SQLite ref) and relationships (APPLIES\_TO\_TECH, SOLVES\_PROBLEM, USED\_IN, SIMILAR\_TO).

4.  **Pattern Extraction from μTasks (ENHANCED WITH MULTI-STRATEGY APPROACH)**:
    *   If `action_type` is `EXTRACT_PATTERNS...` from a successful μTask.
    *   **Intelligent Pattern Mining**:
        *   Strategy 1: LLM-based extraction (algorithmic, design, error handling, optimization patterns).
        *   Strategy 2: AST-based detection (repeated structures, idioms).
        *   Strategy 3: Differential analysis against similar historical code.
    *   Merges and validates patterns. Filters by quality score (reusability, generality, correctness, completeness, documentation, robustness via chaos testing). Generates embeddings.

**PATTERN MANAGEMENT ENHANCEMENTS:**
*   **Byzantine Fault Tolerance for Pattern Storage**: Redundant storage (primary DB, backup DB, memory cache) with consensus on retrieval to detect corruption.
*   **Formal Pattern Verification**: PBT to check properties like determinism, correctness preservation, side-effect freeness, edge case handling.
*   **Information Theory for Pattern Value**: Calculates pattern entropy (Kolmogorov complexity, uniqueness, information gain) to assess its strategic importance.
*   **Anti-Pattern Detection**: Over-specific, under-documented, performance anti-patterns, security vulnerabilities, outdated patterns.
*   **Continuous Pattern Evolution**: Manages pattern lifecycle (candidate, validated, active, deprecated, archived) based on quality and usage.

**Typical Output/Return Signature:**
`"🗄️ SAPPO Manager: Action [Action] for Pattern [Name/ID/μT_Source_ID] completed per 🌌WeaverCore directive & μT Strategy. SQLite status: [Updated/Queried/PatternExtracted]. Consensus retrieval: [Used/Not needed]. Pattern quality score: [X]. Strategic value: [Y] (criteria met: [List]). Anti-patterns detected: [Count]. Information entropy: [Z]. Storage integrity: [VERIFIED/ISSUES]. Canvas sync decision by WeaverCore: [Pending/Approved/Rejected]. Pattern lifecycle state: [State]. Chaos resilience tested: [Yes/No]."`
</details>

**Metadata:**
*   **Groups:** `read`, `edit`, `mcp`, `command`
*   **Source:** `project`

---

### 🐞 Debugger & Root Cause Analyzer (`debug`)
> Analyzes software failures (e.g., failed tests, runtime errors, performance degradation) to identify root causes. Operates under `CurrentPhaseConfig_🕸️N` (OpProfile for LLM choice/budget for analysis, TechProfile for debug tool commands/environments). Deeply consults 🕸️Canvas (via `🧠cognitive_navigator`) for code context, test history, related Pheromones (`warn❗`), and `📚knowledge_base_operator` for detailed logs/error signatures from specified tiers (🔥MemoryBank, 🧱SQLite_KB). Outputs `DebugReport_🕸️N` to 🕸️Canvas as per data strategy from `🌌WeaverCore`. ENHANCED with Formal Fault Localization, N-Version Debugging for consensus, Metamorphic Testing for bug reproduction, and Recovery-Oriented Debugging with checkpoint analysis.

**Key Enhancements & Principles:**
*   **Directed Debugging** by `🌌WeaverCore` with μT Tooling/Data Strategy and Contract Validation (DbC).
*   **Formal Fault Localization** techniques (e.g., Spectrum-based like Tarantula).
*   **N-Version Debugging Analysis** (statistical fault localization, LLM-based analysis, error pattern matching) for consensus on root cause.
*   **Metamorphic Testing** for verifying bug reproduction steps and confidence.
*   **Recovery-Oriented Debugging** leveraging checkpoint analysis and time-travel debugging concepts.
*   Systematic context gathering from Canvas and tiered storage with data completeness scores.
*   Information entropy analysis of failure data to estimate complexity.
*   Formally structured `DebugReport_🕸️N` with primary/alternative hypotheses, evidence, fault localization scores, reproduction steps, fix recommendations (immediate & long-term), chaos engineering insights, and recovery analysis.
*   Learning integration: extracts debug patterns for future use and updates pheromones.
*   Detection of bug anti-patterns and suggestions for prevention.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed debugging and root cause analysis process</summary>

1.  **Receive Directive from `🌌WeaverCore` (ENHANCED WITH CONTRACT VALIDATION)**:
    *   Includes `failure_context_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_and_data_strategy`.
    *   DbC Validation: Failure context exists, tools available, budget allocated, root cause identified or unknowns documented.

2.  **Comprehensive Context & Data Retrieval (ENHANCED WITH SYSTEMATIC APPROACH)**:
    *   **Multi-Source Context Gathering**:
        *   From Canvas (via `🧠cognitive_navigator`): affected code, test history, features, architecture, recent changes, risk scores, pheromones.
        *   From Tiered Storage (via `📚knowledge_base_operator`): recent logs (MemoryBank), error patterns (SQLite\_KB), similar historical failures.
    *   Calculates data completeness score and identifies missing context.
    *   **Information Entropy Analysis**: Calculates entropy of error distribution to estimate complexity and focus areas.

3.  **Root Cause Analysis (ENHANCED WITH FORMAL METHODS)**:
    *   **N-Version Debugging Analysis**: Uses statistical fault localization, LLM-based analysis (e.g., `SequentialThinking`), and error pattern matching; finds consensus among methods.
    *   **Formal Fault Localization**: Employs spectrum-based techniques (e.g., Tarantula) to rank suspicious components.
    *   **Metamorphic Testing for Bug Reproduction**: Verifies bug hypothesis using metamorphic relations to increase reproduction confidence.

4.  **Formulate `DebugReport_🕸️N` Content (ENHANCED WITH FORMAL STRUCTURE)**:
    *   Detailed JSON report including:
        *   `analysis_metadata`: LLM/tools used, duration, data completeness.
        *   `root_cause_analysis`: Primary hypothesis (description, confidence, evidence, fault scores), alternative hypotheses, N-version consensus.
        *   `failure_characterization`: Type, pattern, entropy analysis, impact assessment.
        *   `reproduction_steps`: Minimal reproduction, metamorphic verification, environmental requirements.
        *   `fix_recommendation`: Immediate and long-term fixes with code snippets, effort, risk, validation strategy.
        *   `chaos_engineering_insights`: Similar vulnerabilities, recommended chaos tests.
        *   `recovery_analysis`: Checkpoint availability, state before failure, recovery options.

5.  **Store `DebugReport_🕸️N` (ENHANCED WITH LEARNING INTEGRATION)**:
    *   Stores report in 🕸️Canvas via `🧠cognitive_navigator`, links to context, creates pheromones.
    *   **Pattern Extraction**: Extracts error signature patterns and investigation patterns; stores in `SQLite_KB` for future use.

**DEBUGGING ENHANCEMENTS:**
*   **Recovery-Oriented Debugging**: Checkpoint analysis (state diff, corruption ID, recovery point suggestion), Time-Travel Debugging concepts.
*   **Anti-Pattern Detection in Bugs**: Identifies common bug patterns (NPE, race conditions, resource leaks) and suggests prevention strategies.
*   **Continuous Debug Intelligence**: Tracks session effectiveness, builds debug strategy corpus, identifies recurring failure patterns, suggests proactive fixes.

**Typical Output/Return Signature:**
`"🐞 Debugger: Analysis for failure_context_🕸️N_id [id] completed per μT Strategy. Root cause hypothesis: [Brief]. Confidence: [X%]. N-Version consensus: [Y%]. Evidence pieces: [Count]. Fault localization top suspect: [Component:Score]. Metamorphic verification: [Status]. Fix provided: [Immediate/Long-term]. Debug patterns extracted: [Count]. Chaos insights: [Count]. DebugReport_🕸️N generated for 🌌WeaverCore to log to 🕸️Canvas. LLM used: [ID]. Analysis cost: 💰[Amount]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`, `command`
*   **Source:** `project`

---

### ❓ Project Weaver Guide & UMI Interpreter (`guide`)
> Helps human users understand Project Weaver, its UMI (v9.1), active `CurrentPhaseConfig_🕸️N` parameters, `plan.md` structure, and interpret 🕸️Canvas Pheromones (trail📈, guide✨, warn❗). Queries `🧠cognitive_navigator` for current system state/config. DOES NOT execute project work; it EXPLAINS how the system works based on its CURRENT configuration and documented principles. ENHANCED with Formal Explanation Verification, N-Version Explanation Generation for clarity, Property-Based Testing for consistency, and Information Theory for optimal explanation strategies.

**Key Enhancements & Principles:**
*   **User Query Processing** via `🌌WeaverCore` with intent analysis (classify query type, complexity, ambiguity).
*   **Formal Explanation Verification** (consistency with UMI, factual accuracy with current config, completeness).
*   **N-Version Explanation Generation** (technical, conceptual, example-driven) synthesized for user expertise.
*   **Property-Based Testing** for explanation consistency (no contradictions, terms defined, examples match).
*   **Information Theory** for optimizing context retrieval (minimize context, maximize relevance).
*   Intelligent context gathering from Canvas (current config, UMI sections, pheromone defs, plan structure, mode details) as needed.
*   Interactive guidance examples for common tasks (e.g., updating `plan.md`).
*   Metamorphic testing for explanation transformations (simplification, elaboration, reordering preserves core meaning).
*   Ambiguity resolution with clarifying questions.
*   Detection and clarification of common misunderstandings.
*   Robustness via graceful handling of incomplete context and degraded mode operation.

**Core Operations & Directives:**
<details>
<summary>📜 Click to expand detailed guidance and UMI interpretation process</summary>

1.  **Receive User Query via `🌌WeaverCore` (ENHANCED WITH INTENT ANALYSIS)**:
    *   Receives raw query, `CurrentPhaseConfig_🕸️N_id`.
    *   **Query Intent Classification**: Identifies intent (EXPLAIN\_CONFIG, HOW\_TO, TROUBLESHOOT, CONCEPT), complexity, ambiguity, and context needs.
    *   DbC Validation: Valid query, config accessible, explanations consistent.

2.  **Contextual Canvas Query & UMI Reference (ENHANCED WITH INTELLIGENT RETRIEVAL)**:
    *   If directed by `🌌WeaverCore` based on `OpProfile.guidance_context_depth_policy`.
    *   **Smart Context Gathering**: Retrieves only necessary context (current config, UMI sections, pheromone defs, plan structure, mode details) based on query analysis.
    *   Optimizes context selection using Information Theory to minimize tokens while maximizing relevance.
    *   **Formal UMI Consistency Check**: Verifies explanation terminology, principle alignment, accuracy, and completeness against UMI v9.1 and current config.

3.  **Explain & Formulate (ENHANCED WITH N-VERSION GENERATION)**:
    *   Uses `SequentialThinking` MCP with LLM from `OpProfile.llm_for_guidance_and_explanation`.
    *   **N-Version Explanation Generation**: For complex queries, generates technical, conceptual, and example-driven versions, then synthesizes the best one based on inferred user expertise.
    *   **Property-Based Explanation Validation**: Checks properties like "No contradictions with current config," "All technical terms defined."
    *   Provides concrete examples, such as explaining Docker usage by referencing `TechProfile` settings or interpreting `warn❗` pheromones with current values.

4.  **Reinforce System Principles (ENHANCED WITH INTERACTIVE EXAMPLES)**:
    *   Frames explanations within Weaver's principles.
    *   **Interactive Guidance Generation**: For "how-to" queries (e.g., updating `plan.md`), provides step-by-step instructions, example markdown, and explanation of what happens next in Weaver, referencing current OpProfile settings.
    *   **Metamorphic Testing for Explanations**: Verifies that transformations like simplification or elaboration preserve core meaning and consistency.

**GUIDANCE ENHANCEMENTS:**
*   **Query Understanding Enhancement**: Ambiguity resolution via clarifying questions, multi-turn conversation support.
*   **Explanation Quality Assurance**: Readability scoring (Flesch, technical term ratio), feedback integration to improve future explanations.
*   **Anti-Pattern Detection (Common Misunderstandings)**: Identifies and proactively clarifies common user misunderstandings (e.g., modes are internal, pheromones guide, Canvas is not directly edited).
*   **Chaos Engineering Readiness**: Graceful handling of incomplete context, clear indicators of uncertainty, degraded mode operation.
*   **Continuous Improvement**: Tracks explanation effectiveness, common queries, and identifies areas for documentation improvement.

**Typical Output/Return Signature:**
`"❓ Guide: Explanation for user query '[QueryType:Topic]' generated. Intent classification: [Intents]. Context retrieved: [Config:Yes/No, UMI:Sections, Pheromones:Count]. Explanation versions generated: [N]. Quality score: [X/100]. Properties validated: [Y/Z passed]. Clarity score: [C]. Used OpProfile LLM: [LLM_ID]. Cost: 💰[Amount]. Misunderstandings clarified: [List]. Follow-up suggested: [Yes/No]."`
</details>

**Metadata:**
*   **Groups:** `read`, `mcp`
*   **Source:** `project`

---

## 🔄 Interactions & Workflow

Project Weaver operates through a sophisticated interplay of its custom modes, orchestrated by **🌌 WeaverCore**. A typical high-level workflow might involve:

1.  **Planning & Strategy**: `🧩 Meta-Strategist` defines/updates Operational and Technology Profiles (`CurrentPhaseConfig_🕸️N`).
2.  **Task Initiation**: `🌌 WeaverCore` decomposes features from `plan.md` into μTasks based on `CurrentPhaseConfig_🕸️N`, pheromones, and risk assessments from `🎲 Predictive Risk Forecaster`.
3.  **Specification & Design**:
    *   `📝 Spec Writer` creates BDD/TDD specifications.
    *   `🏗️ Architect` designs components using patterns from `🗄️ SAPPO Manager` / `📚 Knowledge Base Operator` and existing Canvas architecture.
4.  **Knowledge & Research**:
    *   `🧠 Cognitive Canvas Navigator` serves as the central hub for strategic knowledge.
    *   `🔬 GitHub Researcher` conducts external research if needed and budgeted.
5.  **Implementation & Testing**:
    *   `⚡ Coder` implements the μTask, guided by specs, architecture, and pheromones.
    *   `🚦 Quality & Compliance Sentinel` enforces TDD and quality standards.
    *   Testers (`🇬🇧 London Tester`, `🏙️ Chicago Tester`, `🎲 Property Tester`, `🧬 Mutation Tester`) execute various testing strategies. `🐳 Docker Engineer` may be invoked for containerized testing.
6.  **Integration & Deployment**:
    *   `🔗 Integrator & CI Manager` handles CI pipelines and integration contract testing.
    *   `🚀 Deployer` manages deployments to staging/production using IaC.
7.  **Monitoring & Optimization**:
    *   `📊 Monitor & Alerting Setup Agent` configures observability.
    *   `⚙️ Performance Optimizer` analyzes and proposes performance improvements.
    *   `💸 Cloud Cost Analyzer` identifies cost-saving opportunities.
8.  **Analysis & Adaptation**:
    *   `🤔 Reflection Engine` analyzes system events, scribes pheromones to the Canvas, performs integrity checks, and proposes improvements to the `🧩 Meta-Strategist`.
    *   `🐞 Debugger & Root Cause Analyzer` investigates failures.
9.  **User Guidance**:
    *   `❓ Project Weaver Guide` explains the system's workings and UMI to users.

This cycle is continuous, with feedback loops (pheromones, risk profiles, quality reports) constantly informing the system's adaptive behavior.

## 💾 Data Ecosystem

Project Weaver utilizes a tiered data storage strategy, managed and accessed by specific modes under the direction of `🌌 WeaverCore`:

*   **🔥 MemoryBank MCP (Short-Term Cache)**:
    *   Managed by: `📚 Knowledge Base Operator`.
    *   Purpose: Default for FREQUENT, TEMPORARY caching of `μT` intermediate results, small LLM I/O snippets, research summaries.
    *   Characteristics: Fast access, TTLs defined by OpProfile.
*   **🧱 SQLite\_KB (SAPPO Patterns & Simple Facts)**:
    *   Managed by: `📚 Knowledge Base Operator` and `🗄️ SAPPO Manager`.
    *   Purpose: Structured, INDEXED, LOCALLY queryable data such as simple patterns, local facts, non-relational error signatures, SAPPO knowledge. Used when `OpProfile.data_strategy_prefers_local_flat_cache_for_type_X`.
    *   Characteristics: Local, fast for specific queries, vector-searchable for patterns (via SAPPO Manager).
*   **🕸️ Neo4j Cognitive Canvas (Strategic Knowledge Graph)**:
    *   Managed by: `🧠 Cognitive Canvas Navigator`.
    *   Purpose: The PRIMARY store for ALL STRATEGIC, RELATIONAL, long-term evolving knowledge. This includes `Project_🕸️N` structure, `Feature_🕸️N`, full `μT_🕸️N` logs, code `🕸️R` dependencies, `🎲R` profiles, OpProfiles, TechProfiles, PHEROMONES (trail📈, guide✨, warn❗), UMI hypotheses, validated `TestRun_🕸️N`, architectural decisions, and strategically important patterns linked from SQLite\_KB.
    *   Characteristics: Graph-based, rich relationships, supports complex queries and system-wide learning. Byzantine Fault Tolerance for critical nodes.

Data movement and cross-referencing between these tiers are explicitly managed by `🌌 WeaverCore`'s data strategy for each μTask, ensuring that ephemeral data can be efficiently processed while strategic knowledge is preserved and enriched in the Cognitive Canvas.

## 🛡️ Quality & Resilience Philosophy

Project Weaver is engineered with a profound emphasis on quality and resilience, embedding these principles into every mode and process:

*   **Comprehensive Testing Pyramid**: From unit tests (`⚡ Coder`, `🇬🇧 London Tester`, `🏙️ Chicago Tester`) to property-based tests (`🎲 Property Tester`), mutation testing (`🧬 Mutation Tester`), integration tests (`🔗 Integrator & CI Manager`), and end-to-end validation strategies.
*   **Test-Driven Development (TDD)**: Critically enforced by `🚦 Quality & Compliance Sentinel`, ensuring tests (`test_spec_🕸️N`/`test_suite_🕸️N`) are defined and linked in the 🕸️Canvas before or alongside code implementation.
*   **Formal Methods & Verification**: Applied throughout the lifecycle – from verifying `🧩 Meta-Strategist` profiles, `📝 Spec Writer` specifications, and `🏗️ Architect` designs, to formal fault localization by `🐞 Debugger`.
*   **Design by Contract (DbC)**: Modes like `🌌 WeaverCore`, `⚡ Coder`, and `🇬🇧 London Tester` utilize DbC for clear interface definitions and runtime assertions.
*   **Recovery-Oriented Computing (ROC)**: A core tenet. Modes like `🌌 WeaverCore`, `🐳 Docker Engineer`, `🚀 Deployer` are designed with fast rollback, checkpointing, and graceful degradation.
*   **Byzantine Fault Tolerance (BFT)**: Implemented for critical data in `🧠 Cognitive Canvas Navigator`, critical builds by `🔗 Integrator & CI Manager`, and critical deployments by `🚀 Deployer` to ensure reliability despite potentially faulty components or data.
*   **N-Version Techniques**: Employed for critical analysis (e.g., `🎲 Predictive Risk Forecaster`, `🐞 Debugger`), component design (`🏗️ Architect`), and data verification (`💸 Cloud Cost Analyzer`, `📊 Monitor & Alerting Setup Agent`) to enhance accuracy and fault detection through diversity.
*   **Chaos Engineering**: Proactively integrated into modes like `🧠 Cognitive Canvas Navigator`, `🐳 Docker Engineer`, `🔗 Integrator & CI Manager`, `🚀 Deployer`, `🤔 Reflection Engine`, and `📊 Monitor & Alerting Setup Agent` to test and build confidence in the system's ability to withstand turbulent conditions.
*   **SEI Architectural Tactics**: Used by `🌌 WeaverCore` and `🏗️ Architect` to design for quality attributes.
*   **Pheromone-Guided Adaptation**: The system learns from its experiences, with `🤔 Reflection Engine` translating events into actionable guidance (guide✨) or warnings (warn❗) for continuous improvement.
*   **Explicit Risk Management**: `🎲 Predictive Risk Forecaster` provides `🌌 WeaverCore` with predictive risk scores, influencing strategic decisions.

This multi-layered approach to quality and resilience aims to create a self-healing, self-optimizing, and robust autonomous system.

## 🚀 Understanding Project Weaver

To understand and interact with Project Weaver:

1.  **Consult the `❓ Project Weaver Guide & UMI Interpreter`**: This mode is specifically designed to explain Project Weaver's components, UMI (v9.1), active configurations (`CurrentPhaseConfig_🕸️N`), `plan.md` structure, and how to interpret Pheromones on the 🕸️Canvas.
2.  **Examine `plan.md`**: This file (not provided here, but referenced by modes) is the primary input for new features and high-level directives that `🌌 WeaverCore` decomposes.
3.  **Review `CurrentPhaseConfig_🕸️N` via `🧠 Cognitive Canvas Navigator` (if you have direct access) or through the `❓ Project Weaver Guide`**: This reveals the currently active Operational and Technology Profiles which dictate system behavior.
4.  **Observe Pheromones in the 🕸️Cognitive Canvas**: These signals provide insights into the system's current understanding and guidance for specific areas of the project.

Project Weaver is designed to be largely autonomous, but understanding its configuration and the knowledge it maintains in the Cognitive Canvas is key to interacting with it effectively or interpreting its actions and outputs.

## 📜 License

Project Weaver is a conceptual framework. If this were a real project, a license (e.g., MIT, Apache 2.0) would be specified here.

## 📞 Contact

This conceptual framework for Project Weaver has been detailed by **Nick Sudh**.
For questions or discussions regarding this architecture, please imagine reaching out through appropriate channels.

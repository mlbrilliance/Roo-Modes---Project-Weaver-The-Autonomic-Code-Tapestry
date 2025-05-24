# Project Weaver Plan: [PROJECT_NAME] - Autonomic Development Blueprint  weaver_plan_v1.0 (ULTRA_GRANULAR_EDITION)

**Project ID (🕸️N_project_id):** `[AUTO_GENERATED_OR_USER_DEFINED_UNIQUE_ID]`
**Project Weaver Version Context:** `UMI v9.0 - Autonomic Tapestry Edition`
**Date Created:** `YYYY-MM-DD`
**Last Updated:** `YYYY-MM-DD`
**Overall Goal:** `[Clear, concise statement of what this project aims to achieve. E.g., "Develop a scalable, secure, multi-tenant SaaS platform for real-time collaborative document editing with AI-powered suggestions and version control."]`

---

## 🎯 Section 1: Project Initialization & Ecosystem Setup (Phase: `SYS_INIT_ECO_001`)

**Pheromone Focus (Initial trail📈 for this Phase):** `ecosystem_bootstrap_critical_path`
**Objective:** Establish, verify, and document all foundational infrastructure, services, security baselines, core 🕸️Cognitive Canvas entries, and initial project governance required for sustained autonomous development.

### 1.1. Define Core Project Charter in 🕸️Cognitive Canvas (μT_SYS_INIT_CHARTER_001)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` -> `🧠cognitive_navigator`
    *   **Task Description:** Create/Update the primary `Project_🕸️N` in the 🕸️Cognitive Canvas with comprehensive charter metadata.
    *   **Input Data:**
        *   `project_name`: "[PROJECT_NAME]"
        *   `project_vision`: "[Longer-term vision for the project beyond initial goal]"
        *   `project_goal_primary`: "[Overall Goal Statement from above]"
        *   `project_scope_inclusions`: "[Bulleted list of key things IN scope]"
        *   `project_scope_exclusions`: "[Bulleted list of key things OUT of scope]"
        *   `stakeholders_primary_🕸️N_ids`: `["USER_STAKEHOLDER_GROUP_01", "BUSINESS_OWNER_01"]` (Conceptual, link to stakeholder 🕸️Ns if they exist)
        *   `initial_op_profile_preference`: "[e.g., MAX_QUALITY_SETUP, BALANCED_INIT]"
        *   `initial_tech_profile_preference`: "[e.g., PYTHON_FASTAPI_POSTGRES_REACT_DOCKER_AWS, JAVA_SPRING_MYSQL_ANGULAR_K8S_AZURE]"
        *   `estimated_complexity_🎲R_initial`: `[Low/Medium/High/VeryHigh]`
        *   `target_milestone_1_date_estimate`: `[YYYY-MM-DD]`
        *   `budget_code_🏦_initial_allocation`: `[Currency Amount or Computational Units]`
    *   **Action (Conceptual, by `🧠cognitive_navigator`):** Cypher to create/update `Project_🕸️N` and link to preferred `🕸️N_op_profile` and `🕸️N_tech_profile`. Also create `🏦Budget_🕸️N` and link to `Project_🕸️N`.
    *   **Deliverables:** Rich `Project_🕸️N` and linked `🏦Budget_🕸️N` in 🕸️Canvas.
    *   **Pheromone Update:** Set `priority_pheromone_strength_trail📈` on `μT_SYS_INIT_NEO4J_VERIFY_002`.
    *   **Success Criteria (🚦):** All specified metadata accurately stored and linked in 🕸️Canvas.

### 1.2. Infrastructure Setup: 🕸️Cognitive Canvas (Neo4j) Deep Verification & Schema Seeding (μT_SYS_INIT_NEO4J_VERIFY_002)
    *   **Assignee:** `🌌WeaverCore` -> `🧠cognitive_navigator` (assisted by `🛡️canvas_auditor` concepts if available)
    *   **Task Description:** Deeply verify Neo4j instance: connectivity, version, edition, license (if applicable), storage, performance baseline. Seed core schema indices & constraints.
    *   **Prerequisites:** Neo4j running, credentials `${env:NEO4J_...}` available.
    *   **Action (by `🧠cognitive_navigator` script/MCP):**
        1.  Connect & retrieve DBMS info (`CALL dbms.components()`). Log to `Infrastructure_🕸️N {type: 'Neo4jInstance'}`.
        2.  Retrieve storage metrics (`CALL dbms.queryJfr('list')`, `CALL dbms.metrics()`). Log to `Neo4jInstance_🕸️N` properties.
        3.  Execute a simple write/read/delete benchmark query. Log performance ms to `Neo4jInstance_🕸️N`.
        4.  Apply core indices/constraints for essential 🕸️N labels defined in UMI (e.g., `MicroTask.μT_id`, `Feature.feature_id`, `OperationalProfile.profile_name`, etc. from `umi_weaver.txt`). Ensure idempotency (IF NOT EXISTS).
    *   **Deliverables:** Detailed Neo4j instance profile in 🕸️Canvas. Core schema constraints/indices applied.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_MCP_VERIFY_003`.
    *   **Success Criteria (🚦):** All verifications pass. Schema elements created successfully. Performance baseline recorded.

### 1.3. Infrastructure Setup: Core MCP Server Comprehensive Verification & Configuration Logging (μT_SYS_INIT_MCP_VERIFY_003)
    *   **Assignee:** `🌌WeaverCore` -> `🎛️mcp_coordinator`
    *   **Task Description:** Comprehensively verify connectivity, version, and KEY configuration parameters of ALL essential MCP servers. Log this to individual `MCPInstance_🕸️N` nodes in 🕸️Canvas.
    *   **Action (by `🎛️mcp_coordinator`):**
        *   For EACH MCP (`MemoryBank🔥`, `Context7`, `SequentialThinking`, `PerplexityAsk`, custom Neo4j MCP if exists):
            1.  Ping/Health Check: `use_mcp_tool [MCP_Name] get_health_status`.
            2.  Version Info: `use_mcp_tool [MCP_Name] get_version_info`.
            3.  Key Configs (if MCP API supports): `use_mcp_tool [MCP_Name] get_active_config_summary` (e.g., for MemoryBank: current DB backend, default TTL; for Context7: Upstash connection status).
            4.  Log all data to respective `MCPInstance_🕸️N` in 🕸️Canvas, linked to `Project_🕸️N`.
    *   **Deliverables:** Detailed status and config logs for all core MCPs in 🕸️Canvas.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_CLOUD_VERIFY_004`. Strong `warn❗` on `Project_🕸️N` and relevant `MCPInstance_🕸️N` if any critical MCP is down/misconfigured.
    *   **Success Criteria (🚦):** All core MCPs fully operational and configurations logged.

### 1.4. Infrastructure Setup: Cloud Provider Service & Billing Verification (μT_SYS_INIT_CLOUD_VERIFY_004)
    *   **Assignee:** `🌌WeaverCore` -> `☁️cloud_architect` (using provider CLI tools via `execute_command` or provider-specific MCPs)
    *   **Task Description:** Verify access to required cloud services (e.g., Vertex AI for Gemini, Anthropic API endpoint), check current billing status/alerts, and log essential quota information for the primary LLMs into 🕸️Canvas.
    *   **Action (by `☁️cloud_architect`):**
        1.  For each primary LLM provider (Google, Anthropic, OpenAI):
            *   Attempt a minimal, non-billable API call (e.g., list models) to verify authentication & service health.
            *   Programmatically check (if API allows) or link to manual check for current API quota usage and limits.
            *   Check billing account status/alerts.
        2.  Log results (service reachability, key quota limits like TokensPerMinute, RequestsPerMinute) to `CloudProviderService_🕸️N` (e.g., `GoogleVertexAI_🕸️N`) in 🕸️Canvas, linked to `Project_🕸️N`.
    *   **Deliverables:** Cloud LLM service connectivity and key quota/billing status points logged in 🕸️Canvas.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_GIT_SETUP_005`. `warn❗` if billing issues or near quota limits.
    *   **Success Criteria (🚦):** All essential cloud services verified. Critical info logged.

### 1.5. Version Control & Secure Project Workspace Setup (μT_SYS_INIT_GIT_SETUP_005)
    *   **Assignee:** `🌌WeaverCore` (using `execute_command`) -> `🛡️security_auditor` (for secret management advice)
    *   **Task Description:** Ensure robust Git setup: initialize repo, detailed `.gitignore` (from template in 🕸️N_tech_profile or master template), establish branch strategy (e.g., `main`, `develop`, `feature/`), configure pre-commit hooks for basic linting/secret scanning (conceptual, may require manual setup of hooks or a script called by `execute_command`). Secure management of API keys/secrets (e.g., advise on `.env` use, SOPS, Vault - actual implementation external but audited).
    *   **Actions:**
        1.  `execute_command`: `git init`, `mkdir -p src tests docs scripts .roo .vscode .secrets` (conceptual for secrets, actual dir name may vary).
        2.  `🧠cognitive_navigator`: Fetch comprehensive `.gitignore` (`🕸️N_gitignore_template_advanced`) and write to project.
        3.  `🛡️security_auditor`: (Conceptually) Provides best-practice instructions for setting up `.env.example`, and for manually configuring a secrets management solution (like Doppler, Vault, or git-secret) externally. This task *documents* the chosen method.
        4.  `execute_command`: Set up basic Git branch structure: `git checkout -b develop`, `git checkout -b main`.
        5.  `execute_command` (if `🕸️N_tech_profile` has pre-commit hook config): `pre-commit install` (assumes `pre-commit` is installed and a `.pre-commit-config.yaml` is provided/generated based on `🕸️N_tech_profile`).
        6.  `execute_command`: `git add .gitignore README.md plan.md roo_modes_*.json umi_*.txt .env.example`
        7.  `execute_command`: `git commit -m "chore(project_weaver): Secure VCS workspace established with branch strategy, .gitignore, and secrets management protocol"`
    *   **Deliverables:** Secure Git repo. Advanced `.gitignore`. Documented secrets management strategy (`SecretsManagement_🕸️N_doc` in Canvas). Branching strategy defined (`BranchingStrategy_🕸️N_doc`). Pre-commit hooks conceptually active.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_PROFILE_LOCK_006`.
    *   **Success Criteria (🚦):** Git setup complete as specified. Secrets protocol documented.

### 1.6. Confirm, Lock, & Detail Active Operational & Tech Profiles (μT_SYS_INIT_PROFILE_LOCK_006)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist`
    *   **Task Description:** `🧩meta_strategist` deeply analyzes project charter (from `μT_SYS_INIT_CHARTER_001`) and current infrastructure status (from previous μTs). Confirms, refines, or selects the definitive `🕸️N_op_profile` and `🕸️N_tech_profile` for the project's initial development phase. All parameters of these selected profiles are explicitly logged into a `CurrentPhaseConfig_🕸️N` in Canvas for absolute clarity and auditability by other modes.
    *   **Action:**
        1.  `🧩meta_strategist` queries `🧠cognitive_navigator` for suitable profiles based on charter, potentially using `sequential_thinking` if choices have complex tradeoffs (e.g., new tech stack with unknown 🎲R vs. older stack with known limitations).
        2.  `🧩meta_strategist` makes a definitive selection.
        3.  `🧠cognitive_navigator` creates/updates `CurrentPhaseConfig_🕸️N` linked to `Project_🕸️N` and current `Phase_🕸️N` (e.g., `SYS_INIT_ECO_001_PhaseInstance_🕸️N`). This node will SNAPSHOT all critical parameters from the chosen OpProfile and TechProfile (e.g., `llm_for_coding: "claude-3.5-sonnet"`, `test_command: "pytest -s"`, `cost_threshold_μT: 0.005`, etc.).
    *   **Deliverables:** Explicit `CurrentPhaseConfig_🕸️N` with all operational parameters locked and logged for the current phase in 🕸️Canvas. Project now has unambiguous operational settings.
    *   **Pheromone Update:** Very strong `trail📈` from `Project_🕸️N` to "Section 2: Feature Development - [FIRST_FEATURE_NAME]" primary pheromone. System is GO.
    *   **Success Criteria (🚦):** `CurrentPhaseConfig_🕸️N` exists, is fully populated with all relevant parameters, and linked correctly.

---

## 💻 Section 2: Feature Development - [FEATURE_NAME_1] (Phase: `FEAT_DEV_001_[FeatureSlug]`)

**Parent Project ID (🕸️N_project_id):** `[ID_FROM_SECTION_1]`
**Active Configuration (CurrentPhaseConfig_🕸️N_id):** `[ID_FROM_μT_SYS_INIT_PROFILE_LOCK_006]` (All modes will reference this for current OpProfile & TechProfile parameters)
**Pheromone Focus (trail📈 for this Feature Phase):** `develop_feature_[FeatureSlug]` (initially set by `🤔reflection_engine` upon processing this section header by `🌌WeaverCore`)
**Overall Feature Goal:** `[High-level description of the feature]`
**Feature ID (🕸️N_feature_id):** `[AUTO_GEN_FeatureSlug_001]` (Created by `🌌WeaverCore` from section title, linked to `Project_🕸️N` and `CurrentPhaseConfig_🕸️N`)
**Estimated Story Points / Complexity (🎲R_feature_complexity):** `[e.g., 5, 8, 13 based on initial assessment, can be an LLM estimate]` (Stored on `Feature_🕸️N`)

*(The `CurrentPhaseConfig_🕸️N_id` is critical; all modes operating on this feature will first query `🧠cognitive_navigator` for its parameters to know which LLMs to use, cost limits, testing rigor, specific tool commands from TechProfile, etc., ensuring consistent, profile-driven behavior without repeating these in every μT prompt.)*

### 2.1. Deep Specification Elaboration & Validation Loop (Phase: `FEAT_SPEC_[FeatureSlug]_SUBPHASE_001`)

#### 2.1.1. Generate Initial Detailed Specifications (μT_FEAT_[FeatureSlug]_SPEC_DRAFT_001.1)
    *   **Assignee:** `🌌WeaverCore` -> `📝spec_writer`
    *   **Input:** `Feature_🕸️N_id` (goal, context). Reference `CurrentPhaseConfig_🕸️N_id`.
    *   **Task Description:** Generate detailed BDD scenarios (Given/When/Then), TDD test anchors (specific test case names and objectives), user stories (As a [user type], I want [action], so that [benefit]), non-functional requirements (performance, security from `Project_🕸️N_standards` or OpProfile), and data model sketches (if applicable for the feature). Query `🧠cognitive_navigator` for `🕸️P_related_specs` and `warn❗`/`guide✨` pheromones concerning similar features. Resolve ambiguities via UMI Ambiguity Protocol 🚩 if necessary (could trigger sub-μTs like `μT_FEAT_..._SPEC_AMBIGUITY_RESOLVE_X`).
    *   **Deliverables:** Draft `feature_spec_detail_🕸️N` created in 🕸️Canvas, linked to `Feature_🕸️N`. Text file `docs/specs/[feature_slug]_spec_draft_v1.md`.
    *   **Pheromone Update:** `trail📈` on `μT_FEAT_[FeatureSlug]_SPEC_REVIEW_001.2`.
    *   **Success Criteria (🚦):** Draft spec fully populated as per requirements. Stored.

#### 2.1.2. Automated Spec Review & Consistency Check (μT_FEAT_[FeatureSlug]_SPEC_REVIEW_001.2)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (conceptually, using `sequential_thinking` or a dedicated "spec-analyzer" sub-mode if exists).
    *   **Input:** `feature_spec_detail_🕸️N` (draft).
    *   **Task Description:** Review draft spec for internal consistency, clarity, completeness against original Feature Goal, and alignment with project-wide non-functional requirements (from `Project_🕸️N_standards`). Check for conflicting requirements or overlaps with existing `feature_spec_🕸️N`s in Canvas (via `🧠cognitive_navigator`).
    *   **Deliverables:** `SpecReviewReport_🕸️N` linked to `feature_spec_detail_🕸️N`. List of issues/suggestions.
    *   **Pheromone Update:** If issues, `warn❗` on draft spec & `trail📈` back to `📝spec_writer` for revision `μT_FEAT_..._SPEC_REVISE_X`. If clear, `trail📈` to architecture or first code unit.
    *   **Success Criteria (🚦):** Review report generated. Spec status updated to `Validated` or `NeedsRevision`.

*(Iterate SPEC_DRAFT and SPEC_REVIEW μTs if revisions are needed until SpecReviewReport_🕸️N is PASS)*

### 2.2. Detailed Architectural Breakdown & Risk Analysis (Phase: `FEAT_ARCH_[FeatureSlug]_SUBPHASE_002`) - *Conditional as per OpProfile*

#### 2.2.1. Generate Architectural Options & Trade-offs (μT_FEAT_[FeatureSlug]_ARCH_OPTIONS_002.1)
    *   **Assignee:** `🌌WeaverCore` -> `🏗️architect`
    *   **Input:** Validated `feature_spec_detail_🕸️N`. `CurrentPhaseConfig_🕸️N_id` (for design patterns allowed, cost constraints). `Project_🕸️N_arch_principles`.
    *   **Task Description:** For the feature, propose 1-3 high-level architectural approaches (e.g., microservice vs. monolithic module, event-driven vs. request-response). Query `🧠cognitive_navigator` for existing `🕸️P_arch_patterns_used_in_project`, relevant `guide✨`/`warn❗` pheromones on patterns, and `🎲R_scores` of components to be interacted with. Document trade-offs (performance, complexity, cost, security) for each option.
    *   **Deliverables:** `ArchOptionsReport_🕸️N` linked to `feature_spec_detail_🕸️N`, containing multiple `ArchOption_🕸️N` sketches.
    *   **Pheromone Update:** `trail📈` on `μT_FEAT_[FeatureSlug]_ARCH_SELECT_002.2`.
    *   **Success Criteria (🚦):** Report with distinct options and trade-offs generated.

#### 2.2.2. Select & Detail Chosen Architecture (μT_FEAT_[FeatureSlug]_ARCH_SELECT_002.2)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (or `🏗️architect` if delegated by OpProfile, with `sequential_thinking` for decision logic).
    *   **Input:** `ArchOptionsReport_🕸️N`. `CurrentPhaseConfig_🕸️N_id` (for strategic fit). Feature 🎲R.
    *   **Task Description:** Analyze options. Select the optimal architecture. Fully detail it: define all new/modified `component_🕸️N`s, their responsibilities, APIs (`Interface_🕸️N`), data models (`DataModel_🕸️N`), and `🕸️R_interactions` (dependencies, data flows). Document ADR.
    *   **Cost Justification docs💰:** If chosen arch is high-cost.
    *   **Deliverables:** Final `architecture_design_🕸️N` linked to `feature_spec_detail_🕸️N`. ADR file. Updated component/interface/datamodel 🕸️Ns in Canvas.
    *   **Pheromone Update:** Strong `guide✨` from chosen `architecture_design_🕸️N` to various `component_🕸️N`s, guiding subsequent coding μTasks. `trail📈` to first coding μT.
    *   **Success Criteria (🚦):** Chosen architecture fully detailed, documented, and represented in 🕸️Canvas.

### 2.3. Iterative Code & Test Implementation Loop (Phase: `FEAT_CODE_TEST_[FeatureSlug]_SUBPHASE_003`)
*(For each `component_🕸️N` or logical code unit identified in the architecture/spec, a series of μTasks is executed)*

#### **Micro-Loop for Component/Unit: `[ComponentNameOrUnitSlug]`**

##### 2.3.[X].1. Define Test Cases (TDD - Tests First) (μT_FEAT_[FeatureSlug]_TESTDEF_[UnitSlug]_001)
    *   **Assignee:** `🌌WeaverCore` -> `📝spec_writer` or `⚡coder` (per OpProfile: strict TDD vs. BDD-to-Test).
    *   **Input:** Unit requirements from `feature_spec_detail_🕸️N` / `architecture_design_🕸️N`. `CurrentPhaseConfig_🕸️N_id` (`🕸️N_tech_profile` for test framework).
    *   **Task Description:** Write detailed, executable (but initially failing) test cases/stubs for `[ComponentNameOrUnitSlug]` in `tests/[path/to/test_unit.ext]`. Cover positive, negative, edge cases.
    *   **Deliverables:** Test code file created/updated. `TestCase_🕸️N` (or `TestSuite_🕸️N`) created in Canvas, linked to the conceptual `CodeModule_🕸️N` for this unit. TDD Status for this unit on `🚦quality_gatekeeper` prep: `DEFINED`.
    *   **Pheromone Update:** `trail📈` to `_CODEIMP_` for this unit. Strong `guide✨` from tests to code.
    *   **Success Criteria (🚦):** Test file and runnable (failing) stubs created. Test definitions logged in Canvas.

##### 2.3.[X].2. Implement Code Unit (μT_FEAT_[FeatureSlug]_CODEIMP_[UnitSlug]_002)
    *   **Assignee:** `🌌WeaverCore` -> `⚡coder`
    *   **Input:** Unit requirements, defined tests (`TestCase_🕸️N`). `CurrentPhaseConfig_🕸️N_id`. Relevant `guide✨`/`warn❗` pheromones.
    *   **Task Description:** Implement code for `[ComponentNameOrUnitSlug]` in `src/[path/to/code_unit.ext]` to make defined tests pass. Adhere to `🕸️N_tech_profile`.
    *   **Research:** As needed, budgeted by OpProfile, via `🧠cognitive_navigator` or `🔬github_researcher`.
    *   **Deliverables:** Source code written/updated. `CodeModule_🕸️N` / `Function_🕸️N` detailed in Canvas.
    *   **Pheromone Update:** `trail📈` to `_QUALCHK_` for this unit.
    *   **Success Criteria (🚦):** Code implemented. (Subject to Quality Gate).

##### 2.3.[X].3. Quality Gate Check for Code Unit (μT_FEAT_[FeatureSlug]_QUALCHK_[UnitSlug]_003) - MANDATORY
    *   **Assignee:** `🌌WeaverCore` -> `🚦quality_gatekeeper`
    *   **Input:** Path to code, corresponding test definitions (`TestCase_🕸️N` from Canvas), `CurrentPhaseConfig_🕸️N_id` (`🕸️N_tech_profile` for linters/standards).
    *   **Task Description:** Perform full static analysis, compliance, style checks. **Re-verify test definitions against implemented code structure to ensure coverage (not just existence).**
    *   **Deliverables:** PASS/FAIL. `quality_report_🕸️N` for this unit.
    *   **Pheromone Update:** If FAIL, `warn❗` on `_CODEIMP_` μT, `trail📈` to `⚡coder` for rework. If PASS, `trail📈` to `_TESTEXEC_`.
    *   **Success Criteria (🚦):** All checks PASS, including TDD alignment of tests to code.

##### 2.3.[X].4. Execute Unit Tests (μT_FEAT_[FeatureSlug]_TESTEXEC_[UnitSlug]_004)
    *   **Assignee:** `🌌WeaverCore` -> Appropriate Tester (from TechProfile, e.g., `🏙️chicago_tester`).
    *   **Input:** Test files, source code. Test command from `🕸️N_tech_profile`.
    *   **Task Description:** Execute unit tests for `[ComponentNameOrUnitSlug]`.
    *   **Deliverables:** `TestRun_🕸️N` (PASS/FAIL, coverage) in Canvas.
    *   **Pheromone Update:** If FAIL, `warn❗` on code/tests, `trail📈` to `🔍debugger`. If PASS, `guide✨` on `CodeModule_🕸️N`. Increment `trail📈` for next code unit or feature integration if this is the last unit.
    *   **Success Criteria (🚦):** All unit tests for this unit PASS. Coverage meets OpProfile threshold.

##### 2.3.[X].5. Debug Unit (If Tests Fail) (μT_FEAT_[FeatureSlug]_DEBUG_[UnitSlug]_005) - *Conditional*
    *   **Assignee:** `🌌WeaverCore` -> `🔍debugger`
    *   **Input:** Failed `TestRun_🕸️N`, source code `CodeModule_🕸️N`, relevant error context `warn❗` pheromones. OpProfile (for debug depth).
    *   **Task Description:** Diagnose and propose fix for failed unit tests.
    *   **Deliverables:** `DebugReport_🕸️N` with root cause and suggested fix. This fix then goes through a new mini `_CODEIMP_` -> `_QUALCHK_` -> `_TESTEXEC_` cycle.
    *   **Pheromone Update:** `🤔reflection_engine/scribe` logs debug path. If successful, `warn❗` on original error cause may be weakened.
    *   **Success Criteria (🚦):** Root cause identified. Actionable fix proposed.

*(End of Micro-Loop for Component/Unit. Repeat 2.3.[X].1 to 2.3.[X].5 for ALL units in the feature.)*

### 2.4. Feature Integration, System & E2E Testing Loop (Phase: `FEAT_INTEGRATE_TEST_[FeatureSlug]_SUBPHASE_004`)

#### 2.4.1. Define Feature Integration Test Plan (μT_FEAT_[FeatureSlug]_INTG_PLAN_001)
    *   **Assignee:** `🌌WeaverCore` -> `🏗️architect` or senior `🧪tester-definer`.
    *   **Input:** All PASSING `CodeModule_🕸️N`s for this feature, `architecture_design_🕸️N`. `CurrentPhaseConfig_🕸️N_id`.
    *   **Task Description:** Define test scenarios for interactions BETWEEN components of this feature, and between this feature and existing major system components (identified via `🧠cognitive_navigator` from `🕸️P_project_dependency_graph`). Consider high 🎲R interaction points.
    *   **Deliverables:** `IntegrationTestPlan_🕸️N` in Canvas, linked to `Feature_🕸️N`.
    *   **Pheromone Update:** `trail📈` to `_INTG_IMPL_`.
    *   **Success Criteria (🚦):** Comprehensive integration test plan defined.

#### 2.4.2. Implement Integration Tests (μT_FEAT_[FeatureSlug]_INTG_IMPL_002)
    *   **Assignee:** `🌌WeaverCore` -> `⚡coder` or `🧪tester-implementer`.
    *   **Input:** `IntegrationTestPlan_🕸️N`. `🕸️N_tech_profile` (for integration testing tools/frameworks).
    *   **Task Description:** Implement the integration tests.
    *   **Deliverables:** `IntegrationTestSuite_🕸️N` code and Canvas representation.
    *   **Pheromone Update:** `trail📈` to `_INTG_EXEC_`.
    *   **Success Criteria (🚦):** Tests implemented.

#### 2.4.3. Execute Integration Tests (μT_FEAT_[FeatureSlug]_INTG_EXEC_003)
    *   **Assignee:** `🌌WeaverCore` -> Specialized `🧪integration_tester` (if mode exists) or a general Tester.
    *   **Input:** `IntegrationTestSuite_🕸️N`. Staging environment context (if applicable from TechProfile).
    *   **Task Description:** Run all integration tests for the feature.
    *   **Deliverables:** `IntegrationTestRun_🕸️N` results (PASS/FAIL) in Canvas.
    *   **Pheromone Update:** If FAIL, `warn❗` on feature, `trail📈` to `🔍debugger`. If PASS, strong `guide✨` on `Feature_🕸️N` (stability).
    *   **Success Criteria (🚦):** All integration tests PASS.

#### 2.4.4. Define E2E User Acceptance Tests (UAT) (μT_FEAT_[FeatureSlug]_UAT_DEF_004) - *May involve `📝spec_writer` looking at user stories.*
    *   **Assignee:** `🌌WeaverCore` -> `📝spec_writer` or dedicated `🧪uat_designer`.
    *   **Input:** Original `feature_spec_detail_🕸️N` (user stories). `CurrentPhaseConfig_🕸️N_id`.
    *   **Task Description:** Define E2E test scenarios from a user perspective for the completed feature.
    *   **Deliverables:** `UAT_Scenario_🕸️N_Set` in Canvas.
    *   **Pheromone Update:** `trail📈` to `_UAT_EXEC_`.
    *   **Success Criteria (🚦):** UAT scenarios defined.

#### 2.4.5. Execute E2E / UAT (μT_FEAT_[FeatureSlug]_UAT_EXEC_005) - *May need browser automation tools or simulated user interaction MCP if GUI.*
    *   **Assignee:** `🌌WeaverCore` -> `🧪e2e_tester` (conceptual mode using tools like Selenium/Playwright via `execute_command` or MCP).
    *   **Input:** `UAT_Scenario_🕸️N_Set`. Deployed feature (e.g., on a staging env).
    *   **Task Description:** Execute E2E user acceptance tests.
    *   **Deliverables:** `UAT_Run_🕸️N` results (PASS/FAIL) in Canvas.
    *   **Pheromone Update:** If FAIL, `warn❗` on feature, `trail📈` to `🔍debugger`. If PASS, `trail📈` on `Feature_🕸️N` for `_DOC_` or `_DEPLOY_READY_` status.
    *   **Success Criteria (🚦):** All UAT scenarios PASS.

### 2.5. Documentation Generation & Review (Phase: `FEAT_DOC_[FeatureSlug]_SUBPHASE_005`)

#### 2.5.1. Draft Technical & User Documentation (μT_FEAT_[FeatureSlug]_DOC_DRAFT_001)
    *   **Assignee:** `🌌WeaverCore` -> `📚doc_writer`
    *   **Input:** PASSING `Feature_🕸️N` (with all linked specs, arch, code, tests). `CurrentPhaseConfig_🕸️N_id` (for doc style/detail). `guide✨` pheromones on urgent doc needs.
    *   **Task Description:** Create technical documentation (API docs, module descriptions) and user-facing documentation (how-to guides, feature explanations) for `[FEATURE_NAME_1]`. Query `🧠cognitive_navigator` for existing `🕸️N_doc_template` or `🕸️N_style_guide`.
    *   **Deliverables:** Draft `TechnicalDoc_🕸️N` and `UserDoc_🕸️N` linked to `Feature_🕸️N` in Canvas. Files in `docs/feature_slug/`.
    *   **Pheromone Update:** `trail📈` to `_DOC_REVIEW_`.
    *   **Success Criteria (🚦):** Draft documents created, cover essential aspects.

#### 2.5.2. Documentation Review (μT_FEAT_[FeatureSlug]_DOC_REVIEW_002)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (conceptually, using `sequential_thinking` or a "doc-reviewer" sub-mode).
    *   **Input:** Draft `TechnicalDoc_🕸️N` and `UserDoc_🕸️N`.
    *   **Task Description:** Review for clarity, accuracy, completeness, and style guide adherence.
    *   **Deliverables:** `DocReviewReport_🕸️N` for each doc type.
    *   **Pheromone Update:** If issues, `warn❗` on draft docs, `trail📈` back to `📚doc_writer` for revision. If clear, `Feature_🕸️N` `status_pheromone` becomes `READY_FOR_RELEASE_REVIEW`.
    *   **Success Criteria (🚦):** Docs reviewed, approved.

---

## 🚀 Section 3: Release Preparation & Deployment - [RELEASE_VERSION_X.Y.Z] (Phase: `REL_PREP_DEPLOY_XYZ`)

**Pheromone Focus (trail📈 for this Phase):** `release_candidate_XYZ_deployment_pipeline`
**Objective:** Package all completed and verified features, perform final release testing, and deploy `[RELEASE_VERSION_X.Y.Z]` to target environment(s) according to OpProfile strategy.

### 3.1. Release Candidate Branching & Versioning (μT_REL_BRANCH_VERSION_001)
    *   **Assignee:** `🌌WeaverCore` (using `execute_command` for Git).
    *   **Input:** List of `Feature_🕸️N`s tagged `READY_FOR_RELEASE_REVIEW`. Proposed version `X.Y.Z`.
    *   **Task Description:** Create a `release/X.Y.Z` branch from `develop`. Merge completed features into it. Tag the release candidate. Update version numbers in project files (e.g., `setup.py`, `package.json` via `⚡coder` with specific μT).
    *   **Deliverables:** `release/X.Y.Z` branch created. `vX.Y.Z-rc1` tag created. Version numbers updated. `ReleaseCandidate_🕸️N` in Canvas.
    *   **Pheromone Update:** `trail📈` on `_REL_BUILD_ARTIFACT_`.
    *   **Success Criteria (🚦):** Branch & tag exist. Version files updated.

### 3.2. Build Release Artifacts (μT_REL_BUILD_ARTIFACT_002)
    *   **Assignee:** `🌌WeaverCore` -> `🐳docker_engineer` or `☁️cloud_architect` (depending on TechProfile build system).
    *   **Input:** `release/X.Y.Z` branch. `🕸️N_tech_profile` (for build commands, Dockerfile paths, artifact repo info).
    *   **Task Description:** Build release artifacts (e.g., Docker images, JARs, WHEELs). Push to artifact repository.
    *   **Deliverables:** `Artifact_🕸️N` (with link to repo path/tag) in Canvas. Artifacts available in repository.
    *   **Pheromone Update:** `trail📈` to `_REL_STAGING_DEPLOY_`.
    *   **Success Criteria (🚦):** Build successful. Artifacts published.

### 3.3. Deploy to Staging Environment (μT_REL_STAGING_DEPLOY_003)
    *   **Assignee:** `🌌WeaverCore` -> `☁️cloud_architect`
    *   **Input:** `Artifact_🕸️N`. Staging environment config from `🕸️N_tech_profile` or specialized `Environment_🕸️N`.
    *   **Task Description:** Deploy the release candidate artifact to the staging environment.
    *   **Deliverables:** Staging deployment successful. `DeploymentLog_🕸️N` in Canvas.
    *   **Pheromone Update:** `trail📈` to `_REL_STAGING_TEST_`.
    *   **Success Criteria (🚦):** Deployment successful. Application healthy in staging.

### 3.4. Execute Full Regression & Smoke Tests on Staging (μT_REL_STAGING_TEST_004)
    *   **Assignee:** `🌌WeaverCore` -> `🧪comprehensive_tester_suite_runner` (conceptual mode running ALL relevant test suites: Unit, Integration, E2E/UAT).
    *   **Input:** Staging environment URL/access. All test suites linked to features in this release.
    *   **Task Description:** Run the full battery of automated tests against the staging deployment.
    *   **Deliverables:** `MasterTestReport_🕸️N` for staging in Canvas.
    *   **Pheromone Update:** If FAIL, strong `warn❗` on `ReleaseCandidate_🕸️N`, `trail📈` to `🔍debugger` (hotfix on release branch). If PASS, `status_pheromone` on `ReleaseCandidate_🕸️N` becomes `READY_FOR_PROD_APPROVAL`.
    *   **Success Criteria (🚦):** All tests PASS on staging.

### 3.5. Production Deployment Approval Gate (μT_REL_PROD_APPROVAL_005) - *May require human approval based on OpProfile / Risk*
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (with possible human interaction step based on OpProfile `prod_deployment_approval_policy`).
    *   **Input:** `ReleaseCandidate_🕸️N` status (`READY_FOR_PROD_APPROVAL`), `MasterTestReport_🕸️N` for staging. Associated 🎲R. Current `🏦project_budget_🕸️N`.
    *   **Task Description:** Review release candidate readiness. If OpProfile policy is `manual_approval_required`, PING human stakeholder via notification mechanism. Otherwise, `🧩meta_strategist` makes automated GO/NO-GO based on test results, remaining budget, and overall project 🎲R.
    *   **Deliverables:** `ProductionDeploymentApproval_🕸️N` (Approved/Rejected) in Canvas.
    *   **Pheromone Update:** If Approved, `trail📈` to `_REL_PROD_DEPLOY_`. If Rejected, `warn❗` and `trail📈` to debugging/rollback planning.
    *   **Success Criteria (🚦):** Explicit approval (automated or manual) logged.

### 3.6. Deploy to Production (μT_REL_PROD_DEPLOY_006)
    *   **Assignee:** `🌌WeaverCore` -> `☁️cloud_architect`
    *   **Input:** Approved `ReleaseCandidate_🕸️N` / `Artifact_🕸️N`. Production environment config. OpProfile (for deployment strategy: blue/green, canary, rolling).
    *   **Task Description:** Deploy to production using specified strategy. Execute smoke tests post-deployment.
    *   **Deliverables:** Production deployment successful. `ProdDeploymentLog_🕸️N` in Canvas.
    *   **Pheromone Update:** `status_pheromone` on `Release_Version_XYZ_🕸️N` (new node for actual release) becomes `LIVE`. `trail📈` for post-deployment monitoring.
    *   **Success Criteria (🚦):** Deployment successful. Critical smoke tests pass in production.

### 3.7. Post-Deployment Monitoring & Initial Feedback Loop (μT_REL_POST_MONITOR_007)
    *   **Assignee:** `🌌WeaverCore` -> `📊monitor_setup_agent` (conceptual: configures monitoring tools like Prometheus/Grafana/Sentry via scripts/APIs) & `🤔reflection_engine` (to watch for early `warn❗` pheromones).
    *   **Input:** `Release_Version_XYZ_🕸️N`. Monitoring tool configs from TechProfile.
    *   **Task Description:** Ensure monitoring dashboards are active for the new release. `🤔reflection_engine` monitors initial error rates, performance metrics from logging systems (conceptually fed into Canvas) for any immediate negative `trail📈` or new `warn❗` pheromones.
    *   **Deliverables:** Monitoring confirmed active. Initial (e.g., 1 hour) stability report summary `PostReleaseHealth_🕸️N` in Canvas.
    *   **Pheromone Update:** If anomalies, critical `warn❗` on `Release_Version_XYZ_🕸️N`. `trail📈` for normal operations or rollback planning if needed.
    *   **Success Criteria (🚦):** Monitoring active. No critical immediate post-deployment failures.

---

## 🔧 Section 4: System Operations & Autonomous Maintenance (Phase: `SYS_OPS_MAINTAIN_ONGOING`)

**Pheromone Focus (trail📈 types):** `system_maintenance`, `security_audit_cycle`, `refactor_opportunity_discovery`, `canvas_health_check`, `umi_evolution_experiment`
*(These are ongoing, cyclically triggered, or event-driven μTask families managed primarily by `🧩meta_strategist` and `🤔reflection_engine`.)*

### 4.1. Scheduled Tech Horizon Scanning Cycle (μT_MAINT_TECHSCAN_CYCLE_[Date])
    *   (As defined in `🤔reflection_engine` and UMI section XII.12.4)

### 4.2. Scheduled Cognitive Canvas Integrity Audit Cycle (μT_MAINT_CANVAS_AUDIT_CYCLE_[Date])
    *   (As defined in `🤔reflection_engine` and UMI section XIII.13.1)

### 4.3. Scheduled UMI/Mode Effectiveness Review & AMO Proposal Cycle (μT_MAINT_AMO_REVIEW_CYCLE_[Date])
    *   **Assignee:** `🌌WeaverCore` -> `🤔reflection_engine` -> `🧩meta_strategist`
    *   **Task Description:** `🤔reflection_engine` performs deep analysis of 🕸️Canvas for UMI/Mode effectiveness over last N μTasks or time period. Generates `🕸️N_improvement_hypothesis`. `🧩meta_strategist` reviews hypotheses, prioritizes, and schedules A/B tests or direct updates (if high confidence and low risk).
    *   **Deliverables:** `AMO_Report_🕸️N`. New/updated `🕸️N_improvement_hypothesis`. Log of A/B tests planned/executed.
    *   **Success Criteria (🚦):** Review cycle completed. Actionable hypotheses generated/tested.

### 4.4. Proactive Refactoring Identification & Planning Cycle (μT_MAINT_REFACTOR_ID_CYCLE_[Date])
    *   **Assignee:** `🌌WeaverCore` -> `🤔reflection_engine` -> `🏗️architect`
    *   **Task Description:** `🤔reflection_engine` scans 🕸️Canvas for technical debt indicators (high complexity `CodeModule_🕸️N`, frequent bugs in an area `🕸️P_bug_cluster`, strong `technical_debt_warn❗` pheromones). If candidates found, `🏗️architect` is tasked to create a `RefactoringPlan_🕸️N`. Approved plans become backlog features.
    *   **Deliverables:** `RefactoringCandidateReport_🕸️N`. Potential `RefactoringPlan_🕸️N`s.
    *   **Success Criteria (🚦):** Cycle completed. Candidates identified. High-priority refactoring plans created.

### 4.5. Budget Review & OpProfile Tuning Cycle (μT_MAINT_BUDGET_REVIEW_CYCLE_[Date])
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (consulting `💰cost_optimizer` analysis)
    *   **Input:** `🏦project_budget_🕸️N` current status, burn rate forecast from `🧠cognitive_navigator`, `Project_🕸️N` milestone dates.
    *   **Task Description:** Review budget status against project progress. Tune active `🕸️N_op_profile` parameters (e.g., default LLM choice, cost thresholds) to align with remaining budget and timelines. Consider shifting to/from `ULTRA_COST_SAVE_HIBERNATE` if necessary.
    *   **Deliverables:** `BudgetReviewReport_🕸️N`. Updated active `🕸️N_op_profile` parameters in Canvas.
    *   **Success Criteria (🚦):** Review complete. OpProfile tuned to current fiscal reality.

---

## 📖 Appendix A: Definitions & Conventions

*   **[PROJECT_NAME], [FeatureSlug], etc.:** Placeholders to be filled.
*   **🕸️N, 🕸️R, 🕸️P:** Refer to Nodes, Relationships, and Paths in the Cognitive Canvas.
*   **trail📈, guide✨, warn❗:** Pheromone types, typically as properties on 🕸️N or distinct 🕸️R types.
*   **🎲R:** Risk Score (property or linked 🕸️N).
*   **🚦:** Success criteria / Quality Gate status indicator.
*   **🔥:** MemoryBank MCP.
*   **🏦:** Budget / Cost considerations / Status (e.g., a property on `Project_🕸️N`).
*   **💡:** Generative Innovation Protocol.
*   **📡:** Tech Horizon Scanning.
*   **🛡️:** Cognitive Canvas Integrity.
*   **🚩:** Ambiguity Flag.
*   **docs💰:** Cost Justification documentation (could be a `Justification_🕸️N` linked to an expensive μT).
*   **μT_Phase_ShortName_Seq[.SubSeq]:** Micro-task naming for traceability.
*   **OpProfile / TechProfile:** Active Operational (`🕸️N_op_profile`) and Technology Stack (`🕸️N_tech_profile`) Profiles, defined in and queried from 🕸️Canvas via `🧠cognitive_navigator`, guide all mode behavior. Their parameters are SNAPSHOTTED into a `CurrentPhaseConfig_🕸️N` for auditable execution context of a specific phase.

---

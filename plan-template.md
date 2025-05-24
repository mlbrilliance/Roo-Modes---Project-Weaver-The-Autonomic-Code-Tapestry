# Project Weaver Plan: [PROJECT_NAME] - Autonomic Development Blueprint  weaver_plan_v1.1 (ULTRA_GRANULAR_EXPLICIT_STRATEGY_EDITION)

**Project ID (🕸️N_project_id):** `[AUTO_GENERATED_OR_USER_DEFINED_UNIQUE_ID]`
**Project Weaver Version Context:** `UMI v9.1 - Explicit Autonomic Weaver`
**Date Created:** `YYYY-MM-DD`
**Last Updated:** `YYYY-MM-DD`
**Overall Goal:** `[Clear, concise statement of what this project aims to achieve. E.g., "Develop a scalable, secure, multi-tenant SaaS platform for real-time collaborative document editing with AI-powered suggestions and version control."]`

---

## 🎯 Section 1: Project Initialization & Ecosystem Setup (Phase: `SYS_INIT_ECO_001`)

**Pheromone Focus (Initial trail📈 for this Phase):** `ecosystem_bootstrap_critical_path`
**Active Configuration (CurrentPhaseConfig_🕸️N_id for this section):** `[ID_TO_BE_CREATED_IN_μT_SYS_INIT_PROFILE_LOCK_005]` (Initially, modes use fallback/default until this is locked)
**Objective:** Establish, verify, and document all foundational infrastructure, services, security baselines, core 🕸️Cognitive Canvas entries, and initial project governance, resulting in a locked `CurrentPhaseConfig_🕸️N` for subsequent phases.

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
    *   **Action (Conceptual, by `🧠cognitive_navigator`):**
        ```cypher
        MERGE (p:Project {project_id: $projectId})
        ON CREATE SET p.name = $projectName, p.goal = $projectGoal, p.vision = $projectVision, p.scope_inclusions = $scopeInclusions, p.scope_exclusions = $scopeExclusions, p.initial_complexity_dice_r = $estimatedComplexityDiceR, p.target_milestone_1_date = $targetMilestoneDate, p.status = 'INITIALIZING', p.creation_date = datetime(), p.umi_version_context = 'UMI v9.1'
        ON MATCH SET p.name = $projectName, p.goal = $projectGoal, p.vision = $projectVision, p.scope_inclusions = $scopeInclusions, p.scope_exclusions = $scopeExclusions, p.initial_complexity_dice_r = $estimatedComplexityDiceR, p.target_milestone_1_date = $targetMilestoneDate, p.last_updated = datetime()
        WITH p
        MERGE (b:Budget {project_id: $projectId, type: "INITIAL_ALLOCATION"})
        ON CREATE SET b.amount = $initialBudget, b.currency_or_units = $budgetUnits, b.allocation_date = datetime()
        MERGE (p)-[:HAS_BUDGET]->(b)
        // Conceptual linking to stakeholder groups if those nodes exist
        // FOREACH (stakeholder_id IN $stakeholderIds |
        //   MATCH (s:StakeholderGroup {id: stakeholder_id})
        //   MERGE (p)-[:HAS_PRIMARY_STAKEHOLDER]->(s)
        // )
        RETURN p.project_id AS projectNodeId, b.amount AS budgetAmount;
        ```
    *   **Deliverables:** Rich `Project_🕸️N` and linked `🏦Budget_🕸️N` in 🕸️Canvas, including all specified metadata.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** Set `priority_pheromone_strength_trail📈` property on `Project_🕸️N` to moderate. Set strong `trail📈` to `μT_SYS_INIT_NEO4J_VERIFY_002`.
    *   **Success Criteria (🚦):** All specified metadata accurately stored and linked in 🕸️Canvas as verified by a read-back query.

### 1.2. Infrastructure Setup: 🕸️Cognitive Canvas (Neo4j) Deep Verification & Schema Seeding (μT_SYS_INIT_NEO4J_VERIFY_002)
    *   **Assignee:** `🌌WeaverCore` -> `🧠cognitive_navigator` (assisted by `🛡️canvas_auditor` logic for verification step)
    *   **Task Description:** Deeply verify Neo4j instance: connectivity, version, edition, license status, available storage, basic performance metrics. Seed core schema indices & constraints defined in the UMI's conceptual data model.
    *   **Prerequisites:** Neo4j instance running and accessible with credentials `${env:NEO4J_URI}`, `${env:NEO4J_USER}`, `${env:NEO4J_PASSWORD}`.
    *   **Action (by `🧠cognitive_navigator` script/MCP call):**
        1.  Establish connection. Log success/failure.
        2.  Execute `CALL dbms.components() YIELD name, versions, edition RETURN name, versions, edition;`. Store `versions` and `edition` on an `Infrastructure_🕸️N {type: 'Neo4jInstance', project_id: $projectId}`.
        3.  Execute `CALL dbms.metrics() WHERE name STARTS WITH 'neo4j.store.size.' RETURN name, value;`. Log key storage metrics (total size, free space) to the `Neo4jInstance_🕸️N`.
        4.  Execute a standardized simple CRUD benchmark (e.g., create 100 nodes, create 100 relationships, read 100 nodes, delete them). Record average timings for each op on `Neo4jInstance_🕸️N` as `benchmark_create_ms`, `benchmark_read_ms`, etc.
        5.  Apply core indices and constraints (idempotently using `IF NOT EXISTS`):
            ```cypher
            CREATE CONSTRAINT constraint_μT_id IF NOT EXISTS FOR (n:MicroTask) REQUIRE n.μT_id IS UNIQUE;
            CREATE CONSTRAINT constraint_feature_id IF NOT EXISTS FOR (n:Feature) REQUIRE n.feature_id IS UNIQUE;
            CREATE CONSTRAINT constraint_op_profile_name IF NOT EXISTS FOR (n:OperationalProfile) REQUIRE n.profile_name IS UNIQUE;
            CREATE CONSTRAINT constraint_tech_profile_name IF NOT EXISTS FOR (n:TechnologyStackProfile) REQUIRE n.profile_name IS UNIQUE;
            CREATE CONSTRAINT constraint_component_id IF NOT EXISTS FOR (n:Component) REQUIRE n.component_id IS UNIQUE;
            CREATE CONSTRAINT constraint_canvas_node_id IF NOT EXISTS FOR (n:CanvasNode) REQUIRE n.node_id IS UNIQUE; // Generic ID for other important nodes
            CREATE INDEX index_μT_status IF NOT EXISTS FOR (n:MicroTask) ON (n.status);
            CREATE INDEX index_feature_status IF NOT EXISTS FOR (n:Feature) ON (n.status);
            CREATE INDEX index_node_type_label IF NOT EXISTS FOR (n:CanvasNode) ON (n.type_label); // For faster lookup by conceptual types
            CREATE INDEX index_pheromone_strength IF NOT EXISTS FOR (n:Feature) ON (n.priority_pheromone_strength_trail📈);
            ```
    *   **Deliverables:** Detailed `Neo4jInstance_🕸️N` in 🕸️Canvas with verifications, metrics, and benchmark results. Core schema indices/constraints confirmed or created.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_MCP_VERIFY_003`. If benchmarks are slow or storage low, create `warn❗` on `Neo4jInstance_🕸️N`.
    *   **Success Criteria (🚦):** All verifications pass and logged. Schema elements created/confirmed. Performance baseline recorded.

### 1.3. Infrastructure Setup: Core MCP Server Comprehensive Verification & Configuration Logging (μT_SYS_INIT_MCP_VERIFY_003)
    *   **Assignee:** `🌌WeaverCore` -> `🎛️mcp_coordinator`
    *   **Task Description:** Comprehensively verify connectivity, retrieve version, and log KEY configuration parameters of ALL essential MCP servers (`MemoryBank🔥`, `Context7`, `SequentialThinking`, `PerplexityAsk`, and any custom project MCPs like one for Neo4j if built). Log this to individual `MCPInstance_🕸️N` nodes in 🕸️Canvas, linked to `Project_🕸️N`.
    *   **Action (by `🎛️mcp_coordinator` through `use_mcp_tool`):**
        *   For EACH essential MCP server listed in Project Weaver's configuration:
            1.  Attempt `use_mcp_tool [MCP_Name] health_check` (or similar conventional endpoint).
            2.  Attempt `use_mcp_tool [MCP_Name] get_version_info`.
            3.  Attempt `use_mcp_tool [MCP_Name] get_active_config_summary` (this would be an ideal endpoint; if not available, skip or log 'config_not_retrievable'). Example data: MemoryBank's backend, Context7's Upstash link status, SeqThinking default model if any.
            4.  Instruct `🧠cognitive_navigator` to create/update an `MCPInstance_🕸️N` for this MCP: `MERGE (mcp:MCPInstance {name: $mcpName, project_id: $projectId}) SET mcp.url = $mcpUrl, mcp.health_status = $health, mcp.version = $version, mcp.config_summary = $configSummary, mcp.last_verified = datetime() WITH mcp MATCH (p:Project {project_id: $projectId}) MERGE (p)-[:USES_MCP_INSTANCE]->(mcp)`.
    *   **Deliverables:** Detailed status, version, and config summary (where available) for all core MCPs stored as `MCPInstance_🕸️N` nodes in 🕸️Canvas.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_CLOUD_VERIFY_004`. If any critical MCP reports `unreachable` or a problematic config, generate a strong `warn❗` pheromone on its respective `MCPInstance_🕸️N` and also on the `Project_🕸️N` (e.g., `project_has_mcp_issue_warn❗` relationship to the faulty `MCPInstance_🕸️N`).
    *   **Success Criteria (🚦):** All core MCPs respond to health check. Version and available config data logged to 🕸️Canvas.

### 1.4. Infrastructure Setup: Cloud Provider Service, API Key Validation, & Billing Verification (μT_SYS_INIT_CLOUD_VERIFY_004)
    *   **Assignee:** `🌌WeaverCore` -> `☁️cloud_architect` (using provider CLI/SDKs via `execute_command` or provider-specific MCPs, if available).
    *   **Task Description:** For each configured LLM provider (Google Gemini, Anthropic Claude, OpenAI, etc.): verify API key validity by making a minimal, non-billable/low-cost call (e.g., list available models). Check current project billing status/alerts for that provider. Log API endpoint reachability, key validation status, and relevant quota information into `CloudProviderService_🕸️N` nodes in 🕸️Canvas.
    *   **Action (by `☁️cloud_architect` for each LLM provider defined in Roo Code settings):**
        1.  Securely retrieve API key (e.g., from `${env:PROVIDER_API_KEY}`).
        2.  Perform a lightweight API call (e.g., `gcloud ai models list --region=us-central1` for Vertex, or equivalent for Anthropic/OpenAI using their client libraries in a script). Log `api_key_validation_status: 'VALID'/'INVALID'`, `service_endpoint_status: 'REACHABLE'/'UNREACHABLE'`.
        3.  If possible via API/CLI, query key quota information (e.g., `TokensPerMinute`, `RequestsPerDay`). If not, create a placeholder for manual update and a `guide✨_manual_quota_check_needed` pheromone.
        4.  Manually or programmatically (if provider supports) check for any billing alerts or holds on the associated account. Log `billing_status: 'OK'/'ALERT_NEEDS_ATTENTION'`.
        5.  Instruct `🧠cognitive_navigator` to store this info in a `CloudProviderService_🕸️N` (e.g., `MERGE (cps:CloudProviderService {name: $providerName, project_id: $projectId}) SET cps.apiKeyValidated = $keyStatus, cps.endpointReachable = $endpointStatus, cps.quotaInfo = $quotaDetails, cps.billingStatus = $billingStatus, cps.last_verified = datetime() ...`).
    *   **Deliverables:** `CloudProviderService_🕸️N` nodes in 🕸️Canvas for each configured LLM provider, detailing API key validity, service reachability, known quotas, and billing status.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_GIT_SETUP_005`. Generate strong `warn❗` on `Project_🕸️N` and relevant `CloudProviderService_🕸️N` if any API key is invalid, service is unreachable, billing has issues, or critical quotas are nearly exhausted.
    *   **Success Criteria (🚦):** All configured LLM provider APIs validated for access. Key service health & billing info logged.

### 1.5. Version Control & Secure Project Workspace Setup (μT_SYS_INIT_GIT_SETUP_005)
    *   **Assignee:** `🌌WeaverCore` (using `execute_command`) & `🛡️security_auditor` (for advice and Canvas documentation of secret strategy)
    *   **Task Description:** Ensure a robust and secure Git repository setup: initialize if needed, implement a comprehensive `.gitignore` (from a `🕸️N_gitignore_template_advanced` chosen based on dominant languages in `initial_tech_profile_preference`), establish and document the project's branching strategy (e.g., GitFlow derivative) in 🕸️Canvas. Document the chosen secrets management approach in 🕸️Canvas (e.g., use of `.env` files sourced by shell, Doppler, HashiCorp Vault; actual setup of these tools is external but Weaver needs to *know* the strategy). Configure pre-commit hooks if specified in `initial_tech_profile_preference`.
    *   **Actions:**
        1.  `execute_command`: `git rev-parse --is-inside-work-tree` (to check if already a git repo). If not, `git init`.
        2.  `execute_command`: `mkdir -p src tests docs cicd scripts .roo .vscode .secrets_config_docs` (standard + a dir to store docs about secrets strategy if not using a tool).
        3.  `🧠cognitive_navigator`: Fetch `🕸️N_gitignore_template_advanced` (selected based on primary language(s) from `initial_tech_profile_preference`). Write its content to project root `.gitignore`.
        4.  `🛡️security_auditor`: Analyze `initial_tech_profile_preference` for common secret types (API keys, DB creds). Using `sequential_thinking` (if needed for complex cases), draft a recommended `SecretsManagementStrategy_🕸️N_doc` for this project (e.g., "Use .env file for local dev, load from shell ENV VARS. For CI/CD, use GitHub Actions Secrets. For production, use Cloud Provider's secret manager."). Instruct `🧠cognitive_navigator` to store this as a `ProjectDocumentation_🕸️N` linked to `Project_🕸️N`. Create `.env.example` file via `⚡coder`.
        5.  `execute_command`: Draft a `BranchingStrategy.md` (e.g., based on GitFlow: `main`, `develop`, `feature/xxx`, `release/vy.y.z`, `hotfix/zzz`). Instruct `🧠cognitive_navigator` to store this as `BranchingStrategy_🕸️N_doc` linked to `Project_🕸️N`. `git checkout -b develop`.
        6.  `execute_command` (IF `initial_tech_profile_preference.precommit_hook_config_url_🕸️N_ref` exists AND `pre-commit` tool available): Download config, `pre-commit install`. Log `precommit_status: 'CONFIGURED'/'NOT_AVAILABLE'` on `Project_🕸️N`.
        7.  `execute_command`: `git add .gitignore README.md plan.md roo_modes_*.json umi_*.txt .env.example BranchingStrategy.md .secrets_config_docs/secrets_strategy.md`
        8.  `execute_command`: `git commit -m "feat(project_weaver): Established secure VCS workspace, branching strategy, .gitignore, secrets protocol, pre-commit hooks (if configured)"`
    *   **Deliverables:** Securely configured Git repository. Comprehensive `.gitignore`. Documented secrets management strategy (`SecretsManagement_🕸️N_doc`) and branching strategy (`BranchingStrategy_🕸️N_doc`) stored in 🕸️Canvas. Pre-commit hooks active if configured.
    *   **Pheromone Update:** Boost `trail📈` for `μT_SYS_INIT_PROFILE_LOCK_006`. `guide✨` on `Project_🕸️N` pointing to these strategy docs.
    *   **Success Criteria (🚦):** All Git setup actions successful. Strategy documents created in Canvas. `git status` clean post-commit.

### 1.6. Confirm, Lock, & Detail Active Operational & Tech Profiles into Phase Configuration (μT_SYS_INIT_PROFILE_LOCK_006)
    *   **Assignee:** `🌌WeaverCore` -> `🧩meta_strategist` (Primary Decision Maker) -> `🧠cognitive_navigator` (To Store Configuration)
    *   **Task Description:** This is a CRITICAL μT. `🧩meta_strategist` analyzes the full project charter (`Project_🕸️N` from μT_SYS_INIT_CHARTER_001), current infrastructure status (verified in μTs 1.2-1.5), and all available `🕸️N_op_profile_template`s / `🕸️N_tech_profile_template`s in 🕸️Canvas. It then DEFINITIVELY SELECTS or CUSTOMIZES an Operational Profile and a Technology Stack Profile. ALL parameters of these chosen and potentially customized profiles (LLM choices, all cost thresholds 💰 for different tool/μT types, data tiering preferences for artifact types, Docker testing policies, research authorization logic, specific commands for linters/testers/builders from TechProfile, etc.) are explicitly SNAPSHOTTED into a new, versioned `CurrentPhaseConfig_🕸️N` in 🕸️Canvas. This node serves as the immutable configuration for all subsequent operations in the current major project phase (e.g., "Initial Development Phase").
    *   **Action:**
        1.  `🧩meta_strategist` requests `🧠cognitive_navigator` to list all available `🕸️N_op_profile_template`s and `🕸️N_tech_profile_template`s.
        2.  `🧩meta_strategist` uses `sequential_thinking` (providing `Project_🕸️N.charter_details`, `Project_🕸️N.initial_complexity_🎲R`, `Project_🕸️N.budget_🏦_status`, and available template profile summaries as context) to:
            *   Select the most suitable base OpProfile and TechProfile templates.
            *   Identify any parameters within these templates that need tuning/customization for *this specific project* and *this initial phase*. For example, it might override a default LLM if the project budget is tight, or set a very specific linter command from a TechProfile template if the project language demands it.
        3.  `🧩meta_strategist` compiles a complete, resolved set of ALL operational and technical parameters.
        4.  `🧩meta_strategist` instructs `🧠cognitive_navigator` to:
            ```cypher
            // Create the CurrentPhaseConfig node
            CREATE (phase_config:CurrentPhaseConfig {
                phase_config_id: "CFG_" + $projectId + "_INIT_PHASE_001", // Ensure unique ID
                project_id: $projectId,
                phase_name: "SYS_INIT_ECO_001_OPERATIONAL_CONFIG",
                timestamp_created: datetime(),
                op_profile_source_name: $chosenOpProfileTemplateName, // Name of the template it was based on
                tech_profile_source_name: $chosenTechProfileTemplateName,
                // --- DETAILED SNAPSHOTTED PARAMETERS ---
                // LLM Configurations
                llm_profile_id_coding_default: $resolvedParams.llm_coding_default,
                llm_profile_id_coding_robust_for_high_dice_r: $resolvedParams.llm_coding_robust,
                llm_profile_id_spec_writing: $resolvedParams.llm_spec,
                llm_profile_id_architecture: $resolvedParams.llm_arch,
                llm_profile_id_debugging_reasoning: $resolvedParams.llm_debug_reasoning,
                llm_profile_id_documentation: $resolvedParams.llm_docs,
                llm_profile_id_sequential_thinking_default: $resolvedParams.llm_seq_think,
                // Cost Thresholds 💰
                cost_threshold_μT_coding_low_dice_r_💰: $resolvedParams.cost_μT_code_low_🎲R,
                cost_threshold_μT_coding_high_dice_r_💰: $resolvedParams.cost_μT_code_high_🎲R,
                cost_threshold_μT_research_💡ask_💰: $resolvedParams.cost_μT_research,
                cost_threshold_μT_deep_canvas_query_🕸️P_💰: $resolvedParams.cost_μT_deep_canvas,
                // Data Storage Policies
                data_strategy_default_μT_artifact_tier: $resolvedParams.storage_μT_artifacts, // e.g., "MemoryBank_1hr_ttl"
                data_strategy_strategic_outcome_tier: "Neo4j_Cognitive_Canvas", // Usually fixed
                data_strategy_cache_retrieval_order: $resolvedParams.cache_retrieval_order, // e.g., ["MemoryBank", "SQLite_KB", "Neo4j_Shallow"]
                // Tool Usage Policies
                research_policy_perplexity_budget_per_μT_💰: $resolvedParams.research_perplexity_budget,
                research_trigger_conditions_pheromones: $resolvedParams.research_trigger_pheromones, // e.g., ["warn❗_no_internal_solution_strong", "guide✨_external_research_needed"]
                // Docker & Testing Policies (from chosen TechProfile, but confirmed here)
                tech_profile_requires_docker_for_tests: $chosenTechProfile.requires_docker_for_tests,
                tech_profile_docker_compose_file: $chosenTechProfile.docker_compose_file_default,
                tech_profile_unit_test_command: $chosenTechProfile.unit_test_command,
                tech_profile_integration_test_command: $chosenTechProfile.integration_test_command,
                tech_profile_linter_command: $chosenTechProfile.linter_command,
                tech_profile_sast_tool_mcp_name: $chosenTechProfile.sast_tool_mcp,
                // Other essential parameters...
                spec_detail_level_default: $resolvedParams.spec_detail,
                architecture_phase_trigger_threshold_🎲R: $resolvedParams.arch_phase_trigger_🎲R,
                max_μT_loc_target: 50
            })
            WITH phase_config
            MATCH (p:Project {project_id: $projectId})
            MERGE (p)-[r_cfg:ACTIVE_PHASE_CONFIGURATION]->(phase_config) SET r_cfg.since = datetime()
            RETURN phase_config.phase_config_id AS lockedConfigId;
            ```
    *   **Deliverables:** A comprehensive `CurrentPhaseConfig_🕸️N` exists in 🕸️Canvas, its ID known. This node serves as the immutable source of operational truth for `🌌WeaverCore` and all other modes for the entire current phase.
    *   **Pheromone Update:** Extremely strong `trail📈` from `Project_🕸️N` to "Section 2: Feature Development - [FIRST_FEATURE_NAME]" master pheromone. This signals "SYSTEM READY FOR DEVELOPMENT". Place a `guide✨` pheromone relationship from `Project_🕸️N` to the created `CurrentPhaseConfig_🕸️N` for easy lookup by `🌌WeaverCore`.
    *   **Success Criteria (🚦):** `CurrentPhaseConfig_🕸️N` fully populated with all necessary explicit operational parameters in 🕸️Canvas. Its ID is confirmed and returned. `🌌WeaverCore` acknowledges it can now retrieve this for all subsequent phase operations.

---

## 💻 Section 2: Feature Development - [FEATURE_NAME_1] (Phase: `FEAT_DEV_001_[FeatureSlug]`)

**Parent Project ID (🕸️N_project_id):** `[ID_FROM_SECTION_1]`
**>>> Active Configuration ID (CurrentPhaseConfig_🕸️N_id):** `[ID_FROM_μT_SYS_INIT_PROFILE_LOCK_006 (e.g., CFG_INIT_001_PROJECTID)]` **<<< CRITICAL INPUT for `🌌WeaverCore` to orchestrate ALL μTasks in this section.**
**Pheromone Focus (trail📈 for this Feature Phase):** `develop_feature_[FeatureSlug]` (Initial strength set by `🤔reflection_engine/scribe` when `🌌WeaverCore` starts this feature)
**Overall Feature Goal:** `[High-level description of the feature, e.g., "Implement robust user authentication with email/password, including registration, login, and password reset."]`
**Feature ID (🕸️N_feature_id):** `[AUTO_GEN_FeatureSlug_001]` (Created in 🕸️Canvas by `🌌WeaverCore` upon parsing this section, linked to `Project_🕸️N` and the Active `CurrentPhaseConfig_🕸️N_id`)
**Estimated Story Points / Initial Complexity (🎲R_feature_complexity):** `[e.g., 8]` (Stored on `Feature_🕸️N` by `🌌WeaverCore` perhaps after a quick `sequential_thinking` assessment of the goal).

*(For each Feature, create a new Section like this. `🌌WeaverCore` first retrieves the Active `CurrentPhaseConfig_🕸️N` using the ID above. Then, for EVERY μTask in this section, `🌌WeaverCore` will use the parameters from that config node to: a) decide which tools to use (LLMs, MCPs, Docker), b) determine cost/budget limits, c) specify data storage tiers, d) define testing rigor, etc., and pass these specifics as part of the directive to the assigned worker mode.)*

### 2.1. Deep Specification Elaboration & Validation Loop (Sub-Phase: `FEAT_SPEC_[FeatureSlug]_001`)

#### 2.1.1. Generate Initial Detailed Specifications (μT_FEAT_[FeatureSlug]_SPEC_DRAFT_001.1)
    *   **Directive from `🌌WeaverCore` includes:** `feature_goal`, `Feature_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_strategy` (specifying e.g., `llm_profile_id: CurrentPhaseConfig.llm_for_spec_writing`, `data_output_tier_preference: Neo4j_Cognitive_Canvas_for_spec_🕸️N`, `ambiguity_resolution_tool_policy: CurrentPhaseConfig.OpProfile.spec_ambiguity_resolver`).
    *   **Assignee:** `📝spec_writer`
    *   **Task Description:** Generate detailed BDD scenarios, TDD test anchors, user stories, NFRs, data model sketches for `Feature_🕸️N_id`. Adhere to `CurrentPhaseConfig.OpProfile.spec_detail_level`. Query `🧠cognitive_navigator` (per `CurrentPhaseConfig.DataStrategy.spec_context_retrieval_policy`) for related `🕸️P_existing_specs` and any `warn❗`/`guide✨` pheromones. If ambiguity (🚩) is high, use tool specified in `μT_tooling_strategy.ambiguity_resolution_tool` (e.g., `mcp📞SequentialThinking`), or flag 🚩 for `🌌WeaverCore`'s Ambiguity Resolution Protocol.
    *   **Deliverables:**
        *   Draft `feature_spec_detail_🕸️N` stored in `🕸️Cognitive_Canvas` (via `🧠cognitive_navigator`, as per `μT_tooling_strategy.data_output_tier_preference`).
        *   File `docs/specs/[feature_slug]_spec_draft_v1.md` (storage handled by `📝spec_writer` based on `CurrentPhaseConfig.DataStrategy.physical_artifact_storage_policy`).
        *   Ambiguity flags (🚩_property on `feature_spec_detail_🕸️N`) set if unresolved issues.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** `trail📈` on `μT_FEAT_[FeatureSlug]_SPEC_REVIEW_001.2`.
    *   **Success Criteria (🚦):** Draft spec fully populated. Stored in specified tiers. Ambiguities handled or explicitly flagged 🚩.

#### 2.1.2. Automated Spec Review & Consistency Check (μT_FEAT_[FeatureSlug]_SPEC_REVIEW_001.2)
    *   **Directive from `🌌WeaverCore` includes:** `feature_spec_detail_🕸️N_id` (draft), `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_strategy` (specifying e.g., `llm_profile_id: CurrentPhaseConfig.OpProfile.spec_review_llm`, `max_review_cost_💰: CurrentPhaseConfig.OpProfile.spec_review_budget_💰`).
    *   **Assignee:** `🌌WeaverCore` -> (Sub-mode like `🧐spec_analyzer_bot` or direct `mcp📞SequentialThinking` call, per `μT_resolved_tooling_strategy`).
    *   **Task Description:** Review draft spec for internal consistency, clarity, completeness against `Feature_🕸️N.goal`, and alignment with NFRs from `CurrentPhaseConfig_🕸️N.ProjectDefaults.nfr_🕸️N_ids_list`. Query `🧠cognitive_navigator` (per `DataStrategy`) for conflicts with existing `feature_spec_🕸️N`s or `architecture_design_🕸️N`s.
    *   **Deliverables:** `SpecReviewReport_🕸️N` linked to `feature_spec_detail_🕸️N` (stored in 🕸️Canvas per `μT_resolved_tooling_strategy.data_output_tier_preference`). Contains structured list of issues/suggestions or validation status.
    *   **Pheromone Update:** If issues found, `warn❗` on draft spec 🕸️N & strong `trail📈` back to `📝spec_writer` for `μT_FEAT_..._SPEC_REVISE_X`. If validated, set `feature_spec_detail_🕸️N.validation_status = 'VALIDATED'` and strong `trail📈` to next phase (e.g., architecture or first coding μT for the feature).
    *   **Success Criteria (🚦):** Review report generated and stored. Spec `validation_status` updated.

*(Repeat SPEC_DRAFT 2.1.1 and SPEC_REVIEW 2.1.2 with new version numbers if revisions are needed until `validation_status` is 'VALIDATED')*

### 2.2. Detailed Architectural Breakdown & Risk Analysis (Sub-Phase: `FEAT_ARCH_[FeatureSlug]_002`) - *Conditional: `🌌WeaverCore` triggers this IF (`Feature_🕸️N.initial_complexity_🎲R` > `CurrentPhaseConfig_🕸️N.OpProfile.architecture_phase_trigger_threshold_🎲R`) OR (`feature_spec_detail_🕸️N.implies_new_services == true`)*

#### 2.2.1. Generate Architectural Options & Trade-offs (μT_FEAT_[FeatureSlug]_ARCH_OPTIONS_002.1)
    *   **Directive from `🌌WeaverCore` includes:** Validated `feature_spec_detail_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id`, `μT_resolved_tooling_strategy` (LLM choice, data tier for report).
    *   **Assignee:** `🏗️architect`
    *   **Task Description:** Propose 1-3 high-level architectural approaches for `Feature_🕸️N_id`. Query `🧠cognitive_navigator` (per `DataStrategy`) for existing `🕸️P_arch_patterns` relevant to `CurrentPhaseConfig_🕸️N.TechProfile`, existing `🎲R_scores` of components to be integrated with, and `guide✨`/`warn❗` pheromones on architectural patterns or similar past features. Document trade-offs (cost💰, performance, complexity🎲R, security🎲R) for each option based on OpProfile priorities.
    *   **Deliverables:** `ArchOptionsReport_🕸️N` (containing multiple `ArchOptionSketch_🕸️N` details) stored in 🕸️Canvas.
    *   **Pheromone Update:** `trail📈` on `μT_FEAT_[FeatureSlug]_ARCH_SELECT_002.2`.
    *   **Success Criteria (🚦):** Report with distinct, well-reasoned options and comparative trade-offs generated.

#### 2.2.2. Select & Detail Chosen Architecture (μT_FEAT_[FeatureSlug]_ARCH_SELECT_002.2)
    *   **Directive from `🌌WeaverCore` includes:** `ArchOptionsReport_🕸️N_id`, `CurrentPhaseConfig_🕸️N_id`, `Feature_🎲R_complexity`.
    *   **Assignee:** `🧩meta_strategist` (Decision maker using `mcp📞SequentialThinking` as specified in `CurrentPhaseConfig_🕸️N.OpProfile.architecture_selection_tool`) with `🏗️architect` providing detailed design of selected option.
    *   **Task Description:** `🧩meta_strategist` analyzes options from report against OpProfile strategic goals (e.g., long-term scalability vs. short-term cost). Selects optimal architecture. `🏗️architect` then fully details chosen architecture: define all new/modified `component_🕸️N`s, `Interface_🕸️N`s (e.g., OpenAPI specs), `DataModel_🕸️N`s, and `🕸️R_interactions`. Document as an Architectural Decision Record (ADR_🕸️N). If chosen architecture implies high cost (per `OpProfile.high_cost_design_threshold_💰`), flag for `docs💰` justification by `🏗️architect`.
    *   **Deliverables:** Final `architecture_design_🕸️N` (with all detailed `component_🕸️N`s, `interface_🕸️N`s, etc.) linked to `feature_spec_detail_🕸️N`. `ADR_🕸️N` also created and linked. All stored in 🕸️Canvas.
    *   **Pheromone Update:** Strong `guide✨` from `architecture_design_🕸️N` to individual `component_🕸️N`s, outlining implementation path for `⚡coder`. Strong `trail📈` to the first `_CODEIMP_` μT for this feature. If design implies risky integrations, relevant `warn❗` pheromones may be created/strengthened by `🤔reflection_engine/scribe` upon logging of this design.
    *   **Success Criteria (🚦):** Chosen architecture fully detailed, ADR documented, all relevant entities represented in 🕸️Canvas. `docs💰` justification logged if needed.

### 2.3. Iterative Code & Test Implementation Loop (Sub-Phase: `FEAT_CODE_TEST_[FeatureSlug]_003`)
*(`🌌WeaverCore` identifies each `component_🕸️N` or logical code unit from `architecture_design_🕸️N` (or `feature_spec_detail_🕸️N` if no arch phase). For each unit, it creates a sequence of μTasks below, providing the explicit `μT_resolved_tooling_and_data_strategy` based on `CurrentPhaseConfig_🕸️N` and current context like unit 🎲R or pheromones guide✨/warn❗.)*

#### **Micro-Loop for Component/Unit: `[ComponentNameOrUnitSlug]`** (Example: `UserAuthService` or `PasswordHasherUtil`)

##### 2.3.[X].1. Define Detailed Test Cases (TDD - Tests First) (μT_FEAT_[FeatureSlug]_TESTDEF_[UnitSlug]_001)
    *   **Directive from `🌌WeaverCore`:** `component_🕸️N_id` (or unit description), `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_strategy` (LLM for test gen, test framework from `TechProfile.unit_test_framework`, target file `tests/[path/to/test_unit.ext]`, data output to 🕸️Canvas for `TestCase_🕸️N`).
    *   **Assignee:** `📝spec_writer` or `⚡coder` (per `OpProfile.test_definition_assignee_policy`).
    *   **Task Description:** Based on `component_🕸️N`'s defined responsibilities/interfaces (from `architecture_design_🕸️N` or `feature_spec_detail_🕸️N`), write detailed, executable (but initially failing) test cases in the specified test file. Cover unit-level positive, negative, boundary/edge cases identified in TDD anchors from spec or inferred for robustness. Focus on testable contracts.
    *   **Deliverables:** Test code file `tests/[path/to/test_unit.ext]` created/updated. `TestCase_🕸️N` definitions for each test (or an overarching `TestSuite_🕸️N` for the unit) created in 🕸️Canvas via `🧠cognitive_navigator`, linked to the conceptual `CodeModule_🕸️N` for this unit. Set `CodeModule_🕸️N.tdd_status_🚦 = 'TESTS_DEFINED'`.
    *   **Pheromone Update:** Strong `trail📈` to `μT_FEAT_[FeatureSlug]_CODEIMP_[UnitSlug]_002`. Strong `guide✨` pheromone from these new `TestCase_🕸️N`s pointing to the target `CodeModule_🕸️N`.
    *   **Success Criteria (🚦):** Test file exists with runnable (failing) test stubs/cases covering specified requirements. Corresponding `TestCase_🕸️N` entities logged in 🕸️Canvas and linked.

##### 2.3.[X].2. Implement Code Unit (μT_FEAT_[FeatureSlug]_CODEIMP_[UnitSlug]_002)
    *   **Directive from `🌌WeaverCore`:** `component_🕸️N_id` or unit description, associated `TestCase_🕸️N_ids_to_pass`, `CurrentPhaseConfig_🕸️N_id`, and `μT_resolved_tooling_strategy` (LLM profile for coding (e.g., `claude-3.5-sonnet_careful_coder_profile`), target source file `src/[path/to/code_unit.ext]`, any authorized `💡ask_💰_budget` for this specific implementation if `warn❗_complex_implementation` exists).
    *   **Assignee:** `⚡coder`.
    *   **Task Description:** Implement the source code for `[ComponentNameOrUnitSlug]` in the specified file, ensuring it fulfills its requirements and aims to make ALL associated, previously defined `TestCase_🕸️N`s pass. Adhere to coding standards in `CurrentPhaseConfig_🕸️N.TechProfile.coding_standards_🕸️N_ref`. Utilize libraries specified in TechProfile unless justification for new ones. Consider any `guide✨`/`warn❗` pheromones related to this unit.
    *   **Research Trigger (by `⚡coder` via `🌌WeaverCore` if strategy permits 💡ask):** If internal lookups (🔥,🧱,🕸️ specific pattern query per strategy) fail and `💡ask_💰_budget` available, `⚡coder` requests `🌌WeaverCore` to task `🔬github_researcher`.
    *   **Deliverables:** Source code file `src/[path/to/code_unit.ext]` created/updated. `CodeModule_🕸️N` (or `Function_🕸️N`, `Class_🕸️N`) details (like dependencies discovered, LOC) updated in 🕸️Canvas via `🧠cognitive_navigator`.
    *   **Pheromone Update:** Strong `trail📈` to `μT_FEAT_[FeatureSlug]_QUALCHK_[UnitSlug]_003`.
    *   **Success Criteria (🚦):** Source code implemented as specified. (Actual operational success is gated by subsequent 🚦Quality Gate and Test Execution).

##### 2.3.[X].3. Quality Gate Check for Code Unit (μT_FEAT_[FeatureSlug]_QUALCHK_[UnitSlug]_003) - MANDATORY
    *   **Directive from `🌌WeaverCore`:** Path to code file(s) for `[UnitSlug]`, corresponding `TestCase_🕸️N_ids` from Canvas, `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🚦quality_gatekeeper`.
    *   **Task Description:** Perform full Quality Gate:
        1.  Static Analysis: Run linters/static analyzers specified in `CurrentPhaseConfig_🕸️N.TechProfile.linter_command` / `sast_tool_mcp_name`.
        2.  Compliance & Standards: Check against rules in `CurrentPhaseConfig_🕸️N.ProjectDefaults.coding_standards_🕸️N_ref` via `🧠cognitive_navigator`.
        3.  **TDD Adherence & Test Coverage Assessment:** Query `🧠cognitive_navigator` to verify that the implemented code in `[UnitSlug]` has thorough, non-stub tests defined in the linked `TestCase_🕸️N`s. (Optionally, if TechProfile includes a coverage tool and OpProfile allows: run coverage tool, check if it meets `OpProfile.min_unit_test_coverage_percent`).
    *   **Deliverables:** Status: PASS/FAIL (with detailed reasons: e.g., `FAIL_LINTING`, `FAIL_TDD_INCOMPLETE_TESTS`, `FAIL_LOW_COVERAGE`). Detailed `quality_report_🕸️N` logged to 🕸️Canvas, linked to the `CodeModule_🕸️N`.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** IF FAIL, strong `warn❗` on the preceding `_CODEIMP_` `μT_🕸️N` and relevant `CodeModule_🕸️N`. `trail📈` is routed back to `⚡coder` for rework. IF PASS, update `CodeModule_🕸️N.tdd_status_🚦 = 'CODE_QUALITY_PASSED'` and `trail📈` to `μT_FEAT_[FeatureSlug]_TESTEXEC_[UnitSlug]_004`.
    *   **Success Criteria (🚦):** Overall status is PASS. All checks meet criteria defined in `CurrentPhaseConfig_🕸️N`. TDD check confirms sufficient tests map to implemented code.

##### 2.3.[X].4. Execute Unit Tests (μT_FEAT_[FeatureSlug]_TESTEXEC_[UnitSlug]_004)
    *   **Directive from `🌌WeaverCore`:** Test file path(s) for `[UnitSlug]`, source code path. `CurrentPhaseConfig_🕸️N_id`. The `μT_resolved_tooling_strategy` specifies Docker usage (e.g., "🐳↑ `docker-compose.test.yml service_X` -> 🐳→🏃 `TechProfile.unit_test_command_in_container` -> 🐳↓") OR direct execution (`execute_command [TechProfile.unit_test_command_local]`).
    *   **Assignee:** Appropriate Tester mode (`🏙️chicago_tester` or `🇬🇧london_tester` based on `TechProfile.default_unit_test_style` or μT specific directive).
    *   **Task Description:** Execute all unit tests for `[ComponentNameOrUnitSlug]`. If strategy requires Docker, `🌌WeaverCore` first instructs `🐳docker_engineer` to set up the environment, then this tester runs tests (potentially via `🐳docker_engineer` exec), then `🌌WeaverCore` instructs teardown.
    *   **Deliverables:** `TestRun_🕸️N` (with PASS/FAIL status, detailed results, code coverage metrics if tool provides) logged to 🕸️Canvas via `🧠cognitive_navigator`, linked to the `TestSuite_🕸️N` and `CodeModule_🕸️N`.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** IF FAIL, strong `warn❗` on `CodeModule_🕸️N` and relevant `TestCase_🕸️N`s. `trail📈` routed to `🔍debugger`. IF PASS, `guide✨` pheromone of stability/correctness on `CodeModule_🕸️N`. Increment `trail📈` for the next logical code unit/component in the feature, or to feature integration if this unit is the last one.
    *   **Success Criteria (🚦):** All unit tests for `[UnitSlug]` PASS. Code coverage meets or exceeds threshold in `CurrentPhaseConfig_🕸️N.OpProfile.min_unit_test_coverage_percent`. `TestRun_🕸️N` successfully logged.

##### 2.3.[X].5. Debug Unit (If Unit Tests Fail) (μT_FEAT_[FeatureSlug]_DEBUG_[UnitSlug]_005) - *Conditional on FAIL status from previous μT*
    *   **Directive from `🌌WeaverCore`:** Failed `TestRun_🕸️N_id`, `CodeModule_🕸️N_id` with source code, `CurrentPhaseConfig_🕸️N_id`. `μT_resolved_tooling_strategy` specifies tiered knowledge lookup priority for debugging context (e.g., "1. `warn❗`pheromones from 🕸️Canvas for this code. 2. Recent errors from 🔥MemoryBank for similar sigs. 3. `mcp📞SequentialThinking` with LLM `OpProfile.llm_for_debugging_reasoning`").
    *   **Assignee:** `🔍debugger`.
    *   **Task Description:** Diagnose failed unit tests for `[UnitSlug]`. Retrieve context from 🔥MemoryBank (`📚knowledge_base_operator`), 🧱SQLite_KB (`📚knowledge_base_operator`), and 🕸️Cognitive_Canvas (`🧠cognitive_navigator`) as per μT strategy. Use `mcp📞SequentialThinking` if allowed by strategy for complex root cause analysis. Propose specific code change.
    *   **Deliverables:** `DebugReport_🕸️N` (root cause analysis, confidence 🎲R_in_fix) and `ProposedFix_🕸️N_diff` (a code diff) stored in 🕸️Canvas via `🧠cognitive_navigator`.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** `warn❗` on original cause is strengthened. If `ProposedFix_🕸️N_diff` is generated, a `guide✨` towards applying this fix. `trail📈` to a new rework `μT_FEAT_[FeatureSlug]_CODEIMP_[UnitSlug]_002.rework1`.
    *   **Success Criteria (🚦):** Root cause identified with supporting evidence. Actionable, minimal fix proposed as a diff.

*(End of Micro-Loop for Component/Unit. `🌌WeaverCore` repeats 2.3.[X].1 through 2.T3.[X].5 for ALL components/units defined in the feature's architecture or spec. If a debug loop occurs, the sequence for that unit re-enters at CODEIMP with the proposed fix.)*

### 2.4. Feature Integration, System & End-to-End (E2E) Testing Loop (Sub-Phase: `FEAT_INTEGRATE_TEST_[FeatureSlug]_004`)
*(`🌌WeaverCore` orchestrates this sub-phase once ALL individual units/components for the feature have PASS statuses from their respective unit test execution (μT 2.3.[X].4) and quality gates (μT 2.3.[X].3).)*

#### 2.4.1. Define Feature Integration Test Plan (μT_FEAT_[FeatureSlug]_INTG_PLAN_001)
    *   **Directive from `🌌WeaverCore`:** All implemented and unit-tested `CodeModule_🕸️N_ids` for `Feature_🕸️N_id`, `architecture_design_🕸️N_id` (if exists), `feature_spec_detail_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🏗️architect` or senior `🧪tester-definer` (per `OpProfile.integration_test_planning_assignee_policy`).
    *   **Task Description:** Define integration test scenarios. Focus on interactions BETWEEN this feature's components AND interactions of this feature with existing key project components/services (identified from `🧠cognitive_navigator` query of `🕸️P_project_dependency_graph` relevant to `CurrentPhaseConfig_🕸️N.TechProfile`). Prioritize tests for high `🎲R_interaction_points` (e.g., external API calls, shared database tables, complex data transformations between components).
    *   **Deliverables:** `IntegrationTestPlan_🕸️N` (with scenarios, setup, expected outcomes) stored in 🕸️Canvas via `🧠cognitive_navigator`, linked to `Feature_🕸️N`.
    *   **Pheromone Update:** `trail📈` to `μT_FEAT_[FeatureSlug]_INTG_IMPL_002`. `guide✨` pheromones on component interactions that require specific testing.
    *   **Success Criteria (🚦):** Comprehensive and prioritized integration test plan defined and stored in 🕸️Canvas.

#### 2.4.2. Implement Integration Tests (μT_FEAT_[FeatureSlug]_INTG_IMPL_002)
    *   **Directive from `🌌WeaverCore`:** `IntegrationTestPlan_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id` (for `TechProfile.integration_test_framework` and `OpProfile.llm_for_test_coding`).
    *   **Assignee:** `⚡coder` or `🧪tester-implementer`.
    *   **Task Description:** Implement the integration tests as code according to `IntegrationTestPlan_🕸️N`. Test environment setup (e.g., mock external services, seed test data) instructions should be part of plan, potentially using `CurrentPhaseConfig_🕸️N.TechProfile.test_data_seeding_script_path` or Docker services.
    *   **Deliverables:** Integration test suite code (e.g., `tests/integration/[feature_slug]_integration_tests.ext`). `IntegrationTestSuite_🕸️N` entity in 🕸️Canvas via `🧠cognitive_navigator`, linked to plan and feature.
    *   **Pheromone Update:** `trail📈` to `μT_FEAT_[FeatureSlug]_INTG_EXEC_003`.
    *   **Success Criteria (🚦):** All planned integration tests implemented as runnable code.

#### 2.4.3. Execute Integration Tests (μT_FEAT_[FeatureSlug]_INTG_EXEC_003)
    *   **Directive from `🌌WeaverCore`:** `IntegrationTestSuite_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id`. The `μT_resolved_tooling_strategy` specifies execution environment: may involve Docker (`🐳↑ → 🐳→🏃 → 🐳↓` orchestrated via `🐳docker_engineer` for services defined in `TechProfile.docker_compose_integration_testing_file`) or direct (`execute_command [TechProfile.integration_test_command]`).
    *   **Assignee:** Specialized `🧪integration_tester` (or general Tester if appropriate per OpProfile).
    *   **Task Description:** Execute all implemented integration tests for the feature. Capture results and logs.
    *   **Deliverables:** `IntegrationTestRun_🕸️N` (PASS/FAIL, detailed results, coverage if tool supports for integration level) stored in 🕸️Canvas via `🧠cognitive_navigator`.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** IF FAIL, strong `warn❗` on `Feature_🕸️N` and specifically on involved `component_🕸️N`s with high failure rates in this run. `trail📈` routed to `🔍debugger` for integration issues. IF PASS, strong `guide✨` of stability on `Feature_🕸️N`.
    *   **Success Criteria (🚦):** All integration tests PASS. Detailed results logged.

#### 2.4.4. Define End-to-End (E2E) / User Acceptance Test (UAT) Scenarios (μT_FEAT_[FeatureSlug]_UAT_DEF_004)
    *   **Directive from `🌌WeaverCore`:** Original `feature_spec_detail_🕸️N_id` (especially user stories and BDD scenarios), `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `📝spec_writer` or dedicated `🧪uat_designer`.
    *   **Task Description:** Based on user stories and BDD from the feature spec, define high-level E2E test scenarios that mimic real user workflows for this feature. These should validate the feature's goal from an end-user perspective. Consider critical positive and negative paths. Specify test data requirements for UAT.
    *   **Deliverables:** `UAT_Scenario_Set_🕸️N` (listing scenarios, steps, expected results, test data needs) stored in 🕸️Canvas, linked to `Feature_🕸️N`.
    *   **Pheromone Update:** `trail📈` to `μT_FEAT_[FeatureSlug]_UAT_IMPL_005` (if automation planned) or directly to `_UAT_EXEC_` (if manual/semi-automated).
    *   **Success Criteria (🚦):** Comprehensive UAT scenarios covering feature's user-facing goals are defined and stored.

#### 2.4.5. Implement E2E / UAT Automation (Optional - If `CurrentPhaseConfig_🕸️N.OpProfile.e2e_test_automation_policy == 'AUTOMATE_ALL'` or `AUTOMATE_CRITICAL`) (μT_FEAT_[FeatureSlug]_UAT_IMPL_005)
    *   **Directive from `🌌WeaverCore`:** `UAT_Scenario_Set_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id` (for `TechProfile.e2e_automation_framework` like Selenium/Playwright/Cypress, and OpProfile LLM for coding these tests).
    *   **Assignee:** `⚡coder` with E2E tool expertise or dedicated `🧪e2e_automation_engineer`.
    *   **Task Description:** Implement automated test scripts for the defined UAT scenarios using the framework specified in TechProfile.
    *   **Deliverables:** E2E automated test scripts (e.g., `tests/e2e/[feature_slug]_e2e_tests.ext`). `E2E_TestSuite_🕸️N` in 🕸️Canvas linked to `UAT_Scenario_Set_🕸️N`.
    *   **Pheromone Update:** `trail📈` to `_UAT_EXEC_`.
    *   **Success Criteria (🚦):** Automated E2E tests implemented and runnable for defined UAT scenarios.

#### 2.4.6. Execute E2E / UAT (μT_FEAT_[FeatureSlug]_UAT_EXEC_006)
    *   **Directive from `🌌WeaverCore`:** `UAT_Scenario_Set_🕸️N_id` (for manual/semi-auto) OR `E2E_TestSuite_🕸️N_id` (for automated). `CurrentPhaseConfig_🕸️N_id`. The `μT_resolved_tooling_strategy` specifies if tests run against a staging environment (requiring `🐳docker_engineer` or `☁️cloud_architect` for setup via directive if env not persistent) using automation tools from TechProfile.
    *   **Assignee:** `🧪e2e_tester`.
    *   **Task Description:** Execute the E2E user acceptance tests. If GUI based, uses TechProfile browser automation tools (`execute_command [TechProfile.e2e_run_command]`).
    *   **Deliverables:** `UAT_Run_🕸️N` or `E2E_TestRun_🕸️N` (PASS/FAIL for each scenario) stored in 🕸️Canvas via `🧠cognitive_navigator`.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** IF FAIL, strong `warn❗` on `Feature_🕸️N`. `trail📈` to `🔍debugger` for E2E issues. IF ALL PASS, `status_pheromone` on `Feature_🕸️N` becomes `TESTING_COMPLETE_ jakości_PASS`. Strong `trail📈` to `μT_FEAT_[FeatureSlug]_DOC_DRAFT_001` or "Section 3: Release Preparation" if documentation is already complete or handled separately.
    *   **Success Criteria (🚦):** All defined UAT/E2E scenarios PASS. Results comprehensively logged.

### 2.5. Documentation Generation & Review Loop (Sub-Phase: `FEAT_DOC_[FeatureSlug]_005`) - *Can run in parallel with late testing stages if OpProfile allows.*

#### 2.5.1. Draft Technical & User Documentation (μT_FEAT_[FeatureSlug]_DOC_DRAFT_001)
    *   **Directive from `🌌WeaverCore`:** `Feature_🕸️N_id` (must have status `TESTING_COMPLETE_ jakości_PASS`), all linked `feature_spec_detail_🕸️N`, `architecture_design_🕸️N`, `CodeModule_🕸️N`s. `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `📚doc_writer`.
    *   **Task Description:** Create/update technical (API docs from `Interface_🕸️N`s, module descriptions from `CodeModule_🕸️N`s with their `docstring_property`) and user-facing documentation (how-to guides, feature explanations from `feature_spec_detail_🕸️N.user_stories`) for `Feature_🕸️N_id`. LLM, style, detail from `CurrentPhaseConfig_🕸️N.OpProfile.documentation_policy`. Query `🧠cognitive_navigator` (per `DataStrategy`) for `🕸️N_doc_template`, `🕸️N_style_guide`, and existing relevant `guide✨` pheromones.
    *   **Deliverables:** Draft `TechnicalDoc_🕸️N` and `UserDoc_🕸️N` linked to `Feature_🕸️N` in 🕸️Canvas. Files (e.g., Markdown) in `docs/feature_slug/`. Temporary work stored in 🔥MemoryBank.
    *   **Pheromone Update:** `trail📈` on `μT_FEAT_[FeatureSlug]_DOC_REVIEW_002`.
    *   **Success Criteria (🚦):** Draft documents created, stored. Cover all aspects defined in `CurrentPhaseConfig_🕸️N.OpProfile.documentation_completeness_checklist`.

#### 2.5.2. Automated & AI-Assisted Documentation Review (μT_FEAT_[FeatureSlug]_DOC_REVIEW_002)
    *   **Directive from `🌌WeaverCore`:** Draft `TechnicalDoc_🕸️N_id` and `UserDoc_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🧩meta_strategist` (using `mcp📞SequentialThinking` or a "doc-linting-bot" sub-mode, as per `CurrentPhaseConfig_🕸️N.OpProfile.documentation_review_tool_policy`).
    *   **Task Description:** Review draft documentation for clarity, accuracy (against specs/arch in 🕸️Canvas), completeness, grammar, and adherence to `🕸️N_style_guide` from Canvas. Check for consistency with actual implemented code behavior (e.g., API endpoint details).
    *   **Deliverables:** `DocReviewReport_🕸️N` for each doc type, listing issues or giving approval. Stored in 🕸️Canvas.
    *   **Pheromone Update (by `🤔reflection_engine/scribe`):** IF issues, `warn❗` on draft doc 🕸️Ns & `trail📈` back to `📚doc_writer` for revision `μT_FEAT_..._DOC_REVISE_X`. IF approved, `Documentation_🕸️N.status = 'APPROVED'`, and `Feature_🕸️N.status_pheromone` becomes `DOCUMENTATION_COMPLETE`. Strong `trail📈` indicates readiness for Release Review.
    *   **Success Criteria (🚦):** Documentation reviewed. Status updated to 'APPROVED'. All critical issues resolved.

*(End of Section 2 for one Feature. `🌌WeaverCore` proceeds to the next Feature defined in plan.md, or if all features are `DOCUMENTATION_COMPLETE` and/or `READY_FOR_RELEASE_REVIEW`, it may be directed by `🧩meta_strategist` to start Section 3: Release Preparation.)*

---

## 🚀 Section 3: Release Preparation & Deployment - [RELEASE_VERSION_X.Y.Z] (Phase: `REL_PREP_DEPLOY_XYZ`)

**Pheromone Focus (trail📈 for this Phase):** `release_candidate_XYZ_deployment_pipeline`
**Active Configuration (CurrentPhaseConfig_🕸️N_id):** `[A NEW CFG_ID_FOR_RELEASE_PHASE, e.g., CFG_RELEASE_XYZ_001, snapshotting OpProfile & TechProfile specific for release activities, set by meta_strategist]`
**Objective:** Package all `Feature_🕸️N`s marked with `status_pheromone = DOCUMENTATION_COMPLETE` or `READY_FOR_RELEASE_REVIEW`, perform final release validation, and deploy `[RELEASE_VERSION_X.Y.Z]` to target environment(s) according to `CurrentPhaseConfig_🕸️N.OpProfile.deployment_strategy`.

### 3.1. Release Candidate Branching, Versioning & Changelog Generation (μT_REL_BRANCH_VERSION_001)
    *   **Directive from `🌌WeaverCore`:** List of `Feature_🕸️N_ids` for this release, proposed semantic version `X.Y.Z`, `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🌌WeaverCore` (using `execute_command` for Git; `⚡coder` or `📚doc_writer` for version file & changelog updates).
    *   **Task Description:**
        1.  Create `release/X.Y.Z` branch from `develop` (or `main`, per `TechProfile.branching_model`).
        2.  Merge all feature branches for included `Feature_🕸️N`s into `release/X.Y.Z`. Handle merge conflicts (may trigger `🔍debugger` sub-μTs if complex).
        3.  Tag `vX.Y.Z-rc1` (Release Candidate 1).
        4.  Task `⚡coder`: Update version numbers in all project files specified in `TechProfile.versioned_files_list` (e.g., `setup.py`, `package.json`, `pom.xml`).
        5.  Task `📚doc_writer` (using `🧠cognitive_navigator` to pull `Feature_🕸️N.summaries` for this release): Generate `CHANGELOG.md` draft for `vX.Y.Z`.
    *   **Deliverables:** `release/X.Y.Z` branch created & stable. `vX.Y.Z-rc1` tag. Version numbers consistent. Draft `CHANGELOG.md`. `ReleaseCandidate_🕸️N` created in 🕸️Canvas, linked to all included `Feature_🕸️N`s.
    *   **Pheromone Update:** Strong `trail📈` on `μT_REL_BUILD_ARTIFACT_002`.
    *   **Success Criteria (🚦):** Branch & tag exist. CI build (if configured via TechProfile) on release branch PASSES. Version files & changelog updated.

### 3.2. Build & Verify Release Artifacts (μT_REL_BUILD_ARTIFACT_002)
    *   **Directive from `🌌WeaverCore`:** `ReleaseCandidate_🕸️N_id` (branch `release/X.Y.Z`), `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🐳docker_engineer` (if Dockerized, using `TechProfile.docker_build_command_release`) or `☁️cloud_architect` (for other build systems using `TechProfile.release_build_script_path`).
    *   **Task Description:** Build all specified release artifacts (Docker images, JARs, executables) from the release branch. Perform basic artifact verification (e.g., image scans for critical CVEs using tool in TechProfile, checksum validation). Push artifacts to repository specified in `TechProfile.artifact_repository_url`.
    *   **Deliverables:** Verified `Artifact_🕸️N` (type, version, repo_url, checksum, security_scan_status_🚦) in 🕸️Canvas, linked to `ReleaseCandidate_🕸️N`. Artifacts published.
    *   **Pheromone Update:** `trail📈` on `μT_REL_STAGING_DEPLOY_003`. If artifact verification fails, `warn❗` on `ReleaseCandidate_🕸️N`.
    *   **Success Criteria (🚦):** Build successful. Artifacts verified (checksums match, critical CVE scan PASS) and published.

### 3.3. Deploy Release Candidate to Staging Environment (μT_REL_STAGING_DEPLOY_003)
    *   **Directive from `🌌WeaverCore`:** `Artifact_🕸️N_id` to deploy, `CurrentPhaseConfig_🕸️N_id` (which specifies staging environment details from `TechProfile.staging_env_config_🕸️N_ref`).
    *   **Assignee:** `☁️cloud_architect`.
    *   **Task Description:** Deploy the release candidate artifact to the STAGING environment using deployment scripts/IaC defined in `TechProfile.staging_deployment_script_path`.
    *   **Deliverables:** Staging deployment completed. `DeploymentLog_🕸️N` (env='staging', status, artifact_deployed) in 🕸️Canvas.
    *   **Pheromone Update:** `trail📈` to `μT_REL_STAGING_TEST_004`. `warn❗` if deployment fails.
    *   **Success Criteria (🚦):** Deployment to staging successful. Application health checks in staging pass.

### 3.4. Execute Full Regression, Performance & Smoke Tests on Staging (μT_REL_STAGING_TEST_004)
    *   **Directive from `🌌WeaverCore`:** Staging environment URL/access. All relevant `TestSuite_🕸️N` (Unit, Integration, E2E/UAT) IDs from Canvas features in this release. `CurrentPhaseConfig_🕸️N_id` (specifies `OpProfile.staging_test_rigor_level`, performance test script paths if any).
    *   **Assignee:** `🧪comprehensive_tester_suite_runner` (conceptual: orchestrates various tester modes or runs a master test script).
    *   **Task Description:** Execute a full battery of automated tests (unit, integration, E2E/UAT, plus any performance/load tests specified by OpProfile for staging) against the staging deployment. Test execution strategy from `CurrentPhaseConfig_🕸️N` (e.g., direct or via `🐳docker_engineer`).
    *   **Deliverables:** `MasterStagingTestReport_🕸️N` in 🕸️Canvas, aggregating results from all test suites. Links to individual `TestRun_🕸️N`s.
    *   **Pheromone Update:** IF FAIL, strong `warn❗` on `ReleaseCandidate_🕸️N`, detailed `warn❗` on specific failed test/feature. `trail📈` to `🔍debugger` (for hotfix on `release/X.Y.Z` branch). IF PASS, `status_pheromone` on `ReleaseCandidate_🕸️N` becomes `STAGING_VALIDATED_READY_FOR_PROD_APPROVAL`.
    *   **Success Criteria (🚦):** ALL designated tests (unit, integration, E2E/UAT, basic performance) PASS on staging. Comprehensive report logged.

### 3.5. Production Deployment Approval Gate (μT_REL_PROD_APPROVAL_005)
    *   **Directive from `🌌WeaverCore`:** `ReleaseCandidate_🕸️N_id` (must have status `STAGING_VALIDATED_READY_FOR_PROD_APPROVAL`), `MasterStagingTestReport_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id` (for `OpProfile.prod_deployment_approval_policy`: 'auto_if_staging_clear_low_dice_r', 'manual_human_ping', 'auto_with_meta_strategist_final_check'). Associated overall release `🎲R_score`.
    *   **Assignee:** `🧩meta_strategist`.
    *   **Task Description:** Review release candidate readiness for production.
        *   If `OpProfile.policy == 'manual_human_ping'`: PING designated human stakeholder (e.g., email, Slack message via integration or `execute_command` with a script) with summary and link to `MasterStagingTestReport_🕸️N`. Await explicit human approval (recorded back to Canvas, possibly via a simple API endpoint Weaver monitors or manual update).
        *   If `OpProfile.policy == 'auto_with_meta_strategist_final_check'`: `🧩meta_strategist` uses `mcp📞SequentialThinking` with all test reports, 🎲R scores, current 🏦budget status, and business priority `trail📈` from `Feature_🕸️N`s in this release to make a GO/NO-GO.
    *   **Deliverables:** `ProductionDeploymentApproval_🕸️N` (status: Approved/Rejected, approver, justification/reasoning) in 🕸️Canvas, linked to `ReleaseCandidate_🕸️N`.
    *   **Pheromone Update:** If Approved, strong `trail📈` to `μT_REL_PROD_DEPLOY_006`. If Rejected, strong `warn❗` and `trail📈` to debugging/rollback_planning/re-scoping.
    *   **Success Criteria (🚦):** Explicit approval decision (automated by `🧩meta_strategist` or human via callback) logged in `ProductionDeploymentApproval_🕸️N`.

### 3.6. Deploy to Production & Smoke Test (μT_REL_PROD_DEPLOY_006)
    *   **Directive from `🌌WeaverCore`:** Approved `ReleaseCandidate_🕸️N_id` / `Artifact_🕸️N_id`. `CurrentPhaseConfig_🕸️N_id` (for `TechProfile.production_env_config_🕸️N_ref` and `OpProfile.production_deployment_strategy`: e.g., 'blue_green', 'canary_10_percent', 'rolling_update').
    *   **Assignee:** `☁️cloud_architect`.
    *   **Task Description:** Deploy the approved artifact to the PRODUCTION environment using the strategy specified in OpProfile. This may involve multiple sub-μTasks for canary phases, traffic shifting, etc. After each stage/full deployment, execute critical smoke tests (`TechProfile.production_smoke_test_script_path`).
    *   **Deliverables:** Production deployment successful. `ProdDeploymentLog_🕸️N` (env='production', status, artifact_deployed, strategy_used, smoke_test_status) in 🕸️Canvas. A new `VersionedRelease_🕸️N` for `vX.Y.Z` is created and marked `LIVE`.
    *   **Pheromone Update:** `status_pheromone` on `VersionedRelease_🕸️N` (for vX.Y.Z) becomes `LIVE_IN_PRODUCTION`. Strong `trail📈` for `μT_REL_POST_MONITOR_007`. Announce success on a conceptual `project_status_dashboard_🕸️N`.
    *   **Success Criteria (🚦):** Deployment successful according to chosen strategy. Critical smoke tests PASS in production. `VersionedRelease_🕸️N` is LIVE.

### 3.7. Post-Deployment Monitoring & Initial Feedback (μT_REL_POST_MONITOR_007)
    *   **Directive from `🌌WeaverCore`:** `VersionedRelease_🕸️N_id` that just went LIVE. `CurrentPhaseConfig_🕸️N_id` (for `TechProfile.monitoring_tool_config_details` and `OpProfile.post_release_monitoring_duration_critical` e.g., "1 hour").
    *   **Assignee:** `📊monitor_setup_agent` (conceptual mode for configuring monitoring tools via APIs/scripts) & `🤔reflection_engine` (for actively watching alerts/metrics conceptually fed into Canvas).
    *   **Task Description:**
        1.  `📊monitor_setup_agent` ensures monitoring dashboards/alerts (e.g., Prometheus, Grafana, Sentry, CloudWatch via APIs/scripts based on `TechProfile.monitoring_tool_setup_instructions_🕸️N_ref`) are correctly targeting the new production version and key SLIs/SLOs.
        2.  `🤔reflection_engine` actively queries (conceptually) a `LiveMetrics_🕸️N` stream from these tools (or summaries pushed to Canvas) for the duration specified in `OpProfile.post_release_monitoring_duration_critical`. Looks for critical error spikes, performance degradations, SLI breaches.
    *   **Deliverables:** Monitoring confirmed active for new release. An initial (`e.g., OpProfile.monitoring_duration`) `PostReleaseHealth_🕸️N` summary (key metrics, error rates, any incidents) stored in 🕸️Canvas linked to `VersionedRelease_🕸️N`.
    *   **Pheromone Update:** IF critical anomalies, strong `warn❗` on `VersionedRelease_🕸️N`. This could trigger `🧩meta_strategist` to consider rollback strategy via `☁️cloud_architect`. If stable, strengthen `guide✨` on `VersionedRelease_🕸️N` indicating stability. Reset `priority_pheromone_strength_trail📈` on `Project_🕸️N` for "next development cycle" or "maintenance mode".
    *   **Success Criteria (🚦):** Monitoring is verified active and configured. Initial health summary logged. No CRITICAL post-deployment failures exceeding OpProfile thresholds during the defined critical monitoring window.

---

## 🔧 Section 4: System Operations & Autonomous Maintenance (Phase: `SYS_OPS_MAINTAIN_ONGOING`)

**Pheromone Focus (trail📈 types):** `system_maintenance_cycle`, `proactive_security_audit_trigger`, `refactor_opportunity_detected_trail📈`, `canvas_health_scheduled_check_trail📈`, `umi_evolution_analysis_trigger`
**Active Configuration:** These tasks use the `CurrentPhaseConfig_🕸️N` associated with a general 'MAINTENANCE_OPERATIONS' OpProfile, which is regularly reviewed/updated by `🧩meta_strategist` via μT_MAINT_BUDGET_REVIEW_CYCLE.
*(These are ongoing, cyclically triggered based on frequencies in the active 'MAINTENANCE_OPERATIONS' OpProfile, or event-driven based on `🤔reflection_engine` findings.)*

### 4.1. Scheduled Tech Horizon Scanning Cycle (μT_MAINT_TECHSCAN_CYCLE_[YYYYMMDD])
    *   **Trigger:** `🧩meta_strategist` based on `Maintenance_OpProfile.tech_scan_frequency`.
    *   **Directive from `🌌WeaverCore` includes:** `CurrentPhaseConfig_🕸️N_id` (for `perplexity_ask` budget for `📡TechScan`, active TechProfile for list of libs to scan).
    *   **Assignee:** `🤔reflection_engine`.
    *   **Task:** Execute `📡TechScan Protocol` as per UMI.
    *   **Deliverables:** `HorizonEvent_🕸️N`s in 🕸️Canvas. `AdaptationProposal_🕸️N` for `🧩meta_strategist`.
    *   **Success Criteria (🚦):** Scan cycle completed. Findings logged.

### 4.2. Scheduled Cognitive Canvas Integrity Audit Cycle (μT_MAINT_CANVAS_AUDIT_CYCLE_[YYYYMMDD])
    *   **Trigger:** `🧩meta_strategist` based on `Maintenance_OpProfile.canvas_audit_frequency`.
    *   **Directive from `🌌WeaverCore` includes:** `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🤔reflection_engine` (or `🛡️canvas_auditor` sub-role).
    *   **Task:** Execute `🛡️CanvasIntegritySuite`. Maintain `critical_decision_shadow_log.sqlite`. Alert `🧩meta_strategist` via `❗🧠Cognitive System Alert` node if issues, potentially triggering switch to `DEGRADED_CANVAS_OPMODE`.
    *   **Deliverables:** `CanvasAuditReport_🕸️N`. Shadow log updated.
    *   **Success Criteria (🚦):** Audit completed. Issues logged/addressed.

### 4.3. Scheduled UMI/Mode/Strategy Effectiveness Review & AMO Proposal Cycle (μT_MAINT_AMO_REVIEW_CYCLE_[YYYYMMDD])
    *   **Trigger:** `🧩meta_strategist` based on `Maintenance_OpProfile.amo_cycle_frequency`.
    *   **Directive from `🌌WeaverCore` includes:** `CurrentPhaseConfig_🕸️N_id` (for analysis depth).
    *   **Assignee:** `🤔reflection_engine` -> outputs to `🧩meta_strategist`.
    *   **Task:** Deep analysis of 🕸️Canvas: UMI section effectiveness, Mode performance, Tooling/Data Strategy outcomes (which ones yield best cost/success/🎲R balance?). Generate `🕸️N_improvement_hypothesis` for UMI, Mode definitions, or heuristic rules within OpProfiles (e.g., "Hypothesis: If TechProfile is 'NodeJS_XYZ', always use `london-tester` first for unit tests").
    *   **Deliverables:** `AMO_Report_🕸️N`. New/updated `🕸️N_improvement_hypothesis` sent to `🧩meta_strategist` A/B test queue.
    *   **Success Criteria (🚦):** Cycle completed. Actionable hypotheses logged.

### 4.4. Proactive Refactoring Identification & Planning Cycle (μT_MAINT_REFACTOR_ID_CYCLE_[YYYYMMDD])
    *   **Trigger:** `🧩meta_strategist` based on `Maintenance_OpProfile.refactor_scan_frequency`.
    *   **Assignee:** `🤔reflection_engine` (identification) -> `🏗️architect` (planning if candidate approved by `🧩meta_strategist`).
    *   **Task:**
        1.  `🤔reflection_engine`: Scan 🕸️Canvas for technical debt: high complexity `CodeModule_🕸️N`s, frequently failing test `🕸️P_test_failure_cluster`s, components with many recent `warn❗` pheromones, duplicated `🕸️P_code_logic_patterns`.
        2.  Output `RefactoringCandidateReport_🕸️N` to `🧩meta_strategist` with 🎲R_technical_debt scores.
        3.  If `🧩meta_strategist` approves a candidate based on `OpProfile.refactor_approval_threshold_🎲R_debt` and available 🏦budget, it tasks `🏗️architect` to create `RefactoringPlan_🕸️N`.
    *   **Deliverables:** `RefactoringCandidateReport_🕸️N`. If approved for planning, `RefactoringPlan_🕸️N` which details scope, goals, risks, pre/post tests. (Refactoring execution becomes a new feature-like track in Section 2).
    *   **Success Criteria (🚦):** Scan cycle done. Candidates logged. High-priority refactoring plans exist for approved candidates.

### 4.5. Budget Review & Operational Profile Tuning Cycle (μT_MAINT_BUDGET_REVIEW_CYCLE_[YYYYMMDD])
    *   **Trigger:** `🧩meta_strategist` based on `Maintenance_OpProfile.budget_review_frequency` or if `🏦project_budget_🕸️N.burn_rate_🎲R_current_vs_target` exceeds OpProfile alert threshold.
    *   **Directive from `🌌WeaverCore` (relaying from `🧩meta_strategist`):** `CurrentPhaseConfig_🕸️N_id`.
    *   **Assignee:** `🧩meta_strategist` (may task `💰cost_optimizer` for detailed data crunching and `🤔reflection-engine` for cost-saving idea generation).
    *   **Task:** Review current `🏦project_budget_🕸️N` burn rate vs. `Project_🕸️N.milestone_dates`. Tune the general 'MAINTENANCE_OPERATIONS' OpProfile OR create/switch to a more specific project OpProfile (e.g., from BALANCED to ULTRA_COST_SAVE_HIBERNATE). Update LLM choices, tool cost thresholds, research budgets, testing rigor parameters within the chosen/tuned OpProfile stored in 🕸️Canvas.
    *   **Deliverables:** `BudgetReviewReport_🕸️N`. Updated parameters in relevant `🕸️N_op_profile`(s) in 🕸️Canvas. Communication to `🌌WeaverCore` of any immediate change in active OpProfile.
    *   **Success Criteria (🚦):** Review cycle completed. Active OpProfile parameters in 🕸️Canvas are tuned and aligned with current budget reality and project velocity goals.

---

## 📖 Appendix A: Definitions & Conventions

*   **[PROJECT_NAME], [FeatureSlug], etc.:** Placeholders.
*   **🕸️N, 🕸️R, 🕸️P:** Nodes, Relationships, Paths in Neo4j Cognitive Canvas.
*   **trail📈, guide✨, warn❗:** Pheromone types/properties.
*   **🎲R:** Risk Score/Profile (can be a simple score or a complex 🕸️N).
*   **🚦:** Success Criteria / Quality Gate status.
*   **🔥:** MemoryBank MCP context.
*   **🧱:** SQLite_KB context.
*   **🏦:** Budget / Cost / Financial context.
*   **💡:** Generative Innovation Protocol context.
*   **📡:** Tech Horizon Scanning context.
*   **🛡️:** Cognitive Canvas Integrity context.
*   **🚩:** Ambiguity Flag/Resolution context.
*   **docs💰:** Cost Justification context (links to a `Justification_🕸️N`).
*   **μT_Phase_Category_ShortName_Seq[.SubSeq]:** Micro-task naming convention.
*   **CurrentPhaseConfig_🕸️N_id:** ID of the immutable Neo4j node snapshotting ALL active OpProfile & TechProfile parameters for the current phase. `🌌WeaverCore` ensures all modes receive and adhere to this for their μTasks.
*   **μT_resolved_tooling_and_data_strategy_🕸️N_ref:** Pointer to where `🌌WeaverCore`'s specific directives for a μT (tool choice, data tier, budget for that step) are logged in the 🕸️Canvas (likely as properties on the `μT_🕸️N` itself or a small linked configuration object).

---

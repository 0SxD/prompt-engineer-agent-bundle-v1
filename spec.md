# spec.md | CANONICAL HANDOFF & COM. STREAM
# Project: Prompt_Toolkit_v0_1
# Bundle: forked from HumanX_OS_v1
# Bootstrapped: 2026-04-24
# Protocol version: v0.1

<zero_bloat_protocol>
Assume each turn is terminal. Do not retain chat history.
Execute all state-saves directly to spec.md using strict structured fields.
Maintain 3-tier memory architecture:
  1. HOT_CACHE: max 500 words. Immediate next actions + active vars only.
  2. GRAPH_LINKS: minimalist pointers to external files and skills. No inline content.
  3. COMPACTION_LEDGER: record of hard-pruned context. Zero token leakage.
Main chat output: cave-man syntax only.
</zero_bloat_protocol>

---

## HOT_CACHE
<!-- max 500 words | next actions + active vars | overwrite each turn -->

STATUS: bundle_initialized 2026-04-24. Prompt_Toolkit_v0_1 staged. 10 files written. First session pending user upload + paste of 0_QUICKSTART into Project settings.

SESSION_TYPE: scaffold-init.

ACTIVE_TASK: PT-INIT-001 (validate bundle integrity once user uploads to Project, run first archive_check).

NEXT_ACTION (user): (1) Paste 0_QUICKSTART.md code block into Claude Project Settings, REPLACE prior content, save. (2) Upload all 10 bundle files to Project. (3) Open new chat. (4) First message: "load spec.md HOT_CACHE".

NEXT_ACTION (next Claude turn): run archive_check on /mnt/project/, confirm 10-file bundle present and intact, report any missing files, then ask user which mode (a-e per first_move sequence) to advance.

ACTIVE_VARS:
- bundle_files_count: 10 (README, 0_QUICKSTART, spec, skills, Wiki_Log, metrics_ledger, canon/SYMBOLIC_DICTIONARY, canon/PROMPT_COMPONENT_TAXONOMY, canon/WIKI_3x3_SCHEMA, prompts/ARCHETYPES)
- canon_source_uploads: 9 (7 PNGs + 2 MDs from user, registered in PROMPT_COMPONENT_TAXONOMY source-trace section)
- canon_source_in_chat: 1 (giant protocol mashup from prior session, decomposed into 27 components in PROMPT_COMPONENT_TAXONOMY)
- archetypes_seeded: 3 (single-turn-executor, frontloaded-multi-turn, socratic-cascade)
- pre_submit_gate_version: v0.1 (4 rules, all derivation-cited)
- wiki_3x3_schema_version: v0.1

CONFIDENCE: TRUE=1 on bundle structure + first-pass component decomposition + archetype seeding. FALSE=0 on production readiness until first user-driven decomposition session validates the schema in practice.

---

## GRAPH_LINKS
<!-- pointers only, no inline content -->

### bundle files (this scaffold)
- protocol_canon: project://0_QUICKSTART.md
- bundle_map: project://README.md
- skill_tree: project://skills.md
- wiki_log: project://Wiki_Log.md
- metrics_ledger: project://metrics_ledger.md
- symbolic_dictionary: project://canon/SYMBOLIC_DICTIONARY.md
- component_taxonomy: project://canon/PROMPT_COMPONENT_TAXONOMY.md
- wiki_3x3_schema: project://canon/WIKI_3x3_SCHEMA.md
- archetypes: project://prompts/ARCHETYPES.md

### canon source materials (registered in PROMPT_COMPONENT_TAXONOMY, not duplicated in bundle)
- src_image_1_trinity_protocol: user_upload://Trinity_Protocol_overview_image_chrome_brave_IMAGE_2026_4_14.png
- src_image_2_neuro_symbolic_geometry: user_upload://OsXai_Symbolic_Reasoning_Architecture.png
- src_image_3_event_sourced_identity: user_upload://Event_Source_Identity_Architecture.png
- src_image_4_143_blueprint: user_upload://system_directive_protocol.png
- src_image_5_high_confidence_dialectic: user_upload://Symbolic_Symbolic_Arch_Dialectic.png
- src_image_6_a2a_circuit_breaker: user_upload://Neuro_Symbolic_ai_logic_systems_arch.png
- src_image_7_pathos_core_gate3: user_upload://Pathos_Core_Gate_3_overview_diagram.png
- src_md_1_symbolic_overview: user_upload://Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md
- src_md_2_neuro_symbolic_blueprint: user_upload://The_Neuro-Symbolic_Blueprint_wiki_note.md
- src_chat_1_protocol_mashup: chat_message://2026-04-24-prior-turn-paste

### inherited canon (HumanX_OS_v1, referenced for fork pattern only, not for content)
- humanx_os_v1_root: legacy_project://HumanX_OS_v1/ (template inheritance, fork procedure source)
- 143_protocol_a_blueprint: legacy_project://HumanX_OS_v1/canon/143_protocol_a_blueprint.md (governance overlay)

### external (referenced in source materials)
- arxiv_neurosymbolic_explainability: arXiv:2410.14219 (cited by user in src_md_1, not independently verified)

---

## COMPACTION_LEDGER
<!-- record of pruned content with replacement pointer -->

- 2026-04-24 INGESTED: 9 user uploads (7 PNGs + 2 MDs) describing the visual symbolic architecture across multiple iterations. REPLACEMENT_POINTER: canon/SYMBOLIC_DICTIONARY.md (consolidated symbol reference) + canon/PROMPT_COMPONENT_TAXONOMY.md (component decomposition with source traces back to specific images).
- 2026-04-24 INGESTED: giant in-chat protocol mashup from prior session containing system_directive, pert_framework_mandate, 0sXai output template, agent_onboarding_directive_addendum, EXAMPLE_OF_HOW_TURNS_WORK, source-cited research gate, and embedded omx_skill_execution example. REPLACEMENT_POINTER: 27 component entries in canon/PROMPT_COMPONENT_TAXONOMY.md, each with source-trace back to the specific section of the mashup.
- 2026-04-24 PRUNED: HumanX_OS_v1 domain content (SFF grant work, FateX architecture, SageX architecture, career applications). REPLACEMENT_POINTER: HumanX_OS_v1 lives in /mnt/project/ from the prior session's project; this fork inherits architecture only, not content.
- 2026-04-24 NEUROLOGY_REFERENCES: per user explicit instruction this session, neurology references (DMN, prefrontal, hippocampus mappings) in the source materials are noted as metaphor only, not used as architecture justification in the taxonomy. Brain-region labels appear in source images but are not propagated into component definitions.

---

## TASK_QUEUE
<!-- TID: status one-line -->

- PT-INIT-001: pending, validate bundle integrity once user uploads to Project (T-0)
- PT-DECOMP-002: queued, first user-driven prompt decomposition session (validates the taxonomy template in practice)
- PT-LINT-003: queued, first wiki 3x3 schema lint pass after 3 new components added
- PT-ARCHETYPE-004: queued, build first user-specific archetype assembly from a real task
- PT-PROMOTE-005: queued, promote first insight from INSIGHTS_LEDGER to a sub-skill once 2+ tasks confirm or 1 hard-fail
- PT-FORK-006: deferred, document fork procedure for sibling workstream (e.g., Prompt_Toolkit_for_LegalDrafting_v0_1) once v0.1 stable

---

## INSIGHTS_LEDGER
<!-- 1 pattern minimum per turn. Promote to skills.md when 2+ tasks confirm OR 1 hard-fail. -->

- INSIGHT 01 (2026-04-24, scaffold init): Sage's 9 uploads + in-chat mashup contain 27 distinct prompt components, often appearing 3-4 times across different documents with slight variations. Variation is the signal; the canonical version of each component is the union of variations, not any single instance.

- INSIGHT 02 (2026-04-24): The Trinity-of-Trinities pattern (3x3 = 9 sub-evaluators) from Image 1 + Image 5 maps cleanly onto a wiki schema (3 sections of 3 sub-parts each). This means every wiki we write doubles as a 9-cell evaluation rubric. Mechanical to check.

- INSIGHT 03 (2026-04-24): Three distinct prompt archetypes are latent in the source material. Single-Turn Executor (fast pattern-match), Frontloaded Multi-Turn (research with bounded questioning), Socratic Cascade (consequential work, full questioning until 100% confidence). User did not name these explicitly; they emerge from how different components combine.

- INSIGHT 04 (2026-04-24): The visual symbolic layer ([Λ] [Π] [Θ] [0️⃣] [💯] [❓x3] [∞] [∞/∞] [⏳] [💾]) functions as a compression layer for the protocol. A prompt using the symbols is shorter than one written in prose, AND simultaneously becomes a visual artifact that can be rendered as a diagram. Dual-purpose by design.

- INSIGHT 05 (2026-04-24): Per user explicit instruction this session, neurology references (DMN, prefrontal, hippocampus) in the source images are metaphor and should NOT propagate into the taxonomy as architectural justification. The architecture stands on Aristotelian rhetoric (Logos / Pathos / Ethos) and computer science (loops, gates, memory tiers), not on biology.

---

## OPEN_Q
<!-- load-bearing questions; each blocks at least one downstream task -->

OQ-01 (non-blocking, gates v0.2): Does user want CLAUDE.md added to the bundle for CLI Claude Code use? Currently excluded to keep bundle at 10 files and consumer-friendly. Can be added in v0.2 if CLI workflow is adopted.

OQ-02 (non-blocking, gates archetype expansion): Are there more than 3 archetypes? Possible candidates from source material include "Multi-Agent A2A Cascade" (Image 6) and "Read-Only Researcher" (Image 4). Defer until user brings a concrete task that doesn't fit one of the three current archetypes.

OQ-03 (non-blocking, gates research backing): User mentioned "papers supporting the reasoning for their efficacy" should accompany the toolkit. Currently the only external research cited is arXiv:2410.14219 (from src_md_1). Other components have implicit research backing (e.g., chain-of-thought, self-consistency, ReAct, tree-of-thoughts) but no specific arXiv IDs are provided in user materials. Decision: each component entry has a "research_backing" field marked "TBD by user, candidate sources noted" until user provides specific citations.

OQ-04 (non-blocking, gates visual rendering layer): User flagged that the symbolic layer can be rendered as infographics by image generators. Visual rendering is a v0.2+ scope item. v0.1 ships text-only.

OQ-05 (deferred, gates ML framework integration): User mentioned the prompts will eventually feed a "specialized ML framework" with Markov chains and atomic 3x3x3 pass/fail criteria producing standalone executable scripts. This is a separate downstream system. v0.1 produces only the prompt components and archetypes; the ML framework consumes them later.

---

## RULES

### protocol (from 0_QUICKSTART.md v0.1)
- All rules in 0_QUICKSTART.md are canonical. Rewrites require version bump and re-paste into Project settings.
- This file (spec.md) is the running state. Modify freely as the project evolves; preserve structure.

### pre-submit gate rules (v0.1)
- See 0_QUICKSTART.md `<pre_submit_gate>` block, 4 rules.

### coverage rules
- Every wiki page in this project must have 3 sections (Pathos, Ethos, Logos), each with 3 sub-parts (Input, Execution, Output) per canon/WIKI_3x3_SCHEMA.md.
- Every component in canon/PROMPT_COMPONENT_TAXONOMY.md must have: definition, where_it_goes, when_to_use, when_NOT_to_use, 3x3_eval_rubric, copy_paste_block, source_trace, research_backing.
- Every archetype in prompts/ARCHETYPES.md must list mandatory components, optional components, and at least one worked example showing assembly.
- Symbol fidelity is mechanical. The exact bracketed format is preserved in all generated files.

---

## file registry

### canon (read-only in normal operation)
- canon/SYMBOLIC_DICTIONARY.md
- canon/PROMPT_COMPONENT_TAXONOMY.md
- canon/WIKI_3x3_SCHEMA.md
- (referenced) all 9 user uploads in /mnt/user-data/uploads/ from this session
- (referenced) HumanX_OS_v1 canon in legacy /mnt/project/ from prior session

### mutable (self-evolving)
- state: spec.md (this file)
- skill_tree: skills.md
- wiki_log: Wiki_Log.md
- protocol_canon: 0_QUICKSTART.md (version-bumped on hard-fail)
- bundle_map: README.md
- telemetry: metrics_ledger.md
- archetypes: prompts/ARCHETYPES.md (extended with new archetypes as patterns emerge)

---

## first move every new chat

<first_move>
1. Run archive_check: scan /mnt/project/ for the 10 bundle files. Report missing.
2. Read spec.md HOT_CACHE to load current state.
3. Read skills.md tree-index. Load only the sub-skill relevant to the turn.
4. Read metrics_ledger.md last 3 rows.
5. Pre-output eval: TRUE=1 acts, FALSE=0 asks up to 3 Qs.
6. Read OPEN_Q. If unanswered OPEN_Q gates the requested task, answer that first.
7. Ask user which mode to advance: (a) decompose new prompt mash-up, (b) refine existing component, (c) assemble archetype for specific task, (d) lint wiki for 3x3 schema compliance, (e) other.
</first_move>

---

## goal

<goal>
v0.1: stand up the bundle, validate the 10-file structure, validate the 27-component taxonomy template, validate 3 archetypes compose cleanly.

v0.2: ingest first real user prompt mash-up via PT-DECOMP-002, validate template under fire, version-bump rules from any hard-fails.

Long-term: this bundle becomes the open-source reference for prompt component decomposition and archetype assembly. Forks for specific domains (legal drafting, scientific research, customer support, code review, etc.) follow the same scaffold, swap the domain layer.

End every turn TRUE=1 or FALSE=0.
</goal>

END_SPEC

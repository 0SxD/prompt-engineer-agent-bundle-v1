# skills.md | Prompt_Toolkit_v0_1 | skill tree
# POINTERS ONLY. NO INLINE CONTENT. Load 1 sub-skill per turn max.
# Bundle: Prompt_Toolkit_v0_1
# Bootstrapped: 2026-04-24 (v0.1)

## read_protocol (mandatory)
1. Read THIS file first to discover available sub-skills.
2. Load only the sub-skill relevant to the current move. Do NOT preload.
3. Max 1 sub-skill per turn unless user explicitly requests more.
4. If sub-skill is STATUS: pending_draft, note in spec.md OPEN_Q, do not invent content.
5. After task closes, promote new patterns via insight_promotion rule (2+ tasks OR 1 hard-fail).

## status legend
- live: file exists, content ready, can be invoked.
- pending_draft: registered but not yet written. Do not hallucinate.
- pending_extraction: content lives in canon, needs distillation to its own .md.
- inline_in_canon: skill is implemented as a section of an existing canon file, not a standalone file. Reference the canon file and section.

## sonnet_runnable column
Skills tagged Sonnet-runnable (Y) can be executed by a Sonnet sub-agent end-to-end without opus reasoning, given the right inputs.

## tree

### core (gates and arbitration, carry across forks)
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| pre_submit_gate | 4-rule mechanical scan, all TRUE before ship | inline in 0_QUICKSTART.md `<pre_submit_gate>` | inline_in_canon | Y |
| trinity_dialectic_check | Logos / Pathos / Ethos pre-finalize check | inline in canon/WIKI_3x3_SCHEMA.md | inline_in_canon | N |
| symbol_fidelity_scan | mechanical bracket-format check on generated text | inline in 0_QUICKSTART.md gate rule 4 | inline_in_canon | Y |
| em_dash_scan | U+2014 + U+2013 mechanical check | inline in 0_QUICKSTART.md gate rule 3 | inline_in_canon | Y |
| wiki_3x3_lint | scan any new wiki for 3-section, 3-subpart, 9-cell compliance | skills/wiki_3x3_lint.md | pending_draft | Y |

### prompt_component_ops
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| component_decomposer | take new prompt mashup, identify which of the 27 components it uses, flag novel components | skills/component_decomposer.md | pending_draft | N |
| component_definer | for a novel component, fill the full template (def, where, when, when-not, 3x3, copy-paste, source-trace) | skills/component_definer.md | pending_draft | N |
| component_lookup | given a task description, return the list of components most likely needed | skills/component_lookup.md | pending_draft | Y |
| component_diff | compare two versions of the same component across user materials, propose canonical form | skills/component_diff.md | pending_draft | Y |

### archetype_ops
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| archetype_selector | given a task description, recommend single-turn vs frontloaded vs socratic-cascade | skills/archetype_selector.md | pending_draft | Y |
| archetype_assembler | given an archetype + components, write the full XML-Markdown prompt | skills/archetype_assembler.md | pending_draft | Y |
| archetype_extender | propose a new archetype when no existing one fits, decompose it through the same template | skills/archetype_extender.md | pending_draft | N |

### wiki_ops
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| wiki_3x3_writer | write new wiki page conformant to 3-of-3 schema | skills/wiki_3x3_writer.md | pending_draft | Y |
| wiki_3x3_lint | health-check existing wiki for schema compliance | skills/wiki_3x3_lint.md | pending_draft | Y |
| source_trace_filler | for any claim in any wiki, attach source-trace to a canon entry or chat-confirm | skills/source_trace_filler.md | pending_draft | Y |

### research_synthesis (cross-component)
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| research_backing_filler | for components with research_backing TBD, locate candidate arXiv or repo source | skills/research_backing_filler.md | pending_draft | Y |
| citation_discipline | one-source-per-claim, no model-assumption, quote-under-15-words | inline in 0_QUICKSTART.md `<domain_rules>` Copyright clause | inline_in_canon | Y |
| source_triangulation | when 2 sources conflict, propose canonical resolution + flag in spec.md OPEN_Q | skills/source_triangulation.md | pending_draft | Y |

### session_ops (carry across forks)
| slug | summary | path | status | sonnet |
|---|---|---|---|---|
| handoff_writer | At 75% context, write HANDOFF + CUTPASTE + ANALYSIS bundle | skills/handoff_writer.md | pending_draft | Y |
| insight_promotion | 2-tasks-or-hardfail rule, ledger-to-sub-skill promotion | skills/insight_promotion.md | pending_draft | Y |
| metrics_ledger_append | per-turn row append, trend check, tier audit | skills/metrics_ledger_append.md | pending_draft | Y |
| pre_submit_gate_evolution | each hard-fail produces new gate rule, version bump | skills/pre_submit_gate_evolution.md | pending_draft | N |
| archive_check | scan /mnt/project/ for legacy or missing files at every bootstrap | skills/archive_check.md | pending_draft | Y |
| fork_to_sibling_workstream | re-fork this OS to new workstream, preserve invariants | skills/fork_to_sibling_workstream.md | pending_draft | N |

## registry rules
- New sub-skill = new row here + new <snake_case>.md file in skills/.
- Row fields: slug, summary (under 12 words), path, status, sonnet.
- Slug = snake_case, matches filename without .md.
- No inline content in this file.
- Status transitions: pending_draft to live (on file write).
- Skills marked inline_in_canon stay inline; do NOT extract to a separate file unless they grow past 1 page.
- Deprecate: move obsolete row to archive section at bottom.

## sub-agent invocation contract

When dispatching to a Sonnet sub-agent, the calling Opus turn must:
1. Name the sub-skill loaded (one of the slugs above with status=live AND sonnet=Y).
2. State input contract: what canon files, what user answers, what runtime state required.
3. State output contract: what artifact returns, what gates it must clear.
4. Set verification step: which gate (pre_submit_gate? wiki_3x3_lint?) the output passes through before ship.
5. State terminal verdict format: TRUE=1 returns artifact, FALSE=0 returns OPEN_Q escalation.

## archive
- (none)

END_SKILLS

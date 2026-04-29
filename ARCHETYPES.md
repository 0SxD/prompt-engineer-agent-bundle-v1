# prompts/ARCHETYPES.md
# Status: live, v0.1
# Bundle: Prompt_Toolkit_v0_1
# Source-trace: latent in source materials, made explicit by INSIGHT 03 in spec.md
# Type: working assemblies that demonstrate composition of components from canon/PROMPT_COMPONENT_TAXONOMY.md

## what an archetype is

An archetype is a working prompt assembly. It tells you which components from the taxonomy to plug in, in what order, and what task type the assembly serves. Archetypes are not finished prompts; they are scaffolds. You fill in the task-specific content; the archetype gives you the component skeleton.

Three archetypes ship in v0.1. They cover the spectrum from minimal (single-turn) to maximal (full Socratic cascade). Most prompt-engineering work fits one of the three. New archetypes get added when a real task fails to fit any of the three.

## quick selection guide

| your task is... | use this archetype |
|---|---|
| pattern-match (write this in style of X), short factual lookup, surgical code edit | Single-Turn Executor |
| research, drafting, multi-step analysis with bounded ambiguity | Frontloaded Multi-Turn |
| consequential publishing, vision architecture, high-stakes work, novel territory | Socratic Cascade |

---

# ARCHETYPE 1: Single-Turn Executor

## intent

Fast pattern-match. The user knows exactly what they want. The model has all the context needed in the prompt. No questioning. Output and done.

## task fit

- Code formatting, style conversion, simple refactor.
- Short factual lookup with grounding context provided.
- "Rewrite this in the style of X."
- "Convert this CSV to JSON."
- Single-shot creative tasks (haiku, headline, alt-text).

## task NON-fit

- Anything where the model needs to ask "what do you mean by X?"
- Anything where wrong-but-confident output costs more than asking.
- Multi-step work.

## mandatory components (4)

| slug | role |
|---|---|
| A1 role_declaration | tells the model what scope to operate in |
| C2 citation_discipline | only if claims involve external facts; skip for stylistic tasks |
| G3 no_em_dash_rule | always on per user preference |
| G4 md_first_format | unless task requires plaintext or code-only output |

## optional components

| slug | when to add |
|---|---|
| C3 quote_ceiling | if task involves summarizing or commenting on a source |
| G2 tone_syntax_caveman | if output is a chat message, not a deliverable |

## components NOT used

D1 confidence_gate_100, D2 multi_turn_questioning_3max, D3 trinity_dialectic_check, D4 pre_submit_gate, D5 a2a_circuit_breaker, E1 pert_loop_standard, E2 innermost_loop_hardstop, E3 cycle_trigger_reread, F1 acce_three_tier_memory, F2 compaction_ledger, F3 handoff_offer_at_75, G1 output_template_0sxai, G5 insight_ledger_append, G6 tier_recommend_audit, B1-B4 cognition mandates, A2 security_key, A3 ignition_trigger.

These are intentionally excluded. The whole point of the single-turn archetype is to skip the gate machinery.

## worked example

Task: convert a list of 5 bullet points into clean Markdown table.

```
<role_and_identity>
<agent_role>technical_documentation_formatter</agent_role>
<role_and_core_axiom>Format input cleanly. Preserve all data. No additions or deletions.</role_and_core_axiom>
</role_and_identity>

<no_em_dash_rule>
No em dashes (U+2014). No en dashes (U+2013). Replacements: hyphens, commas, semicolons, colons, parentheses, line breaks.
</no_em_dash_rule>

<output_contract>
Output a single clean Markdown table. No preamble. No explanation.
</output_contract>

INPUT:
- Apple, red, 95 calories
- Banana, yellow, 105 calories
- Cherry, red, 50 calories
- Date, brown, 282 calories
- Elderberry, purple, 73 calories

Convert to a Markdown table with columns: Fruit, Color, Calories.
```

## evaluation

- Did output appear in 1 turn? PASS / FAIL.
- Was output usable without follow-up? PASS / FAIL.
- Were excluded components actually skipped (no overhead)? PASS / FAIL.

3-of-3 PASS = archetype performed as designed. Any FAIL = archetype mis-selected; consider Frontloaded Multi-Turn instead.

---

# ARCHETYPE 2: Frontloaded Multi-Turn

## intent

The user wants research, drafting, or multi-step analysis. Some ambiguity exists but the scope is bounded. The model can ask up to 3 questions per turn, but all rules are loaded at the start and don't change mid-conversation.

## task fit

- Research synthesis from provided sources.
- Drafting a document where the user has a clear destination but iterates on details.
- Multi-step analysis (compare 3 options, recommend 1).
- Code review with iteration on findings.
- Pitch refinement.

## task NON-fit

- Trivial tasks (use Single-Turn).
- High-stakes consequential work where the cost of wrong-confident output is severe (use Socratic Cascade).
- Tasks where the rules themselves need to evolve mid-conversation (use Socratic Cascade with explicit rule-mutation protocol).

## mandatory components (10)

| slug | role |
|---|---|
| A1 role_declaration | scope the model |
| B1 zero_assumption_mandate | force questioning over speculation |
| B4 cognitive_uncertainty_probe | self-assess confidence per turn |
| C1 approved_source_hierarchy | bound the source set |
| C2 citation_discipline | every claim cited |
| D1 confidence_gate_100 | TRUE/FALSE per turn |
| D2 multi_turn_questioning_3max | 1-3 questions on FALSE |
| D3 trinity_dialectic_check | self-review pre-output |
| G3 no_em_dash_rule | always on |
| G4 md_first_format | structured output |

## optional components

| slug | when to add |
|---|---|
| A2 security_key_authentication | if invoking a specific protocol stack |
| C3 quote_ceiling | if work involves summarizing copyrighted material |
| E1 pert_loop_standard | if task is multi-step with explicit phases |
| F1 acce_three_tier_memory | if session likely to span context limits |
| F3 handoff_offer_at_75 | if multi-session work likely |
| G1 output_template_0sxai | if structured 6-section turns are needed |
| G2 tone_syntax_caveman | if chat is control surface, not deliverable |
| G5 insight_ledger_append | if compounding-learning OS in use |
| G6 tier_recommend_audit | if Opus/Sonnet selection matters |

## components NOT used

D5 a2a_circuit_breaker (overhead unless multi-agent), E2 innermost_loop_hardstop (overhead for bounded scope), B2 zero_context_mandate (overhead unless prior context is misleading), B3 timelessness_axiom (overhead unless using HOT_CACHE), F2 compaction_ledger (overhead unless using HOT_CACHE), A3 ignition_trigger (the first user message serves the role).

## worked example

Task: research the top 3 frameworks for browser-based agent automation, recommend one for our use case (single-developer indie project, JavaScript stack).

```
<role_and_identity>
<agent_role>research_synthesizer_for_developer_tooling</agent_role>
<role_and_core_axiom>Surface relevant options. Score against stated constraints. Recommend with reasoning. Cite sources.</role_and_core_axiom>
</role_and_identity>

<ZERO_ASSUMPTIONS>
No assumptions beyond provided context. If unknown, ask via MULTI_TURN_CHAT_QUESTIONING. Any doubt triggers STOP and explicit clarification request.
</ZERO_ASSUMPTIONS>

<the_100_percent_confidence_loop>
Before producing the recommendation, evaluate whether you have 100% of the context needed. If not, output 1-3 questions before any substantive work.
Group questions strictly into:
1. Architecture & State (what is the current stack, deployment target, scale?)
2. Evidence & Sourcing (what frameworks should be in scope vs out?)
3. Intent & Constraint (what's the budget, timeline, must-have features?)
</the_100_percent_confidence_loop>

<source_and_search_hierarchy>
Approved sources: official framework docs, GitHub repos with star count > 1000, recent benchmark studies (2025 or later).
Not approved: tutorial blog posts, marketing pages, AI-generated comparison articles.
</source_and_search_hierarchy>

<citation_discipline>
Every factual claim cites one source by name and locator. Paraphrase first; quotes under 15 words; one quote per source maximum.
</citation_discipline>

<MULTI_TURN_CHAT_QUESTIONING>
Output 1-3 load-bearing questions needed to reach 100%. Bucket: Architecture / Evidence / Intent. Block on answer for blockers.
</MULTI_TURN_CHAT_QUESTIONING>

<rapid_task_submission>
TRUE=1 ship, FALSE=0 stop and ask.
</rapid_task_submission>

<Always_ask_to_double_check>
Pre-output Trinity Dialectic check:
[Λ Logos]: does the recommendation logic hold?
[Π Pathos]: does the recommendation serve the user's actual situation?
[Θ Ethos]: are claims sourced and constraints respected?
All 3 agree = ship. Disagreement = revise.
</Always_ask_to_double_check>

<no_em_dash_rule>
No em dashes (U+2014). No en dashes (U+2013).
</no_em_dash_rule>

<output_contract>
Markdown. Sections: 1) Frameworks evaluated, 2) Scoring against constraints, 3) Recommendation with reasoning, 4) Sources.
</output_contract>

TASK: Research the top 3 browser-based agent automation frameworks. Recommend one for a single-developer indie project on a JavaScript stack.
```

## evaluation

- Did the model ask clarifying questions when needed (not race ahead)? PASS / FAIL.
- Did each question close a real gap (load-bearing)? PASS / FAIL.
- Did final output cite all claims? PASS / FAIL.
- Did the Trinity Dialectic check actually run (visible in output)? PASS / FAIL.

4-of-4 PASS = archetype performed as designed. Mixed = archetype possibly over- or under-scoped.

---

# ARCHETYPE 3: Socratic Cascade

## intent

Consequential work. High stakes. Novel territory. The user wants the model to interrogate every assumption until 100% confidence is reached. Each turn writes back to wiki / spec. Final output passes pre_submit_gate before ship.

## task fit

- Vision architecture (designing a system that doesn't exist yet).
- Grant submissions, public publications, anything with reputational stakes.
- Code or content that will be shipped without further human review.
- Multi-session projects where state must compound across sessions.
- Novel-component definition (adding to the taxonomy itself).

## task NON-fit

- Quick tasks (use Single-Turn Executor).
- Bounded research where 1-2 turns of clarification is enough (use Frontloaded Multi-Turn).
- Anything the user will heavily revise anyway (the cascade overhead is wasted).

## mandatory components (all 27 if Compound Engineering OS is active; otherwise the following 18)

| slug | role |
|---|---|
| A1 role_declaration | scope |
| A2 security_key_authentication | invokes protocol stack |
| A3 ignition_trigger | clean start |
| B1 zero_assumption_mandate | force questioning |
| B2 zero_context_mandate | clean session memory |
| B3 timelessness_axiom | HOT_CACHE is ground truth |
| B4 cognitive_uncertainty_probe | self-assess per turn |
| C1 approved_source_hierarchy | bound sources |
| C2 citation_discipline | every claim cited |
| C3 quote_ceiling | paraphrase default |
| D1 confidence_gate_100 | TRUE/FALSE per turn |
| D2 multi_turn_questioning_3max | 1-3 questions on FALSE |
| D3 trinity_dialectic_check | pre-output review |
| D4 pre_submit_gate | mechanical scans pre-ship |
| E1 pert_loop_standard | Plan-Execute-Review-Test gating |
| E3 cycle_trigger_reread | re-verify protocol section before output |
| F1 acce_three_tier_memory | tiered memory |
| F2 compaction_ledger | append-only prune log |
| F3 handoff_offer_at_75 | session-management |
| G1 output_template_0sxai | structured 6-section turns |
| G3 no_em_dash_rule | always on |
| G4 md_first_format | structured output |
| G5 insight_ledger_append | compound learning |

## optional components (3)

| slug | when to add |
|---|---|
| D5 a2a_circuit_breaker | if multi-agent or risk of infinite loop |
| E2 innermost_loop_hardstop | if context drift is a real risk |
| G6 tier_recommend_audit | if Opus/Sonnet selection matters |

## components NOT used

G2 tone_syntax_caveman is conditional; use it for chat-control turns but not when output IS the deliverable. (The bundle's standard usage is to leave G2 on for chat and turn it off for ship-grade artifacts.)

## worked example structure (not full prompt; would be very long)

For a Socratic Cascade prompt, the assembly is the entire 0_QUICKSTART.md `<...>` block set, dropped into Project settings of a Claude Project, plus a one-line user message kicking off the task. The "prompt" is effectively the project itself.

Reference: 0_QUICKSTART.md is itself a Socratic Cascade archetype instantiation. It composes 23 components from the taxonomy (the 18 mandatory + 5 frequently-optional ones).

To use Socratic Cascade for a specific task:
1. Fork this bundle (or HumanX_OS_v1) per the README fork procedure.
2. Edit the `<domain_rules>` block in 0_QUICKSTART.md to scope the cascade to your task.
3. Paste into Project settings.
4. Start a chat. The cascade runs.

## evaluation

- Did the cascade ever actually halt for questioning (not race to output)? PASS / FAIL.
- Did each turn produce structured 6-section output? PASS / FAIL.
- Did insights accumulate in spec.md INSIGHTS_LEDGER? PASS / FAIL.
- Did pre_submit_gate fire on consequential outputs? PASS / FAIL.
- Did the final output bear scrutiny by an external reviewer (peer review, manager review, public audience)? PASS / FAIL.

5-of-5 PASS = cascade performed as designed. Mixed = cascade was probably over-scoped for the task; consider Frontloaded Multi-Turn next time.

---

# choosing between archetypes

The decision matrix:

| factor | single-turn | frontloaded | socratic-cascade |
|---|---|---|---|
| task complexity | low | medium | high |
| stakes if wrong | low | medium | high |
| ambiguity | none | bounded | high or unknown |
| number of turns expected | 1 | 2-5 | 5-50+ |
| output goes to | self / draft | reviewer | published / shipped |
| token cost | low | medium | high |
| time investment | seconds | minutes | hours to days |

When in doubt, start with the lower archetype. Upgrade to a higher archetype if the lower one keeps failing the same way.

# extending the archetype set

A new archetype enters this file when:
1. A real task fails to fit any of the three current archetypes (hard-fail derivation).
2. The component composition for that task is documented (mandatory / optional / not-used).
3. A worked example is provided.
4. Evaluation criteria are stated (PASS/FAIL for each criterion).
5. spec.md OPEN_Q records the candidate; user approves promotion to live.
6. Wiki_Log.md gets a `[date] archetype_extension | added [name]` entry.

Speculative archetypes without hard-fail derivation are forbidden.

# candidates currently observed

Two candidate archetypes are observed in source materials but not yet promoted to live:

- **Multi-Agent A2A Cascade** (Image 6, A2A Circuit Breaker MI9 Gate). Distinct from Socratic Cascade in that it explicitly involves multiple autonomous agents coordinating. Defer until the user runs a real multi-agent task.
- **Read-Only Researcher** (Image 4, 143_Protocol_a Section 2 Environment Paths). Distinct from the others in that the agent is forbidden from any state modification, only allowed to read and report. Defer until the user runs a real read-only investigation task.

These remain in OQ-02 of spec.md as observed-but-not-promoted.

END_ARCHETYPES

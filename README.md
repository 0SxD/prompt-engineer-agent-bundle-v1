# README.md
# Bundle: Prompt_Toolkit_v0_1
# Generated: 2026-04-24
# Forked from: HumanX_OS_v1 (compounding-learning OS pattern)
# Governance overlay: 143_Protocol_a Blueprint
# Domain: prompt component decomposition, taxonomy, archetype assembly

## what this bundle is

A self-evolving operating system for one job: take a messy prompt mash-up, decompose it into atomic components, and document what each component does, where it goes, when to use it, and how to evaluate it. The bundle is a working scaffold, not a finished product. You upload it into a Claude Project (web or app) and it boots a Claude session into "prompt-decomposer + archetype-assembler" mode.

Think of it as a kitchen for prompts. The pantry (`canon/PROMPT_COMPONENT_TAXONOMY.md`) holds the ingredients. The recipe book (`prompts/ARCHETYPES.md`) shows three ways to combine them. The cook (Claude) reads the protocol (`0_QUICKSTART.md`) and follows it every turn.

## who this is for

- People who write a lot of prompts and want to know what parts of their prompts actually do something.
- People building prompt libraries, agent frameworks, or prompt-engineering tools.
- People who want a structured way to ask: "should this prompt be one-turn, multi-turn frontloaded, or full Socratic cascade?"

## what is in the bundle (10 files)

```
README.md                              this file
0_QUICKSTART.md                        protocol cutpaste, goes in Claude Project settings
spec.md                                running state, updated by Claude every turn
skills.md                              tree-index of sub-skills (pointers, no inline content)
Wiki_Log.md                            chronological append-only history
metrics_ledger.md                      silent telemetry, token compression trend

canon/                                 read-only reference, never modified by Claude
  SYMBOLIC_DICTIONARY.md               visual language: [Λ Logos] [Π Pathos] [Θ Ethos] etc.
  PROMPT_COMPONENT_TAXONOMY.md         THE MAIN REFERENCE: 27 components decomposed
  WIKI_3x3_SCHEMA.md                   3-of-3 structure rule for every wiki you write

prompts/                               working assemblies that demonstrate composition
  ARCHETYPES.md                        3 templates: single-turn, frontloaded, socratic-cascade
```

## how to use it (5 minutes)

1. Open a Claude Project (claude.ai or app). Create new, or use existing.
2. Upload all bundle files into Project files. They land at `/mnt/project/`.
3. Open Project settings, "Set project instructions" field. Replace whatever is there with the entire contents of `0_QUICKSTART.md`. Save.
4. Start a new chat. First message: `load spec.md HOT_CACHE`.
5. State auto-loads. Claude reads protocol, runs first-move sequence, asks you which component or archetype you want to advance.

That's it. The bundle does the rest.

## the core idea

Sage's prompt mash-up has 27 distinct components hiding inside it. Most prompts use 5 to 10 of them, glued together in ad-hoc ways. This bundle says: name each component, define what it does, document where it goes in a prompt and when to use it, give every component a 3x3 evaluation rubric (Input gate, Execution gate, Output gate, each scored on Pathos / Ethos / Logos), and then show three working ways to combine them.

The 3x3 rubric (9 sub-evaluators per component) comes from the Trinity-of-Trinities pattern in your uploads (Image 1, Image 2, Image 5). It applies to every wiki we write inside this bundle. Every page has 3 sections (Pathos, Ethos, Logos). Each section has 3 sub-parts (Input, Execution, Output). That is 9 evaluation cells per page, mechanical to check, hard to fake.

## why this is a fork of HumanX_OS_v1, not a fresh build

The HumanX_OS_v1 bundle in `/mnt/project/` already solved file architecture, memory tiers, insight promotion rule, and the pre-submit gate. We inherit those invariants and rewrite only the domain layer. That is the fork procedure documented in `HumanX_OS_v1/README.md`. We carried four invariants:

1. File architecture (`spec.md` + `skills.md` + `Wiki_Log.md` + `metrics_ledger.md`).
2. Three-tier memory (`HOT_CACHE` + `GRAPH_LINKS` + `COMPACTION_LEDGER`).
3. Promotion rule (2 confirms or 1 hard-fail to promote insight to skill).
4. Caveman tone in chat, full content in `.md` files.

What we changed: the domain layer in `0_QUICKSTART.md`, the seeded `spec.md` HOT_CACHE, the `skills.md` tree, the canon files in `canon/`. Everything in `canon/` is new and specific to prompt-engineering work.

## what this bundle is NOT

- Not a prompt library you assemble and sell. The bundle teaches the pattern; the library you build using it is yours.
- Not an agent framework. It is a scaffold for a Claude Project that helps you build prompts. Agents come later (Sage's roadmap).
- Not multimodal. Visual rendering of symbolic prompts is on Sage's roadmap, not in v0.1.
- Not a finished product. v0.1. Designed to evolve. Every hard-fail produces a new rule and bumps the version.

## the 3 archetypes (the recipe book)

Inside `prompts/ARCHETYPES.md` you get three working prompt assemblies, each composed from the components in the taxonomy:

1. **Single-Turn Executor**: rules frontloaded, no questioning, instant execute. For pattern-match tasks.
2. **Frontloaded Multi-Turn**: all rules at start, max 3 questions per turn allowed, iterative refinement. For research and drafting.
3. **Socratic Cascade**: questions cascade until 100% confidence, each turn writes back to wiki, gated by a final approval check. For consequential work, vision architecture, anything you publish.

You pick the archetype based on what your task is. The archetype tells you which components from the taxonomy to plug in.

## evolution rule

Every hard-fail (a prompt that shipped and turned out broken) produces a new rule in the relevant component file. Bump the file version. Append a note to `metrics_ledger.md`. Append a `[date] insight_promotion` line to `Wiki_Log.md`. The bundle gets stronger every time something breaks. Speculative rules without a real failure are forbidden.

## philosophy invariants (do not modify across forks)

1. Environment, not memory, is ground truth (143_Protocol_a Section 2).
2. Zero assumption: any doubt triggers stop and Socratic interrogation.
3. Stigmergic interaction: write artifacts, do not debate.
4. Trinity Dialectic gates all consequential action.
5. Caveman tone in chat, full content in `.md` files.
6. No em dashes. Hyphens, commas, semicolons, colons, parentheses, line breaks only.
7. Approved sources only: arXiv, official docs, auditable GitHub, institutional or lab or military, plus user-provided primary material.

## fork to a sibling workstream

To fork this bundle to a new prompt-related workstream (say, "Prompt_Toolkit_for_LegalDrafting_v0_1"):

1. Copy the entire bundle folder to a new name.
2. Edit `0_QUICKSTART.md`: replace the `<domain_rules>` block with your new domain.
3. Reset `spec.md` HOT_CACHE, OPEN_Q, TASK_QUEUE.
4. Reset `Wiki_Log.md` with a new init entry.
5. Reset `metrics_ledger.md` with new headers, no rows.
6. Edit `skills.md`: keep `core` rows, reset everything else.
7. New chat, paste `0_QUICKSTART.md` block into Project settings.

The four invariants above carry across all forks unchanged.

## first move when re-uploaded

1. Open Project settings, paste `0_QUICKSTART.md` code block into "Set project instructions". REPLACE whatever was there. Save.
2. Upload all bundle files into Project files. They land at `/mnt/project/`.
3. Start a new chat. First user move: `load spec.md HOT_CACHE`.
4. State auto-loads. Claude runs first-move sequence per `0_QUICKSTART.md`. Asks which component you want to advance or which archetype you want to assemble.

END_README

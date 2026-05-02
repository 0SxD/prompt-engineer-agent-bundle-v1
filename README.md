# prompt-engineer-agent-bundle-v1

A self-contained Claude Project bundle for structured prompt decomposition, taxonomy-driven evaluation, and archetype assembly.

## Status

R&D / Experimental. Maintained by Sage / 0SxD as part of an ongoing research portfolio focused on prompt engineering, agent skills, and LLM evaluation.

## What this is

This bundle operationalizes a method for decomposing messy, composite prompts into atomic components and then reassembling them using one of three documented archetypes. It is designed to be uploaded directly into a Claude Project (web or desktop), where it boots the model into a structured "prompt-decomposer and archetype-assembler" mode. The core insight is that most prompts silently combine 5-10 distinct components from a larger taxonomy of 27. Naming each component, defining its role, and scoring it with a 3x3 rubric (Input / Execution / Output, across Pathos / Ethos / Logos) makes prompt quality measurable rather than impressionistic.

The bundle is a working scaffold, not a finished product. It evolves: each hard-fail produces a new rule that increments the component version.

## Approach

- 27-component taxonomy covering every functional part of a prompt (context, instruction, tone, gate, retry logic, etc.)
- Three archetype assemblies: Single-Turn Executor, Frontloaded Multi-Turn, Socratic Cascade
- 3x3 rubric per component (9 sub-evaluators: Input / Execution / Output x Logos / Pathos / Ethos)
- Self-evolving spec: Claude writes back to spec.md and Wiki_Log.md every turn
- Zero-assumption mandate: any doubt triggers a stop and structured questioning before execution
- No em-dashes anywhere; hyphens, colons, parentheses, line breaks only

## Layout

- `0_QUICKSTART.md` - paste into Claude Project settings to boot the protocol
- `spec.md` - running state; Claude updates this every turn
- `skills.md` - tree-index of sub-skills (pointers only, no inline content)
- `PROMPT_COMPONENT_TAXONOMY.md` - the main reference: 27 components decomposed
- `ARCHETYPES.md` - three working prompt assemblies demonstrating composition
- `SYMBOLIC_DICTIONARY.md` - visual language used in evaluation and wiki outputs
- `WIKI_3x3_SCHEMA.md` - structural rule for every wiki page written by the bundle
- `Wiki_Log.md` - chronological, append-only history
- `metrics_ledger.md` - token compression trend and silent telemetry

## Usage / How to read this

This repo is a documentation and skill bundle. To use it:

1. Open a Claude Project (claude.ai or the desktop app).
2. Upload all bundle files into Project files.
3. Open Project settings and replace the instructions field with the full contents of `0_QUICKSTART.md`.
4. Start a new chat. First message: `load spec.md HOT_CACHE`.
5. The bundle auto-boots. Claude reads the protocol and asks which component or archetype to advance.

## Prior art and citations

- Anthropic Skills spec / agentskills.io
- AGENTS.md spec (Linux Foundation Agentic AI Foundation)

See also: [trinity-dialectic](https://github.com/0SxD/trinity-dialectic) for output-side dialectical evaluation.

## License

MIT. Copyright (c) 2026 Sage / 0SxD

## Notes

This repo is part of an active R&D portfolio. Content may move, change, or be withdrawn. Issues and PRs welcome but reviews are best-effort.

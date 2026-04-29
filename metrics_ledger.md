# metrics_ledger.md | silent telemetry | zero canon weight | Prompt_Toolkit_v0_1
# Bundle: forked from HumanX_OS_v1
# Append-only. Purpose: trend output_tokens per task + sonnet:opus ratio + tier_recommend accuracy.
# Origin: dispatch_v2 OS pattern via HumanX_OS_v1.

## legend
- turn_ts: ISO timestamp.
- task_id: Prompt_Toolkit task identifier (PT-INIT-NNN, PT-DECOMP-NNN, PT-LINT-NNN, PT-ARCHETYPE-NNN, BOOT, CLOSE-OUT, etc.).
- turn_number: 1-indexed within the task's chat session. 0 reserved for archive_check scans.
- model: opus | sonnet | haiku.
- input_tokens_est: chars(input) / 4.
- output_tokens_est: chars(Claude output) / 4.
- out_in_ratio: output / input.
- outcome: TRUE1 | FALSE0 | PENDING | ITER-N | scan_clean | scan_flagged_N.
- tier_recommend: opus_gate | sonnet_exec.
- notes: free-text key signals.

## success-eval rule
Rolling avg last 3 completed tasks' output_tokens vs prior 3.
Trending down + approval stable-or-rising = TRUE=1 compounding.
Flat-or-rising = FALSE=0, audit non-reducing skill or wiki bloat.
Sonnet:Opus target ratio above 3:1.

## tier_recommend audit rule
At every 5th task completion, audit prior 5 turns:
- Were opus_gate turns truly structural (novel pattern, hard-fail recovery, taxonomy expansion, archetype design)?
- Were sonnet_exec turns truly routine (pattern-match, established skill, surgical fix)?
- Mismatch = correction insight to spec.md INSIGHTS_LEDGER.

---

## rows

| turn_ts | task_id | turn_number | model | input_tokens_est | output_tokens_est | out_in_ratio | outcome | tier_recommend | notes |
|---|---|---|---|---|---|---|---|---|---|
| 2026-04-24T_PM | PT-INIT-001 | 0 | opus | ~32000 | ~14500 | 0.45 | TRUE1 | opus_gate | bundle scaffold turn. heavy ingest (9 uploads + giant in-chat mashup + project canon). 10-file bundle produced. component taxonomy holds 27 entries. archetypes seeded 3. heaviest single output of v0.1; subsequent decomposition turns expected to compress significantly. |

## notes on baseline trend
- Turn 1 (PT-INIT-001): out_in_ratio 0.45. Scaffold-init turn, expected to be heavy on output. Subsequent turns should drop to 0.20-0.30 range as canon stabilizes and most work becomes lookup + small additions.

## next milestone
Task 5 (after 4 user-driven decomposition or archetype turns): compare rolling out_in_ratio of last 3 completed tasks vs prior 3. Target: rolling avg under 0.30.

## bundle-specific note
Prompt_Toolkit v0.1 is a smaller-scope domain than HumanX. Per-turn outputs should compress faster, easier to drive Sonnet:Opus to 3:1. Realistic target: 2:1 by task 5, 3:1 by task 15.

END_LEDGER

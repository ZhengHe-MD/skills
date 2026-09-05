---
name: badminton-video-editing
description: Edit badminton training into a complete practice record or one-clip-per-routine highlights.
disable-model-invocation: true
---

# Badminton video editing

Produce a chronological video for the player to review their own training. Use **plain cuts, no labels, and no inserted gaps**. Preserve normal speed, the full camera frame, and recorded court audio. Add captions, music, transitions, or coaching evaluation only when requested. These defaults carry forward to revisions unless the user changes them.

## 1. Resolve the brief

Identify the source, player, coach, and requested routines from the conversation and footage. Use descriptive working names when a formal drill name is uncertain. A typical session includes footwork, clears, Chinese 422 (player covers four corners, coach two), half-court control, rear-court-to-net practice, and net control into smash; establish this recording's actual activities and order.

Choose **training record** by default, or **highlights** when the user asks for one representative clip per routine. Reuse an earlier edit's cut list and review notes when available. Resolve missing information from those assets before asking the user. Proceed once the source and mode are known and there is a working routine checklist.

## 2. Map the whole source

Inspect media properties using the locally available tools. Review an overview at roughly 15-second intervals, then samples about every two seconds across the entire recording, including apparent long breaks. This second pass must account for brief resumed practice inside downtime. Use a court crop and timestamped contact sheets for inspection when helpful; keep those annotations outside the export.

An existing reviewed map can satisfy this pass after verifying that it covers the same source and requested routines. Review missing or uncertain regions instead of repeating completed inspection.

Record candidate source intervals, routine, visible activity, and uncertainties. Check the beginning and end separately for a short walk onto court and return toward the camera. Use suitable original shots as bookends; otherwise start and end with practice. End before camera handling.

Finish this pass with a timeline map covering the entire source and the location or confirmed absence of each requested routine.

## 3. Select practice

Read the reference for the chosen mode before selecting:

- **Training record:** [training-record.md](references/training-record.md) defines substantial practice, aborted starts, and downtime removal.
- **Highlights:** [highlights.md](references/highlights.md) defines candidate comparison and one continuous clip per routine.

A feeding group is repeated practice supported by a batch of shuttles, ending in a stop or reload. A rally uses one shuttle; a repetition executes a movement pattern. Neither is interchangeable with a retained clip, which is simply a continuous source interval. An expected 14 or 28 shuttles is context, not a cutting rule. Report a group or feed count only if separately verified.

Finish selection with every requested routine accounted for under the chosen mode and every ambiguous selection flagged for closer review.

## 4. Refine each boundary

Inspect every proposed start and end with samples roughly half a second apart, initially spanning two seconds on either side. Expand the window or inspect denser frames/playback until the first and final actions are clear; a sampled timestamp is only a search aid.

Start with the player's preparation before the first committed movement or feed. Keep the last stroke, follow-through, and visible outcome, including a miss. End before a separate reload, conversation, or rest. Preserve ordinary recovery and preparation within practice. Merge overlapping intervals and undo deletions that remove only recovery.

Finish with ordered, non-overlapping intervals whose starts and outcomes have been inspected, and the mode's coverage check complete. Describe review honestly: sampled inspection is not uninterrupted playback or an exact shuttle count.

## 5. Export and verify

Read [media.md](references/media.md) before freezing the cut list or rendering. Save source identity, exact selections, export settings, and verification results so revisions can reuse the work. Export to a distinct file; a highlights request keeps the existing training record intact.

Deliver the playable video and its measured duration after both editorial and technical checks pass. Keep selection notes out of the picture. If a routine is absent or a check remains unresolved, state that specific limitation rather than claiming complete coverage or verification.

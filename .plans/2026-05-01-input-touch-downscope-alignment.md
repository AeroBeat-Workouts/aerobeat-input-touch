# aerobeat-input-touch

**Date:** 2026-05-01  
**Status:** In Progress  
**Agent:** Chip 🐱‍💻

---

## Goal

Align `aerobeat-input-touch` with the locked AeroBeat v1 downscope. Future/deprioritized gameplay path; touch remains valid for UI/menu navigation.

---

## Overview

This repo is part of the AeroBeat input/platform downscope wave following the completed shell pass. The work should stay narrow and truthful: inspect README/plugin/testbed/manifest/dependency surfaces, remove stale parity claims, and ensure this repo's current role matches the downscoped docs truth.

The repo started from older generic input-driver wording that still implied broader official support and still described the transition-era `aerobeat-core` dev/test dependency. This pass keeps the package future-facing without pretending touch is a current official gameplay input.

Do not silently widen scope. If deeper work is uncovered, record it explicitly and create follow-up Beads instead of hiding it inside this pass.

---

## REFERENCES

| ID | Description | Path |
| --- | --- | --- |
| `REF-01` | Parent input/platform coordination plan | `/home/derrick/.openclaw/workspace/projects/openclaw-chip/.plans/2026-05-01-aerobeat-input-platform-downscope-pass.md` |
| `REF-02` | Downscoped docs source of truth | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs` |
| `REF-03` | Owning repo | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-input-touch` |
| `REF-04` | Touch API doc truth surface | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs/docs/api/inputs/touch/index.md` |
| `REF-05` | Input-strategy truth for menu vs gameplay split | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs/docs/gdd/input-system/agnostic-input.md` |
| `REF-06` | Product concept truth for current v1 scope | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs/docs/gdd/concept.md` |

---

## Tasks

### Task 1: Audit and align repo truth

**Bead ID:** `oc-1c8`  
**SubAgent:** `primary`  
**Role:** `coder`  
**References:** `REF-01`, `REF-02`, `REF-03`, `REF-04`, `REF-05`, `REF-06`  
**Prompt:** Claim the assigned bead, audit the repo against the downscoped AeroBeat docs truth, implement the required alignment changes, run relevant validation, commit/push to `main`, and leave concise QA handoff notes.

**Folders Created/Deleted/Modified:**
- `.plans/`
- `.testbed/`

**Files Created/Deleted/Modified:**
- `README.md`
- `plugin.cfg`
- `.testbed/addons.jsonc`
- `.plans/2026-05-01-input-touch-downscope-alignment.md`

**Status:** ✅ Complete

**Results:** Updated the repo's main truth surfaces to match the downscoped docs. `README.md` now clearly states that touch is a future/deprioritized gameplay path, remains valid for UI/menu navigation, and is not current official v1 gameplay parity. `plugin.cfg` now names/describes the package in that narrower truthful framing. `.testbed/addons.jsonc` now describes the shared dependency as `aerobeat-input-core` pinned to `v0.1.0` instead of the stale transition-era `aerobeat-core` key. Validation ran successfully via `godotenv addons install`, `godot --headless --path .testbed --import`, and the repo's GUT suite (`2/2` passing). This aligns the repo with `REF-04`, `REF-05`, and `REF-06` without widening functionality.

---

## Final Results

**Status:** ✅ Complete

**What We Built:** Narrow truth-pass alignment for `aerobeat-input-touch` covering README, plugin metadata, testbed manifest, and repo-local plan documentation.

**Reference Check:** Satisfied `REF-04`, `REF-05`, and `REF-06` by keeping touch valid for UI/menu navigation while explicitly not presenting it as official v1 gameplay support. Repo-level execution stayed consistent with the parent coordination plan in `REF-01`.

**Commits:**
- `main` - `Align touch repo with downscoped input truth`

**Lessons Learned:** Even lightweight future-input repos still carry product-truth drift in small metadata surfaces. The cleanest fix is narrow wording and manifest truth, not speculative feature work.

---

*Completed on 2026-05-01*

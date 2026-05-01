# AeroBeat Touch Input

Touch input remains a **future gameplay support path** for AeroBeat.

For the current AeroBeat v1 slice:

- **Official gameplay input:** camera only
- **Official gameplay features:** Boxing and Flow
- **Valid current use for touch:** UI and menu navigation on touch-capable/mobile surfaces
- **Not current official parity:** touch-driven gameplay

This repo stays useful because it preserves the touch-provider seam for future work without implying that touch is an equal-status AeroBeat v1 gameplay target today.

## 📋 Repository Details

- **Type:** Input Driver
- **Current stance:** future/deprioritized gameplay support; truthful for UI/menu navigation
- **License:** **Mozilla Public License 2.0 (MPL 2.0)**
- **Dependencies:**
  - `aerobeat-input-core` (canonical shared input contract)
  - `aerobeat-vendor-*` (allowed)

## GodotEnv development flow

This repo uses the AeroBeat GodotEnv package convention.

- Canonical dev/test manifest: `.testbed/addons.jsonc`
- Installed dev/test addons: `.testbed/addons/`
- GodotEnv cache: `.testbed/.addons/`
- Hidden workbench project: `.testbed/project.godot`
- Repo-local unit tests: `.testbed/tests/`

The repo root remains the package/published boundary for downstream consumers. Day-to-day development, debugging, and validation happen from the hidden `.testbed/` workbench using the pinned OpenClaw toolchain: Godot `4.6.2 stable standard`.

### Restore dev/test dependencies

From the repo root:

```bash
cd .testbed
godotenv addons install
```

That restores this repo's committed dev/test manifest into `.testbed/addons/`, including the shared `aerobeat-input-core` contract and GUT.

### Open the workbench

From the repo root:

```bash
godot --editor --path .testbed
```

Use this `.testbed/` project as the canonical direct-development and bugfinding surface for touch-input work.

### Import smoke check

From the repo root:

```bash
godot --headless --path .testbed --import
```

### Run unit tests

From the repo root:

```bash
godot --headless --path .testbed --script addons/gut/gut_cmdln.gd \
  -gdir=res://tests \
  -ginclude_subdirs \
  -gexit
```

### Validation notes

- `.testbed/addons.jsonc` is the committed dev/test dependency contract.
- The manifest should describe the shared input dependency as `aerobeat-input-core`, not the older transition-era `aerobeat-core` key.
- Repo-local unit tests live under `.testbed/tests/`.
- Keep touch wording truthful: valid for UI/menu navigation today, but not current official gameplay parity.

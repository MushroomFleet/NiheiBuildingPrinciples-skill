# Nihei Building Principles — Skill

A Claude Code skill and creative toolkit grounded in the architectural, spatial, and narrative design philosophy of **Tsutomu Nihei** (Blame!, Abara, Biomega, Knights of Sidonia, Aposimz, Tower Dungeon).

This repository contains a **building-principles advisory agent** for enhancing and assessing creative projects, an **image prompt enhancement system**, and a collection of **procedural generation JSON profiles** for ComfyUI users running DJZ-ZeroBytes nodes.

---

## What's Included

### 🏗️ Nihei Building Principles Skill

The core skill — a narrative and art direction advisory agent that evaluates creative projects against **12 scored dimensions** derived from Nihei's 25+ year body of work.

**Location:** `nihei-building-principles/SKILL.md`

**Activation:** `"using Nihei Building Principles"` or `"NiheiBuildingPrinciples"` with any creative document attached.

**Accepts:** Game design documents, level designs, film production design, novel world-building, visual art direction guides, scripts, codebases, architectural concepts, VR experience designs, tabletop RPG settings — any creative project with spatial, environmental, or narrative components.

**Outputs:** `[projectname]_README_TN.md` — a scored assessment with detailed analysis and an enhanced plan with specific alignment recommendations.

**The 12 Dimensions (4 Tiers):**

| Tier | Dimension | Key Question |
|------|-----------|--------------|
| 1 Essential | Architecture-as-Narrative | Does the environment carry the story? |
| 1 Essential | Incomprehensible Scale | Does scale exceed human processing? |
| 1 Essential | Anti-Anthropocentric Design | Are spaces hostile to habitation? |
| 2 Core | Cognitive Estrangement | Does the work produce genuine disorientation? |
| 2 Core | Visual Geometry Discipline | Hard for environment, soft for biology? |
| 2 Core | Environmental Hostility | Is the environment actively detrimental? |
| 3 Reinforcing | Narrative Sparsity | Story through traversal, not exposition? |
| 3 Reinforcing | Subnature Presence | Is decay a primary feature? |
| 3 Reinforcing | Material Credibility | Do impossible structures feel plausible? |
| 4 Atmospheric | Darkness-Default Lighting | Is light incidental, not designed? |
| 4 Atmospheric | Posthuman Thematic Resonance | Do themes emerge from design? |
| 4 Atmospheric | Emotional Register | Dread and solitude over comfort? |

**Skill Structure:**

```
nihei-building-principles/
├── SKILL.md                              # Entry point — triggers, workflow, dimensions
├── references/
│   ├── design-philosophy.md              # Core Nihei methodology
│   ├── assessment-protocol.md            # Scoring rubrics for all 12 dimensions
│   └── output-template.md               # README_TN.md format specification
└── assets/
    └── README_TN_template.md             # Blank output template
```

---

### 📄 Grounding Document

**File:** `TsutomuNihei-Grounding.md`

The comprehensive design reference distilled from detailed analysis of Nihei's life, influences, and works. This is the **corpus** from which all other artifacts in this repository were derived. It covers:

- Core identity — manga artist, former construction supervisor and architectural draftsman
- Foundational influences — HR Giger, Blade Runner, Ghost in the Shell, Akira, Gundam, Piranesi's Carceri d'Invenzione, construction industry experience
- Architectural philosophy — anti-anthropocentric design, neuroarchitecture inversion, ascendance of subnatures, museum of architectural styles
- The Four Disorientations — Immateriality, Incomprehensible Scale, Narrative Absence, Sterility & Hostility
- Visual language — geometry rules, darkness-default lighting, low viewpoints, diminutive figures
- 15 Design Axioms for agentic use
- Quick-reference palette — materials, tonal range, emotional register

---

### 🎨 Image Prompt Enhancement System

**File:** `t2i-Nihei-ENH.md`

A complete text-to-image [prompt enhancement system](https://github.com/MushroomFleet/DJZ-ENH-system) that transforms basic prompts into visually-rich 80-100 word descriptions grounded in Nihei's design language. Built for use as a system prompt or reference document for any image generation workflow.

**Features:**
- 5 style categories (Nihei Manga, Architectural Concept Art, Biopunk Horror, Industrial SF Photography, Frozen Wasteland)
- Architectural style mixing rules (Brutalist, Gothic, Industrial, Greco-Roman, Japanese, Bauhaus, Alien)
- The Four Disorientations applied to prompt enhancement
- 6 worked enhancement examples
- 10-step enhancement process
- Hard constraints ensuring Nihei aesthetic fidelity

---

### ⚡ ZeroBytes JSON Profiles (ComfyUI)

Five procedural generation profiles for use with **DJZ-ZeroBytes** nodes in ComfyUI. Each profile uses vocabulary pools extracted from the grounding document and ENH system to produce deterministic, seed-reproducible prompts.

#### ZeroPrompt — Generation Profile

**File:** `zeroprompt-Nihei.json`

Full text-to-image [prompt generation](https://github.com/MushroomFleet/ComfyUI-DJZ-ZeroPrompt). Produces complete Nihei-grounded image prompts from scratch.

- 8 templates, 13 pools (8 standard + 5 custom)
- Custom pools: `architecture_idiom` (20), `subnature` (20), `material` (20), `geometry` (15), `disorientation` (12)
- **~117 quadrillion combinations**

#### ZeroENH — Enhancement Profile

**File:** `zeroENH-Nihei.json`

Deterministic [prompt enhancement](https://github.com/MushroomFleet/DJZ-ENH-system) that fills gaps in user prompts with Nihei-aligned vocabulary. Detects what's missing and adds style, lighting, details, environment, camera, and mood without overriding the user's subject.

- 8 templates, 8 pools (strict schema)
- Classification block with keyword/pattern gap detection
- Anti-pairs preventing incoherent combinations (18 triggers)
- **~513 billion combinations**

#### ZeroEDIT — General Edit Profile

**File:** `zeroedit-Nihei.json`

[Edit/instruct prompts](https://github.com/MushroomFleet/ComfyUI-ZeroEDIT-nodes) that transform existing images of unknown content into Nihei's aesthetic. Preserves the original subject while applying megastructure environments, monochromatic rendering, and architectural dread.

- 7 templates, 9 pools
- 34 edit operations: transform (12), change (6), add (8), replace (4), remove (4)
- Preservation clauses on all 7 templates
- **~14.4 billion combinations**

#### ZeroEDIT Architectural — Empty Scenes Only

**File:** `EDIT-Nihei-architectural.json`

Restricted to **empty architectural scenes and landscapes** — no creatures, people, or inhabitants. Transforms any source image into uninhabited Nihei megastructure environments, frozen wastelands, and desolate infrastructure.

- 7 templates, 9 pools
- 35 edit operations: transform (16), change (5), add (6), replace (3), remove (5)
- Preservation clauses protect compositional structure
- **~12.4 billion combinations**

#### ZeroEDIT Creatures — Character/Creature Focus

**File:** `EDIT-Nihei-creatures.json`

Restricted to **creature and character design** — close-ups, portraits, and key art. Transforms subjects into biomechanical entities, safeguards, gauna, silicon life-forms, posthuman figures, and mutated drones. No empty scenes.

- 7 templates, 9 pools
- 28 edit operations: transform (12), change (4), add (8), replace (4)
- Preservation clauses protect pose, gesture, and portrait framing
- **~11.9 billion combinations**

---

## Profile Combination Summary

| Profile | Type | Templates | Pools | Combinations |
|---------|------|-----------|-------|--------------|
| `zeroprompt-Nihei.json` | Generation | 8 | 13 | ~1.17 × 10¹⁷ |
| `zeroENH-Nihei.json` | Enhancement | 8 | 8 | ~5.13 × 10¹¹ |
| `zeroedit-Nihei.json` | Edit (General) | 7 | 9 | ~1.44 × 10¹⁰ |
| `EDIT-Nihei-architectural.json` | Edit (Architecture) | 7 | 9 | ~1.24 × 10¹⁰ |
| `EDIT-Nihei-creatures.json` | Edit (Creatures) | 7 | 9 | ~1.19 × 10¹⁰ |

---

## Usage

### As a Claude Code Skill

Place the `nihei-building-principles/` folder in your skills directory and trigger with:

> "Using Nihei Building Principles, assess this game design document."

Claude will read the reference files, score all 12 dimensions, and produce a `[projectname]_README_TN.md` with assessment, recommendations, and an enhanced plan.

### As a ComfyUI Profile

Load any `.json` profile into the corresponding DJZ-ZeroBytes node:
- `zeroprompt-Nihei.json` → **[DJZ-ZeroPrompt](https://github.com/MushroomFleet/ComfyUI-DJZ-ZeroPrompt)** node
- `zeroENH-Nihei.json` → **[DJZ-ZeroENH](https://github.com/MushroomFleet/ComfyUI-ZeroENH)** node
- `zeroedit-Nihei.json` / `EDIT-Nihei-architectural.json` / `EDIT-Nihei-creatures.json` → **[DJZ-ZeroEDIT](https://github.com/MushroomFleet/ComfyUI-ZeroEDIT-nodes)** node

### As a Prompt Engineering Reference

Use `t2i-Nihei-ENH.md` as a [system prompt](https://github.com/MushroomFleet/DJZ-ENH-system) or reference document for any LLM-assisted image generation workflow. The 10-step process and hard constraints ensure consistent Nihei aesthetic output.

---

## 📚 Citation

### Academic Citation

If you use this codebase in your research or project, please cite:

```bibtex
@software{nihei_building_principles,
  title = {Nihei Building Principles: Narrative and Art Direction Skill Based on Tsutomu Nihei's Design Philosophy},
  author = {Drift Johnson},
  year = {2025},
  url = {https://github.com/MushroomFleet/NiheiBuildingPrinciples-skill},
  version = {1.0.0}
}
```

### Donate:

[![Ko-Fi](https://cdn.ko-fi.com/cdn/kofi3.png?v=3)](https://ko-fi.com/driftjohnson)

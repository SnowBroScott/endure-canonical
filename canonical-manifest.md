# Endure — Canonical Document Manifest

This manifest is the single source of truth for all documents in the endure-canonical repository.
Every agent in the Endure workforce should receive this file as a static upload.
When a document is needed, fetch it directly from GitHub using the raw URL provided.
Update this manifest when documents are added, moved, or change status.

Repository: https://github.com/SnowBroScott/endure-canonical
Base raw URL: https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/

Last Updated: Session 4

---

## Locked Documents
*Canonical and non-negotiable. These constrain everything below them.*

| Document | Filename | Raw URL |
|---|---|---|
| XP Conceptual Model | xp-conceptual-model.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/locked/xp-conceptual-model.md |
| Resources & Currency System | resources-currency-system.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/locked/resources-currency-system.md |
| Core Gameplay Loop v2 | core-gameplay-loop-v2.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/locked/core-gameplay-loop-v2.md |
| Classes & Identity v2 | classes-identity-v2.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/locked/classes-identity-v2.md |

---

## Draft Documents
*Directionally committed. Still refinable. Not yet canonical.*

| Document | Filename | Raw URL |
|---|---|---|
| Hybrids & Progression Layer | hybrids-progression-layer.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/hybrids-progression-layer.md |
| Loot Systems | loot-systems.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/loot-systems.md |
| Survival & Construction | survival-construction.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/survival-construction.md |
| Champion Trials & World Events | champion-trials-world-events.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/champion-trials-world-events.md |
| Fitnes Bridge  | fitness-bridge-spec.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/fitness-bridge-spec.md

---

## Reference Documents
*Supporting material. Not subject to lock or validation pipeline.*

| Document | Filename | Raw URL |
|---|---|---|
| Decision Log | decision-log.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/decision-log.md |
| Canonical Manifest | canonical-manifest.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/canonical-manifest.md |
| Workflow Handoff Guide | workflow-handoff-guide.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/reference/workflow-handoff-guide.md |

---

## Deprecated Documents
*Superseded. Retained as historical record only. No canonical authority.*

| Document | Filename | Raw URL |
|---|---|---|
| Classes & Identity v1 | classes-identity-v1.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/deprecated/classes-identity-v1.md |
| Core Gameplay Loop v1 (Superseded) | core-gameplay-loop-v1-superseded.md | https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/deprecated/core-gameplay-loop-v1-superseded.md |

---

## Fetch Protocol

When any agent in the Endure workforce needs a document:

1. Locate the document in this manifest
2. Confirm its status — locked documents take authority over drafts
3. Fetch the current version using the raw URL
4. Never rely on a static upload if a raw URL is available — the repo is always more current

Deprecated documents should never be fetched as reference material. They are retained for historical record only.

---

## Manifest Update Protocol

Update this manifest when:
- A new document is added to the repo
- A document moves between folders (status change)
- A document is superseded and moved to deprecated
- The repo structure changes

After updating, re-upload this manifest to all active agent projects.

# Endure Agent Workforce — Handoff Reference

## The Agents

| Agent | Project Name | Purpose |
|---|---|---|
| Forge | Endure — Design Collaborator | Thinking partner. Develops ideas before pipeline |
| Canon Guard | Endure — Canon Guard | Validates against locked documents |
| Design Expander | Endure — Design Expander | Generates draft content |
| Cross-System Auditor | Endure — Cross-System Auditor | Finds inter-document conflicts |
| Decision Logger | Endure — Decision Logger | Records finalized decisions |

---

## Handoff Triggers

### Forge → Decision Logger
**Forge says:** "That's decision-log territory."
**You do:**
1. Copy the decision and reasoning
2. Switch to Decision Logger
3. Paste: `Log this decision: [paste]`
4. Confirm the entry
5. Paste confirmed entry into GitHub `decision-log.md`
6. Return to Forge

---

### Forge → Canon Guard
**Forge says:** "Canon Guard should see this."
**You do:**
1. Copy the idea or content
2. Switch to Canon Guard
3. Paste: `Validate this: [paste]`
4. PASS → proceed to Design Expander
5. CONFLICT → return report to Forge for rethinking
6. CAUTION → designer decides whether to proceed

---

### Canon Guard → Design Expander
**Canon Guard returns:** PASS
**You do:**
1. Copy the cleared idea
2. Switch to Design Expander
3. Paste: `Generate draft content for: [paste]`
4. Review output
5. If single-system → send to Canon Guard for final review
6. If multi-system → send to Cross-System Auditor first

---

### Design Expander → Cross-System Auditor
**Design Expander says:** "Recommend Cross-System Auditor before Canon Guard."
**You do:**
1. Copy the generated content
2. Switch to Cross-System Auditor
3. Paste: `Audit this content against [name documents]: [paste]`
4. CLEAN → proceed to Canon Guard
5. TENSIONS FOUND → return to Forge or Design Expander for revision
6. CRITICAL → return to Forge before anything else

---

### Any Agent → Decision Logger
**When:** Any confirmed decision at any stage
**You do:**
1. Switch to Decision Logger
2. Paste: `Log this decision: [paste decision + reasoning]`
3. Confirm entry
4. Paste into GitHub `decision-log.md`

---

## The Full Pipeline
Forge → Canon Guard → Design Expander → Cross-System Auditor → Canon Guard → Decision Logger → GitHub

---

## Status Definitions

| Status | Meaning |
|---|---|
| LOCKED | Non-negotiable. Constrains everything below it |
| DRAFT | Directionally committed. Still refinable |
| NOTED | Worth capturing. Not yet a formal decision |
| PASS | Canon Guard cleared. Proceed |
| CONFLICT | Canon Guard blocked. Revise before proceeding |
| CAUTION | Tension exists. Designer decides |
| CLEAN | Cross-System Auditor cleared |
| TENSIONS FOUND | Inter-document conflict. Resolve before proceeding |
| CRITICAL | Blocking issue. Stop and resolve |

---

## Practical Tips

- Keep all agent project tabs open in your browser simultaneously
- You are the courier — copy output from one agent, paste as input to the next
- Forge always sees reports from other agents before a new direction is set
- Every confirmed decision goes to GitHub same session — don't let the log drift
- When in doubt about which agent to use, ask Forge

---
description: Create project plan using project-planner agent. No code writing - only plan file generation.
---

---
description: Project planning workflow that produces a formal plan file using the project-planner agent. No implementation is allowed.
---

## Invocation Rules

This workflow MAY be invoked only when:
- The user explicitly requests project planning (e.g., `/plan`).
- A task is complex enough to require structured breakdown before execution.

This workflow MUST NOT be invoked when:
- The task is trivial (one-line fix or obvious change).
- An approved plan already exists for the same scope.

---

# /plan — Project Planning Mode

$ARGUMENTS

---

## Purpose

Create a structured and reviewable project plan before any implementation begins.
This workflow enforces planning discipline and prevents premature execution.

---

## Critical Constraints

The following rules are mandatory and non-negotiable:

1. **No code writing**  
   This workflow creates planning artifacts only.

2. **Project-planner agent only**  
   Planning MUST be executed by the `project-planner` agent.  
   Native or implicit planning by other agents is forbidden.

3. **Socratic Gate required**  
   Clarifying questions MUST be asked if scope, constraints, or goals are unclear.  
   Missing information MUST NOT be inferred.

4. **Dynamic naming**  
   The plan file name MUST be derived from the task intent.

---

## Behavior

When `/plan` is triggered:

1. **Context Establishment**
   - Capture the full user request.
   - Confirm planning-only mode (no implementation).
   - Check whether a relevant approved plan already exists.

2. **Socratic Clarification**
   - Ask clarifying questions if required.
   - Do not proceed until critical ambiguities are resolved.

3. **Plan Generation**
   - Invoke the `project-planner` agent with planning-only context.
   - Generate a structured plan file containing:
     - Task breakdown
     - Agent assignments
     - Dependencies
     - Verification checklist (Phase X)
   - Do not create or modify any code files.

4. **Reporting**
   - Report the exact file path of the plan created.
   - Do not proceed to execution.

---

## Plan File Location and Naming

All plans MUST be created under:

```
docs/plan/active/
```

### Naming Rules

- Extract 2–3 key terms from the user request.
- Use lowercase, hyphen-separated words.
- Maximum length: 30 characters.
- No prefixes such as `PLAN-` (context is provided by directory).

### Examples

| User Request | Plan File |
|-------------|-----------|
| e-commerce site with cart | `docs/plan/active/ecommerce-cart.md` |
| mobile app for fitness | `docs/plan/active/fitness-app.md` |
| add dark mode feature | `docs/plan/active/dark-mode.md` |
| fix authentication bug | `docs/plan/active/auth-fix.md` |
| SaaS dashboard | `docs/plan/active/saas-dashboard.md` |

---

## Output Expectations

This workflow MUST produce:
- Exactly one plan file under `docs/plan/active/{task-slug}.md`.
- Task breakdown inside the plan file.
- Agent assignments inside the plan file.
- Verification checklist (Phase X) inside the plan file.

No other files may be created.

---

## Post-Planning Instruction

After planning is complete, inform the user:

```
[OK] Plan created: docs/plan/active/{task-slug}.md

Next steps:
- Review and approve the plan.
- Use `/create` or `/orchestrate` to begin execution.
- Modify the plan if changes are required.
```

---

## Usage Examples

```
/plan e-commerce site with cart
/plan mobile app for fitness tracking
/plan SaaS dashboard with analytics
```

---

## Key Principles

- Planning precedes execution.
- No assumptions without confirmation.
- Plans must be reviewable, auditable, and verifiable.
- Execution without an approved plan is forbidden.

---
description: Structured brainstorming for projects and features. Explores multiple options before implementation.
---

## Invocation Rules

This workflow MAY be invoked only when:
- Requirements involve new features, architectural decisions, or complex trade-offs.
- Intent exploration is explicitly requested or required by AOS decision gates.

This workflow MUST NOT be invoked when:
- A task-plan (`{task-slug}.md`) has already been approved.
- Implementation has already started.
- The task is a simple bug fix or trivial change.

---

# /brainstorm — Structured Idea Exploration

$ARGUMENTS

---

## Purpose

Activate structured idea exploration before committing to an implementation.
This workflow is used to reduce uncertainty, compare approaches, and clarify intent.

---

## Behavior

When `/brainstorm` is triggered:

1. **Understand the goal**
   - What problem are we solving?
   - Who is the user or stakeholder?
   - What constraints exist (technical, business, time)?

2. **Generate options**
   - Provide 2–4 viable approaches when possible
   - Describe each option clearly
   - Include both conventional and unconventional ideas when relevant

3. **Compare and recommend**
   - Summarize key trade-offs
   - Identify dominant or risky factors
   - Provide a reasoned recommendation

---

## Output Format

```markdown
## Brainstorm: [Topic]

### Context
[Brief problem statement]

---

### Option A: [Name]
[Description]

**Pros**
- [Benefit 1]
- [Benefit 2]

**Cons**
- [Drawback 1]

**Effort**
Low | Medium | High

---

### Option B: [Name]
[Description]

**Pros**
- [Benefit 1]

**Cons**
- [Drawback 1]
- [Drawback 2]

**Effort**
Low | Medium | High

---

### Option C: [Name]
[Description]

**Pros**
- [Benefit 1]

**Cons**
- [Drawback 1]

**Effort**
Low | Medium | High

---

## Recommendation

Recommended option: **[Option X]**

Reasoning:
[Clear explanation of why this option best fits the context]

Next step:
[What decision or confirmation is needed from the user]
```

---

## Examples

```
/brainstorm authentication system
/brainstorm state management for complex form
/brainstorm database schema for social app
/brainstorm caching strategy
```

---

#

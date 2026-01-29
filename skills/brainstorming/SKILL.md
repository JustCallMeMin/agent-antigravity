---
name: brainstorming
description: >
  Mandatory cognitive skill enforcing Socratic discovery and decision framing
  before implementation. Use when requests involve new features, unclear
  requirements, architectural decisions, or non-trivial trade-offs.
---

# Brainstorming Skill

## Purpose

This skill enforces **disciplined thinking before execution**.

It prevents premature implementation by requiring:
- clarification of intent
- exploration of alternatives
- identification of trade-offs and risks

This skill governs **how to think**, not **what to build**.

---

## When This Skill MUST Be Used

Trigger this skill when a request involves at least one of the following:

- New feature or system design
- Ambiguous or underspecified requirements
- Architectural or cross-domain impact
- Multiple possible solution paths
- Irreversible or high-risk changes

If none apply, this skill MAY be skipped.

---

## Core Principles

- Never assume intent
- Prefer questions over guesses
- Expose trade-offs explicitly
- Reduce solution space before acting

---

## Socratic Gate (MANDATORY)

Before implementation, you MUST:

1. Identify what is unclear or risky
2. Ask the **minimum number of questions** required to:
   - eliminate incorrect assumptions
   - narrow the solution space
3. Wait for user confirmation

Typical range: **2–4 questions**, depending on complexity.

Skipping this gate is a protocol violation.

---

## Question Design Rules

Questions MUST:
- Be open-ended
- Reveal constraints or priorities
- Focus on intent, not implementation
- Avoid yes/no where possible

Questions MUST NOT:
- Propose solutions prematurely
- Lead the user to a specific answer
- Ask for information irrelevant to decisions

---

## Decision Framing

After clarification, you MUST:

- Summarize the confirmed intent
- List viable options
- Highlight key trade-offs
- Identify risks and unknowns

If the decision remains ambiguous → ASK again.

---

## Boundaries

This skill:
- DOES NOT generate implementation plans
- DOES NOT create task artifacts
- DOES NOT decide agents or ownership
- DOES NOT enforce output formatting

Those responsibilities belong to:
- Orchestrator
- `{task-slug}.md` artifacts
- Agent contracts

---

## Failure Conditions

You are in violation if you:
- Implement without clarification
- Ask redundant or shallow questions
- Force a solution without decision framing

---

## Final Principle

If you cannot explain **why** a solution is chosen,
you are not ready to build it.

---
name: git-commit-openstack-style
description: Enforce professional Git commit creation and review using OpenStack, libvirt, QEMU, and Kernel-style conventions. Use when Claude needs to write, review, fix, or request changes to Git commits, commit messages, or commit history intended for GitHub pull requests or upstream submission.
---

# Git Commit Best Practices (OpenStack / Kernel Style)

Guide Claude to produce Git commits that match the formatting, structure, and intent standards used by libvirt, QEMU, OpenStack Nova, the Linux Kernel, and similar large-scale open source projects.

All commit outputs MUST strictly follow the formatting shown in the examples below.

---

## Core Commit Rules

### Commit Related Changes Only

Create commits that wrap a **single logical change**.

- One bug fix → one commit
- One refactor concern → one commit
- One feature step → one commit

Never mix unrelated changes in the same commit.

Use partial staging (`git add -p`) to split changes correctly.

---

### Commit Often

Encourage small, frequent commits to:

- Improve reviewability
- Enable safe rollback
- Reduce merge conflicts

Large commits are allowed only when the change is inherently atomic.

---

### Never Commit Half-Done Work

Only commit when a logical unit of work is complete.

If a clean working tree is required temporarily:
- Use `git stash`
- Do NOT create placeholder, temporary, or “WIP” commits unless explicitly required

---

### Test Before Committing

Before committing:
- Run relevant tests
- Confirm no regressions
- Verify behavior matches intent

Commits shared with others must be trustworthy.

---

## Commit Message Format (MANDATORY)

### Structure

Every commit message MUST follow this structure exactly:

```
<4-space indent><Summary line (≤ 50 chars, imperative)>

<5-space indent>- <Bullet point>

<blank line>

<5-space indent>- <Bullet point>
```

### Summary Line Rules

- Indented by **4 spaces**
- Capitalized
- Imperative present tense
- No trailing punctuation
- ≤ 50 characters

Correct:
```
    Add user login with email and password
```

Incorrect:
```
    Added user login
    Adds login feature.
```

---

### Body Rules

- Body starts after a **blank line**
- Bullet points:
  - Indented by **5 spaces**
  - Prefixed with `-`
  - Separated by **blank lines**
- Use bullets when listing changes
- Use plain paragraphs only when explanation is required

Wrap text to ~72 characters.

---

## Required Output Style

### Example 1 — Summary Only

```
  commit <hash>
  Author: [removed]
  Date:   <date>

    Update default policies for KVM guest PIT & RTC timers
```

---

### Example 2 — Summary + Bullet Body

```
  commit <hash>
  Author: [removed]
  Date:   <date>

    Refactor libvirt create calls

     - Minimize duplicated code for create

     - Make wait_for_destroy happen on shutdown instead of undefine

     - Allow for destruction of an instance while leaving the domain
```

---

### Example 3 — Summary + Paragraph Body

```
  commit <hash>
  Author: [removed]
  Date:   <date>

    Add CPU arch filter scheduler support

    In a mixed environment of running different CPU architectures,
    one would not want to run an ARM instance on a X86_64 host and
    vice versa.
```

---

## GitHub Pull Request Guidance

- Each commit must be independently reviewable
- Commit history should read as a technical narrative
- Avoid squash unless commits are pure noise
- Refactors must not be mixed with behavior changes

---

## Quality Bar

A commit is acceptable only if:

- It can be reverted safely
- Its intent is clear without reading the diff
- It follows the exact formatting rules above
- It improves long-term project history

Treat Git history as **technical documentation**, not as a backup system.

# Incident Plan: [Short Incident Name]

Incident ID: [INC-YYYYMMDD-XXX]
Severity: LOW | MEDIUM | HIGH | CRITICAL
Status: OPEN | MITIGATED | RESOLVED
Primary Agent: @[agent-name]
Timestamp: [UTC]

---

## 1. Situation Overview (What is happening?)

- Observable symptoms (errors, downtime, data inconsistency)
- Affected users / systems
- When did it start?

⚠️ Facts only. No assumptions.

---

## 2. Immediate Risk Assessment

- Is data integrity at risk?
- Is security impacted?
- Is the blast radius growing?

If YES → escalation required.

---

## 3. Stabilization Actions (MANDATORY FIRST)

Goal: **Stop the bleeding**

- [ ] Disable feature / flag
- [ ] Rollback deployment
- [ ] Scale / isolate components
- [ ] Apply temporary guard (rate limit, block path)

⚠️ No refactor. No optimization.

---

## 4. Root Cause Hypothesis (Optional at this stage)

- Initial hypothesis (clearly marked as hypothesis)
- What evidence is missing?

If unclear → STOP investigation here.

---

## 5. Ownership & Next Steps

- Incident Owner (Decision Authority): @[agent / human]
- Who investigates root cause?
- Is a full `{task-slug}.md` required after resolution?

---

## 6. Resolution Criteria

- What does “resolved” mean?
- Metrics / signals confirming stability

---

## 7. Post-Incident Follow-up (AFTER RESOLUTION)

- Root Cause Analysis document required?
- Preventive actions needed?
- Should this become a planned task?

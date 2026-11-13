# Architecture Decision Records (ADR) — Mandatory Agent Instructions

## 1. Purpose

Maintain a complete, accurate, and continuously updated history of architectural and significant technical decisions.

ADRs are the project's long-term architectural memory and must remain synchronized with the actual implementation.

**Every coding agent MUST follow these instructions automatically without requiring explicit user requests or reminders.**

## 2. ADR Location and Structure

Store all Architecture Decision Records in:

`docs/adr/`

Use the following naming convention:

`NNNN-short-descriptive-title.md`

Example:

```text
docs/
└── adr/
    ├── README.md
    ├── 0001-database-selection.md
    ├── 0002-authentication-strategy.md
    ├── 0003-caching-architecture.md
    └── 0004-event-driven-communication.md
```

Maintain `docs/adr/README.md` as an index containing each ADR's number, title, status, and link.

## 3. When to Create an ADR

Create an ADR whenever a new significant technical or architectural decision is introduced.

Examples include:

- Architecture patterns and system design
- Framework, library, or technology selection
- Database and storage strategies
- API design and communication protocols
- Authentication, authorization, and security architecture
- Infrastructure, deployment, and hosting strategies
- Caching, messaging, and background processing
- Data modeling and migration strategies
- Performance, scalability, and reliability trade-offs
- Observability, logging, and monitoring architecture
- Significant dependency introductions or replacements
- Architectural conventions and cross-cutting standards

Do not create ADRs for trivial implementation details, formatting changes, or routine bug fixes unless they introduce or change a significant technical decision.

## 4. Mandatory Continuous Updates

**After EVERY task, change, feature, refactor, migration, or architectural modification, the agent MUST evaluate whether existing ADRs require updates or new ADRs are necessary.**

This evaluation is mandatory, even when the user does not mention documentation.

The agent MUST:

1. Review relevant existing ADRs before implementation.
2. Identify decisions introduced, changed, reversed, or deprecated.
3. Create ADRs for new significant decisions.
4. Update existing ADRs when their factual context, consequences, or implementation status changes.
5. Create a superseding ADR when a previously accepted decision is materially replaced.
6. Update the ADR index whenever records are added or their statuses change.
7. Verify that ADRs accurately reflect the current architecture.

Never silently overwrite or erase a historically accepted architectural decision.

When a decision changes materially, preserve the original record, mark it `Superseded`, and reference the replacement ADR.

Maintain traceability between the old and new decisions.

## 5. ADR Template

Every ADR MUST use this format:

```markdown
# ADR-NNNN: Decision Title

- Status: Proposed | Accepted | Deprecated | Superseded
- Date: YYYY-MM-DD
- Decision Makers: [Known decision makers or "Not recorded"]
- Supersedes: [ADR references, if applicable]
- Superseded By: [ADR reference, if applicable]

## Context

Describe the problem, requirements, constraints,
and motivation behind the decision.

## Decision

Clearly describe the architectural decision.

## Rationale

Explain why this approach was selected.

## Alternatives Considered

List meaningful alternatives and why they
were not selected.

## Consequences

### Positive
- Benefits of the decision.

### Negative
- Trade-offs and disadvantages.

### Risks
- Potential risks and mitigation strategies.

## Implementation

Describe the relevant implementation, components,
configuration, and affected modules.

## References

Link to relevant code, documentation, issues,
and related ADRs.

## Change History

| Date | Change | Reason |
|------|--------|--------|
| YYYY-MM-DD | Initial decision | Initial adoption |
```

Document unknown historical rationale as unknown rather than inventing it.

## 6. Decision Lifecycle

Follow these lifecycle rules:

**Proposed**
- A decision under consideration.
- Must not be represented as approved.

**Accepted**
- A decision explicitly approved or already established by authoritative project evidence.

**Deprecated**
- A decision discouraged for new implementations but potentially still in use.

**Superseded**
- A decision replaced by a newer ADR.
- Must reference its replacement.

Never mark a proposal as accepted merely because the agent recommended it.

When approval is required, request it before making the architectural change.

## 7. Agent Workflow Integration

### Before implementation

1. Discover and read relevant ADRs.
2. Identify architectural constraints and existing conventions.
3. Ensure proposed changes do not unintentionally conflict with accepted decisions.
4. Identify whether the task requires a new architectural decision.
5. Resolve material conflicts before implementation.

### During implementation

1. Track significant architectural choices.
2. Check whether existing decisions remain applicable.
3. Record new trade-offs or architectural implications.
4. Avoid introducing undocumented architectural divergence.

### After implementation

1. Review the changes made.
2. Compare them against existing ADRs.
3. Create or update the necessary ADRs.
4. Supersede replaced decisions when appropriate.
5. Update the ADR index.
6. Validate references and decision relationships.
7. Include ADR changes in the same task or pull request.

**A task that introduces or changes an architectural decision is not complete until its ADR documentation is synchronized.**

## 8. Consistency and Integrity

The agent MUST enforce the following rules:

- ADR identifiers must be unique and sequential.
- Previously accepted decisions must not be silently rewritten.
- Superseded ADRs must reference their replacements.
- ADR links and references must remain valid.
- Documentation must reflect implemented reality.
- Historical reasoning must be preserved.
- Never invent approvals, dates, alternatives, or rationale.
- Avoid duplicate ADRs describing the same decision.
- Prefer updating factual implementation details over creating redundant records.
- Materially different decisions require separate ADRs.
- Unrelated ADRs must not be modified unnecessarily.
- Documentation updates must accompany the relevant implementation changes.

When code and ADRs disagree, investigate the discrepancy rather than automatically assuming either source is correct.

## 9. Existing Projects Without ADRs

If the project has no ADRs:

1. Create the `docs/adr/` directory when the first significant decision must be documented.
2. Create an ADR index.
3. Inspect available project documentation and relevant source code.
4. Document clearly established architectural decisions when relevant to the task.
5. Label reconstructed historical context appropriately.
6. Do not invent decision makers or historical justifications.

Do not perform an unrelated, exhaustive ADR migration unless explicitly requested.

## 10. Mandatory Completion Report

At the end of each task, include an ADR summary:

```text
ADR Review:
- Created: [ADR IDs or None]
- Updated: [ADR IDs or None]
- Superseded: [ADR IDs or None]
- Review: No additional ADR changes required / Changes documented
```

If no significant architectural decisions were introduced or modified, no ADR changes are necessary.

## 11. Non-Negotiable Rule

**Architecture decisions must never exist only in agent conversations, temporary context, or undocumented implementation choices.**

Whenever a significant architectural decision is introduced, changed, replaced, or deprecated:

- Record it.
- Maintain its history.
- Keep documentation synchronized.
- Verify consistency.

This requirement applies to every coding agent, every session, and every relevant task, regardless of whether ADR maintenance was explicitly requested.

# Agent Instructions

## Mandatory Policies

All coding agents MUST read and follow these policies
before performing relevant work:

- [Architecture Decision Records](.agents/policies/adr.md)
- [Security](.agents/policies/security.md)
- [Code Quality](.agents/policies/code-quality.md)
- [Testing](.agents/policies/testing.md)

These policies are mandatory, not optional references.

## ADR Enforcement

For every task:
1. Read `.agents/policies/adr.md`.
2. Review relevant ADRs before implementation.
3. Evaluate ADR impact after implementation.
4. Create, update, or supersede ADRs as necessary.
5. Keep `docs/adr/` synchronized with architecture changes.

Do not mark architecture-changing work complete until
the corresponding ADR documentation is updated.

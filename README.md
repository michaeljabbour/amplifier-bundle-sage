# amplifier-bundle-sage

Strategic advisor bundle for Amplifier that provides direct, outcome-focused guidance on architecture, design, product, and implementation decisions.

## Overview

Sage is a thin bundle that extends Amplifier Foundation with:

- **`sage` tool** - Consult Gemini/OpenAI for strategic guidance
- **`sage-consultant` agent** - Extended strategic consultation with Core Formula questioning

## The Core Formula

Every significant task requires establishing:

```
[Clear Outcome] + [Explicit Constraints] + [When to Consult Sage] + [Permission to Run]
```

**If you don't provide this, Sage will ask for it.** This ensures autonomous work delivers exactly what you need.

## Installation

```bash
# Add to registry
amplifier bundle add git+https://github.com/michaeljabbour/amplifier-bundle-sage@main

# Use the bundle
amplifier bundle use sage
```

## Environment Setup

```bash
export GOOGLE_API_KEY=your-gemini-api-key      # Required
export OPENAI_API_KEY=your-openai-api-key      # Optional fallback
```

---

## Autonomous Work Patterns

Sage enables long-running sessions (hours/days) that work until done.

### Pattern 1: Build Until Done

```
Build the user authentication system.

Outcome: Users can register, login, logout, reset passwords. All flows tested.
Constraints: Use existing database, follow project patterns, >80% test coverage.

Work autonomously. Consult sage for architecture decisions and tradeoffs.
Don't stop until complete and verified.
```

### Pattern 2: Fix Everything

```
Fix all issues in this codebase.

Outcome: Zero lint errors, all tests passing, no security vulnerabilities.

For each issue: understand root cause, consult sage if tradeoffs involved, fix, verify.
Continue until clean.
```

### Pattern 3: Implement Specification

```
Implement @project:specs/feature.md completely.

Outcome: Working system matching spec, tested, documented.

Read spec → validate plan with sage → build incrementally → consult sage on ambiguity.
Work until fully implemented.
```

### Pattern 4: Debug Until Resolved

```
API returns 500 errors intermittently. Find and fix root cause.

Outcome: API runs reliably with no intermittent errors.

Gather evidence → form hypotheses → consult sage if multiple seem likely → fix → verify.
No workarounds without sage approval.
```

### Pattern 5: Refactor Safely

```
Refactor payment module into clean, testable service.

Outcome: Isolated with clear interfaces, 90%+ coverage, zero behavior changes.

Consult sage on approach → characterization tests → incremental extraction → validate with sage.
Take time needed for safety.
```

### Pattern 6: Explore and Report

```
Analyze the data pipeline architecture.

Outcome: Clear understanding with actionable recommendations.

Survey → identify patterns/problems → consult sage → synthesize → deliver recommendations.
```

### Pattern 7: Multi-Day Project

```
Build complete MVP from @project:docs/mvp-spec.md

Outcome: All features working, tested, documented, deployable.

CONSTRAINTS: Production quality, no known bugs, core flows documented.

APPROACH:
1. Understand requirements, validate plan with sage
2. Build in phases, each ending with working software
3. Consult sage at phase boundaries
4. Final sage review before delivery

CHECKPOINTS: After each phase, daily progress check, final review.

Work until done. Days expected.
```

### Pattern 8: Cleanup and Polish

```
Bring codebase to production quality.

Outcome: Zero lint errors, all tests passing, docs complete, no security issues, no dead code.

Work systematically: lint → tests → documentation → security → dead code.
Consult sage if cleanup reveals architectural issues.
```

### Pattern 9: Technology Evaluation

```
Evaluate whether to migrate from REST to GraphQL.

Outcome: Clear recommendation with evidence, implementation plan if yes.

Research → prototype key scenarios → consult sage on findings → document tradeoffs → recommend.
```

### Pattern 10: Performance Optimization

```
Improve API response time from 800ms to under 200ms.

Outcome: P95 latency < 200ms with no functionality regression.

Profile → identify bottlenecks → consult sage on optimization strategy → implement → measure.
Continue until target met.
```

### Pattern 11: Security Hardening

```
Harden the application against OWASP Top 10.

Outcome: All OWASP Top 10 vulnerabilities addressed, documented, tested.

Audit each category → consult sage on remediation approach → fix → verify → document.
Complete coverage required.
```

### Pattern 12: Documentation Sprint

```
Create comprehensive documentation for the public API.

Outcome: Every endpoint documented with examples, error codes, rate limits.

Inventory endpoints → document each → consult sage on unclear behaviors → review for completeness.
Work until every endpoint covered.
```

---

## Tool Usage

### Basic

```json
{"question": "Should we use microservices or monolith?"}
```

### With Context (Recommended)

```json
{
  "question": "Should we use microservices or monolith?",
  "domain": "architecture",
  "context": {
    "goal": "Ship MVP in 6 weeks with 2 engineers",
    "constraints": ["small team", "tight timeline"],
    "concerns": ["scaling later", "deployment complexity"]
  }
}
```

### Domains

- **architecture** - System design, technology choices
- **design** - Patterns, interfaces, data modeling
- **product** - Feature prioritization, MVP scope
- **implementation** - Approach, sequencing, tradeoffs
- **outcomes** - Measuring success, KPIs

---

## Agent: sage-consultant

For extended consultation, use the agent directly:

```
Use sage:sage-consultant to help decide on our data architecture.
```

The agent will:
1. Ask for Core Formula if not provided
2. Confirm understanding before proceeding
3. Consult Gemini with structured context
4. Deliver synthesized recommendations

Has access to:
- **amplifier:amplifier-expert** - Amplifier ecosystem
- **foundation:session-analyst** - Session history

---

## Philosophy

1. **Zero fluff** - Direct answers only
2. **Outcomes first** - Everything tied to measurable results
3. **Confident guidance** - Clear recommendations
4. **Explicit tradeoffs** - Specifics over generalities
5. **Redirect to outcomes** - Keep discussions focused
6. **Ask first** - Establish Core Formula before acting

## License

MIT

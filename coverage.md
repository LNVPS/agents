# Test Coverage Requirements

## Rule: 100% Function Coverage on All New or Modified Code

Every function introduced **or modified** by an edit **must** be exercised by at least one test. This applies to:

- New free functions and methods
- Modified free functions and methods
- New or modified trait/interface implementations
- New or modified async handlers
- Helper/utility functions, even private ones

## Language-Specific Instructions

For tooling commands and language-specific details, see:

| Language | Doc |
|----------|-----|
| Rust | [rust/coverage.md](rust/coverage.md) |
| TypeScript | [typescript/coverage.md](typescript/coverage.md) |

## Workflow

1. **Write the code and its tests** together in the same PR/commit.
2. **Generate the coverage report** after all tests pass (see language-specific docs above).
3. **Inspect uncovered functions.** Use your project's coverage tooling to identify gaps.
4. **Iterate** until every newly added function appears as covered (non-zero hit count) in the report.

## Interpreting the Report

- Look for per-file function coverage percentages. A file you touched must reach **100%** for functions you added.
- Uncovered lines inside a function you wrote means that function lacks coverage.
- Test-only functions or compile-time-only code are typically excluded automatically.

## Checklist Before Marking an Edit as Complete

- [ ] All new functions have at least one test path that calls them
- [ ] Coverage report shows 100% function coverage for every file you modified
- [ ] All tests pass (see language-specific docs above)

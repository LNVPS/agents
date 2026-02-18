# Bug Fixes

## Required: Add a Regression Test for Every Bug Fix

When resolving a bug, you **MUST** add a unit test that:

1. **Reproduces the original failure** — the test should fail on the unfixed code and pass after the fix.
2. **Is placed in the appropriate test module** — follow the project's test organization conventions.
3. **Has a descriptive name** that makes the bug clear, e.g. `test_cost_overflow_with_zero_value`, `test_amount_rounds_correctly`.

## Checklist Before Marking a Bug as Fixed

- [ ] Root cause identified
- [ ] Fix applied
- [ ] Unit test added that would have caught the bug
- [ ] All tests pass (see project-specific build-and-test docs)

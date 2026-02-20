# Test Coverage Requirements — TypeScript

See [../coverage.md](../coverage.md) for the base rules.

## TypeScript-Specific Instructions

### Generate the coverage report

Using Jest:

```bash
yarn test --coverage
```

Using Vitest:

```bash
yarn vitest --coverage
```

Using c8 with Node.js:

```bash
yarn c8 yarn test
```

### Interpreting the report

- Look for the `% Funcs` column in the terminal summary.
- A file you touched must reach **100%** for functions you added.
- The HTML report (usually in `coverage/lcov-report/index.html`) highlights uncovered lines in red.
- Istanbul/nyc ignore comments (`/* istanbul ignore next */`) can exclude code that genuinely cannot be tested.

### Checklist additions

- [ ] Coverage report shows 100% function coverage for every file you modified
- [ ] `yarn test` passes with no failures
- [ ] `yarn lint` produces no errors
- [ ] `yarn typecheck` (or `tsc --noEmit`) produces no errors

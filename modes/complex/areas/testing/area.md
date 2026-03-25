# Testing

This is where code meets its tests. Write tests, run tests, watch them fail, fix them, watch them pass. Repeat until perfect.

## Purpose

The Testing area is where the rubber meets the road. Your code exists here, and your tests verify that it works correctly. This area enforces the discipline of test-driven development.

## What Goes Here

### Code Under Test
- Implementation code
- Unit tests
- Integration tests
- End-to-end tests

### Test Files
- Test source files
- Fixtures and mocks
- Test utilities

### Test Results
- Passing tests (green)
- Failing tests (red)
- Test coverage reports

## The Testing Loop

```
Write Test → Run Test → Test Fails → Fix Code → Run Test → Test Passes → Move to Debugging if needed
```

### Step 1: Write Test
- Write a test that describes the expected behavior
- Run the test and watch it fail (this is good!)
- Write minimum code to make test pass

### Step 2: Run Test
- Execute your test suite
- Review output carefully
- Understand failure messages

### Step 3: When Tests Pass
- Run full test suite
- Check coverage
- Move to Debugging area if any test fails
- Move to Build when ALL tests pass

### Step 4: When Tests Fail
- **Don't panic!** This is normal
- Move to Debugging area
- Debug until tests pass
- Return to Testing for verification

## Testing Philosophy

### Test Types

| Type | What it tests | When to write |
|------|---------------|--------------|
| Unit | Individual functions/methods | First |
| Integration | How components work together | During |
| E2E | Full user flows | Last |

### What Makes a Good Test

1. **Clear name** - Test name describes what it verifies
2. **Single responsibility** - One assertion per test (mostly)
3. **Independent** - Tests don't depend on each other
4. **Repeatable** - Same result every time
5. **Fast** - Runs in milliseconds

### Test Coverage

- Aim for 80%+ coverage on critical paths
- 100% coverage is not always worth it
- Focus on edge cases and error paths

## Area Guidelines

### DO
- Write tests before or alongside code
- Run tests frequently (after every change)
- Test edge cases and error conditions
- Keep tests fast
- Use descriptive test names

### DON'T
- Skip testing "because it's simple"
- Leave failing tests unaddressed
- Write tests that only pass sometimes
- Test implementation details instead of behavior

## Workflow

1. **Create tests** - Write test files alongside code
2. **Run tests** - Execute test suite
3. **Review failures** - Understand what's broken
4. **Fix or Debug** - If tests fail, move to Debugging
5. **Verify** - When tests pass, final check
6. **Push to Build** - When ready

## Debugging Loop

If tests fail, you'll cycle between Testing and Debugging:

```
Testing → (fail) → Debugging → (fix) → Testing → (pass) → Build
                           ↑_______________|
```

This loop continues until ALL tests pass. No exceptions.

## Tips

- Red-Green-Refactor: Red (write failing test), Green (make pass), Refactor
- Test behavior, not implementation
- Mock external dependencies
- Keep test data minimal
- Use descriptive assertions

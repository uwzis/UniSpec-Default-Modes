# /roadmap:test

Write and run tests in the Testing area.

## When to Use

Use this workflow when:
- Implementing new features
- Fixing bugs
- Running test suite
- Verifying code works

## Steps

### 1. Check Testing Area

List topics being tested:
```
unispec topic list -a Testing
```

### 2. Run Tests

Execute your test suite:
```bash
# Your test command - customize for your project
pytest
# or
cargo test
# or
npm test
```

### 3. Analyze Results

#### Tests Pass
- Great job!
- Run full test suite to be sure
- Move to `/roadmap:build` when ready

#### Tests Fail
- Don't panic!
- Read the failure messages carefully
- Move to `/roadmap:debug` to fix

### 4. Write Tests (If Needed)

If adding new functionality:
1. Write the test first (TDD)
2. Watch it fail
3. Write code to make it pass
4. Run tests again

### 5. Update Tasks

Mark completed tasks in `tasks.md`:
```markdown
## Testing
- [x] Write unit tests
- [x] Write integration tests
```

## Test Best Practices

- **Name tests clearly**: `test_user_can_login`
- **One assertion per test** (mostly)
- **Test edge cases**: empty, null, max values
- **Test errors**: what happens on bad input?

## Debugging Loop

If tests fail, you'll cycle:

```
Testing → (fail) → Debugging → (fix) → Testing → (pass) → Build
                            ↑_______________|
```

This is NORMAL. Keep cycling until tests pass!

## Next Steps

- **Tests pass** → `/roadmap:build`
- **Tests fail** → `/roadmap:debug`

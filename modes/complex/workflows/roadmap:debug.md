# /roadmap:debug

Debug test failures in the Debugging area.

## When to Use

Use this workflow when:
- Tests are failing
- You need to find and fix bugs
- You're in the testing/debugging loop

## Steps

### 1. Acknowledge Failure

It's okay! Test failures are normal. Let's fix them.

### 2. Read the Error

**Read carefully.** The error message tells you exactly what's wrong.

```
FAILED test_user_login.py::test_invalid_password
AssertionError: Expected status 401, got 200
```

This tells you:
- Test name: `test_invalid_password`
- What happened: Expected 401, got 200
- What should happen: Invalid password should return 401

### 3. Locate the Failure

Find the failing test and the code it tests:
```
unispec topic list -a Debugging
```

### 4. Find Root Cause

Ask "why?" 5 times:

1. **Why did it fail?** → Invalid password returned 200
2. **Why did it return 200?** → No password validation
3. **Why no validation?** → Validation was in wrong function
4. **Why wrong function?** → Copied from login success
5. **Why copied wrong?** → Rush job, didn't check

### 5. Fix the Issue

Make ONE change:
- Fix the bug
- Add missing code
- Fix test (if test was wrong)

### 6. Run Tests Again

Go back to Testing area:
```
unispec topic push "Feature Name" Testing
```

Then run tests:
```bash
pytest
```

### 7. Check Results

#### Tests Pass
- Excellent!
- Move to Build when ready

#### Tests Fail
- Come back to Debugging
- Try again
- Ask for help if stuck

## Debugging Loop

```
Testing → FAIL → Debugging → FIX → Testing → PASS → Build
                        ↓_____________FAIL|
```

You might do this many times. That's normal!

## Tips

- **One change at a time**
- **Read the error** - it's trying to help
- **Check assumptions** - you're probably wrong about something
- **Take breaks** - fresh eyes find bugs faster
- **Rubber duck it** - explain problem out loud

## Common Issues

### "Works on my machine"
- Check environment variables
- Check dependency versions

### "It was working yesterday"
- What changed?
- Check git log

### "I don't understand the error"
- Google it
- Break it down smaller

## Remember

> Debugging is where you go when you're too smart to write tests that fail.

But seriously, bugs happen to everyone. Stay calm, be systematic, and you'll find the issue.

Paddy believes in you! 🦫

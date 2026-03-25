# Debugging

Tests failed? You're in the right place. This is where we figure out why things aren't working and fix them.

## Purpose

The Debugging area exists because sometimes code doesn't work. Tests fail. Bugs appear. Rather than ignoring this reality, Roadmap Mode embraces it directly. When tests fail, you come here to systematically find and fix the problem.

## What Goes Here

### Debugging Activities
- Investigating test failures
- Finding root causes
- Fixing bugs
- Adding missing functionality
- Fixing edge cases

### Debugging Tools
- Print statements
- Debuggers
- Logging
- Stack traces
- Test output

### Fixed Issues
- Notes about what was broken
- What you changed to fix it
- What you learned

## The Debugging Process

### Step 1: Read the Failure

**READ THE ERROR MESSAGE.** It's telling you exactly what's wrong.

```
Assertion failed: expected 42, got 0
```

This means: your code returned 0 when it should have returned 42.

### Step 2: Locate the Failure

- Which test failed?
- What line in the test?
- What function is being tested?

### Step 3: Find the Root Cause

Ask "why?" five times:

1. Why did the test fail? → Because the function returned 0
2. Why did it return 0? → Because the variable wasn't initialized
3. Why wasn't it initialized? → Because we forgot to set it
4. Why did we forget? → Because the initialization was in the wrong place
5. Why was it in the wrong place? → Because we copied the wrong template

### Step 4: Fix the Issue

Make the minimum change needed to pass the test.

### Step 5: Run Tests Again

- Go back to Testing area
- Run the tests
- If they pass → Move to Build
- If they fail → Come back here

## Debugging Loop

```
Testing → FAIL → Debugging → FIX → Testing → PASS → Build
                              ↓____________FAIL|
```

You might cycle through Testing and Debugging many times. That's normal and expected.

## Common Debugging Patterns

### The "It Should Work But Doesn't" Pattern

1. Add logging to see what's happening
2. Check your assumptions
3. Verify input values
4. Check for off-by-one errors
5. Check for null/undefined values

### The "Test Was Passing But Now Isn't" Pattern

1. What changed since it was passing?
2. Check recent commits
3. Check environment differences
4. Check test data differences

### The "Works On My Machine" Pattern

1. Check for hardcoded paths
2. Check environment variables
3. Check dependencies versions
4. Check working directory

## Area Guidelines

### DO
- Read error messages carefully
- Take breaks when stuck
- Explain the problem out loud (Rubber duck debugging)
- Simplify the problem
- Check the basics (typos, imports, etc.)
- Ask for help if needed

### DON'T
- Change multiple things at once
- Guess and hope
- Ignore test failures
- Leave debugging mid-session
- Get frustrated (it happens to everyone)

## Debugging Tools

### Print Debugging
```python
print(f"x = {x}, y = {y}")
```

### Debugger
```bash
python -m pdb script.py
# or
rust-gdb binary
```

### Logging
```rust
log::debug!("Processing item: {:?}", item);
```

### REPL/Interactive
```python
python -i script.py
```

## Workflow

1. **Analyze failure** - Read the test output
2. **Locate code** - Find the problematic function
3. **Understand** - Read the code, trace the issue
4. **Fix** - Make the change
5. **Verify** - Go back to Testing
6. **Repeat** - Until tests pass

## Tips

- **One change at a time** - Don't fix three things and not know which worked
- **Read the error** - It's trying to help you
- **Check your assumptions** - You're probably wrong about something
- **Take breaks** - Fresh eyes find bugs faster
- **Rubber duck it** - Explain the problem out loud
- **Search** - Someone else has had this problem

## Remember

> "Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it." - Brian Kernighan

The best debugging is preventing bugs through good tests. But when bugs appear, embrace the challenge!

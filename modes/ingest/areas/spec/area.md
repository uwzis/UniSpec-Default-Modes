# Spec

Finalize and complete specifications. Verify everything is linked and documented.

## Purpose

The Spec area is the final stop. Review specs for completeness, verify all links are in place, and ensure documentation is thorough.

## What Goes Here

### Finalized Specs
- Complete specifications
- Verified links
- Final documentation

### Completion Checklist
- All interfaces documented
- All edge cases noted
- All links verified

## The Process

### Step 1: Review Spec

Check completeness:

- [ ] Purpose clearly stated
- [ ] All arguments documented
- [ ] All return values documented
- [ ] All errors documented
- [ ] Edge cases identified
- [ ] Behavior steps documented
- [ ] Tests referenced
- [ ] Code links verified

### Step 2: Verify Links

Check that all links work:

```bash
# List links for topic
unispec index list --topic "login"

# Verify files exist
ls -la src/auth/login.rs
```

### Step 3: Add Examples

If not already present, add usage examples:

```markdown
## Example

```rust
let result = login(
    "user@example.com".to_string(),
    "password123".to_string()
)?;

println!("Token: {}", result.token);
```
```

### Step 4: Final Review

Read the spec as if you've never seen the code:
- Is it clear?
- Can you implement from this?
- Are there gaps?

### Step 5: Complete

The spec is done! It now documents the code completely.

## Completion Checklist

```markdown
## Spec Complete ✓

- [x] Purpose: Clear
- [x] Interface: Complete
- [x] Errors: Documented
- [x] Edge Cases: Noted
- [x] Tests: Referenced
- [x] Links: Verified
- [x] Examples: Added

**Status**: Complete
**Verified**: [Date]
**Reviewed By**: [Name]
```

## Guidelines

### DO
- Verify every link works
- Check completeness
- Add examples
- Proofread

### DON'T
- Leave incomplete specs
- Skip verification
- Forget examples

## Verification Commands

```bash
# Check links
unispec index list --topic "topic-name"

# Find by path
unispec index find "file.rs" --by path

# List all links
unispec index list
```

## What Happens Next

These specs are now available for:
- Documentation generation
- AI agent understanding
- Future reference
- Onboarding new developers

## Tips

- Read it out loud
- Check for clarity
- Verify examples work
- Ensure consistency

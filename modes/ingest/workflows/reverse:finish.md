# /reverse:finish

Finalize specifications in Spec area.

## When to Use

Use this workflow when:
- Reviewing completed specs
- Verifying completeness
- Finishing documentation

## Steps

### 1. Review Spec

Open and read the spec:

```bash
unispec topic show "login"
```

### 2. Check Completeness

Verify all sections:

- [ ] **Purpose** - Clear description
- [ ] **Interface** - Signature, args, returns
- [ ] **Errors** - All error cases
- [ ] **Behavior** - Step by step
- [ ] **Edge Cases** - What happens with edge cases
- [ ] **Examples** - Usage examples

### 3. Verify Links

Check all code connections:

```bash
# List links
unispec index list --topic "login"

# Verify files exist
ls src/auth/login.rs
ls tests/auth/login_test.rs
```

### 4. Add Examples

If missing, add usage examples:

```markdown
## Example

```rust
use crate::auth::login;

// Successful login
let result = login(
    "user@example.com".to_string(),
    "password123".to_string()
)?;

println!("Got token: {}", result.token);

// Failed login - returns error
match login("bad@example.com".to_string(), "wrong".to_string()) {
    Ok(_) => println!("Should not succeed"),
    Err(AuthError::InvalidCredentials) => println!("Correct!"),
}
```
```

### 5. Mark Complete

Add completion metadata:

```markdown
---

## Spec Complete ✓

**Status**: Complete
**Created**: 2024-01-15
**Reviewed**: 2024-01-15
**Verified Links**: 5 files

### Review Notes
- All error cases documented
- Examples added
- Links verified
```

### 6. Done!

The spec is now complete and ready for use.

## Completion Checklist

```markdown
## ✓ Complete

- [x] Purpose: Clear and concise
- [x] Interface: Full signature with types
- [x] Errors: All error cases documented
- [x] Behavior: Step-by-step flow
- [x] Edge Cases: All boundary conditions
- [x] Examples: Working code examples
- [x] Links: Verified and complete
- [x] Tests: Referenced

**Ready for use!**
```

## Tips

- Read it like it's new to you
- Check if you'd understand the code from this spec
- Verify every link
- Add examples!

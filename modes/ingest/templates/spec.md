# [Function/Component Name]

## Purpose
[Clear description of what this does]

## Location
- File: `src/path/file.rs`
- Lines: 1-50

## Interface

### Signature
```rust
pub fn name(arg: Type) -> ReturnType
```

### Arguments
- `arg_name`: Description

### Returns
- Description

### Errors
- `ErrorType`: When this error occurs
- AnotherError: When this occurs

## Behavior
1. First thing the code does
2. Second thing
3. Third thing
4. Return result

## Edge Cases
- Empty input → [what happens]
- Invalid input → [what happens]
- Error case → [what happens]
- Null/None → [what happens]

## Examples

### Basic Usage
```rust
let result = name(arg);
match result {
    Ok(value) => println!("Success: {}", value),
    Err(e) => println!("Error: {:?}", e),
}
```

### Error Handling
```rust
// This will fail because...
let result = name(invalid_arg);
assert!(result.is_err());
```

## Tests
- Location: `tests/file.rs`
- Test name: `test_name`

## Links
- Source: `src/path/file.rs`
- Module: `src/path/mod.rs`
- Tests: `tests/file.rs`
- Config: `config/file.toml`

---

**Status**: [Draft/Complete]
**Created**: [Date]
**Verified**: [Date]

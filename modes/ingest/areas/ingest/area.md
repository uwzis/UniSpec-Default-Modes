# Ingest

Analyze code and create specifications. Link specs to code as you go.

## Purpose

The Ingest area is where you analyze code from the Code area and create detailed specifications. As you create specs, you link them to the code they document.

## What Goes Here

### Draft Specifications
- Analysis of code behavior
- Interface documentation
- Edge case identification

### Links
- Connections to source code
- Test file references
- Related components

## The Process

### Step 1: Analyze Code

Read and understand the code:

```rust
// src/auth/login.rs
pub fn login(email: String, password: String) -> Result<Token, AuthError> {
    // Find user by email
    let user = users::find_by_email(&email)?;
    
    // Verify password
    if !verify_password(&password, &user.password_hash)? {
        return Err(AuthError::InvalidCredentials);
    }
    
    // Generate token
    let token = generate_token(user.id)?;
    Ok(token)
}
```

### Step 2: Extract Specification

Document what the code does:

```markdown
## login

**Function**: `pub fn login(email: String, password: String) -> Result<Token, AuthError>`

**Purpose**: Authenticate user with email and password

**Arguments**:
- `email`: User's email address
- `password`: User's password

**Returns**: 
- `Ok(Token)`: JWT token on success
- `Err(AuthError::InvalidCredentials)`: Wrong email/password

**Behavior**:
1. Look up user by email
2. Verify password against hash
3. Generate JWT token
4. Return token

**Errors**:
- InvalidCredentials: Email not found or password wrong

**Edge Cases**:
- Empty email → handled by validation
- Empty password → handled by validation  
- Non-existent email → returns error (doesn't reveal if email exists)
```

### Step 3: Link to Code

Use `unispec index` to connect spec to code:

```bash
# Link the spec to the source file
unispec index add --topic "login" --path src/auth/login.rs

# Link to related files
unispec index add --topic "login" --path src/auth/mod.rs
unispec index add --topic "login" --path src/users/mod.rs
unispec index add --topic "login" --path tests/login_test.rs
```

### Step 4: Push to Spec

When spec is complete:
```
unispec topic push "login" Spec
```

## Specification Template

```markdown
# Function/Component Name

## Purpose
What this does.

## Location
- File: `src/path/file.rs`
- Lines: 1-50

## Interface

### Signature
```rust
pub fn name(arg: Type) -> ReturnType
```

### Arguments
- `arg`: Description

### Returns
- Description

### Errors
- ErrorType: When

## Behavior
1. Step 1
2. Step 2
3. Return

## Edge Cases
- Case 1
- Case 2

## Tests
- Location: `tests/file.rs`

## Links
- Source: `src/file.rs`
- Related: `src/other.rs`
```

## Guidelines

### DO
- Read the actual code
- Document what it DOES, not what it should do
- Link as you create specs
- Note edge cases from conditionals

### DON'T
- Copy comments without understanding
- Skip error handling
- Forget to link files

## Workflow

1. **Analyze** - Read and understand code
2. **Create Spec** - Document behavior
3. **Link** - Connect to source files
4. **Push** - Move to Spec for finalization

## Tips

- Read error handling paths carefully
- Check for edge cases in conditionals
- Note what happens with None/null
- Trace data flow

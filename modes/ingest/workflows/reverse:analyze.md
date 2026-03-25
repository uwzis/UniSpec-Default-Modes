# /reverse:analyze

Analyze code and create specifications in Ingest area.

## When to Use

Use this workflow when:
- Creating specs from Code area
- Documenting code behavior
- Linking specs to source

## Steps

### 1. Select Topic

Choose a topic from Ingest area:

```bash
unispec topic list -a Ingest
```

### 2. Read the Code

Open and analyze the source file:

```rust
// src/auth/login.rs
pub fn login(email: String, password: String) -> Result<Token, AuthError> {
    // 1. Find user
    let user = users::find_by_email(&email)?;
    
    // 2. Verify password
    if !verify_password(&password, &user.password_hash)? {
        return Err(AuthError::InvalidCredentials);
    }
    
    // 3. Generate token
    let token = generate_token(user.id)?;
    Ok(token)
}
```

### 3. Extract Specification

Create spec in `spec.md`:

```markdown
# login

## Purpose
Authenticate user and return JWT token.

## Interface
```rust
pub fn login(email: String, password: String) -> Result<Token, AuthError>
```

## Arguments
- `email`: User's email (validated)
- `password`: User's password

## Returns
- `Ok(Token)`: JWT token on success
- `Err(AuthError::InvalidCredentials)`: Auth failed

## Behavior
1. Look up user by email in database
2. Verify password against stored hash (bcrypt)
3. Generate JWT token with user ID
4. Return token

## Errors
- InvalidCredentials: Email not found OR password wrong
  - Note: Returns same error to prevent email enumeration

## Edge Cases
- Empty email → validation error
- Empty password → validation error
- Non-existent user → InvalidCredentials error
- Database error → propagated
```

### 4. Link to Code

Connect spec to source:

```bash
# Link to source file
unispec index add --topic "login" --path src/auth/login.rs

# Link to related files
unispec index add --topic "login" --path src/auth/mod.rs
unispec index add --topic "login" --path src/users/mod.rs

# Link to tests
unispec index add --topic "login" --path tests/auth_test.rs
```

### 5. Push to Spec

When spec is drafted:

```bash
unispec topic push "login" Spec
```

## Tips

- Read the actual implementation
- Check error handling paths
- Note edge cases from conditionals
- Link as you create specs

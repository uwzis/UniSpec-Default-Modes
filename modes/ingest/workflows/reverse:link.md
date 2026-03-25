# /reverse:link

Connect specifications to code files and verify links.

## When to Use

Use this workflow when:
- Creating links from specs
- Verifying existing links
- Building the link matrix

## Steps

### 1. Check Current Spec

Review the spec topic:

```bash
unispec topic show "login"
```

### 2. Add Missing Links

Link to all relevant files:

```bash
# Main source
unispec index add --topic "login" --path src/auth/login.rs

# Module file
unispec index add --topic "login" --path src/auth/mod.rs

# Dependencies
unispec index add --topic "login" --path src/users/mod.rs
unispec index add --topic "login" --path src/token/mod.rs

# Tests
unispec index add --topic "login" --path tests/auth/login_test.rs
unispec index add --topic "login" --path tests/integration/auth_test.rs

# Configuration
unispec index add --topic "login" --path config/auth.toml
```

### 3. Verify Links

Check all links work:

```bash
# List links for topic
unispec index list --topic "login"

# Find by path
unispec index find "login.rs" --by path
```

### 4. Create Link Matrix

Document connections:

```markdown
## Link Matrix

| Type | File | Purpose |
|------|------|---------|
| Source | src/auth/login.rs | Implementation |
| Module | src/auth/mod.rs | Module exports |
| Uses | src/users/mod.rs | User lookup |
| Uses | src/token/mod.rs | Token generation |
| Test | tests/auth/login_test.rs | Unit tests |
| Config | config/auth.toml | Auth config |
```

### 5. Verify Completion

All relevant files should be linked!

## Link Types

| Type | Description |
|------|-------------|
| Source | Main implementation |
| Module | Module/crate exports |
| Uses | Dependencies |
| Used By | Callers |
| Test | Test files |
| Config | Configuration |
| Docs | Documentation |

## Tips

- Link all related files
- Include tests
- Don't forget config
- Verify links exist

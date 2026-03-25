# /reverse:import

Import code files as topics in Code area.

## When to Use

Use this workflow when:
- Starting to document a new codebase
- Adding new files to document
- Setting up for analysis

## Steps

### 1. Import Files

Import code files as topics:

```bash
# Import specific file
unispec topic add "src/main.rs" -a Code

# Import directory
unispec topic add "src/auth/" -a Code

# Import with friendly name
unispec topic add "Auth Module" -a Code
```

### 2. Group Related Files

Create topic groups:

```
Code/
├── auth/
│   ├── login.rs
│   ├── logout.rs
│   └── register.rs
├── users/
│   ├── mod.rs
│   └── profile.rs
└── api/
    └── routes.rs
```

### 3. Review Structure

List what you've imported:

```bash
unispec topic list -a Code
```

### 4. Plan Priorities

Decide what to spec first:
- Entry points (main, handlers)
- Public APIs
- Core business logic
- Utilities

### 5. Push to Ingest

When ready to analyze:

```bash
unispec topic push "src/auth/login.rs" Ingest
```

## Tips

- Start with important files
- Group related code together
- Use clear topic names
- Plan before importing everything

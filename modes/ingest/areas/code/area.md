# Code

Import and review code files. Plan which ones need specifications.

## Purpose

The Code area is where you import existing code files as topics. This lets you review what's in your codebase and plan which files need detailed specifications.

## What Goes Here

### Imported Code Topics
- Individual files as topics
- Directories as topic groups
- Components to document

### Planning Notes
- Which files need specs
- Priority order
- Dependencies to consider

## The Process

### Step 1: Import Files

Import code files as topics:

```bash
# Import individual file
unispec topic add "src/auth/login.rs" -a Code

# Import directory as topic
unispec topic add "src/auth/" -a Code

# Import component
unispec topic add "User Module" -a Code
```

### Step 2: Review What's There

For each imported topic, note:
- What the file/module does
- How complex it is
- How important it is

### Step 3: Plan What to Spec

Create a plan:
- Priority 1: Public APIs, entry points
- Priority 2: Core business logic
- Priority 3: Helpers, utilities
- Priority 4: Everything else

### Step 4: Push to Ingest

When ready to create specs:
```
unispec topic push "src/auth/login.rs" Ingest
```

## Topic Structure

```
Code/
├── src/
│   ├── main.rs
│   ├── auth/
│   │   ├── login.rs      ← Topic
│   │   ├── logout.rs    ← Topic
│   │   └── mod.rs       ← Topic
│   └── users/
│       ├── mod.rs
│       └── ...
├── tests/
└── ...
```

## Guidelines

### DO
- Import files systematically
- Group related files
- Plan your approach
- Start with important files

### DON'T
- Import everything at once
- Skip the planning phase
- Forget to link code to specs

## Workflow

1. **Import** - Add code files as topics
2. **Review** - Understand what's there
3. **Plan** - Decide what needs specs
4. **Push** - Send to Ingest for spec creation

## Tips

- Start with entry points (main, handlers, routes)
- Then focus on public APIs
- Then internal logic
- Use descriptive topic names

## Next Steps

After Code area, move to Ingest to create specifications.

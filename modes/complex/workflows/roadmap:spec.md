# /roadmap:spec

Write or update specifications in the Spec area.

## When to Use

Use this workflow when:
- Writing a new specification
- Updating an existing spec
- Refining requirements

## Steps

### 1. Check Spec Area

List existing specifications:
```
unispec topic list -a Spec
```

### 2. Write Specification

Create or update `spec.md`:

```markdown
# Feature Name

## Problem Statement
What problem does this solve?

## User Stories
- As a [user], I want [goal] so that [benefit]

## Requirements

### Must Have
- [ ] Requirement 1
- [ ] Requirement 2

### Should Have
- [ ] Nice-to-have 1

### Could Have
- [ ] Future enhancement

## Acceptance Criteria
- [ ] Criterion 1 (testable)
- [ ] Criterion 2 (testable)

## Examples
Input → Expected Output

## Edge Cases
- What happens with invalid input?
- What happens with empty data?

## Technical Notes
- Any technical considerations
- Dependencies
```

### 3. Add Tasks

Create `tasks.md`:

```markdown
# Tasks - Feature Name

## Implementation
- [ ] Task 1
- [ ] Task 2

## Testing
- [ ] Write unit tests
- [ ] Write integration tests

## Documentation
- [ ] Update API docs
- [ ] Update README
```

### 4. Link Related Files

Index any related code or documents:
```
unispec index add --topic "feature" --path docs/design.md
```

### 5. Push to Testing

When specification is complete:
```
unispec topic push "Feature Name" Testing
```

## Next Steps

After spec is written, move to `/roadmap:test` to implement and test.

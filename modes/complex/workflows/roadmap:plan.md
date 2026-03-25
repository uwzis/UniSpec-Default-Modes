# /roadmap:plan

Plan a new feature from the roadmap.

## When to Use

Use this workflow when:
- Starting a new feature
- Planning work for a sprint
- Breaking down a large initiative

## Steps

### 1. Review Roadmap

Check the Roadmap area for existing items:
```
unispec topic list -a Roadmap
```

### 2. Create Feature Topic

Add a new topic for the feature:
```
unispec topic add "Feature Name" -a Roadmap
```

### 3. Fill Out Planning Details

In the spec.md, document:
- **Problem**: What problem does this solve?
- **Users**: Who needs this feature?
- **Priority**: Must have / Should have / Could have
- **Estimate**: Story points or time estimate
- **Dependencies**: What must be built first?
- **Risks**: What could go wrong?

### 4. Define Acceptance Criteria

Write clear, testable criteria:
- What must be true for this to be complete?
- How will we verify it works?

### 5. Create Tasks

Break into actionable tasks in tasks.md:
- Implementation tasks
- Testing tasks
- Documentation tasks

### 6. Push to Spec

When ready for implementation:
```
unispec topic push "Feature Name" Spec
```

## Next Steps

After planning, move to `/roadmap:spec` to write the full specification.

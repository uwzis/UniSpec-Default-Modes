# Roadmap

This is where features are planned, prioritized, and prepped before any code is written. Think of it as the "thinking area" - nothing gets built until it lives here first.

## Purpose

The Roadmap area serves as the strategic planning layer for your project. Before anyone writes a single line of code, the work should be thought through here.

## What Goes Here

### Feature Ideas
- New capabilities you want to build
- Improvements to existing features
- Technical debt items
- Infrastructure changes

### Planning Elements
- **Priority** - Must have, Should have, Could have, Won't have
- **Estimates** - Story points, t-shirt sizes, or time estimates
- **Dependencies** - What must be built first?
- **Risks** - What could go wrong?

### Before Moving to Spec

Before pushing to Spec, ensure you have:
- [ ] Clear feature description
- [ ] Identified dependencies
- [ ] Rough estimate of effort
- [ ] Known risks or concerns
- [ ] Success criteria (what does "done" look like?)

## Area Guidelines

### DO
- Think big picture
- Consider user needs
- Identify technical requirements
- Plan for testing from the start
- Document assumptions

### DON'T
- Write code here (that's what Spec is for)
- Skip this area and go straight to building
- Add items without clear priorities
- Ignore dependencies

## Workflow

1. **Add to Roadmap** - Create a new topic with feature idea
2. **Plan** - Fill out the planning details
3. **Review** - Check that it's ready for specification
4. **Push to Spec** - When ready, move to Spec area

## Example Topic Structure

```
Roadmap/
├── user-authentication/
│   ├── spec.md          # Feature description
│   ├── roadmap.md       # Planning details
│   └── tasks.md         # Implementation tasks
└── api-redesign/
    └── ...
```

## Tips

- Keep roadmap items at a high level
- Don't over-plan - leave room for discovery
- Review roadmap regularly
- Move items to Spec when you're ready to work on them

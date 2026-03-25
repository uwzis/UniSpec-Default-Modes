# /roadmap:build

Move completed work to Build area and prepare for deployment.

## When to Use

Use this workflow when:
- All tests pass
- Code is reviewed
- Ready to ship

## Prerequisites

Before moving to Build, verify:

- [ ] All tests pass (100% green)
- [ ] Code reviewed
- [ ] Documentation updated
- [ ] No known bugs
- [ ] Performance acceptable
- [ ] Security reviewed

## Steps

### 1. Final Test Run

Run the complete test suite:
```bash
# Run all tests
pytest --tb=short
# or
cargo test
```

Verify everything passes!

### 2. Code Review

- Check code quality
- Look for issues
- Ensure standards met

### 3. Update Documentation

- API docs current?
- README updated?
- Comments added?

### 4. Update Changelog

Document what changed:
```markdown
## [Version] - YYYY-MM-DD

### Added
- New feature

### Fixed
- Bug in login
```

### 5. Build Release

Create build artifacts:
```bash
# Build
npm run build
# or
cargo build --release
```

### 6. Push to Build

Move to Build area:
```
unispec topic push "Feature Name" Build
```

### 7. Deploy (Optional)

Ship it!
```bash
# Deploy
npm run deploy
# or
kubectl apply -f deploy/
```

## What Happens in Build

The feature is:
- Complete
- Tested
- Documented
- Ready for production

## After Build

- Monitor in production
- Watch for bugs
- If issues found → move back to Roadmap

## Celebration!

You did it! The feature is shipped.

Take a moment to celebrate, then go back to Roadmap for the next thing!

Paddy is proud of you! 🦫

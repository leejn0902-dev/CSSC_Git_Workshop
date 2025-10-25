# Pull Request Workflow

## What is a Pull Request?

A Pull Request (PR) is a method of submitting contributions to a project. It allows you to propose changes, discuss them with collaborators, and merge them into the main codebase after review.

## The PR Workflow

### 1. Fork and Clone (for external contributors)

```bash
# Fork via GitHub UI, then clone your fork
git clone https://github.com/YOUR-USERNAME/CSSC_Git_Workshop.git
cd CSSC_Git_Workshop
```

### 2. Create a Feature Branch

```bash
# Always work on a new branch, not main
git checkout -b feature/my-new-feature
```

### 3. Make Your Changes

```bash
# Edit files, add new features or fix bugs
# Test your changes locally
```

### 4. Commit Your Changes

```bash
git add .
git commit -m "Add feature: descriptive commit message"
```

### 5. Push to GitHub

```bash
git push origin feature/my-new-feature
```

### 6. Create the Pull Request

1. Navigate to the repository on GitHub
2. Click "Pull requests" > "New pull request"
3. Select your branch to compare with `main`
4. Fill in the PR template:
   - **Title**: Clear, concise description
   - **Description**: What changes and why
   - Link related issues with `Fixes #issue-number`
   - Add reviewers
   - Add labels

## Pull Request Best Practices

### Writing Good PR Descriptions

A good PR description includes:

```markdown
## What does this PR do?
Brief summary of changes

## Why are we making this change?
Context and motivation

## Related Issues
Fixes #123
Related to #456

## Testing
- [ ] Unit tests pass
- [ ] Manual testing completed
- [ ] No new warnings

## Screenshots (if applicable)
[Add screenshots for UI changes]

## Checklist
- [ ] Code follows project style guidelines
- [ ] Documentation updated
- [ ] Tests added/updated
```

### Code Review Process

**As an Author:**
- Keep PRs small and focused (one feature/fix per PR)
- Write clear descriptions
- Respond to feedback promptly
- Update your PR based on review comments
- Mark conversations as resolved when addressed

**As a Reviewer:**
- Review promptly
- Be constructive and respectful
- Explain your reasoning
- Approve when satisfied or request changes
- Use GitHub's review features (comment, approve, request changes)

## PR Review Features

### Commenting on Code

- **Single comment**: Click the `+` icon next to a line
- **Multi-line comment**: Click and drag to select multiple lines
- **Suggestions**: Propose specific changes that can be committed directly

```suggestion
// Reviewers can suggest code changes like this
const betterVariableName = value;
```

### Review Status

- ✅ **Approved**: Ready to merge
- 💬 **Comment**: Feedback without approval
- ❌ **Request Changes**: Issues must be addressed

### Merge Strategies

1. **Merge Commit**: Creates a merge commit (preserves all commits)
2. **Squash and Merge**: Combines all commits into one (cleaner history)
3. **Rebase and Merge**: Replays commits on base branch (linear history)

## Draft Pull Requests

Use draft PRs for work-in-progress:
- Shows you're working on something
- Prevents accidental merges
- Allows early feedback
- Mark as "Ready for review" when complete

## Exercise

1. Fork this repository
2. Create a new branch
3. Add your name to a contributors file
4. Push your branch
5. Create a pull request
6. Request a review from a peer
7. Review someone else's PR

## Common PR Commands

```bash
# Update your branch with latest main
git checkout main
git pull upstream main
git checkout feature/my-feature
git merge main

# Or use rebase for cleaner history
git checkout feature/my-feature
git rebase main

# Make changes after review
git add .
git commit -m "Address review feedback"
git push origin feature/my-feature
```

## Dealing with Merge Conflicts

1. Update your branch with the latest main
2. Resolve conflicts in your editor
3. Mark as resolved and commit
4. Push the changes

```bash
git checkout main
git pull origin main
git checkout feature/my-feature
git merge main
# Fix conflicts in your editor
git add .
git commit -m "Resolve merge conflicts"
git push origin feature/my-feature
```

## Best Practices Summary

✅ **Do:**
- Keep PRs small and focused
- Write descriptive titles and descriptions
- Link related issues
- Add tests for new features
- Update documentation
- Respond to reviews quickly
- Keep your branch up to date

❌ **Don't:**
- Create huge PRs with many unrelated changes
- Force push after someone has reviewed (unless necessary)
- Merge without review (unless it's a minor fix)
- Leave PR descriptions empty
- Ignore review feedback

## Resources

- [About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [Reviewing Changes in PRs](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests)

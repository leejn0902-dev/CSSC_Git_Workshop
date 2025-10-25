# GitHub Collaboration Best Practices

## Communication Guidelines

### Writing Good Documentation

**README.md Essentials:**
- Project description and purpose
- Installation instructions
- Usage examples
- Contributing guidelines
- License information

**Code Comments:**
```python
# Good: Explains WHY, not WHAT
# Cache the result to avoid expensive recalculation on each request
cache = {}

# Bad: States the obvious
# Set x to 5
x = 5
```

### Issue and PR Communication

**Be Clear and Concise:**
```markdown
# Good Issue Title
"Login button doesn't work on mobile Safari"

# Bad Issue Title
"Button broken"
```

**Be Respectful:**
- Use inclusive language
- Assume good intentions
- Provide constructive feedback
- Thank contributors

**Example Feedback:**
```markdown
# Good
"Thanks for the PR! I noticed the function might throw an error 
if the input is null. Could you add a null check?"

# Avoid
"This code is wrong. You forgot null checks."
```

## Repository Organization

### Branch Naming Conventions

```bash
feature/add-login-page
bugfix/fix-navigation-error
hotfix/security-patch
docs/update-readme
refactor/cleanup-api-layer
```

### Commit Message Format

Follow conventional commits:

```
type(scope): subject

body (optional)

footer (optional)
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

**Examples:**
```bash
feat(auth): add OAuth2 login support

fix(api): handle null response in getUserData
Fixes #123

docs(readme): update installation instructions

chore(deps): upgrade dependencies to latest versions
```

## Code Review Best Practices

### For Authors

**Before Requesting Review:**
- [ ] Run tests locally
- [ ] Check code formatting
- [ ] Update documentation
- [ ] Add appropriate labels
- [ ] Write clear PR description
- [ ] Keep changes focused and small

**During Review:**
- Respond to all comments
- Ask questions if unclear
- Make requested changes promptly
- Mark conversations as resolved
- Thank reviewers

### For Reviewers

**What to Review:**
- Code correctness and logic
- Test coverage
- Performance implications
- Security concerns
- Code style consistency
- Documentation completeness

**How to Give Feedback:**

✅ **Do:**
```markdown
"Consider using a Set instead of an Array here for better lookup 
performance. Here's an example: ..."
```

❌ **Don't:**
```markdown
"This is slow. Use a Set."
```

**Review Checklist:**
- [ ] Does it solve the problem?
- [ ] Are there tests?
- [ ] Is it maintainable?
- [ ] Are there edge cases?
- [ ] Is it secure?
- [ ] Is documentation updated?

## Team Workflows

### GitHub Flow

1. **Create a branch** from `main`
2. **Add commits** with your changes
3. **Open a PR** for discussion
4. **Review and discuss** changes
5. **Deploy** to test environment (optional)
6. **Merge** to `main` after approval
7. **Deploy** to production

### Release Process

```
main (production)
  ↑
  └── release/v1.2.0
        ↑
        └── feature branches
```

**Steps:**
1. Create release branch from `main`
2. Finish features and bug fixes
3. Test release branch
4. Tag release (`v1.2.0`)
5. Merge to `main`
6. Deploy to production

## Issue Management

### Triaging Issues

**Labels System:**
```
Priority:
- priority: critical
- priority: high
- priority: medium
- priority: low

Type:
- type: bug
- type: feature
- type: enhancement
- type: documentation

Status:
- status: blocked
- status: help wanted
- status: good first issue
```

**Issue Lifecycle:**
1. **New** → Label and prioritize
2. **Triaged** → Assign to milestone
3. **In Progress** → Assign to developer
4. **In Review** → Link to PR
5. **Done** → Close with reference

### Templates

Create `.github/ISSUE_TEMPLATE/`:

**Bug Report:**
```markdown
---
name: Bug Report
about: Report a bug
labels: bug
---

## Description
[Clear description of the bug]

## Steps to Reproduce
1. 
2. 
3. 

## Expected Behavior
[What should happen]

## Actual Behavior
[What actually happens]

## Environment
- OS: 
- Browser: 
- Version: 
```

**Feature Request:**
```markdown
---
name: Feature Request
about: Suggest a new feature
labels: enhancement
---

## Problem
[What problem does this solve?]

## Proposed Solution
[How should it work?]

## Alternatives
[Other approaches considered]
```

## Security

### Managing Secrets

**Never commit:**
- API keys
- Passwords
- Private keys
- Access tokens

**Use:**
- Environment variables
- GitHub Secrets (for Actions)
- `.env` files (add to `.gitignore`)

### Security Best Practices

```markdown
# .gitignore
.env
.env.local
secrets.yml
*.key
*.pem
```

**If you accidentally commit a secret:**
1. Rotate the secret immediately
2. Remove from Git history (`git filter-branch` or BFG)
3. Force push (if allowed)
4. Report to security team

### Dependabot

Enable Dependabot for automatic dependency updates:

```yaml
# .github/dependabot.yml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
    open-pull-requests-limit: 10
```

## Documentation

### Essential Files

**README.md:**
- What the project does
- How to install it
- How to use it
- How to contribute

**CONTRIBUTING.md:**
- How to set up development environment
- Coding standards
- PR process
- Where to ask for help

**CODE_OF_CONDUCT.md:**
- Expected behavior
- Unacceptable behavior
- Reporting process

**LICENSE:**
- Legal terms for using the project

### Wiki vs Documentation Folder

**Use Wiki for:**
- Detailed guides
- Tutorials
- Architecture decisions
- FAQs

**Use `/docs` folder for:**
- API documentation
- Code-adjacent docs
- Versioned documentation

## Collaboration Tools

### GitHub Discussions

Enable Discussions for:
- Q&A forum
- Feature discussions
- Announcements
- Community building

Categories:
- 💡 Ideas
- 🙏 Q&A
- 📣 Announcements
- 🗳️ Polls

### Team Mentions

```markdown
@org/team-name can you review this?
@username what do you think?
```

### Notifications

**Manage your notifications:**
- Watch repositories you care about
- Unwatch inactive repositories
- Use custom notification routing
- Set up email filters

**Notification levels:**
- **Participating**: You're mentioned or involved
- **All Activity**: Every update
- **Ignore**: No notifications
- **Custom**: Choose specific events

## Metrics and Health

### Repository Insights

Track project health:
- **Contributors**: Who's contributing
- **Traffic**: Views and clones
- **Commits**: Activity over time
- **Community**: Community standards checklist

### Community Standards

Achieve 100% by adding:
- [ ] Description
- [ ] README
- [ ] Code of conduct
- [ ] Contributing guidelines
- [ ] License
- [ ] Issue templates
- [ ] Pull request template

## Open Source Best Practices

### Licensing

Choose an appropriate license:
- **MIT**: Permissive, allows commercial use
- **Apache 2.0**: Permissive with patent grant
- **GPL**: Copyleft, derivative works must be open source
- **BSD**: Permissive with attribution

### Welcoming Contributors

**Good First Issues:**
```markdown
Label issues with `good first issue` for newcomers
- Clear description
- Expected outcome
- Hints on where to start
```

**Recognizing Contributors:**
- Thank contributors in PR comments
- Add contributors to README
- Use All Contributors bot
- Celebrate milestones

## Resources

- [GitHub Skills](https://skills.github.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)
- [Choose a License](https://choosealicense.com/)
- [Open Source Guides](https://opensource.guide/)

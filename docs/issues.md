# Working with GitHub Issues

## What are Issues?

GitHub Issues are a powerful way to track bugs, enhancements, questions, and tasks for your project. They serve as a central place for discussion and planning.

## Key Features

- **Labels** - Categorize issues (bug, enhancement, question, etc.)
- **Assignees** - Assign issues to team members
- **Milestones** - Group issues into larger goals
- **Comments** - Discuss and collaborate on solutions
- **References** - Link to commits, PRs, and other issues
- **Mentions** - Notify team members with @username

## Creating an Issue

1. Navigate to the repository
2. Click on the "Issues" tab
3. Click "New Issue"
4. Fill in:
   - **Title**: Clear, concise description
   - **Description**: Detailed information, steps to reproduce (for bugs), or requirements (for features)
   - **Labels**: Add relevant labels
   - **Assignees**: Assign to yourself or team members
   - **Projects**: Link to a project board (optional)
   - **Milestone**: Associate with a milestone (optional)

## Issue Templates

Good issue templates help maintain consistency. Example bug report template:

```markdown
## Bug Description
A clear description of the bug

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. See error

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- OS: [e.g., Windows 10]
- Browser: [e.g., Chrome 96]
- Version: [e.g., 1.2.3]
```

## Linking Issues to Code

- **Reference in commits**: Use `#issue-number` in commit messages
  ```
  git commit -m "Fix navigation bug, closes #42"
  ```
- **Close automatically**: Use keywords like `fixes`, `closes`, or `resolves`
- **Link in PRs**: Reference issues in PR descriptions

## Exercise

1. Create a new issue in this repository
2. Add appropriate labels
3. Assign it to yourself
4. Add a comment with additional context
5. Reference another issue using `#number`

## Best Practices

✅ **Do:**
- Write clear, descriptive titles
- Provide detailed descriptions with context
- Use templates for consistency
- Add labels for easy filtering
- Search before creating duplicates

❌ **Don't:**
- Use vague titles like "It doesn't work"
- Create duplicate issues without checking first
- Leave issues unassigned if you're working on them
- Forget to close resolved issues

## Resources

- [GitHub Issues Documentation](https://docs.github.com/en/issues)
- [About Issue Templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests)

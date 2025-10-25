# Hands-On Exercises

Complete these exercises to practice GitHub skills. Each exercise builds on GitHub-specific features.

## Exercise 1: Your First Issue

**Goal**: Learn to create and manage GitHub issues

**Tasks**:
1. Navigate to the "Issues" tab
2. Click "New Issue"
3. Choose "Bug Report" or "Feature Request" template
4. Fill in all sections with meaningful information
5. Add labels: `good first issue`, `help wanted`, or `documentation`
6. Assign the issue to yourself
7. Submit the issue
8. Add a comment with additional context
9. Edit the issue to add more details

**Verification**: You should see your issue in the Issues list with the labels you added.

---

## Exercise 2: Working with Labels

**Goal**: Organize issues with labels

**Tasks**:
1. Go to Issues → Labels
2. Create a custom label called `workshop-exercise`
3. Choose a color and description
4. Apply this label to the issue you created in Exercise 1
5. Filter issues by your new label

**Verification**: Your issue should appear when filtering by `workshop-exercise`.

---

## Exercise 3: Fork and Clone

**Goal**: Create your own copy of this repository

**Tasks**:
1. Click the "Fork" button at the top right
2. Wait for GitHub to create your fork
3. Clone your fork to your local machine:
   ```bash
   git clone https://github.com/YOUR-USERNAME/CSSC_Git_Workshop.git
   cd CSSC_Git_Workshop
   ```
4. Verify you're on your fork:
   ```bash
   git remote -v
   # Should show YOUR-USERNAME, not PotatoPirate8
   ```

**Verification**: You have a local copy of your fork.

---

## Exercise 4: Create a Branch and Make Changes

**Goal**: Practice the branch workflow

**Tasks**:
1. Create a new branch:
   ```bash
   git checkout -b add-my-name
   ```
2. Create a file `participants.md` with your name:
   ```markdown
   # Workshop Participants
   
   - Your Name
   ```
3. Commit your changes:
   ```bash
   git add participants.md
   git commit -m "docs: add my name to participants"
   ```
4. Push your branch:
   ```bash
   git push origin add-my-name
   ```

**Verification**: You should see your branch on GitHub.

---

## Exercise 5: Your First Pull Request

**Goal**: Create a pull request to contribute

**Tasks**:
1. Go to your fork on GitHub
2. Click "Pull requests" → "New pull request"
3. Click "compare across forks"
4. Set base repository to `PotatoPirate8/CSSC_Git_Workshop` and base to `main`
5. Set head repository to your fork and compare to `add-my-name`
6. Click "Create pull request"
7. Fill in the PR template:
   - Title: "Add [Your Name] to participants"
   - Description: Explain what you added
   - Check the appropriate boxes
8. Submit the pull request

**Verification**: Your PR appears in the original repository's Pull Requests tab.

---

## Exercise 6: Review a Pull Request

**Goal**: Practice code review

**Tasks**:
1. Find a classmate's pull request
2. Go to "Files changed" tab
3. Hover over a line of code and click the "+" to add a comment
4. Write a constructive comment or suggestion
5. Click "Add single comment" or "Start a review"
6. If starting a review, add 2-3 comments then click "Finish review"
7. Choose "Approve" or "Comment"

**Verification**: Your review appears on the PR.

---

## Exercise 7: Respond to Review Feedback

**Goal**: Handle review comments professionally

**Tasks**:
1. Wait for someone to review your PR (or ask a classmate)
2. Read the review comments
3. Respond to each comment
4. Make changes if suggested:
   ```bash
   # Make edits to your file
   git add participants.md
   git commit -m "docs: address review feedback"
   git push origin add-my-name
   ```
5. Mark conversations as resolved

**Verification**: Updated commits appear in your PR.

---

## Exercise 8: Create a GitHub Action

**Goal**: Set up automation with GitHub Actions

**Tasks**:
1. In your fork, create `.github/workflows/greet.yml`
2. Add this workflow:
   ```yaml
   name: Greet

   on: [push]

   jobs:
     greet:
       runs-on: ubuntu-latest
       steps:
         - name: Say hello
           run: echo "Hello from ${{ github.actor }}!"
   ```
3. Commit and push:
   ```bash
   git add .github/workflows/greet.yml
   git commit -m "ci: add greeting workflow"
   git push
   ```
4. Go to Actions tab to see it run

**Verification**: You see a successful workflow run.

---

## Exercise 9: Create a Project Board

**Goal**: Organize work with GitHub Projects

**Tasks**:
1. Go to Projects → "New Project"
2. Choose "Board" template
3. Name it "Workshop Tasks"
4. Create columns:
   - To Do
   - In Progress
   - Done
5. Add your issues to the board
6. Move items between columns
7. Add a custom field for "Priority"

**Verification**: You have a functional project board.

---

## Exercise 10: Use Issue References

**Goal**: Link issues and PRs

**Tasks**:
1. Create a new issue: "Update documentation"
2. Note the issue number (e.g., #42)
3. Create a new branch and make a small documentation change
4. In your commit message, reference the issue:
   ```bash
   git commit -m "docs: update README, relates to #42"
   ```
5. Create a PR and in the description write "Fixes #42"
6. Notice the automatic link created

**Verification**: The issue shows a reference to your PR.

---

## Bonus Exercise 11: Markdown Mastery

**Goal**: Practice GitHub-flavored markdown

**Tasks**:
1. Create a file `markdown-practice.md` in your fork
2. Include examples of:
   - Headers (h1-h6)
   - Bold and italic text
   - Code blocks with syntax highlighting
   - Links and images
   - Task lists
   - Tables
   - Emojis (`:rocket:` → 🚀)
   - Mentions (`@username`)
   - Issue references (`#number`)
3. Preview your markdown on GitHub

**Verification**: Your markdown renders beautifully on GitHub.

---

## Bonus Exercise 12: Explore GitHub Insights

**Goal**: Understand repository metrics

**Tasks**:
1. Go to Insights tab
2. Explore each section:
   - Contributors: Who has contributed
   - Traffic: Views and clones
   - Commits: Activity graph
   - Code frequency: Additions and deletions
   - Network: Branch visualization
3. Take note of interesting patterns

**Verification**: You understand what each metric means.

---

## Challenge Exercise: Complete Workflow

**Goal**: Demonstrate end-to-end GitHub workflow

**Tasks**:
1. Find or create an issue
2. Assign it to yourself
3. Create a branch
4. Make changes to fix/implement the issue
5. Write a good commit message
6. Push your branch
7. Create a pull request
8. Link the issue in the PR
9. Request a review
10. Address feedback
11. Get approval
12. Merge the PR (if you have permission)

**Verification**: Issue is closed automatically when PR merges.

---

## Reflection Questions

After completing the exercises, consider:

1. What GitHub feature did you find most useful?
2. How could GitHub improve team collaboration?
3. What's the difference between Git and GitHub now that you've used both?
4. How would you use GitHub in your next project?
5. What best practices will you adopt?

## Next Steps

- Contribute to open source projects
- Create your own repository
- Set up CI/CD with GitHub Actions
- Explore GitHub Advanced Security
- Join the GitHub Community Forum

**Congratulations on completing the GitHub Workshop!** 🎉

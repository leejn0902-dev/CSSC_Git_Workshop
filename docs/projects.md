# GitHub Projects

## What are GitHub Projects?

GitHub Projects is a flexible, customizable tool for planning and tracking work. It integrates seamlessly with issues and pull requests, providing a visual way to organize and prioritize your work.

## Project Views

Projects support multiple views:

- **Board** (Kanban): Visualize workflow stages (To Do, In Progress, Done)
- **Table**: Spreadsheet-like view with custom fields
- **Roadmap**: Timeline view for planning releases

## Creating a Project

### Organization/Repository Level

1. Navigate to your repository or organization
2. Click "Projects" tab
3. Click "New Project"
4. Choose a template or start from scratch:
   - **Board**: Kanban-style workflow
   - **Table**: Spreadsheet view
   - **Roadmap**: Timeline planning
5. Name your project and add a description

## Adding Items to Projects

### From Issues/PRs

- Drag issues/PRs directly to the project board
- Use the "+" button to search and add existing items
- Convert notes to issues

### Creating Items Directly

- Click "+" on the project board
- Add draft items that can be converted to issues later
- Type `#` to link to existing issues

## Custom Fields

Enhance your project with custom fields:

- **Status**: To Do, In Progress, Done
- **Priority**: High, Medium, Low
- **Size**: Small, Medium, Large
- **Sprint**: Sprint 1, Sprint 2, etc.
- **Assignee**: Team members
- **Labels**: From repository labels

### Adding Custom Fields

1. Click on the field header dropdown
2. Select "New field"
3. Choose field type:
   - Single select
   - Text
   - Number
   - Date
   - Iteration

## Automation

GitHub Projects includes powerful automation:

### Built-in Workflows

- **Item added to project**: Auto-set status to "To Do"
- **Item closed**: Auto-set status to "Done"
- **Pull request merged**: Auto-set status to "Done"
- **Item reopened**: Auto-set status to "In Progress"

### Setting up Automation

1. Click "⋯" menu on your project
2. Select "Workflows"
3. Enable built-in workflows
4. Customize triggers and actions

## Organizing Work

### Kanban Board Example

**Columns:**
1. **Backlog**: Ideas and future work
2. **To Do**: Prioritized and ready to start
3. **In Progress**: Currently being worked on
4. **In Review**: Awaiting code review
5. **Done**: Completed work

### Sprint Planning

```
Sprint 1 (2 weeks)
├── High Priority
│   ├── Feature A
│   └── Bug Fix B
├── Medium Priority
│   └── Feature C
└── Low Priority
    └── Documentation D
```

## Filtering and Sorting

### Filters

```
is:open assignee:@me
is:issue label:bug
is:pr status:"In Review"
```

### Saved Views

Create custom views for different perspectives:
- **My Work**: `assignee:@me is:open`
- **Bugs**: `is:issue label:bug`
- **Current Sprint**: `iteration:@current`

## Insights and Reports

### Built-in Charts

- **Burndown**: Track progress over time
- **Velocity**: Measure team throughput
- **Cumulative flow**: Visualize work distribution

### Creating Charts

1. Go to your project
2. Click "Insights" tab
3. Click "New chart"
4. Configure:
   - Chart type
   - X and Y axes
   - Filters

## Collaboration

### Team Workflows

**Planning Meeting:**
1. Review backlog in table view
2. Set priorities and estimates
3. Move items to "To Do" column
4. Assign to team members

**Daily Standup:**
1. Filter by assignee
2. Review "In Progress" items
3. Identify blockers
4. Update status

**Sprint Review:**
1. Review "Done" column
2. Close completed issues
3. Move incomplete items back to backlog

## Exercise

1. Create a new project for this workshop
2. Add some issues to the project
3. Create custom fields (Priority, Size)
4. Set up a Kanban board with columns:
   - Backlog
   - To Do
   - In Progress
   - Done
5. Enable automatic workflows
6. Move items through the workflow
7. Create a saved view for high-priority items

## Project Templates

### Software Development

```
Columns:
- 📋 Backlog
- 📝 To Do
- 🏗️ In Progress
- 👀 In Review
- ✅ Done

Fields:
- Priority (High/Medium/Low)
- Size (S/M/L)
- Sprint
- Type (Feature/Bug/Docs)
```

### Bug Tracking

```
Columns:
- 🐛 New Bugs
- 🔍 Investigating
- 🔧 Fixing
- 🧪 Testing
- ✅ Resolved

Fields:
- Severity (Critical/High/Medium/Low)
- Component
- Assigned To
```

### Release Planning

```
Views:
- Roadmap: Timeline of releases
- Table: All features with target dates
- Board: Current release items

Fields:
- Target Release
- Status
- Dependencies
- Team
```

## Best Practices

✅ **Do:**
- Keep the board updated
- Use consistent statuses across projects
- Add descriptions to items
- Link related issues and PRs
- Use labels for categorization
- Set up automation to reduce manual work
- Archive completed projects
- Use custom fields for team-specific needs

❌ **Don't:**
- Let items stagnate without updates
- Create too many columns (keep it simple)
- Forget to link issues to the project
- Overcomplicate with too many custom fields
- Mix different types of work without labels
- Ignore the backlog (regularly groom it)

## Keyboard Shortcuts

- `C`: Create new item
- `E`: Edit item
- `Cmd/Ctrl + Enter`: Save item
- `/`: Focus search
- `Cmd/Ctrl + K`: Command palette

## Integration with Other Features

### Issues

```markdown
<!-- In issue description -->
This issue is tracked in Project #1
```

### Pull Requests

PRs automatically appear in projects when:
- Manually added
- Linked via "Development" section
- Referenced in commits

### Milestones

Combine with projects:
- Milestones for time-based grouping
- Projects for workflow tracking
- Labels for categorization

## Resources

- [GitHub Projects Documentation](https://docs.github.com/en/issues/planning-and-tracking-with-projects)
- [Project Planning Best Practices](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/best-practices-for-projects)
- [Automating Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/automating-your-project)

# GitHub Actions Basics

## What are GitHub Actions?

GitHub Actions is a CI/CD platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that run on specific events in your repository.

## Key Concepts

- **Workflow**: An automated process defined by a YAML file
- **Event**: Triggers that start a workflow (push, pull_request, schedule, etc.)
- **Job**: A set of steps that execute on the same runner
- **Step**: An individual task (run a command, use an action)
- **Action**: A reusable unit of code
- **Runner**: Server that runs your workflows (GitHub-hosted or self-hosted)

## Workflow File Structure

Workflows are defined in `.github/workflows/` directory using YAML files.

### Basic Example

```yaml
name: CI

# When to run this workflow
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

# Jobs to run
jobs:
  build:
    # Runner environment
    runs-on: ubuntu-latest
    
    # Steps to execute
    steps:
    - name: Checkout code
      uses: actions/checkout@v3
      
    - name: Run tests
      run: npm test
```

## Common Workflow Triggers

```yaml
# On push to main branch
on:
  push:
    branches: [ main ]

# On any pull request
on:
  pull_request:

# On schedule (cron syntax)
on:
  schedule:
    - cron: '0 0 * * *'  # Daily at midnight

# On multiple events
on:
  push:
    branches: [ main, develop ]
  pull_request:
  workflow_dispatch:  # Manual trigger
```

## Common Use Cases

### 1. Continuous Integration (CI)

Run tests on every push or PR:

```yaml
name: Test Suite

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: npm ci
      
    - name: Run tests
      run: npm test
      
    - name: Run linter
      run: npm run lint
```

### 2. Automated Deployment

Deploy on merge to main:

```yaml
name: Deploy

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Deploy to production
      run: ./deploy.sh
      env:
        API_KEY: ${{ secrets.API_KEY }}
```

### 3. Code Quality Checks

```yaml
name: Code Quality

on: [pull_request]

jobs:
  quality:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Run code formatter check
      run: npm run format:check
      
    - name: Security audit
      run: npm audit
```

## Using Actions from Marketplace

GitHub Marketplace offers thousands of pre-built actions:

```yaml
steps:
  # Checkout code
  - uses: actions/checkout@v3
  
  # Setup programming languages
  - uses: actions/setup-node@v3
  - uses: actions/setup-python@v4
  - uses: actions/setup-java@v3
  
  # Cache dependencies
  - uses: actions/cache@v3
    with:
      path: ~/.npm
      key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
  
  # Upload artifacts
  - uses: actions/upload-artifact@v3
    with:
      name: my-artifact
      path: dist/
```

## Working with Secrets

Store sensitive data in GitHub Secrets:

1. Go to repository Settings > Secrets and variables > Actions
2. Click "New repository secret"
3. Add name and value
4. Reference in workflow:

```yaml
steps:
  - name: Deploy
    env:
      API_TOKEN: ${{ secrets.API_TOKEN }}
      DATABASE_URL: ${{ secrets.DATABASE_URL }}
    run: ./deploy.sh
```

## Matrix Builds

Test across multiple versions:

```yaml
jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest, macos-latest]
        node-version: [14, 16, 18]
    
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-node@v3
      with:
        node-version: ${{ matrix.node-version }}
    - run: npm test
```

## Workflow Status Badge

Add a status badge to your README:

```markdown
![CI](https://github.com/username/repo/workflows/CI/badge.svg)
```

## Exercise

1. Create a `.github/workflows` directory in your fork
2. Create a simple workflow file `ci.yml`
3. Configure it to run on push and pull_request events
4. Add a step that prints "Hello, GitHub Actions!"
5. Push your changes and watch the workflow run
6. Check the "Actions" tab to see the results

### Sample Exercise Workflow

```yaml
name: Hello Actions

on: [push, pull_request]

jobs:
  greet:
    runs-on: ubuntu-latest
    steps:
    - name: Print greeting
      run: echo "Hello, GitHub Actions!"
      
    - name: Show runner info
      run: |
        echo "OS: ${{ runner.os }}"
        echo "Event: ${{ github.event_name }}"
        echo "Repository: ${{ github.repository }}"
```

## Debugging Workflows

- Check the Actions tab for workflow runs
- Click on a workflow run to see job details
- Click on a job to see step-by-step logs
- Use `actions/checkout@v3` to access your code
- Add debug steps with `run: echo "Debug: ${{ toJson(github) }}"`
- Enable debug logging: Add secret `ACTIONS_STEP_DEBUG` = `true`

## Best Practices

✅ **Do:**
- Use specific action versions (`actions/checkout@v3`, not `@main`)
- Cache dependencies to speed up workflows
- Use matrix builds for cross-platform testing
- Keep workflows focused and modular
- Use secrets for sensitive data
- Add status badges to README
- Set up branch protection to require workflow success

❌ **Don't:**
- Hardcode secrets in workflow files
- Run unnecessary jobs on every commit
- Use outdated actions
- Create overly complex workflows
- Ignore failed workflows

## Common Workflow Patterns

### Run only on specific file changes

```yaml
on:
  push:
    paths:
      - 'src/**'
      - 'tests/**'
```

### Conditional steps

```yaml
steps:
  - name: Only on main branch
    if: github.ref == 'refs/heads/main'
    run: echo "This is main branch"
```

### Dependent jobs

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: npm run build
  
  test:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - run: npm test
```

## Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
- [Workflow Syntax Reference](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [GitHub Actions Examples](https://github.com/actions/starter-workflows)

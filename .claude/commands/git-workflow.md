# Git Workflow Assistant

Assist with git operations and workflow management for: $ARGUMENTS

## Instructions

Analyze the current repository state and help with git operations. Follow a structured approach based on what the user needs.

## Workflow Steps

### 1. Repository State Analysis
- Run `git status` to understand current working tree state
- Run `git log --oneline -20` to see recent history
- Run `git branch -a` to see all branches
- Check `git stash list` for any stashed changes
- Identify the current branch and its tracking status

### 2. Branch Management
Based on the task, help with:
- **Feature branches**: Create from up-to-date main/develop branch
  - Naming: `feature/description`, `fix/description`, `chore/description`
- **Branch cleanup**: Identify and remove merged/stale branches
- **Branch switching**: Safely switch with uncommitted changes
- **Rebasing**: Interactive rebase for clean history before merging

### 3. Commit Workflow
- **Stage selectively**: Use `git add -p` for partial staging when appropriate
- **Commit messages**: Follow conventional commits format
  - `feat:` new features
  - `fix:` bug fixes
  - `refactor:` code refactoring
  - `docs:` documentation changes
  - `test:` adding or updating tests
  - `chore:` maintenance tasks
  - `perf:` performance improvements
- **Atomic commits**: Each commit should represent one logical change
- **Amend**: Fix the last commit when needed (before pushing)

### 4. Merge and Rebase Strategy
- **Feature to main**: Prefer squash merge or rebase for clean history
- **Conflict resolution**: Step-by-step guidance for merge conflicts
  - Identify conflicting files
  - Understand both sides of the conflict
  - Choose appropriate resolution strategy
  - Verify resolution with tests
- **Fast-forward**: When possible, keep linear history

### 5. Pull Request Preparation
- Ensure branch is up to date with target branch
- Squash fixup commits if needed
- Verify all tests pass
- Generate a summary of changes with `git diff main...HEAD --stat`
- Create descriptive PR with `gh pr create` if gh CLI is available

### 6. Common Operations
- **Undo last commit** (keeping changes): `git reset --soft HEAD~1`
- **Discard changes in file**: `git checkout -- <file>`
- **Cherry-pick**: Apply specific commits to current branch
- **Bisect**: Find the commit that introduced a bug
- **Blame**: Understand who changed what and why
- **Reflog**: Recover lost commits or branches

### 7. Release Workflow
- Tag releases following semver: `git tag -a v1.2.3 -m "Release v1.2.3"`
- Generate changelog from commit history
- Verify tag is on the correct commit
- Push tags: `git push origin --tags`

### 8. Safety Practices
- Never force push to shared branches (main, develop)
- Always pull before pushing to shared branches
- Use `--force-with-lease` instead of `--force` when necessary
- Create backup branches before destructive operations
- Verify remote state before rewriting history

## Output Format

For each git operation:
1. **Current State**: What the repo looks like now
2. **Proposed Action**: What commands will be run and why
3. **Expected Result**: What the repo will look like after
4. **Rollback Plan**: How to undo if something goes wrong

Always explain the "why" behind git operations, not just the commands.

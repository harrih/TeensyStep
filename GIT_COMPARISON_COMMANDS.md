# Quick Reference: Git Branch Comparison Commands

This is a quick reference guide for comparing branches in Git.

## Basic Comparison Commands

### Compare two branches (current vs improveCallback)

```bash
# Show commits in improveCallback but not in current branch
git log --oneline copilot/compare-commits-between-branches..improveCallback

# Show commits in current branch but not in improveCallback
git log --oneline improveCallback..copilot/compare-commits-between-branches

# Show both with visual graph
git log --oneline --graph --left-right --boundary copilot/compare-commits-between-branches...improveCallback
```

## File Differences

```bash
# Show which files differ (statistics)
git diff --stat copilot/compare-commits-between-branches improveCallback

# Show actual differences in all files
git diff copilot/compare-commits-between-branches improveCallback

# Show differences in a specific file
git diff copilot/compare-commits-between-branches improveCallback -- path/to/file
```

## Viewing Specific Changes

```bash
# Show commits with dates and authors
git log --pretty=format:"%h - %an, %ar : %s" copilot/compare-commits-between-branches..improveCallback

# Show detailed commit information
git log --stat copilot/compare-commits-between-branches..improveCallback

# Show commits with full diff
git log -p copilot/compare-commits-between-branches..improveCallback
```

## Finding Common Ancestor

```bash
# Find merge base (common ancestor)
git merge-base copilot/compare-commits-between-branches improveCallback

# Show the common ancestor commit
git show $(git merge-base copilot/compare-commits-between-branches improveCallback)
```

## Branch Relationship Visualization

```bash
# Show all branches and their relationships
git log --all --graph --decorate --oneline

# Show just the two branches
git log --graph --oneline copilot/compare-commits-between-branches improveCallback
```

## Counting Changes

```bash
# Count commits in improveCallback not in current branch
git log --oneline copilot/compare-commits-between-branches..improveCallback | wc -l

# Count commits in current branch not in improveCallback
git log --oneline improveCallback..copilot/compare-commits-between-branches | wc -l

# Count file changes
git diff --shortstat copilot/compare-commits-between-branches improveCallback
```

## Merging/Rebasing

```bash
# Preview what would be merged (dry run)
git merge --no-commit --no-ff improveCallback

# Actually merge improveCallback into current branch
git merge improveCallback

# Rebase current branch onto improveCallback
git rebase improveCallback

# Abort merge if there are conflicts
git merge --abort

# Abort rebase if there are conflicts
git rebase --abort
```

## Checking Specific Commits

```bash
# Show a specific commit
git show dcdb0ee

# Show files changed in a specific commit
git show --stat dcdb0ee

# Show just the commit message and metadata
git log --format=fuller -1 dcdb0ee
```

## GitHub-Specific Comparison

```bash
# If you prefer to use GitHub's web interface:
# Visit: https://github.com/harrih/TeensyStep/compare/copilot/compare-commits-between-branches...improveCallback
```

## Using Git Diff with Better Formatting

```bash
# Show side-by-side diff
git diff --color-words copilot/compare-commits-between-branches improveCallback

# Show diff with more context lines
git diff -U10 copilot/compare-commits-between-branches improveCallback

# Show only names of changed files
git diff --name-only copilot/compare-commits-between-branches improveCallback

# Show names and status (Added, Modified, Deleted)
git diff --name-status copilot/compare-commits-between-branches improveCallback
```

## Tips

1. **Replace branch names**: Replace `copilot/compare-commits-between-branches` and `improveCallback` with your actual branch names
2. **Two dots vs three dots**: 
   - `branch1..branch2` shows commits in branch2 not in branch1
   - `branch1...branch2` shows commits that differ between the branches
3. **HEAD reference**: You can use `HEAD` instead of the current branch name
4. **Remote branches**: Prefix with `origin/` for remote branches (e.g., `origin/master`)

## Example Workflow

```bash
# 1. Fetch latest changes
git fetch origin

# 2. Compare your branch with target
git log --oneline HEAD..origin/improveCallback

# 3. See what files will change
git diff --stat HEAD origin/improveCallback

# 4. Review specific file changes
git diff HEAD origin/improveCallback -- src/MotorControlBase.h

# 5. Merge if everything looks good
git merge origin/improveCallback
```

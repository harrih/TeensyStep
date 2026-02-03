# Branch Comparison: copilot/compare-commits-between-branches vs improveCallback

This document provides a comprehensive comparison between the current branch (`copilot/compare-commits-between-branches`) and the `improveCallback` branch.

## Branch Information

- **Current Branch**: `copilot/compare-commits-between-branches`
  - Latest commit: `b4044b0` - Initial plan
  - Base: `795d58b` - Update library.properties

- **Compare Branch**: `improveCallback`
  - Latest commit: `dcdb0ee` - activated speed override
  - Contains: 279 commits ahead of current branch

## Summary of Differences

The `improveCallback` branch is significantly ahead of the current branch with 279 additional commits. The current branch only has 2 commits that diverged from an earlier point in the repository history.

### Commits Only in improveCallback Branch

The improveCallback branch contains 279 commits that are not in the current branch. Key commits include:

1. **dcdb0ee** - activated speed override
2. **6db682c** - changed step ISR to invoke callback AFTER last pulse
3. **c10de78** - add definition of static constexpr members
4. **cd4bd9e** - bump version (v2.3.2)
5. **d32ff53** - changed std::abs to abs to escape the Arduino madness
6. **e151a87** - Added callback functionality to RotateControl
7. **9efde61** - Bump version to 2.3.1
8. **d1fd0bd** - Fix issue with uint32_t overflow for large speed / acceleration values
9. **1275433** - Fix bug preventing restart after overrideSpeed(0)
10. **07ba4db** - Fixes issue stopping motor when no steps are left
11. **7d1a0bf** - Optimize speed of motor group in case v_max
12. **cfb50b0** - Keep interrupt register force update for stm32f4
13. **8f66022** - Fix first pulse being too long
14. Plus 266 more commits...

### Commits Only in Current Branch

The current branch has 2 commits:
1. **b4044b0** - Initial plan
2. **795d58b** - Update library.properties

### File Changes Between Branches

When comparing the branches, the following files differ:

```
README.md                             |  5 +----
library.json                          |  2 +-
library.properties                    |  2 +-
src/MotorControlBase.h                |  6 +++---
src/StepControlBase.h                 |  4 ++--
src/Stepper.cpp                       |  6 ------
src/accelerators/LinStepAccelerator.h |  7 -------
src/timer/teensy3/TimerField2.h       | 13 ++++++++++---
8 files changed, 18 insertions(+), 27 deletions(-)
```

## Git Commands for Branch Comparison

Here are the most useful Git commands for comparing these branches:

### 1. View Commit History Comparison (Graphical)
```bash
git log --oneline --graph --left-right --boundary copilot/compare-commits-between-branches...improveCallback
```

This shows commits from both branches with visual indicators:
- `<` commits unique to the left branch (current)
- `>` commits unique to the right branch (improveCallback)

### 2. List Commits Only in improveCallback
```bash
git log --oneline copilot/compare-commits-between-branches..improveCallback
```

### 3. List Commits Only in Current Branch
```bash
git log --oneline improveCallback..copilot/compare-commits-between-branches
```

### 4. View File Differences (Statistics)
```bash
git diff --stat copilot/compare-commits-between-branches improveCallback
```

### 5. View Detailed File Differences
```bash
git diff copilot/compare-commits-between-branches improveCallback
```

### 6. View Differences for Specific File
```bash
git diff copilot/compare-commits-between-branches improveCallback -- <filename>
```

### 7. Show Commits with Author and Date
```bash
git log --pretty=format:"%h - %an, %ar : %s" copilot/compare-commits-between-branches..improveCallback
```

### 8. Show Merge Base (Common Ancestor)
```bash
git merge-base copilot/compare-commits-between-branches improveCallback
git log --oneline $(git merge-base copilot/compare-commits-between-branches improveCallback)
```

### 9. Compare Specific Files Between Branches
```bash
git diff copilot/compare-commits-between-branches improveCallback -- src/MotorControlBase.h
```

### 10. View Branch Relationship
```bash
git log --all --graph --decorate --oneline
```

## Key Features in improveCallback Branch

Based on the commit history, the `improveCallback` branch includes:

1. **Callback Improvements**: Enhanced callback functionality, especially for RotateControl
2. **Bug Fixes**: Multiple critical bug fixes including:
   - Speed override restart issues
   - Uint32_t overflow for large speed/acceleration values
   - Motor stopping issues
   - First pulse timing issues for STM32F4
3. **Platform Support**: Enhanced STM32F4 support
4. **Performance Optimizations**: Improved motor group speed optimization
5. **Version Updates**: Multiple version bumps (v2.1.0, v2.2.0, v2.3.0, v2.3.1, v2.3.2)
6. **Code Quality**: Fixed compatibility issues with modern compilers (GCC9+)

## Recommendation

The `improveCallback` branch appears to be a mature development branch with significant improvements and bug fixes. It contains 279 commits of work including:
- Critical bug fixes
- New features (callback functionality)
- Platform support enhancements
- Performance improvements
- Version releases

If you need to merge or rebase these changes, consider using:

```bash
# To merge improveCallback into current branch
git merge improveCallback

# Or to rebase current branch onto improveCallback
git rebase improveCallback
```

**Note**: Given the significant divergence (279 commits), merging or rebasing may require careful conflict resolution.

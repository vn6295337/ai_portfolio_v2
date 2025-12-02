# Subtree Duplication Fix

## Problem
`ai-models-discoverer_v3` repository contained entire `ai_portfolio_v2` structure (nested directories, all sub-projects).

## Root Cause
Incorrect subtree initialization pushed parent portfolio content instead of subdirectory content.

## Solution
1. Created clean repo with only pipeline content
2. Force pushed to `ai-models-discoverer_v3` remote
3. Re-established subtree sync

## Status

| Subtree | Remote | Duplication | Sync Status |
|---------|--------|-------------|-------------|
| ai-land | https://github.com/vn6295337/ai-land.git | None | ✓ Working |
| askme_v2 | https://github.com/vn6295337/askme_v2.git | None | ✓ Working |
| intelligent-model-selector | https://github.com/vn6295337/intelligent-model-selector.git | None | ✓ Working |
| ai-models-discoverer_v3 | https://github.com/vn6295337/ai-models-discoverer_v3.git | Fixed | ✓ Working |

## Commands

**Push to subtree:**
```bash
git subtree push --prefix=<directory> <remote-name> main
```

**Pull from subtree:**
```bash
git subtree pull --prefix=<directory> <remote-name> main --squash
```

**Example:**
```bash
git subtree push --prefix=ai-models-discoverer_v3 ai-models main
git subtree pull --prefix=ai-models-discoverer_v3 ai-models main --squash
```

## Remotes

```
ai-land     → ai-land/
ai-models   → ai-models-discoverer_v3/
askme       → askme_v2/
intelligent-model-selector → intelligent-model-selector/
```

---
Fixed: 2025-12-02

# Some useful command to work on this repo

## 1. Keep `main` Branch in Sync with the Upstream Repository

```bash
git fetch upstream
git checkout main  # Ensure on the main branch
git merge upstream/main  # Merge the latest upstream changes
git push origin main  # Push the updates to fork on GitHub
```

## 2. Create a Separate Branch for Your Changes

Create new feature branch:
```bash
git checkout -b working-branch
```

Make your changes and commit:
```bash
git add .
git commit -m "New Work Update"
```

Push changes:
```bash
git push origin working-branch
```

## 3. Keep the Working Branch Updated

If the upstream repository gets new changes after started working, we should rebase the branch onto the updated main:

```bash
git fetch upstream
git checkout main
git merge upstream/main  # Ensure main is up to date
git checkout working-branch
git rebase main  # Reapply your changes on top of the latest main
```

If conflicts occur, Git will prompt to resolve them manually.

Then, push the updated branch:
```bash
git push origin my-feature-branch --force  # Use --force for rebasing
```
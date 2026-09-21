# Crew Sync Workflow

## Task 1 — Push from Clone A

In Clone A, checked out `feature/overtime-pay`, added time-and-a-half overtime pay for shifts over 8 hours, committed the change, and pushed it successfully.

![Task 1](screenshots/task1.png)

## Task 2 — Diverge from Clone B

In Clone B, changed `calculatePay` to round shift pay instead of truncating it. The push was rejected because Clone B had not fetched Clone A's changes.

![Task 2](screenshots/task2.png)

## Task 3 — Reconcile with a Merge

Fetched the remote changes in Clone B and merged `feature/overtime-pay`. Resolved the conflict in `calculatePay` so the overtime and rounding behaviors were reconciled. Tests passed and the merged branch was pushed successfully.

![Task 3 Conflict](screenshots/task3-conflict.png)

![Task 3 Push](screenshots/task3-push.png)

## Task 4 — Diverge Again and Rebase

In Clone A, made another change to `calculatePay` without fetching first. The push was rejected. Fetched the remote branch, rebased onto it, resolved the conflict, verified the tests passed, and pushed the rebased branch without using force.

![Task 4 Rejected Push](screenshots/task4-rejectedpush.png)

![Task 4 Rebase Conflict](screenshots/task4-rebaseconflict.png)

![Task 4 Resolution and Successful Push](screenshots/task4-resolution-and-successful-push.png)

## Task 5 — Merge into Main

Merged the completed `feature/overtime-pay` branch into `main` and pushed `main` successfully.

![Task 5](screenshots/task5.png)

## Task 6 — Tag and Document

Created the `v1.0-synced` tag and pushed the tag to GitHub. The GitHub repository page shows the `v1.0-synced` tag.

![Task 6](screenshots/task6.png)

## Written Answers

### 1. What did the rejected push error message tell you, and why did it happen?

The rejected push error told me that the remote branch contained changes that were not in my local branch. The push was rejected because my local branch was behind the remote branch, so Git required me to first fetch and reconcile the remote changes before pushing my own changes.

### 2. What's the actual difference between how you resolved Task 3 (merge) vs Task 4 (rebase)?

In Task 3, I used a merge to combine the remote changes with my local changes. This preserved both lines of development and created a merge commit. In Task 4, I used a rebase to move my local commit on top of the updated remote branch. This rewrote the local commit's position in history and resulted in a more linear history.

### 3. What one habit would have avoided both rejected pushes in this lab?

The one habit that would have avoided both rejected pushes is fetching or pulling the latest changes from the remote branch before starting work and pushing changes.

### 4. Which approach - merge or rebase - would you default to on a shared team branch, and why?

I would default to merge on a shared team branch because it preserves the existing shared history and does not rewrite commits that other teammates may already have.


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


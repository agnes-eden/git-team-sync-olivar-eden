# Git Team Sync Workflow

## 1. What did the rejected push error say, and why did it happen?

The rejected push showed a **non-fast-forward** or **fetch first** error. It happened because the remote `feature/loyalty-points` branch contained commits that were not yet in my local branch. Another clone had already pushed changes to the same branch, so Git rejected my push to prevent overwriting the remote work.

## 2. What is the difference between the Task 3 merge and Task 4 rebase?

In Task 3, I used **merge** to combine the changes from the remote branch with my local changes. This created a merge commit and required me to manually resolve a conflict in `orders.js`.

In Task 4, I used **rebase** to replay my local commit on top of the updated remote branch. This also produced a conflict in `orders.js`, which I resolved before continuing the rebase. Unlike the merge, the rebase created a new commit with a new commit ID and kept the feature branch history linear.

## 3. What is one habit that would avoid both rejected pushes?

One useful habit is to **fetch and check the remote branch before starting work or pushing**, especially when multiple team members are working on the same branch. This helps me see whether someone else has already pushed changes and allows me to integrate their work before pushing my own.

## 4. Which approach would you use by default on a shared team branch, and why?

For a shared team branch, I would generally use **merge** when integrating changes because it preserves the existing commit history and does not rewrite commits that other team members may already have. Rebase can be useful for cleaning up personal or private branch history, but rewriting shared history can cause problems for other developers.

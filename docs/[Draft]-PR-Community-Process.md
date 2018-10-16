This page defines to process for a pull request lifecycle on Terasology. Especially when a PR should be merged or closed.

## 1. When to merge
A PR can be merged by everyone with merge permissions (list at the end of the page) given the following conditions are met:
1. reviewed by at least two contributors and approved
2. passes all tests (green build / GooeyHub success notification in the comments)
3. No outstanding requested changes

## 2. What if not enough reviewers?
A PR which seems ready to be merged but does not have enough approvals may be merged with a delay of 14 days:
1. Request a review from two people from the list at the end of the page (personal choice depending on the PR topic)
2. Announce the upcoming merge in a comment like > "I will merge this PR in two weeks"
3. 14 Days later, given no other activity/feedback occured, the PR may be merged

## 3. Exceptions: Huge PRs, API breaking, Global architecture decisions
For large PRs or potential API breaking changes, request a review from cervator to test the PR in the all-module-workspace. The 14 days-rule for inactivity does still apply, slow progress with some breaking changes is preferable to no progress ;)

## 4. When to close a PR
A PR can be closed if:
1. The creator announces that he does not continue the PR. In this case the PR should be closed and linked to an issue if someone else wants to continue the work.
2. If it became inactive for more than 14 days and is not merge-ready. In this case it may be closed after three months:
    1. Announce the upcoming close in a comment like > "I will close this PR in three months as it seems inactive"
    2. After 3 months of inactivity after the comment, the PR can be closed without a second warning

Alternative for point 2, above:
- If it is inactive for more than 2 months and is not merge-ready: 
  - announce the upcoming closure in a comment: "I will close this PR in 72 hours as it has been inactive for two months." 
  - after 3 days of further inactivity the PR can be closed without additional warnings. 

***
## People with merge permissions
Name | Permissions
--- | ---
cervator | global
manu3d | global
... | ...

Permissions: 
* _global_ (MovingBlocks & Terasology)
* _modules_ (Terasology only)
* _/module name/_ (Single module permissions)
# Git branching strategy

We will have two long-lived git branches, `master` and `development`.

`master` will continuously deploy to our staging environment.

`development` will continuously deploy to our development environment.

We have a development and staging environment as an Azure AppService.

## Starting new work

When someone begins new work, they cut a new branch from `development` and name it after their work, perhaps `feature1`.  New changes are pushed to the feature branch origin (DevOps) often. CI is configured to build all pull-requests (PRs) but new commits to `feature1` will not trigger a new build.

## Merging to `development`

When new work is complete, we set up a Pull Request (PR) from `feature1` to `development`. Discussion about, and approval of changes happens in the PR interface in DevOps.

Once this new work is approved we close the PR, which merges the code. From here, our CI pipeline will build the new changes on the `development` branch.  Next, our CD pipeline will deploy the new work to our development environment.

## Merging to `master`

Once a new body of work is merged to `development` (likely via multiple PRs) and any manual QA work has finished in the development environment, we set up a PR from `development` to `master`.

This constitutes a new production release candidate.  Any last-minute discussion, as well as approval happens in the PR interface. Once approved and merged, CI runs for `master`. Finally, CD runs and deploys the `master` branch to the staging environment.

## Race conditions on merges to development

Imagine two PRs called A and B are open against the `development` branch. The two PRs both change code in the same file. Now, we merge PR A to development.  After this merge PR B will report that it is "unmergeable" in DevOps.  This is because `development` contains the changes from PR A, but PR B does not contain those changes -- git doesn't know what to do.

In this case we have a couple options.

1. Rebase: `git rebase B_branch development`.  Rebasing the branch replays all of the commits from B on top of the _new_ `development` branch (which now contains changes from A). Rebasing is the preferred method for handling these issues.  Push the `B_branch` and you'll be able to use DevOps to close the PR.
2. Manual conflict resolution. Instead of using the DevOps UI to merge the PR, execute the merge locally. `git checkout development && git merge B_branch`. Git will report merge conflicts, which you can resolve locally, manually, using your editor.  When you're done push the `development` branch and DevOps will automatically close the open PR.

## Patching production/master

Imagine that many PRs have been merged to `development`, and you find a problem in production that needs a quick fix. At this point `development` has moved far past `master`.  In this case we code the fix to production in a new branch cut from `master`, maybe called `prod_fix`. We set up a PR against `master` for review and discussion.

Any QA or manual testing will take place in a one-off environment deployed from the `prod_fix` branch; with the Azure PaaS we could manually deploy to an empty Deployment Slot. Once the PR on `master` is merged CI/CD takes care of deployment to the production environment.

Now we have to bring those new changes in master back into development.  We use rebase again: `git rebase development master`.

## Incorporating fixes into a Release Pull Request

A Release Pull Request is a PR that is set up from a "frozen" branch, usually to `master`.

The code in a PR may need to be updated to pass a build, or to incorporate feedback, or for some other reason.

After our PR code looks good, we need to `cherry-pick` these changes back into our development stream.

Here are steps that cut a new Release branch from master, make some changes, then re-incorporate those changes into the development stream.

```
git checkout development
git pull
git checkout -branch sprint-1-release
git push

# At this point, set up a PR from `sprint-1-release` -> `master` in DevOps.
# Problems were found in the `sprint-1-release` branch, so you made fixes, added, committed, and pushed them to `sprint-1-release`

git log
#From the log output, gather the commit SHAs for any changes that you made.  Let's say we have two, `SHA1` and `SHA2`

git checkout development
git cherry-pick SHA1
git cherry-pick SHA2
git push
```
Now, you have pulled two specific commits from the release branch, and applied them to the development stream.

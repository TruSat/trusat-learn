---
id: contributing
title: Contributing Code
sidebar_label: Contributing Code
---

The core maintainers of the TruSat [codebase](https://github.com/trusat) very much welcome contributions, especially those that tackle [open issues](https://github.com/trusat/trusat-frontend/issues)! If you wish to contribute, either open an issue then make a [pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) or make a pull request against a currently open issue. We also invite you to join the [TruSat Discord Server](https://discord.gg/SC76Wph) to engage in real-time conversation around the development needs of TruSat.

## Catching bugs / Requesting features

If you find a bug when using TruSat please let us know! If you are familiar with GitHub you can help by opening an issue (making sure to label it as a `bug`). Similarly if you have a new feature that you like to see added to TruSat then open an issue, explain the feature and add the label `enhancement`

## Branch naming convention

TruSat maintainers use the following branch naming convention when using [Git](https://en.wikipedia.org/wiki/Git):

- `master` - The production environment
- `dev` - The branch used for deploying to the development/staging server environment
- `feature/{name-of-feature}` - A feature branch
- `bugfix/{name-of-bug-being-fixed}` - Fixing a bug larger in scope than a hotfix
- `hotfix/{name-of-hotfix}` - Hotfix changes for production issues (branches off master)
- `chore/{summary-of-chore}` - Cleaning up / organizing the code
- `wip/{name-of-wip}` - Branched out for some “work in progress” stuff (not ready, can be experimental and you want to keep a remote copy)

And here are some examples of branch names:

- `feature/single-iod-form`
- `feature/single-iod-form-styles`
- `bugfix/whitepaper-not-rendering-on-ipad`
- `hotfix/typo-on-welcome-page`
- `chore/removing-unused-imports`
- `wip/add-3box-for-authentication`

## Branch creation to opening a PR

- In command line, checkout the development branch of the repository you have just cloned (named “dev”) with `git checkout dev` then `git pull` to ensure you have the latest development branch on your local machine
- Referencing the branch naming convention outlined above determine the group and name for your branch then run `git checkout -b {group}/{name-of-group}` to create the new branch and check it out.
- Commit early and commit often with clear and concise comments. All commits should remain focused in scope so try to avoid submitting PR's that contain unrelated commits.
- Run `git push --set-upstream origin <your-new-branch>` to add your new branch to the remote repo when you feel the work completed warrants a back up.
- When ready to open a PR, use `git push` to add all your latest commits to the remote copy.
- Do not open a PR without directing it to an open issue on GitHub. If an issue does not exist, create it and add a label. Here's an example:


    The "How To" page content is out of date when compared to the latest communication content found in the TruSat discuss forum

- When ready click the green "New pull request" button on the "Pull requests" page for the repo on GitHub, making sure you are requesting to merge your branch into the development branch, and not master. The only branches that can open a PR to the “master” branch are those grouped as “hotfix” or “dev”.
- Assign at least one reviewer to your PR.
- Add detailed comments to outline what your PR achieves and make sure to reference the issue that will be closed by this PR by utilizing the issue number. Bulleted lists are preferred. For example:


    - Updates the “how to” view with the latest comms content
    - New styles added including a change of font to the headers which matches the latest changes to the "About" page.
    - This closes #32.

- Do not open the PR if there are merge conflicts found. Instead - push a fix to your branch that clears the conflicts.
- If no merge conflicts are found, open the PR.

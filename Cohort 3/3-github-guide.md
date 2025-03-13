# GitHub Guide

Open-source projects are collaborative software projects where the source code is publicly available, allowing anyone to contribute. This detailed guide is for those new to open-source contributions.

&#x1F4CC; If you are a confident contributor, feel free to do it your own way, but please follow our naming convention.

During the cohort, you will work with two repositories, each corresponding to a local folder on your machine: the **WiEP repository**, which is used for progress tracking, and the **Ethereum Client repository**, for those who challenge themselves by solving issues.

- [Contributing to the WiEP Repository](#contributing-to-the-wiep-repository)
- [Contributing to Ethereum Clients](#contributing-to-ethereum-clients)
- [Advanced Git Techniques](#advanced-git-techniques)
- [Resources](#resources)

## Contributing to the WiEP Repository

### 1. Fork, Clone, and Set Up Upstream

Log into your GitHub account, go to the [WiEP repository](https://github.com/wiepteam/studygroup.git) and fork it by pressing the `Fork` button. After forking, you'll see a copy of the repository in your GitHub account under **Your Repositories**. Clone it to your local machine using the CLI. Add the upstream for the original WiEP repository:

```bash
git clone https://github.com/<YOUR-GITHUB-ACCOUNT>/studygroup.git
cd wiep-studygroup
git remote add upstream https://github.com/wiepteam/studygroup.git
```

You can verify the added remotes using:

```bash
git remote -v
```

The output should be like:

```bash
origin  https://github.com/your-github-account/wiep-studygroup.git (fetch)
origin  https://github.com/your-github-account/wiep-studygroup.git (push)
upstream        https://github.com/wiepteam/studygroup.git (fetch)
upstream        https://github.com/wiepteam/studygroup.git (push)
```

### 2. Create a New Branch

For each new week of assignments, create a new branch named `cohort-3-week-#` (replace # with the current week number):

```bash
git checkout -b cohort-3-week-#
```

### 3. Make Your Changes, Commit and Push

Find your name in the progress table and make the necessary changes in your row as required by the home assignment.

&#x2757; **Important:** Only modify your row to prevent merge conflicts. Avoid unnecessary formatting changes (e.g., extra spaces, new lines).

Stage your changes, commit with a clear message following the week number, and push your branch:

```bash
git add .
git commit -m "Add week # assignment"
git push -u origin cohort-3-week-#
```

### 4. Open a Pull Request

Go to your forked WiEP repository on GitHub. Open a Pull Request by clicking `Compare & pull request`.

#### Select repositories:

- **Base Repository**: wiepteam/studygroup  
- **Base Branch**: main  
- **Head Repository**: your-github-account/wiep-studygroup  
- **Head Branch**: cohort-3-week-# 

For the title, use this template: `YOUR-NAME: Cohort 3 Week #`.

In the description, add the current agenda issue number, for example: `Issue #123`. All agenda issues are in the [Sessions Tracker](./1-sessions-tracker.md).

Then, on the next screen, click `Create pull request` to finalize it.

Actively monitor your open PR. You will normally receive email notifications for any updates, comments, or requested changes. If reviewer feedback is provided, simply make your changes, add new commits, and push them again like in [Step 3](#3-make-your-changes-commit-and-push) until your PR is merged.

&#x1F4CC; When your PR is open and you need to make changes in the code, simply edit your files, commit, and push again. Your updates will automatically be added to the same PR until it is closed or merged.

Congratulations! You've successfully made your first open-source contribution to the **WiEP** repository! &#x1F389;

### 5. Weekly Updates: Syncing with Upstream and Making New Contributions

At the start of each new week (after your previous PR merges), update your local main to get all the latest changes:

```bash
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```

&#x1F4CC; You may have to resolve conflicts after the merge. Conflict resolution depends on your IDE. To master merge, watch [this video](https://www.youtube.com/watch?v=Sqsz1-o7nXk&t=373s). You can also look for guides specific to your IDE or reach out to us on [Discord](https://discord.gg/JvEVfKBY6W) for support.

Now, repeat steps [2](#2-create-a-new-branch) to [4](#4-open-a-pull-request), from creating a new branch to opening a pull request, for your weekly contribution.

## Contributing to Ethereum Clients

When working on Ethereum client projects, you will address specific issues. For each issue, create a new branch and pull request.

### 1. Refer to the Client’s Contributor Documentation

Follow the contributor documentation for the client you are working on:

- **[Besu Contributor Guide](https://lf-hyperledger.atlassian.net/wiki/spaces/BESU/pages/22154241/First+contribution)**
- **[Lodestar Contributor Guide](https://chainsafe.github.io/lodestar/contribution/getting-started)**
- **[Prysm Contributor Guide](https://github.com/prysmaticlabs/prysm/blob/develop/CONTRIBUTING.md)**

### 2. Fork, Clone, and Create a Branch for Each Issue

Fork the Ethereum client repository.
Clone your forked copy locally using the CLI.
Add the upstream for the original client repository:

```bash
git clone https://github.com/your-github-account/client-repo.git
cd client-repo
git remote add upstream https://github.com/client-github-account/client-repo.git
```

Create a new branch for the issue using the pattern `issue-#`:

```bash
git checkout -b issue-123
```

### 3. Implement Your Fix or Feature, Commit and Push

Make the necessary changes.
Stage and commit your changes with a clear message. Check the project’s naming conventions and use the following template as a guideline.
Push your branch to your fork:

```bash
git add .
git commit -m "Add your comment"
git push origin issue-123
```

### 4. Open a Pull Request

Open a pull request using the Client PR template. Fill in all required fields as outlined in the template.

&#x2757; **Important:** Don't forget to sign the CLA by pressing the `CLA not signed yet` button in PR comments from the CLA assistant.

If you are not sure about your code, open the pull request in **Draft mode**. To do this, select `Create draft pull request` from the drop-down menu when opening the PR. In the PR comments, address any questions you have for the reviewer. Feel free to tag a reviewer or a mentor using `@github-name`. After receiving reviewer feedback, change your code, commit and push again to update the PR, or proceed with the discussion until everything is clear. Once your code is ready, click `Ready for review` to convert it to an open PR and request a review.

Actively monitor your open PR. If reviewer feedback is provided, simply make your changes, add new commits, and push them again. Use PR comments, the client's Discord contributor channel, or the [WiEP Discord](https://discord.com/invite/JvEVfKBY6W) study-group channel to progress and reach your goal.

Your goal is to get your PR merged. Once it’s merged, congratulations—you’ve successfully contributed to the Ethereum Protocol! 🎉

## Advanced Git Techniques

For more complex projects, there are advanced Git techniques that can help streamline your workflow. Some examples include:

- [Git Stash](https://youtu.be/BSLzA8oCT7g?si=wNd5gT2fLb8EUSck) allows you to temporarily save changes that are not yet ready to be committed, without losing work. This is useful when you need to switch branches or update your working directory but don’t want to commit unfinished changes.

- [Rebase](https://www.youtube.com/watch?v=qZDF7EPiS0g) allows you to integrate changes from one branch into another by moving or combining a sequence of commits to a new base commit. This technique is useful for maintaining a clean, linear commit history. However, it can rewrite commit history, so use it with caution.

- [Cherry-pick](https://www.youtube.com/watch?v=i657Bg_HAWI) lets you select specific commits from one branch and apply them to another branch. This is particularly useful when you want to apply a bug fix or feature to a different branch without merging the entire branch.

In addition to using the Git command line interface, you can take advantage of visual tools such as the [Source Control panel in VSCode](https://code.visualstudio.com/docs/editor/versioncontrol) and [GitHub Desktop](https://desktop.github.com/), or other Git GUI clients. These tools provide a more visual representation of your repository's history and changes, which can be especially helpful when working on complex projects.

To learn more about these techniques, we encourage you to investigate and practice them in a safe environment (such as a test repository). For additional support or if you have questions about advanced Git workflows, reach out on [WiEP Discord server](https://discord.com/invite/JvEVfKBY6W).

## Resources

- [Github blog](https://github.blog/developer-skills/github/)

- [Github: Pull requests documentation](https://docs.github.com/en/pull-requests)

- [Beginners guide to github: Creating pull request](https://github.blog/developer-skills/github/beginners-guide-to-github-creating-a-pull-request/)

- [Youtube series: Git &#x00B7; Definitive Guides](https://youtube.com/playlist?list=PLfU9XN7w4tFzW200TaCP1W9RTE8jRSHU5&si=VZOYptfAQglrrEl6)

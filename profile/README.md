# Process Handbook
## Collaboration
We use GitHub as the principal collaboration platform for software development projects. Try to put all your ideas, queries, concerns here. 

In addition to GitHub, we prefer @teams over voice call. Send a request to talent@droplet.ink for being invited to the channel.

## Issues and Request for Requirement 
| ⚠️ Please note |
|-|
|All the changes in dev branch must come through **Pull Requests created by developers** to keep track of changes. Please do not upload any file in the `dev` branch directly. **Additional files can be added to Issues or comments by attaching the file in the description, not directly into the repository.** <p><p> Additionally, we generally try to avoid uploading executable files in the source code repository directly. Executable files are **created through build** from source code, so **only** source code should be kept in the repository.|

# Guidelines for capturing video while reporting an issue.
## Download -> Installation -> Configuration
1. Download recommended screen recording software from [here](https://bandicam.com/downloads)
2. Install the software
3. Change the default settings for optimal video sharing in github as shown in the following images
  - Before your changes settings are as below:
    ![bandicam-installation-default](https://github.com/NevaehTechPMO/Calcutta-high-Court/assets/7395474/9ace3b03-9a91-414b-bd4c-908b56d0b662)
  - After your changes settings should be as below:
    ![bandicam-installation-after-changes](https://github.com/NevaehTechPMO/Calcutta-high-Court/assets/7395474/9911be7b-a6df-409b-a3f5-fa303e3907a9)
## Recording the video while reporting issues:
1. Always start with Apps' home screen. It ensures that developers can reference the version of target App for the issue.
2. Record all the steps necessary for reproducing the issue
3. Hover your mouse on the part of the UI where attention is required by the developers to understand the issue.
## Mentions steps as per the Issue Reporting Template
1. Add the steps as per the `issue reporting template` in writing so that the video and the steps can be correlated by the developer trying to fix the issue.
2. Take backup of the `database`, `zip` it and add it in the issue so that developers can reproduce accurately
3. And of course try to mention any other related information that you may think useful

> The developers at Nevaeh just wanted to thank you for taking the time to keep us informed so well. We know you’ve got a full workload going and we wanted to share with you a browser app that has helped us tremendously (BIG time saver)! Check out [Grammarly](https://www.grammarly.com/browser). It helps to autocorrect spelling, punctuation and even synonyms instantly, so you can keep being awesome as always and save a bit of time. Thanks again to all of you for contributing!!!


> To express your idea harness the power of **Markdown**. **Markdown** has simple syntax to format your writing. Spend some time in learning it. Be assured that your time won't be wasted. It will allow you to communicate more expressively. [Check it out](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). **Markdown** is 🚀

# Developer's Handbook
1. Any feature/bug to be addressed should be clearly written down in an issue first. It gives all the stakeholders to have a common understanding of what's expected when the work is done.
2. For new feature development write in with small, manageable development parts. Issues should be treated as `functions` in computer science; meant to do one thing and one thing well. An issue trying to address too many things often results in `code smell`
3. Always create [Pull Request(PR)](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) to resolve issue, never directly push in main branch.
   1. First, create a branch from an issue following [this](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-a-branch-for-an-issue).
   2. Checkout the branch locally with `git fetch; git switch <new-branch-name>`.
   3. Commit and push your changes to the new branch.
   4. Compare branches and create PR following [this](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
   5. Push all subsequent commits for that issue to the PR branch
   6. When you have successfully fixed the issue, add a video to demonstrate the fix.
   7. When done, assign a reviewer to the PR, after PR is approved by the reviewer, the PR can be merged to the main branch, squashing all the changes together in a single commit.

   Exception to this rule is only applicable for initial commits of a repository to create a reasonable base. For example, when creating a new repository there may be a few commits to bring the code in stable state. After that, always use PR to resolve issues.
4. There is one **default** branch in a repository from which the software is released. Always create a new branch from the **default** branch.
  1. Sync with the **default** branch of the repository. And sync often.
  2. Keep logical completions in separate commits.
  3. Commit with clear and meaningful commit messages.
[Here's](https://gist.github.com/luismts/495d982e8c5b1a0ced4a57cf3d93cf60) a good starting point in your journey with git.

|⚠️ Default Branch|
|-|
| Default branch can have different names based on the repository you are using. E. g., **main**, **dev** etc. Check your repositories' default branch before creating branches and syncing |
3. Following are some typical use cases of git
    - Cloning a repository
   ```console
      git clone <repository> 
      git submodule --init --recursive
   ```
   > **_NOTE:_** `git submdoule --init -recursive` is necessary if there's a submodule in a repository. However, do it to avoid confusing error messages during compilation if one exists, and you forgot to initialize the submodule.

    - Syncing with the **default** branch
    
    ```console
       git pull origin <dev> 
    ```
    > **_NOTE:_** Where `dev` is the respositories' default branch
4. A day in the life of programmer from source code management point of view. The scenario is as follows
   > You are working on an issue. You have downloaded the repository, made changes to the source code and tested it locally. It seems to meet the expected behavior and has passed all necessary test cases. It's time that you update the source code in your `remote` `git` repository.
   ```console
   git add -u
   git commit -m "<Changes defined in clear and concise message>"
   git pull origin <default branch>
   git submodule update --init --recursive
   git push
   ```
   > `git add -u` - Stages all the changed files for commit
   > 
   > `git commit -m "<Changes defined in clear and concise message>"` - Commits the changes in your local repository. Change the commit message reflecting the changes you've done in this commit.
   > 
   > `git pull origin <default branch>` - Sync with default branch of your repository
   > 
   > `git submodule update --init --recursive` - Sync submodules (if one exists) for the repository.
   > 
   > **_NOTE_**: You should always build your source after this. There's always a possibility that changes by somebody else might interfere with your portion of change, leaving your version of the code broken. If that happens you need to fix it locally. Also you should test your code and verify whether it yields different results than you expected. If so happens, fix it and then start all over again.
   > 
   > `git push` - Updates your branch to remote repository
   
   Please go through the below video or presentation for some typical cases in Git.
   [gitexplainer.webm](https://github.com/NevaehTechPMO/.github-private/assets/156404761/7aa6831a-ffee-4ab9-a4dc-bb0c6252e8b0)
   [gitexplainer.odp](https://github.com/NevaehTechPMO/.github-private/files/14786983/gitexplainer.odp)
   [gitexplainer.pptx](https://github.com/NevaehTechPMO/.github-private/files/14787088/gitexplainer.pptx)

# UI/UX (WIP)

1. Web
   - Use light background. Prefer to use [`oklch(92.8% 0.006 264.531)`] for the background. ![image](https://github.com/user-attachments/assets/15bae94e-16fd-45c9-9144-4f8b48203ff8)
   - Use [`oklch(0.202 0 162.37 / 0.85)`] for free flowing texts over default background (other than texts over `buttons` or any other `html elements`). ![image](https://github.com/user-attachments/assets/38e473df-c36a-4bc4-b8d8-505271949aa4)
   - Use [`oklch(55.61% 0.24767775297588435 276.454417954991)`] for `primary button` background color ![image](https://github.com/user-attachments/assets/810b9736-541a-4ba1-b662-4d0d1a354db2), `white` for `text color`.
   - Use [`oklch(0.5401 0.2734 29.64 / 0.649)`] for `errors and warning`. ![image](https://github.com/user-attachments/assets/f3c106c4-7c5e-463c-a3de-b491187538d3)
   - Use [JetBrains Mono](https://www.jetbrains.com/lp/mono/) for all texts.
   - Be judicious while choosing units. Read this wonderful [article](https://www.joshwcomeau.com/css/surprising-truth-about-pixels-and-accessibility/) for internalizing the concepts behind.
   - Be precise yet informative with `UI/UX writing`. Follow the principles mentioned [hre](https://ix.siemens.io/docs/language/writing-style-guide-getting-started).
   
2. Desktop
   - Always stick to `Windows` default.

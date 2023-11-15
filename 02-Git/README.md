# Git & Github

1. [What, Why and How of Git](#What-Why-and-How-of-Git)
2. [Lifecycle](#Lifecycle)
3. [Git Branching](#Git-Branching)
4. [Merging and Conflict Resolution](#Merging-and-Conflict-Resolution)
5. [Github Overview](#Github-Overview)
6. [Git remote SSH](#Git-remote-SSH)
7. [What are Github Features?](#What-are-Github-features)
8. [Github Co-pilot](#Github-Co-pilot)

---
&nbsp;
&nbsp;


## What, Why and How of Git

&nbsp;

### What is Git?

Certainly! Git is a version control system that helps you track changes in your code and collaborate with others efficiently. Let's break down the "what, why, and how" of Git.
Git is a DevOps tool used for source code management. It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.

So Git is a distributed version control system. It is a tool that helps you manage and track changes in your codebase. With Git, you can:

- **Track Changes**: Git allows you to keep a history of changes made to your code, recording each modification, addition, or deletion.
- **Collaborate**: Git enables multiple people to work on the same project simultaneously, without interfering with each other's work.
- **Branching**: Git allows you to create branches, which are like separate workspaces. This helps you develop new features or fix bugs without affecting the main project until you're ready.
- **Merging**: Git makes it easy to merge changes from different branches back into the main project.

&nbsp;

### Why use Git?

Git was created by Linus Torvalds in 2005 to address specific challenges in managing the development of the Linux kernel. The key reasons for creating Git include:

1. **Distributed Version Control:** Unlike centralized version control systems, Git is distributed, allowing each user to have a complete local copy of the repository. This decentralization enhances collaboration and provides flexibility in development workflows.

2. **Speed and Performance:** Git is designed to be fast and efficient, allowing for quick branching, merging, and version tracking. This speed is crucial for large projects like the Linux kernel.

3. **Data Integrity:** Git uses a cryptographic hash function to ensure the integrity of the data. Every change and file is checksummed, making it highly resistant to corruption.

4. **Branching and Merging:** Git provides powerful branching and merging capabilities, enabling developers to work on different features or bug fixes simultaneously without conflicts. Merging changes back into the main codebase is made easier.

5. **Open Source Collaboration:** Git facilitates collaboration in open source projects by making it easier for developers worldwide to contribute, clone repositories, and propose changes through pull requests.

6. **Offline Capabilities:** Since developers have a complete copy of the repository on their local machines, Git allows them to work offline and commit changes locally. This is particularly beneficial for developers who may not always have a reliable internet connection.

7. **Flexibility:** Git is not tied to a specific workflow and can adapt to various development methodologies. This flexibility has contributed to its widespread adoption in diverse software development projects.

In summary, Git was created to provide a robust, distributed version control system that addresses the specific needs of large and collaborative software development projects, with a focus on speed, data integrity, and flexibility.


&nbsp;

> Now it comes to how to use Git? Let's explore it in the Lifecyle.

&nbsp;

## Lifecyle

&nbsp;

Let;s get started on using Git:

### Download git

This link has details on how to install Git in multiple operating systems:
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

Verify if Git is installed by using the following command in the command prompt:

```bash
 git --version
 ```

Now it's time to create local Git Repository:

In your computer, create a folder for your project. Let's call this project folder "Test"

Go into this project folder, right click within the folder and select '''Open Git bash here" and add a local Git repository to the project using the following command.

```bash
git init
```

The ```git init``` command adds a local Git repository to the project, we also call it initialization of a Git repo.

&nbsp;

### Staging and Committing the code


Committing is the process in which the code is added to the ***local repository***. Before committing the code, it has to be in the ***staging area***. The staging area is there to keep track of all the files which are to be committed.

Any file which is not added to the staging area will not be committed. This gives the developer control over which files need to be committed.

**Staging**

Use the following command for staging the file:

```bash
git add demo.txt
```
```
In case you want to add multiple files you can use:

```bash
git add file1 file2 file3
```

If you want to add all the files inside your project folder to the staging area, use the following command:

```bash
git add .
```

Use this carefully since it adds all the files and folders in your project to the staging area.


**Committing**
Use the following command to commit the file:

```bash
git commit -m "Initial Commit"
```

“Initial Commit” is the commit message here. Enter a relevant commit message to indicate what code changes were done in that particular commit.

### Git Status and Git Log

Now modify the ```demo.txt``` file and add the following snippet:

```bash 
Initial Content Adding more Content
```

**Status**

Use ```git status``` to find out information regarding what files are modified and what files are there in the staging area — it shows other information as well, which we can ignore for now.

Use the following command to see the status:

```bash
git status
```

The status shows that ```demo.txt``` is modified and is not yet in the staging area.

Now let us add ```demo.txt``` to the staging area and commit it using the following commands:

```bash
git add demo.txt git commit -m "demo.txt file is modified"
```

**Log**

Use ```git log``` to print out all the commits which have been done up until now.

The command used for this is:
```bash
git log
```

The log shows the author of each commit, the date of the commit, and the commit message.

&nbsp;

### about remote repositories

A remote URL is Git's fancy way of saying "the place where your code is stored." That URL could be your repository on GitHub, or another user's fork, or even on a completely different server.

You can only push to two types of URL addresses:

- An HTTPS URL like https://github.com/user/repo.git
- An SSH URL, like git@github.com:user/repo.git

Git associates a remote URL with a name, and your default remote is usually called origin.

&nbsp;

### Creating remote repositories

You can use the ```git remote add``` command to match a remote URL with a name. For example, you'd type the following in the command line:


```bash
git remote add origin <REMOTE_URL>
```

This associates the name <mark>origin</mark> with the <mark>REMOTE_URL</mark>.

&nbsp;

### Cloning with HTTPS URLs

The <mark>https://</mark> clone URLs are available on all repositories, regardless of visibility. <mark>https://</mark> clone URLs work even if you are behind a firewall or proxy.

When you <mark>git clone</mark>, <mark>git fetch</mark>, <mark>git pull</mark>, or <mark>git push</mark> to a remote repository using HTTPS URLs on the command line, Git will ask for your GitHub username and password. When Git prompts you for your password, enter your personal access token. Alternatively, you can use a credential helper like [Git Credential Manager](https://github.com/git-ecosystem/git-credential-manager/blob/main/README.md). Password-based authentication for Git has been removed in favor of more secure authentication methods. For more information, see "Managing your personal access tokens."

&nbsp;

### Cloning with SSH URLs

SSH URLs provide access to a Git repository via SSH, a secure protocol. To use these URLs, you must generate an SSH keypair on your computer and add the public key to your account on GitHub.com. For more information, see "[Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)."


When you <mark>git clone</mark>, <mark>git fetch</mark>, <mark>git pull</mark>, or <mark>git push</mark> to a remote repository using SSH URLs, you'll be prompted for a password and must provide your SSH key passphrase. For more information, see "[Working with SSH key passphrases](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases)."

&nbsp;

## Git Branching

&nbsp;

Up until now we have not created any branch in Git. By default, Git commits go into the master branch.

### What is a branch?

A branch is nothing but a pointer to the latest commit in the Git repository. So currently our master branch is a pointer to the second commit “demo.txt file is modified”.

**Why are multiple branches needed?**

Multiple branches are needed to support multiple parallel developments. Refer the image below to see how branches work.


![Git branches](./images/branches.jpg)


Initially, commit 1 and commit 2 were done in the master branch. After commit 2 a new Branch called as “Test” is created, and commit 3 and commit 4 are added to the test branch.

At the same time, a different commit 3 and commit 4 are added to the master branch. Here we can see that after Commit 2, two parallel developments are being done in 2 separate branches.

The Test Branch and the Master Branch have diverged here and have different code — the code from Test Branch can be merged with the Master branch using ```git merge```. This will be covered later.

**Create a New Branch in Local**

Create a new branch called test using the following command:

```bash
git branch test
```
This command creates the ```test``` branch.


We are still in the context of the master branch. In order to switch to the ```test``` branch. use the following command:

```bash
git checkout test
```

Now we are in the ```test``` branch.

You can list out all the branches in local using the following command:

```bash
git branch
```

**Do Some Commits in the New Branch**

Modify ```demo.txt``` by adding the following snippet:

```bash
Initial Content Adding more Content Adding some Content from test Branch
```

Now stage and commit using the following commands:

```bash
git add demo.txt git commit -m "Test Branch Commit"
```

This commit was done in the Test Branch, and now Test Branch is ahead of Master Branch by 1 commit — as the test branch also includes the 2 commits from the master branch.

You can verify the commit history in Test Branch using:

```bash
git log
```
&nbsp;

## Merging and Conflict Resolution

&nbsp;

### Basic Merging

Currently, Test Branch is ahead of the Master by 1 commit. Let’s say that now we want all the code in the Test Branch to be brought back to the Master Branch. This is where git merge is very useful.


In order to merge the code from the test branch into the master branch, follow these steps:


First go back to the master/main branch:

```bash
git checkout main
```

Then run the <mark>merge</mark> command:

```bash
git merge test
```

After running these 2 commands, the merge should be successful. In this example, there are no conflicts.

But in real projects, there will be conflicts when a merge is being done. Resolving the conflict is something which comes with experience, so as you work more with Git you will be able to get the hang of resolving conflicts.

Run <mark>git log</mark> now and you will notice that the master also has 3 commits.

&nbsp;

### Conflicts and Resolution

Occasionally, this process doesn’t go smoothly. If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly. If your fix for issue #53 modified the same part of a file as the hotfix branch, you’ll get a merge conflict that looks something like this:

```bash
$ git merge test
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```


>A git merge conflict is an event that takes place when Git is unable to automatically resolve differences in code between two commits. Git can merge the changes automatically only if the commits are on different lines or branches.



![Git branches](./images/merge-conflict.jpg)


Git hasn’t automatically created a new merge commit. It has paused the process while you resolve the conflict. If you want to see which files are unmerged at any point after a merge conflict, you can run <mark>git status</mark>:

```bash
$ git status
On branch main
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

    both modified:      index.html

no changes added to commit (use "git add" and/or "git commit -a")

```

Anything that has merge conflicts and hasn’t been resolved is listed as unmerged. Git adds standard conflict-resolution markers to the files that have conflicts, so you can open them manually and resolve those conflicts. Your file contains a section that looks something like this:

```bash
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> iss53:index.html

```

This means the version in <mark>HEAD</mark> (your <mark>main</mark> branch, because that was what you had checked out when you ran your merge command) is the top part of that block (everything above the =======), while the version in your <mark>test</mark> branch looks like everything in the bottom part. In order to resolve the conflict, you have to either choose one side or the other or merge the contents yourself. For instance, you might resolve this conflict by replacing the entire block with this:

```bash
<div id="footer">
please contact us at email.support@github.com
</div>

```

This resolution has a little of each section, and the <mark><<<<<<<, =======</mark>, and <mark>>>>>>>></mark> lines have been completely removed. After you’ve resolved each of these sections in each conflicted file, run git add on each file to mark it as resolved. Staging the file marks it as resolved in Git.

If you want to use a graphical tool to resolve these issues, you can run <mark>git mergetool</mark>, which fires up an appropriate visual merge tool and walks you through the conflicts:

```bash
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc3 codecompare vimdiff emerge
Merging:
index.html

Normal merge conflict for 'index.html':
  {local}: modified file
  {remote}: modified file
Hit return to start merge resolution tool (opendiff):

```

If you want to use a merge tool other than the default (Git chose <mark>opendiff</mark> in this case because the command was run on macOS), you can see all the supported tools listed at the top after “one of the following tools.” Just type the name of the tool you’d rather use.

After you exit the merge tool, Git asks you if the merge was successful. If you tell the script that it was, it stages the file to mark it as resolved for you. You can run <mark>git status</mark> again to verify that all conflicts have been resolved:


```bash
$ git status
On branch main
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:

    modified:   index.html

```

If you’re happy with that, and you verify that everything that had conflicts has been staged, you can type <mark>git commit</mark> to finalize the merge commit. The commit message by default looks something like this:

```bash
Merge branch 'test'

Conflicts:
    index.html
#
# It looks like you may be committing a merge.
# If this is not correct, please remove the file
#	.git/MERGE_HEAD
# and try again.


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# All conflicts fixed but you are still merging.
#
# Changes to be committed:
#	modified:   index.html
```

If you think it would be helpful to others looking at this merge in the future, you can modify this commit message with details about how you resolved the merge and explain why you did the changes you made if these are not obvious.

&nbsp;

### Branching Strategies

So in essence, Git branching strategy allows developers to collaborate on a project while also tracking changes and maintaining multiple versions. 

There are several Git branching strategies available, i.e. Trunk-Based Development, Feature Branching, Git Flow each with its own set of advantages and disadvantages. The best strategy is determined by the project’s and team’s unique requirements. We’ll go over three popular Git branching strategies:

1. Trunk-based Development Branching

Trunk-Based Development is a Git branching strategy that emphasizes frequent integration and testing on the main branch to ensure a high level of collaboration and continuous delivery.

&nbsp;

![Trunk-based branching](./images/trunk-based-branching.png)

&nbsp;

2. Feature Branching

Feature Branching is a Git branching strategy that involves creating separate branches for individual features or changes to allow for isolation, testing, and review before merging into the main branch.

&nbsp;

![Feature branching](./images/feature-branching.png)

&nbsp;


3. Git Flow Branching

Git Flow is a Git branching model that builds on Feature Branching by adding additional branches for managing releases and hotfixes, providing a structured approach for managing different types of changes in larger teams or more complex projects.

&nbsp;

![Git Flow branching](./images/git-flow-branching.png)

&nbsp;


## Github Overview

&nbsp;

### What is GitHub?

&nbsp;

At a high level, GitHub is a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code. To understand exactly what GitHub is, you need to know two connected principles:

- Version control
- Git

So, in easy words, GitHub is a for-profit company that offers a cloud-based Git repository hosting service. Essentially, it makes it a lot easier for individuals and teams to use Git for version control and collaboration.

GitHub’s interface is user-friendly enough so even novice coders can take advantage of Git. Without GitHub, using Git generally requires a bit more technical savvy and use of the command line.

GitHub is so user-friendly, though, that some people even use GitHub to manage other types of projects – like writing books.

Additionally, anyone can sign up and host a public code repository for free, which makes GitHub especially popular with open-source projects.

As a company, GitHub makes money by selling hosted private code repositories, as well as other business-focused plans that make it easier for organizations to manage team members and security. We utilize Github extensively at Kinsta to manage and develop internal projects.

&nbsp;

### How does Github work?

&nbsp;

GitHub users create accounts, upload files, and create coding projects. But the real work of GitHub happens when users begin to collaborate.


While anyone can code independently, teams of people build most development projects. Sometimes these teams are all in one place at once time, but more often they work asynchronously. There are many challenges to creating collaborative projects with distributed teams. GitHub makes this process much simpler in a few different ways.

First, all the code and documentation are in one place. This limits issues with access for anyone who wants to contribute to a project. Each repository also contains instructions and other details to help outline project goals and rules.

Next, coding is more creative and abstract than most non-technical people think it is. For example, say two devs are working on different pieces of code. These two pieces of code should work together. But sometimes one piece of code can make the other code fail. Or a piece of code can have an unexpected impact on how the other code works.

GitHub solves these problems by showing how both files will change the main branch. It catches these errors before pushing changes, making the coding process more efficient.

GitHub also makes it easier to track changes and go back to previous versions of a project. 

&nbsp;

## What are Github's Features?

&nbsp;

GitHub is a web-based platform built on top of Git, providing additional features and services to enhance collaboration, code management, and project coordination. Here are some key features of GitHub:

1. **Repository Hosting:**
   - **Git Repositories:** GitHub hosts Git repositories, making it easy for developers to manage and collaborate on their codebase.
   - **Remote Access:** Users can clone repositories to their local machines, make changes, and push those changes back to the remote repository.

2. **Collaboration:**
   - **Issues:** GitHub provides an issue tracking system to report bugs, suggest features, or discuss any aspect of the project. Issues can be assigned, labeled, and commented on.
   - **Pull Requests:** Developers can propose changes to a repository by submitting pull requests. This allows others to review, comment, and suggest modifications before merging the changes into the main codebase.

3. **Branching and Merging:**
   - **Branches:** GitHub supports branching, allowing developers to work on features or fixes in isolation without affecting the main codebase.
   - **Merging:** Once changes are ready, they can be merged back into the main branch through pull requests.

4. **Collaborative Coding:**
   - **Code Review:** GitHub facilitates code review with inline comments and discussions. Changes can be reviewed by team members before merging.
   - **Blame:** Developers can use the blame view to see who made each change in a file, providing accountability.

5. **Automation:**
   - **Actions:** GitHub Actions allows for the automation of workflows, such as running tests, building and deploying applications, and other custom processes triggered by events.

6. **Documentation:**
   - **Wiki:** GitHub provides a wiki for each repository, allowing teams to create and maintain project documentation.
   - **README Files:** Repositories often contain README files in Markdown format, providing information about the project, its purpose, and how to get started.

7. **Community and Social Features:**
   - **Forks:** Users can fork repositories to create their copy. This is often used for contributing to projects or experimenting with changes.
   - **Stars and Watches:** Users can "star" repositories to bookmark them, and "watch" to receive notifications about changes and discussions.

8. **Security:**
   - **Security Alerts:** GitHub can alert repository owners about known vulnerabilities in their dependencies.
   - **Branch Protection:** Users can configure branch protection rules to prevent direct pushes to specific branches, ensuring code quality.

9. **Integration:**
   - **Third-Party Integrations:** GitHub integrates with various third-party tools and services, such as continuous integration services, project management tools, and more.

GitHub's features make it a powerful platform for collaborative software development, providing tools to streamline workflows, enhance communication, and ensure code quality and security.

&nbsp;

### Git vs Github

&nbsp;

![Git vs Github](./images/git-vs-github.png)

&nbsp;

## Github Copilot

&nbsp;

### Copilot

&nbsp;

GitHub Copilot is an AI pair programmer. You can use GitHub Copilot to get suggestions for whole lines or entire functions right inside your editor.

![Github Copilot](./images/github-copilot.png)

It can suggest complete lines of code or entire functions by analysing how you code. GitHub Copilot can assemble code from user comments and predicts your code by just reading the function name you have declared. It allows you to cycle through alternative suggestions and manually edit the suggested code. It autofill repetitive code, or create unit tests for your methods.


The GitHub Copilot editor extension sends your comments and code to the GitHub Copilot service, which then uses OpenAI Codex to synthesize and suggest code. it actually works by reading through all the open-source code on the GitHub repos worldwide and then collect the data and tries to find the best possible code related to it! It is said to work great with repetitive code patterns so users can let it generate the rest of the code. The AI assistant can also help you learn a new programming language.

&nbsp;

### GitHub Copilot Working:

&nbsp;

1. **AI Model:**
GitHub Copilot is powered by Codex, a language model based on OpenAI's GPT-3 architecture. Codex has been trained on a diverse range of publicly available code from various programming languages.

2. **Integration:**
It is integrated into Visual Studio Code, a popular source-code editor, making it accessible to a broad community of developers.

3. **Code Suggestions:**
GitHub Copilot offers real-time code suggestions as developers’ type. It provides completions for entire lines or blocks of code, aiming to predict what the developer intends to write based on the context of the code.

4. **Multilingual Support:**
GitHub Copilot supports multiple programming languages, allowing developers to work in languages like Python, JavaScript, TypeScript, Java, C++, and more

5. **Learning from Context:**
The tool learns from the context of the code being written and from the patterns it has identified in the large dataset it was trained on. It adapts to the specific coding style and preferences of the developer

6. **User Feedback:**
GitHub Copilot encourages developers to provide feedback on its suggestions. Users can submit feedback about the accuracy and usefulness of the suggested code, helping improve the model over time

&nbsp;

### Benefits:

&nbsp;

1. **Productivity:**
GitHub Copilot aims to boost developer productivity by reducing the time spent on routine coding tasks. It can generate boilerplate code and handle repetitive sections, allowing developers to focus on more complex and creative aspects of their work

2. **Learning Aid:**
It serves as a learning aid, helping developers understand different coding patterns and styles. Developers can learn from the suggestions and gain insights into best practices

3. **Efficient Collaboration:**
GitHub Copilot can facilitate collaboration by providing consistent code suggestions across a team. This can lead to more standardized and maintainable codebases

&nbsp;

### Concerns and Considerations:

&nbsp;

1. **Accuracy:**
While GitHub Copilot is powerful, it might not always provide accurate or secure code. Developers need to review and test the suggestions thoroughly

2. **License and Copyright Issues:**
Developers should be mindful of licensing and copyright issues when using code suggestions from GitHub Copilot, as the generated code might be based on various open-source projects

3. **Dependency on Internet Connection:**
GitHub Copilot relies on an internet connection to access the Codex model, which could be a consideration for developers working in environments with restricted internet access

GitHub Copilot has generated significant interest in the developer community due to its potential to reshape coding workflows. However, developers should use it judiciously and be aware of its capabilities and limitations

&nbsp;

---
&nbsp;
## Previous topic: [Linux](https://github.com/rise2innovate/DevOps/blob/main/01-Linux/README.md)     |     Next topic: [Ansible](https://github.com/rise2innovate/DevOps/blob/main/03-Ansible/README.md)
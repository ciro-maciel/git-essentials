# Git Essential

Welcome to the **Git Essential** repository! Here, we’ll explore the foundational concepts and key commands of Git, one of the most popular and powerful tools for version control.

## What is Git?

Git is a distributed version control system created in [2005](https://github.com/git/git/commit/e83c5163316f89bfbde7d9ab23ca2e25604af290) by [**Linus Torvalds**](https://github.com/torvalds) the same developer behind the Linux kernel. The need for a secure, fast, and reliable version control system arose during the development of Linux itself. Git quickly gained prominence for its innovative features and the security it offers for handling change history.

## What is Git used for?

Git allows developers to track all changes made to a project’s code, making it easier to collaborate and integrate changes from different contributors. In addition to storing and managing different versions, Git provides tools to:

- Create independent branches for new features
- Merge changes across branches
- Store snapshots of code progress (commits)
- Revert changes and access the full project history

This versatility is essential for collaborative development and efficient code management.

## How to Use Git Simply

Getting started with Git can seem complex, but a few essential commands cover most needs:

- **Install Git**: [Git Downloads](https://git-scm.com/downloads)
- **Configure Git** (username and email):

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "youremail@example.com"
   ```


## Essential Command Guide

- **`git clone repository-url-from-github`**: Clones a remote repository from GitHub to your local environment.

- **`git init`**: Initializes a new Git repository in the current directory.

- **`git add .`**: Adds all files and changes in the current directory to the staging area, preparing them for the commit.

- **`git commit -m "commit message"`**: Records the changes in the staging area with a descriptive message about what was modified.

- **`git branch -M main`**: Renames the current branch to "main". The `-M` option forces the rename, moving the branch if necessary.

- **`git remote add origin https://github.com/username/repository-name.git`**: Adds a remote repository to the local one with the name "origin". Use `https://github.com/username` to set up the remote repository via HTTPS or `git@github.com:username` for SSH.

- **`git push -u origin main`**: Sends the commits on the "main" branch to the "origin" remote repository, setting "main" as the default branch for future push and pull commands. The `-u` option sets the upstream to simplify future push and pull commands.

- **`git remote add origin git@github.com:username/project.git` `git branch -M main` `git push -u origin main`**: To connect a local repository to a remote repository on GitHub. Adds the remote repository, renames the main branch to "main," and pushes the initial commits.

- **`git fetch`**: Fetches updates from the remote repository without merging them into the current branch, updating remote references.

- **`git pull origin main`**: Updates the local "main" branch with changes from the "origin" remote repository, combining `git fetch` and `git merge`.

- **`git push --force-with-lease`**: A safer way to force-push local changes to the remote repository. It checks that no changes have been made by other collaborators, avoiding accidental overwrites.

- **`git revert id_of_commit_to_be_reverted`**: Creates a new commit that undoes the changes made by the specified commit, preserving the history. Useful for safely reversing changes without rewriting the history.

- **`git reset --hard id_of_commit_before_the_one_to_be_deleted`**: Resets the repository to the state of the specified commit, deleting all changes made after that commit. Ideal for local use. To sync remotely, follow up with `git push --force-with-lease`.

- **`git commit --amend -m "rewritten_message"`**: Changes the message of the last commit. After using this command, sync with the remote using `git push --force-with-lease`.

- **`git cherry-pick COMMIT_HASH`**: Used to retrieve a specific commit. Example: Suppose you have two branches ("main" and "develop") and want to pick just the first commit from "develop"; `cherry-pick` allows you to do this.


## Workflows

Git offers great flexibility for managing projects, especially in teams. Below, we present some of the main workflows that help organize, collaborate, and maintain code quality.

### 1. **Centralized Workflow**

This is the simplest model, where all developers work on a single branch, usually `main` or `master`. The basic steps are:

- Clone the repository
- Make changes locally
- Commit and push directly to the main branch

Ideal for: Small teams or personal projects. It's easy to manage but less suitable for large teams due to the risk of frequent conflicts.

### 2. **Feature Branch Workflow**

In this model, each new feature or bug fix is developed in a separate branch, known as a “feature branch.” The sequence is:

- Create a new branch for the feature or bug fix (`git checkout -b feature-name`)
- Work on the branch and commit regularly
- When the feature is ready, merge it into the main branch (or submit it as a Pull Request)

Advantages:
- Keeps the main branch stable
- Allows parallel work on multiple features

Ideal for: Medium to large teams, where each member can work on different features without interrupting others' work.

### 3. **Gitflow Workflow**

**Gitflow** is a more comprehensive and structured workflow model, ideal for large projects with defined release cycles. It uses different branches to manage features, releases, and fixes:

- `main`: Contains the code of the latest released version
- `develop`: Development branch where new features are integrated
- **Feature branches**: Created from `develop` to work on new features
- **Release branches**: Created from `develop` to prepare for a new release
- **Hotfix branches**: Created from `main` to fix critical bugs in the production version

This model allows for a well-organized workflow, ideal for projects requiring stability and a defined release process.

### 4. **Forking Workflow**

Widely used in open-source projects, the Forking Workflow allows contributors to work on a copy of the original repository:

- **Fork** the repository to create a copy in your account
- Work on changes in your own copy
- Submit changes to the original repository via a Pull Request

This model promotes collaboration without affecting the main repository and facilitates code review before any merge.

Ideal for: Open-source projects and external contributions.

### 5. **Trunk-Based Development Workflow**

In Trunk-Based Development, developers make frequent commits directly to a central branch, typically `main`, and integrate small changes as quickly as possible. This approach emphasizes:

- Frequent commits and quick integrations
- Minimizing long-lived branches
- Fast and constant code reviews

It is a workflow that favors agile teams and continuous delivery (CI/CD) environments.

Ideal for: Teams following DevOps practices who need high delivery speed.

### How to Choose the Best Workflow?

Choosing a workflow depends on factors such as team size, project complexity, and release frequency. Experiment with different approaches to find the one that best suits your needs. Practicing and adapting workflows will help your team gain efficiency and maintain a clean and organized code history.


## Common Terms

- **`fork`**: A copy of a repository to your own GitHub account, creating a new repository in your account that is independent of the original. This allows you to make changes without affecting the original repository.

- **`issues`**: A tool used to manage tasks, feature requests, and bug fixes in open-source projects, allowing collaborators to discuss and track progress.

- **`pull request`**: A mechanism to submit proposed changes to the original repository. A pull request is a request for project maintainers to review and potentially merge the changes. It goes through a review process and may be accepted or rejected.

## About the Author

This repository was created and is maintained by **Ciro Cesar Maciel**. I am a Software Engineer passionate about creating efficient and well-documented solutions. I am always looking for new tools and practices that can simplify and improve the development workflow.

In addition to this project, I have been working on other interesting projects related to automation, Artificial Intelligence (AI), browser extensions, and more. I am also beginning to teach what is necessary to learn Artificial Intelligence (AI), helping others to get started on their AI journey.

If you are interested in Software Development, Data Science, AI, or other tech topics, feel free to explore my GitHub profile and connect with me.

### How to Find Me:

- GitHub: [ciro-maciel](https://github.com/ciro-maciel)
- LinkedIn: [Ciro Cesar Maciel](https://www.linkedin.com/in/ciro-maciel/)
- Website: [ciro-maciel](https://www.ciro-maciel.click)

I am always open to new collaborations and projects. If you have an interesting idea or just want to exchange thoughts about development, don't hesitate to reach out!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

<!-- omit from toc -->
# Source Control with Git

Source control, also known as version control or revision control, is a software management practice that involves tracking and managing changes to a set of files, typically used in software development but also applicable to various other disciplines, such as networking.

The primary goal of source control is to keep track of the history of changes made to files and to enable collaboration among multiple contributors.

[GitHub](https://github.com/) is a platform that incorporates source control as one of its core features. GitHub is built around the concept of Git, which is a distributed version control system.

<!-- omit from toc -->
## Content

- [Terminology](#terminology)
  - [Branch](#branch)
- [Getting Started with Git](#getting-started-with-git)
  - [Prerequisites](#prerequisites)
  - [Install Git](#install-git)
  - [Establish Git Config](#establish-git-config)
  - [Establishing Connection to Source Control](#establishing-connection-to-source-control)
- [Execution](#execution)
  - [Establish a New, Local Directory](#establish-a-new-local-directory)
  - [Set Branch to 'Main'](#set-branch-to-main)
  - [Tagging](#tagging)
- [Quick Command Reference](#quick-command-reference)
- [References](#references)

## Terminology

| Term | Description |
|----------|----------|
| SCM                    | Source Control Management |
| Source Control         | Environment where shared code/files live. (i.e. GitHub)
| Gist                   | Source Control Library of snippets or micro-blogs. |
| Project                | Source Control Library driven by a VTB to maintain clear objectives and timelines. |
| Working Directory        | Folder on your workstation where files are stored. (ex: `.git`, `README.md`) |
| Local Repository       | Cached location on your workstation where **committed** files are stored. (hidden .git folder) |
| Remote Repository      | `git remote -v` </br> This is your **source control**, where your **local repository** gets uploaded to. |
| Clone                  | `git clone <URL>` </br> Takes code from a **remote repository** and downloads it to your **working directory** (`pwd`). |
| Stage / Index / Cache  | `git add <FILE>` </br> Takes code from  **working directory** and moves it to your **local repository** so that it can be managed (**commit** and **push**). |
| Commit                 | `git commit -m "<COMMIT-MESSAGE>"` </br> Confirms and records that all changes made to the **staged**, **local repository** code is ready to be uploaded/**pushed**.
| Push                   | `git push` </br> Uploads code from the **local repository** to the **remote repository**.
| Pull                   | `git pull` </br> | Download code from **remote repository** to the **local repository**. |
| Merge                  | Taking the code from one **branch** and pushing the changes to another branch. This is initiated via "pull request."

![Git Repository](../assets/git-repository.jpg)

### Branch

- Movable location of where the code lives.
- There are typically multiple branches per repository. Here are some best-practice examples:
  - **[Master/Main]** - production ready; fully tested and bug free.
  - **[Develop]** - tested and ready to go into production (main); may require features of bug fixes.
  - **[Feature]** - new items being introduced to the into the code.
    - Release branches are comprised of multiple feature branches.
- The current, working branch can be verified via: `git branch`

![Git Branches](../assets/git-branches.png)

**[- Back to Top -](#content)**

## Getting Started with Git

### Prerequisites

- Established account on a Source Control service (i.e. Gitlab/Github).
- Visual Studio Code preinstalled on your workstation.
- If you're using a UNIX system, access to the terminal and basic understanding of commands.

### Install Git

Follow the instructions here:\
<https://git-scm.com/book/en/v2/Getting-Started-Installing-Git>

If you are installing to **Windows**, use the following recommended settings:

- Use Visual Studio Code as Git’s default editor
- Set default branch to ‘main’
- Git from command line and also from 3rd-party software
- Use OpenSSL library
- Checkout Windows-style, commit Unix-style line endings
- Use MinTTY
- Default pull behavior (fast-forward or merge)
- Git Credential Manager Core
- Enable file system caching

### Establish Git Config

1. On your workstation, open your 'user' directory:
    - `C:\Users\%USERPROFILE%` on Windows.
    - `~/` on UNIX systems.
2. Create a new file: `.gitconfig`
    - On a UNIX system this can be done on the console by typing: `nano .gitconfig`
3. Drop in the following recommended settings in to your `.gitconfig`

   ```json
   [user]
       name = <REPLACE WITH NAME>
       email = <REPLACE WITH EMAIL>
       username = <REPLACE WITH USERNAME>
   
   [core]
       editor = vim
   
   [color]
       ui = auto
   
   [color "branch"]
       current = yellow bold
       local = green bold
       remote = cyan bold
   
   [color "diff"]
       meta = yellow bold
       frag = magenta bold
       old = red bold
       new = green bold
       whitespace = red reverse
   
   [color "status"]
       added = green bold
       changed = yellow bold
       untracked = red bold
   
   [alias]
       histx = log --pretty=format:'%h %ad | %s%d [%an] ' --date=short
       hist = log --graph --oneline --decorate --all
       stat = status -s
       s = status
       trackhead = reflog
   
   [init]
       defaultBranch = main
   
   [pull]
       rebase = true
       ff = only
   
   [stash]
       showPatch = true
   ```

    - Please ensure to update the fields surrounded by open-angle brackets: `< >`
4. Save and close.

### Establishing Connection to Source Control

In order to establish a connection between **source control** and your local workstation, you'll need to exchange secure, shared keys via SSH.

- [GitHub Guide to SSH shared keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [GitLab Guide to SSH Shared keys](https://docs.gitlab.com/ee/user/ssh.html)

**[- Back to Top -](#content)**

## Execution

### Establish a New, Local Directory

1. Create a new folder on your workstation.
    - Recommendation: Name the folder something meaningful based on the scope of your code. Between words, use a dash `-` instead of a space.
2. Open up Visual Studio Code and open the folder you just created.
3. Within your folder, start by creating a New File: `README.md`
4. Jump down to the terminal (`ctrl` + `~`).
    - If available, open up the `Git Bash` profile by clicking the down-arrow next to the `+` in the terminal window.
5. In the terminal CLI, ensure you are in the desired directory (`pwd`). If not, move to the correct directory (`cd`).
6. `git --version` to confirm your install and running version.
    - If there is no result or the result is unexpected, you may need to review your Git installation.
7. `git init` to initialize your folder into a Git repository.
    - This will create a `.git/` folder within your repository. Use `ls -la` to confirm.

### Set Branch to 'Main'

If Git was installed correctly your default branch should be `main`. If this is the case, you may skip this section. Otherwise, you may execute the following commands to covert from the `master` branch to `main`:

- `git checkout -b main` to establish and move to the `main` branch.
- `git branch -d master` will delete the `master` branch.
- `git branch` will allow you to verify current/existing branches.

### Tagging

<https://git-scm.com/book/en/v2/Git-Basics-Tagging>

### Git Diff

<https://youtu.be/R25rGNWrDKc?si=CHZR6k3x2DH7OJVP>

**[- Back to Top -](#content)**

## Quick Command Reference

| Command | Description |
|----------|----------|
| `git init <PROJECT-NAME>` | Creates a new local repository with the specified argument |
| `git status` | Lists all new or modified files to be committed |
| `git config --global user.name “<USER-NAME>”` | Defines the name you want associated with your commit |transactions |
| `git config --global user. Email "<USER-EMAIL>"` | Defines the email address you want associated with your commit transactions |
| `git config --global color.ui auto` | Turns on colorization of command line output |
| `$ add [file]` | Prepares the file for commit by logically moving it to the staged area |
| `git ls-files --stage` | Lists all the files in the staged area |
| `git commit -m "<MSG>"` | Adds the staged files permanently in version history |
| `git diff` | Shows unstaged file differences |
| `git diff --staged` | Shows file differences between staging and the last file version |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git checkout <BRANCH-NAME>` | Switches to the specified branch and updates the working directory |
| `git merge <BRANCH-NAME>` | Combines the specified branch’s history into the current branch |
| `git branch -d <BRANCH-NAME>` | Deletes the specified branch |
| `git rm [file]` | Deletes the file from the working directory and the staging area |
| `git log` | Lists version history for the current branch |
| `git log --oneline` | Lists version history in one line for the current branch |
| `git log –oneline –decorate --graph` | Lists version history in one line, decorated in graphical form for the  |current branch |
| `git push <ALIAS> <BRANCH>` | Uploads all local branch commits to remote repository |
| `git pull` | Downloads from remote repository and incorporates changes |
| `git clone <URL>` | Clones an existing repository |
| `git rebase <BRANCH>` | Rebases your current HEAD onto BRANCH |
| `git stash` | Temporarily stores all modified tracked files |

**[- Back to Top -](#content)**

## References

- <https://www.cbtnuggets.com/learn/it-training/ntrdctn-src-cntrl-gt>
- <https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow>
- <https://www.devopsuniversity.org/git-tutorials-git-commands/>

---

**[- Notes / NetDevOps -](../..)**

**[- Notes / Home -](../../..)**

# Piscine git workshop notes (2024 february)

### Part I |  GitHub
If you want to take your projects home after Piscine:
- Create GitHub account
    - Go to Settings -> SSH and GPG keys
    - Get your SSH key from Shell00 ex03!
        - Even if the project is finished, you can still clone your repository from project page
        - IF that doesn't work for some reason: you can find your SSH key on computer.
            - Go to Home directory, in settings select: Show hidden files
            - Look for the folder: .ssh
            - Open id_rsa.pub (your PUBLIC key) and it is inside
    - Go back to GitHub, select New SSH key & copy it
    - Now go to "Your repositories" & select New (put settings as you want them)
    - After the repo is created, click on green button "Code" on repository page and copy the line under Local -> SSH
    - Clone your repository in terminal
    - Put all folders & files you want into local repo, then git add, commit & push
        - If you are copying from another local repository, be careful not to copy the .git folder
    - You are done!!

There is also a way to link the remote repository you created now with your local repos that are already linked to your 42 remote repos.
Like this you can select where to push. This process is a little bit more complicated but you can follow this guide by one of the 42 students:
https://github.com/francisrafal/42-connect-multiple-remotes-tutorial

(I never did this though but I'm also still not using VSCode change is scary)

_________

### Part II |  Basics of git

#### What is git?
Git is a **version control system**. It is there to help you keep track of how your code changes over time as you work on it.
It also makes collaboration easier (through branching, merging etc).

#### What is a git repository?
Simply put it is a storage place to store one specific project you are working on.
Every repository has the (hidden) directory named `.git`. This is used to store all the information about your repository, like the
content of your previous commits.
You can create a git repository by using the command: `git init`. For your 42 projects, your repositories are automatically created
for you, so you can `git clone` them from the intra.

#### Staging area
Staging area is where you put everything you changed, before you commit it. You can add things to the staging area with the command
`git add`. If you have changed (or added) something, but did not add it to the staging area, `git status` will list it below "untracked
files". Anything that is NOT in the staging area at the time of a commit will NOT be committed.
Deleting previously added files from the repo and then using `git add` will NOT delete them from the staging area. You have to use
`git rm` for this. So if, for example, you have previously did: `git add *`, then `rm a.out`, you have to `git rm a.out` too, otherwise
it will still be part of the commit.


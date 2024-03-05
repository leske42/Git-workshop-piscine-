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

*Git is very verbose. This means, most of the time when you do something, it will display a lot of text updating you about what exactly happened,
and what other things you might want to do. These messages are often colorful (red, brown, green etc). This does not mean that they are
error messages, so don't be scared if you see them, instead read them carefully.*

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

Try the following: go to one of your git repositories. Do `touch abc`, `git add abc`, `rm abc` and then check what `git status` tells you.

#### Git commit
Using `git commit` means: you ask git to make a snapshot of your project in its current state. This is a very useful
feature, since some changes you make to the code can potentially mess up your project - and then you can see where it went wrong, and even return to an old commit. You can use `git log`
to view your previous commits.

*Each commit has to include a commit message. Commit messages are very important, as later, when you look back at your commits, you will use these
to track the changes you implemented. For example, a git log that looks like this does not tell you much about what is going on:*

commit 6fde8c6fab3774390920f18bb20066725ee61cfa<br>
Author: Random Person<br>
Date: Random Date<br>
abcd second commit idk

(yes i used to commit like this until like 1/4 of common core)<br>
*it is actually fun to read back old commit messages if you have the time*

Try the following: go to one of your projects where you committed a lot. Commit all of your recent changes (if any). Use `git log` to view your previous commits.
Select one and copy the *commit hash* from the top. Use `git checkout <commit hash>` and see what changed. Use `git checkout master` (or whatever branch you were on) to return.

#### Remote repositories
Remote repositories are like this one - they are not stored locally on your computer. You can connect a local repository (that you have on your computer) with a remote one.
When you `git clone` from intra, this is exactly what happens. You create a local repository, which is already linked with a remote repository. Whenever you `git push`, you are
moving your data from local repo to the connected remote one. Anything that is NOT committed will NOT be pushed. That's why it can happen that you have your C04 project on your computer, but
when, during evaluation, you clone it from the intra, the repository appears to be empty.

If you create a new repository with `git init`, it will initially not have any remote repository connected to it. You can still do commits, but `git push` in this context makes no sense.
This is dangerous, as randominette can arrive at any time.

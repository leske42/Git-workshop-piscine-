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

## What is git?

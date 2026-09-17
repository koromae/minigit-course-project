# Homework 2 — Part 2 Submission

Student name: Mahawa Koroma

GitHub username: koromae

## 1. Git Command Observations

| Command or workflow | What did you observe? | What was the user trying to accomplish? | What problem or risk did it address? |
|---|---|---|---|
| 1. git diff -> git add -> git diff --staged | Observation: when this workflow is run, all changes made are saved and ready to be committed. Evidences are found by running git status command right after running this workflow | the user was trying to stage the changes they did on their file. | With this workflow, the student was able to compare the working tree with the staging area (git diff), stage the modification in the working tree (git add), which was verified by running the last command of this workflow(git diff -- staged) which shows the saved modifications in the staging area. |
| 2. git commit -m “...” —> git log -n 1 | Observation: after running this workflow of command, a new ID identifying a recent saved record is displayed | The user is trying to keep a permanent record of the approved changes made on the file | This workflow of command permanently recorded a snapshot of the staged changes of the file using the command “git commit -m “...” “ and verified the action by running the command “git log -n 1” which displays the commitID of the last commit recorded. |
| 3. git remote add origin -> git remote -v | Observation: a connecting is created between the local folder and a pre-created remote repository; the second command of the work flow proves the action was successful by displaying the url link of the remote repository | The user is trying to establish a smooth connection between his local repository and an online one where they will collaborate with teammates | This solved the problem of connectivity and collaboration. With this command workflow, the user was able to link the local repository with a remote repository on GitHub that his collaborator and teammate can access on Github to work and share ideas, suggestions and update codes. |
| 4. git push -u origin main -> git status | Observation : with this command workflow, we observed that the changes that were recorded locally are now available online after running “git push -u origin main”, and after running “git status” locally, all changes are confirmed to be synchronized with the online ones | The user was trying to make the recorded changes available remotely on Github so that any collaborator can access it | The command workflow addressed the problem of making files available online for a smooth and seamingless collaboration between peers and teammates. The availability and synchronization of the file online on github is confirmed by the message outputted when “git status” is run. The working tree and staging area is clean, and the file is up to date with the online version, confirming that there is no unsaved modifications left over |




## 2. User Needs


### UN-GIT-01 — Short descriptive title


> A student or teammate needs a way to check the different modifications that are being done on the file because they need to understand what has changed locally before saving a permanent record or version of the file.


### UN-GIT-02 — Short descriptive title


>  _A developper and his collaborator need a way to select and keep a permanent record of specific files because they want to preserve intentional and meaningful  records or versions of the code overtime__


### UN-GIT-03 — Short descriptive title


>  _A developer and collaborators need a way to make their  most up-to-date code available and accessible online because they want an accurate and smooth collaboration between each other while working on the file.


## 3. User Requirements


| ID and short title | User requirement | Source user need | Rationale |
|---|---|---|---|
| UR-GIT-01 |   a developer must be able to review and have a clear summary changes that have been made in the file before they permanently record a version    | UN-GIT-01 |   allow developer to review  |
| UR-GIT-02 |           a developer must be able to choose, select and keep a permanent record of their work  whenever they want to organize their changes and save them meaningfully for easy reviews      | UN-GIT-02|      Allow user to select wanted modifications to be saved together in meaningful way for easy code reviews      |
| UR-GIT-03 |   A team member (developer or collaborators) must be able to access up-to-date files, edit and share the work on the file with all teammates for a synchronized workflow      | UN-GIT-03 |    Unable all teammates  to work with and access the most up-to-date file version.       |
| UR-GIT-04 |   A developper and collaborators must be aable to download new modifications and continue working with the most up-to-date file whenever they want on their local desktop     | UN-GIT-03     |       Enable developers and collaborator to download most recents recorded and shared updates locally |



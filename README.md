# ITECT 116 - Activity Project Compilation

## Help And Guide ( Git Commands )

### Initialize repository

* **git init**
    * (one time only | Pag naka pag init kana di mo na kilangan pa ulit mag init pa).
* **git branch -m main**
    * (Change from master to main).
* **git remote add origin "--GIT REPOSITORY LINK--"**
    * (one time only | Pag naka pag remote add kana di mo na kilangan pa ulit mag remote).
 
### Retrieve Data from Github Repository

* **git pull origin main**
    * (retrieve data from git repository).
      
### Upload New Update to Github Repository

* **git add .**
    * (Add all data in folder to repository).
* **git commit -m "--COMMENT--"**
    * (Save and Add comment in file).
* **git push origin main**
    * (Upload the file to GIT repository ).
<br/>

### NOTE (FOR CONTRIBUTORS)
* Always back up your files before pulling from the repository.
    * To prevent lost of your new updates.

<br/>

## Help And Guide ( How to Run React App )

### VS Code Terminal

* **cd directory(dapat nasa loob nung file)**
    * (cd [name ng folder na gaw ni loel]).
    * ex. cd rizal-interactive-web (para pumasok sa main folder natin
    * required kung ang naka lagay sa terminal ay ( ex. PS C:\Users\PC\Desktop\rizal\>  |  dapat ay PS C:\Users\PC\Desktop\rizal\rizal-interactive-web> - nasa main folder kana )
    * para di na mag cd, pag nag open ng folder sa VS Code dapat ay i-select or pumasok ka sa folder "rizal-interactive-web" - (main folder) para rekta na PS C:\Users\PC\Desktop\rizal\rizal-interactive-web>
* **npm install**
    * (to install necessary file/folder - node_modules).
    * di kasi na pupush sa git repo yang node_modules folder
    * **npm install** ( sa unang pull ng files sa repo required iinstall )


* **npm start**
    * (to start the react app - [http://localhost:3000](http://localhost:3000) to view it in your browser.).

## GIT FEATURE

# Step 1: Initialize and set up remote and branches (if not already done)

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git init`                                  | Initialize a new Git repository locally                           |
| `git branch -m main`                        | Rename the default branch to 'main'                               |
| `git remote add origin "Link"`              | Add the remote repository URL (replace "Link" with your repo URL) |

<br>

# STEP 2: Create new branch (-b) or transfer to existing branch (main/ branch_name)

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git fetch origin`                          | Fetch latest changes from remote (list of all branches - REQUIRED) |
| `git branch`                                | To know what branch you are on (OPTIONAL)                         |
| `git checkout main`                         | Switch to main branch                                             |
| `git checkout -b new-branch-name`           | Create and switch to a new feature branch (to add new branch - NOTES: ignore this if already has exsiting branch just use "git checkout branch-name" to switch branch)                        |
| `git checkout branch-name`                  | Switch to other branch (if with existing branch)                  |
| `git status`                                | Check branch status (OPTIONAL)                                    |

<br>

# STEP 3: Pull data from repo branch to local computer 
### NOTES: Make sure local files is up-to-date from main branch before coding and pushing

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git pull origin main`                      | pull data of main to local computer                               |
| `git pull origin branch-name`               | pull data of other branch to local computer                       |

<br>

# STEP 4: Push local data to repo

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git add .`                                 | Stage all files for the initial commit                            |
| `git commit -m "Initial commit"`            | Commit the staged files with a message                            |
| `git push -u origin main`                   | Push initial commit to remote 'main' branch and set upstream tracking |

<br>

# STEP 5: Pull main to update your own branch before pushing your new upate code to own branch.


| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout your-branch-name`             | Switch to your feature branch                                     |
| `git pull origin main`                      | Update local main branch with remote changes                      |
| `git add .`                                 | Stage all files for the initial commit                            |
| `git commit -m "Initial commit"`            | Commit the staged files with a message                            |
| `git push origin your-branch-name`          | Push the branch to the remote (own branch)                        |

<br>

# STEP 6: Merge chnages to main branch (Merge data of your branch into Main branch).
### NOTES: Make sure your branch is up todate before merging to main branch. <br> After "git merge main" then switched to main branch (git checkout main). <br> Ignore this message: "'main' Your branch is behind 'origin/kana' by 2 commits, and can be fast-forwarded ". <br> After merging your own branch into main (git merge your-own-branch) and pushing, it will be automatically updated. <br> Use "git status" to double check the branch.

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout main`                         | Switch to main branch                                             |
| `git pull origin main`                      | Update main with latest remote changes                            |
| `git checkout your-branch-name`             | Switch to your feature branch your-branch                         |
| `git merge main`                            | Update your feature branch with main (optional but recommended)   |
| `git checkout main`                         | Switch to the main branch                                         |
| `git merge your-branch-name`                | Merge your feature branch into main                               |
| `git push origin main`                      | Push the updated main branch to the remote                        |
| `git status`                                | Check branch status                                               |

<br>

# STEP 7: (Optional if merging does not work in main into feature branch)

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout branch-name`                  | Switch to feature branch                                          |
| `git fetch origin`                          | Fetch latest changes from remote                                  |
| `git merge origin/main`                     | Merge main branch into feature branch                             |

<br>

# Undo merge
### If you have NOT pushed yet (This erases the merge commit locally.)

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout main`                         | Switch to main branch                                             |
| `git log`                                   | Find the commit hash before merge                                 |
| `git reset --hard <commit-hash>`            | reset the ongoing merging process                                 |

<br>

### If you have ALREADY pushed to remote

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout main`                         | Switch to main branch                                             |
| `git log --oneline`                         | Find the merge commit hash: (**the latest commit should say "Merge branch 'your-branch-name'"**)                                      |
| `git revert -m 1 <merge-commit-hash>`       | Revert the merge (ex> "**a1b2c3d Merge branch 'other_branch'**" = **git revert -m 1 a1b2c3d**). This creates a new commit that undoes the changes from the merge.                                                 |
| `git push origin main`                      | Push to remote (-m 1 tells Git to keep the history of main as the base.) |

<br>

### Forcefully go back (⚠️ risky with team)
* If you really want to erase history and reset main (not recommended if others already pulled):

| Command                                     | Description                                                       |
|---------------------------------------------|-------------------------------------------------------------------|
| `git checkout main`                         | Switch to main branch                                             |
| `git reset --hard <old-commit-hash>`        | Reset main to the exact commit before the merge (removes the merge and all commits after it). |
| `git push origin main --force`              | Force push your local main (now rolled back) to overwrite the remote main. |

## NOTES:
* Working alone → **git reset --hard** is fine.
* Working with a team → **git revert** is safer because it doesn’t rewrite history. 
<br>

# Process of git command

| New User (No existing branch)                                     | Old User (with existing branch)                                   |
|-------------------------------------------------------------------|-------------------------------------------------------------------|
| INITIALIZE LOCAL REPO (CREATE NEW BRANCH)                         | INITIALIZE LOCAL REPO (CHANGE BRANCH) - SKIP IF ALREADY DONE INITIALIZE |
|                                                                   |                                                                   |
| `git init`                                                        | `git init`                                                        |
| `git fetch origin`                                                | `git fetch origin`                                                |
| `git remote add origin "Link"`                                    | `git remote add origin "Link"`                                    |
| `git checkout -b new-branch-name`                                 | `git checkout your-branch-name`                                   |
| `git pull origin main`                                            | `git pull origin main` / `git pull origin your-branch-name`       |
|                                                                   |                                                                   |
|                                                                   |                                                                   |
| PUSH LOCAL CHANGES TO OWN BRANCH                                  | PUSH LOCAL CHANGES TO OWN BRANCH                                  |
|                                                                   |                                                                   |
| `git checkout your-branch-name`                                   | `git checkout your-branch-name`                                   |
| `git add .`                                                       | `git add .`                                                       |
| `git commit -m "Initial commit"`                                  | `git commit -m "Initial commit"`                                  |
| `git push -u origin your-branch-name`                             | `git push -u origin your-branch-name`                             |
|                                                                   |                                                                   |
| FETCH LATEST UPDATES FROM MAIN TO OWN BRANCH                      | FETCH LATEST UPDATES FROM MAIN TO OWN BRANCH                      |
|                                                                   |                                                                   |
|                                                                   |                                                                   |
| `git checkout your-branch-name`                                   | `git checkout your-branch-name`                                   |
| `git pull origin main `                                           | `git pull origin main `                                           |
| `git add .`                                                       | `git add .`                                                       |
| `git commit -m "Initial commit"`                                  | `git commit -m "Initial commit"`                                  |
| `git push origin your-branch-name`                                | `git push origin your-branch-name`                                |
|                                                                   |                                                                   |
|                                                                   |                                                                   |
| MERGE CHANGES FROM OWN BRANCH TO MAIN BRANCH                      | MERGE CHANGES FROM OWN BRANCH TO MAIN BRANCH                      |
|                                                                   |                                                                   |
| `git checkout main`                                               | `git checkout main`                                               |
| `git pull origin main`                                            | `git pull origin main`                                            |
| `git checkout your-branch-name`                                   | `git checkout your-branch-name`                                   |
| `git merge main`                                                  | `git merge main`                                                  |
| `git checkout main`                                               | `git checkout main`                                               |
| `git merge your-branch-name`                                      | `git merge your-branch-name`                                      |
| `git push origin main`                                            | `git push origin main`                                            |


<br/>
<br/>
<br/>
<br>

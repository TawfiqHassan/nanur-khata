# Nanu's Recipe Book - My Git Story

## Chapter 1: The First Recipe
Nanu said winter is coming, so I started with the bhapa pitha recipe. 

**Commands Used & Story:**
* `mkdir nanur-khata` and `cd nanur-khata`: Created the project folder and opened it.
* `git init`: Initialized the Git repository.
* `git config --global user.name` and `user.email`: Set up my Git identity.
* Created `bhapa-pitha.md` and staged it using `git add bhapa-pitha.md`.
* Nanu corrected the gur measurement. I updated the file and used diff commands to check the changes.

**Theory Answer: git diff vs git diff --staged**
* **`git diff`**: Shows the difference between the working directory and the staging area. It helps you see what changes you have made that are not yet staged.
* **`git diff --staged`**: Shows the difference between the staging area and the last commit. It lets you see exactly what will be included in your next commit.

After verifying, I committed the recipe using `git commit -m`. I accidentally staged `bazar-list.txt` along the way, but I safely unstaged it using `git reset bazar-list.txt` without deleting the actual file.

## Chapter 2: The Secret Spice
Nanu warned me that her secret spice blend must never reach GitHub. 

**Commands Used & Story:**
* Created `secret-masala.txt`, some `.tmp` files, and a `draft/` folder.
* Created a `.gitignore` file and added `secret-masala.txt`, `*.tmp`, and `draft/` rules to it.
* Ran `git status` to prove that Git is successfully ignoring these secret files.

## Chapter 3: The Eid Special
I wanted to test Eid recipes safely, so I used branches to isolate my work.

**Commands Used & Story:**
* `git branch eid-special` and `git checkout eid-special`: Created and switched to a testing branch.
* Added `biryani.md` and `shemai.md` using two separate commits.
* Switched back to `main` using `git checkout main`. The new files were not there because they were isolated in the `eid-special` branch. 
* Ran `git merge eid-special` to bring the recipes safely into the main book.

**Challenge: Creating & Resolving a Merge Conflict**
To trigger a conflict on purpose, I created a new branch `spicy-biryani` and modified `biryani.md`. Then, I went back to `main` and modified the exact same line in `biryani.md` differently. When I ran `git merge spicy-biryani`, Git stopped and threw a "Merge conflict" error because both branches changed the same file on the same line. 
**Resolution:** I opened `biryani.md`, removed the Git conflict markers, kept the final recipe text I wanted, and ran `git add biryani.md` followed by `git commit` to successfully resolve the conflict.



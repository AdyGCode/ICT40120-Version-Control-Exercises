# Session 03 Exercises

These exercises are based on content
from: https://education.launchcode.org/lchs/chapters/git/index.html

> **WINDOWS USERS**
>
> Ensure you have followed the FAQs below **BEFORE** starting
> these exercises.
>
> -
>
> **MAC & LINUX USERS**
>
> TODO: Create FAQs on setting up

In these exercises we presume you have completed the FAQs as required 
**BEFORE** starting the exercises. 


## Exercise 01 - Setting up your details for git

In this exercise you will be:

1. Open the Windows Terminal
2. Checking that git is accessible and which version is installed
3. Changing the git default branch to "main"
4. Adding your name and email to git


```shell
git --version
git config --global init.defaultBranch="main"
git config --global user.name="YOUR NAME HERE"
git config --global user.email="YOUR_STUDENT_ID@tafe.wa.edu.au"
```

Check the values are set using:

```shell
git config list
```

## Exercise 02 - Starting a repo

You will be completing these steps to create a new repository

1. Open the Windows Terminal
2. Make sure you are in your Source/Repos folder
3. Create a new folder
4. Change into the folder
5. Initialise the repository
6. Check the status of the repository

> **NB:**
> 
> Change `2025` to the current year, and `s1` to the current semester 
> (`s1`or `s2`)

---

Check the current working directory:
```shell
pwd
```
It should be shown as something similar to:

```text
/c/Users/USERNAME/Source/Repos
```

Create the new Exercises Folder, and check it exists:

```shell
mkdir git-exercises-2025-s1
ls
```
You should see a folder entry in the file listing `git-exercises-2025-s1/`

Make this new folder the working directory:

```shell
cd git-exercises-2025-s1
```
When you change into the folder you will see a prompt similar to the one 
below. Note there is no (main) at the end, so we are pretty sure this folder 
is NOT version controlled.

```text
MINGW64 ~/Source/Repos/git-exercises-2025-s1
 ```

Start the repository

```shell
git init .
```

Notice how the prompt changes and has a blue `(main)` at the end? A good 
indicator we are in a repo! 

```text
MINGW64 ~/Source/Repos/git-exercises-2025-s1 (main)
```

Check the status:

```shell
git status
```

We should see a message about being on the main branch and no commits and 
nothing to commit.

```text
On branch main
No commits yet
nothing to commit (create/copy files and use "git add" to track)
```

## Exercise 03 - Creating new "ReadMe" and ".gitignore' Files

In this exercise you will be:

1. Creating an empty `ReadMe.md` and `.gitignore` file
2. Stashing the empty files
3. Committing them to version control
4. Adding content to the `ReadMe.md` file 
5. Checking the status
6. Stashing and committing to version control
---

In the Bash CLI we can use the `touch` command to create a new empty file.

```shell
touch ReadMe.md
touch .gitignore
```

Check the files are created using:

```shell
ls -la
```

Example output from `ls -la`:

```text
total 8
drwxr-xr-x 1 USERNAME GROUP 0 Mar 28 11:20 ./
drwxr-xr-x 1 USERNAME GROUP 0 Mar 28 11:13 ../
drwxr-xr-x 1 USERNAME GROUP 0 Mar 28 11:19 .git/
-rw-r--r-- 1 USERNAME GROUP 0 Mar 28 11:20 .gitignore
-rw-r--r-- 1 USERNAME GROUP 0 Mar 28 11:20 ReadMe.md
```

Check the status:

```shell
git status
```

Example output from `git status`:

```text
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        ReadMe.md

nothing added to commit but untracked files present (use "git add" to track)
```

Add the files to stash

```shell
git add ReadMe.md
git add .gitignore
```

Check the status:

```shell
git status
```


Example output from `git status`:

```text
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   ReadMe.md
```

We are able to commit the new files using a multi-line commit message. We do 
this by **NOT** closing the `"` (quotes) until the last line of the message, 
pressing <kbd>ENTER</kbd> each time we want to start a new line.

```shell
git commit -m "init: Start of Exercises Project

- add empty ReadMe.md
- add empty .gitignore
"
```

Example output from `git commit`:

```text
[main (root-commit) 7380b2e] init: Start of Exercises Project
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .gitignore
 create mode 100644 ReadMe.md
```

Open the `ReadMe.md` file in your favourite text editor and add the 
following content to it:

```markdown
# Git Exercises

- Author:   YOUR_NAME_HERE
- Start:    YYYY-MM-DD
- Finish:   ---

## Completion list

| Session | Completed |
|---------|-----------|
| 01      | [ ]       |
| 02      | [ ]       |
| 03      | [ ]       |
| 04      | [ ]       |
| 05      | [ ]       |
| 06      | [ ]       |
| ...     | ...       |
```

Replace YYYY with the current year, MM with the month, and DD with the date.

Save the file.
Close your text editor.

```shell
git status
git add ReadMe.md
git commit -m "docs(ReadMe): Add ReadMe initial content"
git status
```


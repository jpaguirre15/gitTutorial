How to GitHub
Date: 04/24/2019


--------------------------------------------------------------------------------
Concepts of Git
  - Keeps track of code history
  - Takes "snapshots" of your files
  - You decide when to take a snapshot by making a "commit"
  - You can visit any snapshot at any time
  - You can stage files before committing

Basic commands
  - $git init			                    // Initialize Local Git Repository
  - $git add <file>                   // Add File(s) to Index
  - $git status                       // Check Status of Working Tree
  - $git commit                       // Commit Changes in Index
  - $git push                         // Push to Remote Repository
  - $git pull                         // Pull Latest From Remote Repository
  - $git clone                        // Clone Repository Into a New Directory

  - Note: $touch <file + extension>   // Creates a file


Step 1: Right Click on a Folder and Choose 'Git Bash Here'
D:\Cheat Sheets\Git\Screenshoot_Instructions\Screenshot (2).png
  - A terminal pop-up should open
  - D:\Cheat Sheets\Git\Screenshoot_Instructions\Screenshot (3).png

Step 2: Run Git Commands
  - $ git init
  - $ git config --global user.name '<insert name here>'
  - $ git config --global user.email '<insert email here>'

  - $ git add index.html  // Add to the staging area

  Notes:
  - $ git status          // Check what's in the staging area
  Output:
  On branch master

  No commits yet

  Changes to be committed:
    (use "git rm --cached <file>..." to unstage)

          new file:   index.html

  Untracked files:
    (use "git add <file>..." to include in what will be committed)

          app.js


  - $ git rm --cached index.html
  - $ git status
  Output:
  On branch master

  No commits yet

  Untracked files:
    (use "git add <file>..." to include in what will be committed)

          app.js
          index.html

  nothing added to commit but untracked files present (use "git add" to track)

  - $ git *.html   // Will add any html files

  - $ git add .    // Adds all file to the staging area

  - If any changes occur during staging...
  - '$ git status' will output:
    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)

            new file:   app.js
            new file:   index.html

    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git checkout -- <file>..." to discard changes in working directory)

            modified:   index.html

    - Meaning.. we would have to do '$ git add .  again
    - '$ git status' will now output:
      On branch master

      No commits yet

      Changes to be committed:
        (use "git rm --cached <file>..." to unstage)

              new file:   app.js
              new file:   index.html

Step 3: Commit
  - $ git commit
  - A vim editor will open.
    - To type, press 'i' to go to insert mode
  - Remove the comment on 'Initial commit'
  - esc + ':wq' + enter


.
.
.
Later on editing the app.js

Step 4: Edit + Commit
  - $ git add .
  - $ git commit m 'changed app.js' // To skip vim editing


Additional Info:
  - touch .gitignore
  - touch log.txt

Step 5: Try to add log.txt and .gitignore
  - $ git add .
  - $ git status

  - Note: Since .gitignore includes log.txt,
    - log.txt won't be added

.
.
.
Later on, adding 2 more folders called 'dir1' and 'dir2'...
Also adding files on those folders 'app1.js' and 'app2.js'...

Step 6: Try to add dir1 and dir2
  - $ git add .
  - $ git status

  - Note: since .gitignore now includes /dir2,
    - Folder dir2 and contents inside will not be added
    - Also adding for instance *.txt will withdraw all text files


  - Commit all:
    - $ git commit -m 'another change'

--------------------------------------------------------------------------------

Branches
Description: Imagine being in a team of devs. working on a project. And you're
             assigned the project of creating the log-in. Branching prevents
             the main code being edited and changed w/o finishing the
             functionality. You could create a branch called login and work in
             that branch. You could commit it but won't be commited to the main
             branch.

Step 1: Create a branch:
  - $ git branch login

  - Note: Notice that you're still on the (master) branch
    jpagu@DESKTOP-5FOOA78 MINGW64 /d/Cheat Sheets/Git/GitTest (master)

  - To change branch login, enter command:
    - $ git checkout login

.
.
.
Later on, adding a file called login.html

Step 2: Commit in the branch:
  - $ git add .
  - $ git commit -m 'login form'

  - Change back to master:
    - git checkout master
    - Note: If you change back to master branch.. you won't see the things you
            edited on the login branch! WOWZA!

Step 3: Merge
  - $ git merge login
  - vim editor opens:
    - Under 'Merge branch 'login'', put (to edit vim, press 'i'):
    - Added login
    - esc + ':wq' + enter

--------------------------------------------------------------------------------

Remote Repository
  - Go to GitHub website
  - '+' sign on upper right corner
    - D:\Cheat Sheets\Git\Screenshoot_Instructions\Screenshot (6).png

  - Fill out Repository name
  - Put a description
  - Click 'Create repository'
  - D:\Cheat Sheets\Git\Screenshoot_Instructions\Screenshot (6).png

  - Instructions will tell you what to do:
    echo "# gitTutorial" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin https://github.com/jpaguirre15/gitTutorial.git
    git push -u origin master

  - Note: Since we've done 'git init' earlier.. we don't need to do it anymore
  - Note: Adding a README.md is important for audiences to know














.

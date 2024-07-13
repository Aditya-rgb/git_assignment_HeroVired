# git_assignment_HeroVired_2

# Assignment question 1 - You are part of a development team working on a Python application called "CalculatorPlus." The application provides basic arithmetic operations, such as addition, subtraction, multiplication, and division. Your task is to implement a new feature that adds support for calculating the square root of a number.

1. Created a repository named "git_assignment_HeroVired" from the github UI. Made it in "private" mode and added a README.md file.
2. Went to my local and opened git bash. Gave the command "git clone git@github.com:Aditya-rgb/git_assignment_HeroVired.git"
3. To make the "dev" branch gave the command "git checkout -b dev"
   From git bash terminal, "vi CalculatorPlus.py", pasted the code from VLearn platoform.
   Alternatley opened VScode from git bash terminal using the command "code ."
4. Saved the code in the local dev branch.
   Then in git bash gave the following commands :
   git add .
   git commit -m "Pushing the initial code from local dev to remote dev""
   git push -u origin dev #setting the dev branch as upstream so that next time when i push anything i wont have to explicitly mention anything in my commands.

5. Went to local main branch and did "git merge dev"
   Before pushing anything from local main to remote main did this :
   git pull origin main #pulled the updates for the readme file which i am writing
   git merge dev
   git push #pushed the Version 1 release of the code.

7. Added Manish Panda as one of my colloaborators.
8. Added a feature branch feature/sqrt form the dev branch with the command "git checkout -b feature/sqrt".
   Added the square root function in the code in local and did the following commands.
   git add .
   git commit -m "Added the square root functionality to the code in feature branch."
   git push -u origin feature/sqrt #setting the feature/sqrt branch as upstream so that next time when i push anything i wont have to explicitly mention anything in my commands.

9. Found a bug in the dev branch so to fix it did the following commands :
   git checkout dev
   code .
   #made the fix
   git add .
   git commit -m "Fixed the divide bug in Dev local and now pushing to dev remote."
   git push

10. Now making sure the fix made in dev reflects in my feature branch so for that did the following :
   git checkout feature/sqrt
   git merge dev 
   git push
   
10 .Opened Github UI
    clicked on pull request
    new pull request ( main <- dev)
    created the request
    clicked on Assigness on the right and added manish panda
    Manish went to my repo, went to pull requests in his UI
    clicked on my pull request which was reflecting there
    clicked on files changed
    reviewed my code and have the appropriate comments and then clicked on Approve.
    I came to my pull request then and did the merge, closed my request
    Remote main brnach finally reflected the code as same as dev

11. Now to merge the changes from feature/sqrt to dev
     git checkout dev
     git pull origin dev # good practice
     git merge feature/sqrt
     git push
     # Now the square root functionality reflects in local dev and remote dev too.

12. Did the testing in dev in VS code, code runs good. Now as part of the question merging the latest changes intorducted in dev (square root functionality) to main
      then did this: git checkout main
                     git pull origin main #good practice
                     git merge dev
                     git push
13. Adding the release version 2!!

# git_assignment_HeroVired_2

# Assignment question 2 - For a project that deals with large binary files, integrate Git LFS (Large File Storage) to handle these files efficiently. Demonstrate how to add, commit, and push binary files to the repository, ensuring they are tracked by Git LFS correctly. Clone the repository on another machine to verify that the binary files are downloaded correctly.

# In the repository ‘git_assignment_HeroVired’, create a branch ‘lfs’. Upload any large file whose size is over ‘200mb’ and try to push this file into the repository.

1.Created a random .bin file of size 300MB.

2.Downloaded into the local machine and put it in main branch

3. Following GIT commands were executed in git bash :
   
   git checkout -b LFS # Creating a new branch LFS from MAIN branch
   
   ls -lrt
   
   ls -lrta
   
   git lfs track "*.bin" # Tracking Large Files: Identifing the large files in the LFS branch that needs to be managed by Git LFS.
   
   git status
   
   git add .
   
   git commit -m "Pushing 300mb bin file to remote"
   
   git push -u origin LFS # Pushing the large file to remote GIT branch LFS


#Clones the repo in a separate machine and put in the following commands:

  509  git clone git@github.com:Aditya-rgb/git_assignment_HeroVired.git  # Cloning my repo into another location
  510  ls -lrt
  511  cd git_assignment_HeroVired/
  512  ls -lrt
  513  git checkout LFS
  514  ls -lrta
  total 292989
  drwxr-xr-x 1 KIIT 197121         0 Jul 13 16:43 ../
  -rw-r--r-- 1 KIIT 197121       853 Jul 13 16:43 CalculatorPlus.py
  -rw-r--r-- 1 KIIT 197121        43 Jul 13 16:44 .gitattributes
  -rw-r--r-- 1 KIIT 197121      3294 Jul 13 16:44 README.md
  drwxr-xr-x 1 KIIT 197121         0 Jul 13 16:45 ./
  -rw-r--r-- 1 KIIT 197121 300000000 Jul 13 16:45 300MB.bin              # .bin file pulled from remote branch
  drwxr-xr-x 1 KIIT 197121         0 Jul 13 16:45 .git/

  515  history


# Assignment question 3 -  In this same GitHub repository, create a new branch ‘geometry-calculator’, we'll work on a simple Python program that calculates the area of a circle and the area of a rectangle. We'll use Git stash to switch between working on multiple features (calculating circle area and calculating rectangle area) without committing incomplete changes.

1. Created a branch geometry-calculator by:
   git checkout -b geometry-calculator (from main)
2. Pasted the inital code in the new repo and pushed it to remote :
   code . (Opened VS code and created a python file "GeometryCalculator.py" and pasted the inital draft)
   git add .
   git commit -m "WIP : Pushing the inital code to the remote from geometry-calculator local repo"
   git push -u origin geometry-calculator #setting the geometry-calculator branch as upstream so that next 
   time when i push anything i wont have to explicitly mention anything in my commands.
3. Created the feature branch "feature/circle-area from branch geometry-calculator
   code . # Implemented the circle area code in the code in VScode
   git status
   git stash save "WIP : Stashing the changes made in feature/circle-area" #saving the stash with a message
   git status #this shows "nothing to commit" which indicates working directory is clean.

5. Came back to geometry-calculator and created the brnach feature/rectangle-area
   git checkout geometry-calculator
   git status
   git checkout -b feature/rectangle-area #Creating new branch
   code .
   git stash save "WIP : Stashing the changes made in feature/rectangle-area" Stashing the changes made in 
   feature/rectangle-area" #saving the stash with a message
   git status #this shows "nothing to commit" which indicates working directory is clean.


7. According to the question, now will go back to feature/circle-area and push the code to git
   git checkout feature/circle-area
   ls -lrt
   git status #shows nothing to commit as we stashed away everything
   git stash list #to unstash the correct stash belonging to this branch because git stash in universal across 
   whole repository
   git stash apply stash@{1} # un stashing the changes which was made only in the circle-area branch
   code .
   git add .
   git commit -m "Un-stashed and completed the circle area code and pushing it remote now."
   git push -u origin feature/circle-area  #pushing to remote and setting the branch as upstream

8. Now doing the same with feature/rectangle-area branch
   git checkout feature/rectangle-area
   git status
   git stash apply stash@{0}
   code .
   git add .
   git commit -m "Un-stashed and completed the rectangle area code and pushing it remote now."
   git push -u origin feature/rectangle-area

Next steps involved creating 2 pull requests
I have created two pull requests into the geometry-calcualtor instead of dev and tested it there, then from geometry-calculator into main.
First, geometry-calculator <- feature/circle-area, and getting it reviewed by shubham Rajak
Second, geometry-calculator <- feature/rectangle-area, and getting it reviewed by shubham Rajak again
Now the geomtery-calculator branch has the whole code with both circle area and rectangle code snippets.

Finalt step, creating a pull request again for main branch
main <- geometry-calcultor, and getting it reviewed

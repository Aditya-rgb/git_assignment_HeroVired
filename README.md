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

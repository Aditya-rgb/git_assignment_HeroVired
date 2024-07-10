# git_assignment_HeroVired_2

Assignment question 1
1. Created a repository named "git_assignment_HeroVired" from the github UI. Made it in "private" mode and added a README.md file.
2. Went to my local and opened git bash. Gave the command "git clone git@github.com:Aditya-rgb/git_assignment_HeroVired.git"
3. To make the "dev" branch gave the command "git checkout -b dev"
   From git bash terminal, "vi CalculatorPlus.py", pasted the code from VLearn platoform.
   Alternatley opened VScode from git bash terminal using the command "code ."
4. Saved the code in the local dev branch.
   Then in git bash gave the following commands :
   git add .
   git commit -m "Commiting the changes in the dev branch for the calculator plus code"
   git push -u origin dev #setting the dev branch as upstream so that next time when i push anything i wont have to explicitly mention anything in my commands.

5. Went to local main branch and did "git merge dev"
   Before pushing anything from local main to remote main did this :
   git pull origin main #pulled the updates for the readme file which i am writing
   git push #pushed the Version 1 release of the code.

6. Added Manish Panda as one of my colloaborators.
7. Added a feature branch feature/sqrt form the dev branch with the command "git checkout -b feature/sqrt".
   Added the square root function in the code in local and did the following commands.
   git add .
   git commit -m "Added the square root functionality to the code and pushing it now to feature branch(remote)."
   git push -u origin feature/sqrt #setting the feature/sqrt branch as upstream so that next time when i push anything i wont have to explicitly mention anything in my commands.

8. Found a bug in the dev branch so to fix it did the following commands :
   git checkout dev
   code .
   #made the fix
   git add .
   git commit -m "bug fixation is in the divide function and pushing the implemented fix"
   git push

9. Now making sure the fix made in dev reflects in my feature branch so for that did the following :
   git checkout feature/sqrt
   git merge dev #Now this gave me a merge conflict error in which i did "code .", opened my VScode and accepted the incoming changes post which my conflict got resolved.
   git add .
   git commit -m "Bringing in the fix from the dev branch"
   git push
   
10 .Opened Github UI
    clicked on pull request
    new pull request ( main <- feature/branch)
    created the request
    clicked on Assigness on the right and added manish panda
    Manish went to my repo, went to pull requests in his UI
    clicked on my pull request which was reflecting there
    clicked on files changed
    reviewed my code and have the appropriate comments and then clicked on Approve.
    I came to my pull request then and did the merge closed my request
    Remote main brnach finally reflected the code as same as feature/sqrt

11. Now to merge the changes from feature/sqrt to dev
     git checkout dev
     git pull origin dev # good practice
     git merge feature/sqrt
     git push
     # Now the changes pushed form local dev to remote dev

12. Did the testing in dev in VS code, code runs good.
      then did this git checkout main
                    git pull origin main #good practice
                    git merge dev
                    git push
13. Adding the release version 2!!


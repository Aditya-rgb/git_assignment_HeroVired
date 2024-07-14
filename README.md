# git_assignment_HeroVired - 1

## Assignment Overview 
You are part of a development team working on a Python application called "CalculatorPlus." The application provides basic arithmetic operations, such as addition, subtraction, multiplication, and division. Your task is to implement a new feature that adds support for calculating the square root of a number.

## Steps Taken

1. **Repository Creation**: 
   - Created a repository named "git_assignment_HeroVired" from the GitHub UI in "private" mode and added a README.md file.

2. **Cloning the Repository**: 
   - Opened Git Bash and cloned the repository:
     ```bash
     git clone git@github.com:Aditya-rgb/git_assignment_HeroVired.git
     ```

3. **Creating a Development Branch**: 
   - Created the "dev" branch:
     ```bash
     git checkout -b dev
     ```

4. **Adding Initial Code**: 
   - Opened the code file:
     ```bash
     vi CalculatorPlus.py
     ```
   - Pasted the initial code and saved it.

5. **Committing Changes**: 
   - Added and committed the code:
     ```bash
     git add .
     git commit -m "Pushing the initial code from local dev to remote dev"
     git push -u origin dev
     ```

6. **Merging Changes**: 
   - Merged changes from the "dev" branch to the "main" branch:
     ```bash
     git checkout main
     git pull origin main
     git merge dev
     git push
     ```

7. **Collaboration**: 
   - Added Manish Panda as a collaborator.

8. **Adding a Feature Branch**: 
   - Created a feature branch for square root functionality:
     ```bash
     git checkout -b feature/sqrt
     ```
   - Added the square root function and committed:
     ```bash
     git add .
     git commit -m "Added the square root functionality to the code in feature branch."
     git push -u origin feature/sqrt
     ```

9. **Bug Fixing**: 
   - Fixed a bug in the "dev" branch:
     ```bash
     git checkout dev
     code .
     # made the fix
     git add .
     git commit -m "Fixed the divide bug in Dev local and now pushing to dev remote."
     git push
     ```

10. **Ensuring Feature Branch Update**: 
    - Merged fixes from "dev" into the "feature/sqrt" branch:
      ```bash
      git checkout feature/sqrt
      git merge dev
      git push
      ```

11. **Pull Request Process**: 
    - Created a pull request from "main" to "dev" and added reviewers.
    - Merged approved pull requests.

12. **Final Testing**: 
    - Tested the application in the "dev" branch, ensured functionality was intact, and merged changes to "main":
      ```bash
      git checkout main
      git pull origin main
      git merge dev
      git push
      ```

## Versioning
- Added release version 2.

# git_assignment_HeroVired - 2

## Assignment Overview
For a project dealing with large binary files, integrate Git LFS (Large File Storage) to handle these files efficiently. This project demonstrates how to add, commit, and push binary files to the repository, ensuring they are tracked correctly by Git LFS. Additionally, it verifies that the binary files are downloaded correctly when cloned on another machine.

## Steps Taken

1. **File Creation**: 
   - Created a random `.bin` file of size 300MB.

2. **Branch Creation**: 
   - Switched to the main branch and created a new branch `lfs`:
     ```bash
     git checkout -b LFS
     ```

3. **Tracking Large Files**: 
   - Executed the following commands to track the `.bin` files:
     ```bash
     git lfs track "*.bin" # Tracking large files with Git LFS
     git status
     ```

4. **Adding and Committing**: 
   - Added and committed the large file:
     ```bash
     git add .
     git commit -m "Pushing 300MB bin file to remote"
     git push -u origin LFS
     ```

5. **Cloning the Repository**: 
   - Cloned the repository on another machine to verify that the binary file is correctly downloaded:
     ```bash
     git clone git@github.com:Aditya-rgb/git_assignment_HeroVired.git
     ```

6. **Verifying Files**: 
   - Navigated to the cloned repository and checked the files:
     ```bash
     cd git_assignment_HeroVired/
     git checkout LFS
     ls -lrta
     ```

   - Confirmed that the 300MB binary file was pulled correctly:
     ```
     -rw-r--r-- 1 KIIT 197121 300000000 Jul 13 16:45 300MB.bin
     ```

## Conclusion
Successfully integrated Git LFS to manage large binary files within the project. The process included creating a large binary file, tracking it with Git LFS, and verifying successful download on another machine.

# git_assignment_HeroVired - 3

## Assignment Overview
In this assignment, we will create a new branch ‘geometry-calculator’ in the existing GitHub repository to develop a simple Python program that calculates the area of a circle and the area of a rectangle. We will use Git stash to switch between working on these features without committing incomplete changes.

## Steps Taken

1. **Branch Creation**:
   - Created a branch `geometry-calculator` from the main branch:
     ```bash
     git checkout -b geometry-calculator
     ```

2. **Initial Code Push**:
   - Opened VS Code and created a Python file `GeometryCalculator.py` with the initial draft of the code.
   - Added and committed the initial code to the remote `geometry-calculator` branch:
     ```bash
     code .
     git add .
     git commit -m "WIP: Pushing the initial code to the remote from geometry-calculator local repo"
     git push -u origin geometry-calculator
     ```

3. **Feature Branch for Circle Area**:
   - Created a feature branch `feature/circle-area` from `geometry-calculator`:
     ```bash
     git checkout -b feature/circle-area
     code . # Implemented the circle area code in VS Code
     git status
     git stash save "WIP: Stashing the changes made in feature/circle-area" # Saving the stash with a message
     git status # Shows "nothing to commit" indicating the working directory is clean
     ```

4. **Feature Branch for Rectangle Area**:
   - Switched back to `geometry-calculator` and created the branch `feature/rectangle-area`:
     ```bash
     git checkout geometry-calculator
     git status
     git checkout -b feature/rectangle-area
     code . # Implemented the rectangle area code in VS Code
     git stash save "WIP: Stashing the changes made in feature/rectangle-area" # Saving the stash with a message
     git status # Shows "nothing to commit" indicating the working directory is clean
     ```

5. **Unstash and Push Circle Area Code**:
   - Switched back to `feature/circle-area` and unstashed the changes:
     ```bash
     git checkout feature/circle-area
     git status # Shows nothing to commit as we stashed everything
     git stash list # To list all stashes
     git stash apply stash@{1} # Unstashing the changes made in circle-area branch
     code .
     git add .
     git commit -m "Un-stashed and completed the circle area code and pushing it remote now."
     git push -u origin feature/circle-area
     ```

6. **Unstash and Push Rectangle Area Code**:
   - Switched to `feature/rectangle-area` and unstashed the changes:
     ```bash
     git checkout feature/rectangle-area
     git status
     git stash apply stash@{0} # Unstashing the changes made in rectangle-area branch
     code .
     git add .
     git commit -m "Un-stashed and completed the rectangle area code and pushing it remote now."
     git push -u origin feature/rectangle-area
     ```

7. **Creating Pull Requests**:
   - Created two pull requests into the `geometry-calculator` branch for testing:
     1. `geometry-calculator <- feature/circle-area`, reviewed by Shubham Rajak
     2. `geometry-calculator <- feature/rectangle-area`, reviewed by Shubham Rajak

   - The `geometry-calculator` branch now contains the complete code for both circle area and rectangle area calculations.

8. **Final Pull Request to Main**:
   - Created a pull request to merge `geometry-calculator` into `main`:
     ```bash
     main <- geometry-calculator, reviewed and merged.
     ```

## Conclusion
Successfully implemented the calculation of the area of a circle and rectangle in the Python program using Git stash for switching between features. The code was reviewed, tested, and merged into the main branch.


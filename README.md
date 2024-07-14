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

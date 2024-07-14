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

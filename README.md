# git_assignment_HeroVired_2

# Assignment question 2
# For a project that deals with large binary files, integrate Git LFS (Large File Storage) to handle these files efficiently. Demonstrate how to add, commit, and push binary files to the repository, ensuring they are tracked by Git LFS correctly. Clone the repository on another machine to verify that the binary files are downloaded correctly.

# In the repository ‘git_assignment_HeroVired’, create a branch ‘lfs’. Upload any large file whose size is over ‘200mb’ and try to push this file into the repository.

1.Created a random .bin file of size 300MB.
2.Downloaded into the local machine and put it in main branch
3. Following GIT commands were executed in git bash : 
  523  git checkout -b LFS # Creating a new branch LFS from MAIN branch
  524  ls -lrt
  525  ls -lrta
  526  git lfs track "*.bin" # Tracking Large Files: Identifing the large files in the LFS branch that needs to be managed by Git LFS.
  527  git status
  528  git add .
  529  git commit -m "Pushing 300mb bin file to remote"
  530  git push -u origin LFS # Pushing the large file to remote GIT branch LFS


#Clones the repo in a separate machine and put in the following commands
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

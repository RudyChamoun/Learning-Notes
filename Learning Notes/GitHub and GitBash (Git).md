
## Description
This file contains the instructions and functionalities of working on development on github

## Key Concepts

- Repository : On github you have your online repository that contains the different files used when working on the project.

- Collaborators : There are many collaborators on the same project (Rudy and Elio).

- Working on local repository : I can link my online repository to be stored locally[using gitbash], I can then modify then files using any IDE i would like (VSCode...)

## Individual Project

- It's worth noting that directly modifying the main branch is a common practice,
 especially for smaller projects or personal repositories.
 
 - Instructions for GitBash :
	1. Navigate to local directory containing local repository : cd
    2. Create file on current local directory : touch 
    3. Modify to my need the code in this file (using VScode)
    4. Add all the changes to the staging area : git add "filename.ext"
    5. Save changes made to this file :git commit -m "Name of Change"
    6. Upload local repository content to a remote repository (Github) git push
    
## Collaborative Project

- In collaborative projects or larger teams, it's often recommended to work on separate 
 branches for new features or bug fixes and then merge those branches into main once the changes are reviewed and approved.

### Key Concepts For Collaborative Project

- Working on Files (*branch*) : When modifying the files in my repository, it is a good practice to create a branch (copy of the repository) so that the actual code is not affected directly.

- Working on Files (*pull request/merge*) :When I have finished modifying the code, in order to save the changes to my repository, I file for a "pull request" (used to review code on the branch before modifying the main branch) and then we "merge" the changes to the main branch.

-  Instructions for GitBash :
        1. Navigate to local directory where I want to store the cloned repository : cd
        2. Once in the directory, Clone the repository : git clone https://github.com/username/repository.git
        3. Create a new branch from the main : git checkout -b my-feature-branch
        3. Modify to my need the code in this file (using VScode)
        4. Make your changes on this new branch and follow the steps for adding, committing, and pushing your changes.
        5. Once your changes are ready, you can create a pull request on GitHub to merge your changes from my-feature-branch into main. 
        
This allows other contributors to review your changes before they're merged into the main branch.

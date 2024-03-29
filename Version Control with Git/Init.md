
# :memo: Git

keypoints:
- A commit is a snapshot of the project in time, and the collection of commits contains the project's history.
- Branches allow independent teams to work on the project at once at scale , Master branch is the default branch
- A branch can be created to work on a version of the project that other branches do not know about.
- After merge ,the Master branch contains new features
- Pull requests are requests to merge your branch into other branch, A pull request is a request
  for others to review and approve the changes made to the project on a branch.
  ***Continuous Improvements - Commits***
  ***Simultaneous Stability and Development - Branches***
  ***Improved Quality - Pull Requests***
  - Repository : Project History
  - Each user has a local repository, containing the project history as a collection of commits.
  - Git : Distributed Version Control System
  - Git Repo : A series of Snapshots, or commits.
- Working Tree : a single commit's directories and files.
- Staging Area / Index : contains a list of files that are to be committed next.
- Local Repository : Contains the commits of the projects
- Remote Repository : Contains the commits of the projects
- /.git : contains the staging area and the local repository
***Project directory includes the staging area, working tree and a .git directory. The .git directory contains the local repository.***
- ls -a : list all hidden directories
-  Git status to view the status of files in the working tree and staging area.
- touch filename : to create a file
-  git add : to add content to the staging area. (git add . : to stage all the files)
- To modify file contents : echo "Arjun Sharma" > arjun.txt
- Commit : git commit -m "initial commit" 
- Committed Logs - git log --oneline -#
- If local repo exists : use git add to add the remote
- If local repo does not exists : use git clone to add the remote
- git clone : used to create a local copy of a remote repository
- git remote -v(verbose) : displays info about the remote repositories associated with the local repositories.
- If you already have a local repository with commits that you want to push to a remote repository,
   you can use the git remote add command. This command add's information about the remote repository to the local repository.
- git remote add origin1 https://github.com/rjrockzz/All-Of-Git.git  :  GitHub URL is associated with an alias named origin1.
- A Branch is an independent line of development
- git push : writes commits for a branch to a remote repository
- Git push synchronizes the branches on the local and remote repositories so that they contain exactly the same commits. 
 - The set upstream, or -u option, is used to set up a tracking relationship between your local branch and the corresponding
    remote branch. Git can then inform you when the branches are out of sync.
- Git models the relationship of commits with the directed acyclic graph. The entire graph contains a project's history.
  Each node in Git represents a commit. The arrows point at a commit's parents.
  - A merge occurs when a commit has more than one parent.
  - Commit points to the parent
*   Git Objects - 
      1. commit object is a simple text file that contains information
      such as the commit user information, commit message, a reference 
      to the commit's parent or parents, and a reference to the root tree
      of the project. That information is all that Git needs to rebuild 
      he full contents of a commit. 
      
      2. An annotated tag is a reference to a specific commit. 
      
      3. A tree is an object that contains a list of the filenames 
      and directories inside of a directory. 
      
      4. A blob is an object that stores the content of a file that is being 
      managed by Git.
     
-  A Git ID is the name of a Git object. All of the objects stored by Git are named with a 40-character hexadecimal string.
- Git IDs are SHA - 1 : Secure Hash Algorithms - 1
- C:\Users\RJ\repos\myproject
- A Git object's name is also known as its Git ID.
- Commits can be associated with references. A reference is a user-friendly name that points to a commit's SHA-1
  value or another reference. If a reference points to another reference, it's called a symbolic reference.
- A branch label points to the most recent commit in the branch. That commit is commonly called the tip of the branch. 
- cat  master
- HEAD is a reference to the current commit. It usually points to the branch label of the current branch.
- One head per repo
- C:\Users\RJ\repos\myproject\.git>cat head
  ref: refs/heads/master
- If we append a ~ to HEAD in the command, we are referring to the current commit's parent, whose SHA-1 hash begins with 1e.
  Appending a single ~ is equivalent to appending a ~1.
  If we execute the command with an argument of master~3, we will reference the commit three commi
   - ts away from the current commit, whose SHA-1 begins with 14.
- HEAD~^ 2 refers to the parent's second parent.
- git tag v1.0
- To tag a commit with an annotated tag, you also use the git tag command, but specify the -a option. This will create a Git object.
- A tag is a reference to a specific commit.
- C:\Users\RJ\repos\myproject>git push https://github.com/rjrockzz/All-Of-Git.git v1.0
- git branch featureX : to create a branch
- git branch checkout featureX : To switch to that branch
- git checkout -b featureX : Combines branch and checkout commands
- Checkout updates the working tree and HEAD reference.
- Detached HEAD : The HEAD reference points directly to a commit.
- C:\Users\RJ\repos\myproject>git branch -d featureX
  Deleted branch featureX (was 2a4fa7a).
- Git reflog is a command that returns a local list of recent HEAD commits.

- git checkout -b featureX 7bcb146 : to get back to our dangling commits
- Mergiing combines work of independent branches.
 - There are four main types of merges, 
  * fast-forward merge(Default) : A fast-forward merge moves the base branch label to the tip of the topic branch. 
                                : A fast forward merge is possible only if no other commits have been made to the 
                                  base branch since the topic branch was created.
  * Merge commit : A merge commit combines the work of the tips of the feature and base branches and places
                   the result into a single merge commit.
                   git merge --no-ff featureX
  * squash merge
  * Rebase. 
  - Hunk - different parts of a file
  - A merge conflict occurs when two branches change the same hunk in different ways.
  - If merge conflict occurs Git modifies file(s) and places them in the working tree.
  - Tracking branch is a local branch that represents a remote branch.<remote>/<branch>
  - A tracking branch is decoupled from its corresponding local branch.
  - A tracking branch is decoupled from its corresponding remote branch.
  - A remote repository is necessary to have tracking branches.
  - When you clone a repository, the default branch is set up as a tracking branch.
  - Fetch : retrieves new objects and references from the remote repository.
  - Pull : Fetches and merges commits locally : To merge a branch in the project
  - Push : Adds new objects and references to the remote repository
  -  Rebasing on the base branch It lets you perform a single rebase operation of your 
    Pull Request commits on top of your base branch and then perform a merge.

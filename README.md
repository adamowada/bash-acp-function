### Here's the acp() function for .bashrc:
```
acp() {
  commitMessage="$*"
  gitStatus="$(git status)"
  regex='branch\s(\S+)\s'
  [[ $gitStatus =~ $regex ]]
  workingBranch="${BASH_REMATCH[1]}"
  git add .
  git commit -m "$commitMessage"
  git push origin $workingBranch
  echo ""
  echo "git add . commit -m \"${commitMessage}\" on branch ${workingBranch} was successful."
}
```

### Use case: 
Ok say you are busy working on a branch and you want to quickly acp without typing a lot. Just type in your terminal:
```
$ acp "commit message goes here"
```
or:
```
$ acp commit message goes here
```
Then your terminal will use git status to find the branch you are working on, git add . , git commit -m "commit message", then git push to the working branch. Finallly it will display a success message displaying the commit message and branch.
```
git add . commit -m "commit message goes here" on branch working-branch was successful.
```

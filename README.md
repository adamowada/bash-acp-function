# test
testing


Blah blah test test
more test

test number 3

ok test 4 for sure

test 5

asd test 6

uggg test 7 - success!

### Ok here's the acp() code for .bashrc:
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

test 8 without quotes in terminal
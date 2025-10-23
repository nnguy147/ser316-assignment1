# Number Guessing Game

## Initial Branch Structure

### main
- Initital Number guessing game

### dev
- Adds encouraging message for players

### feature1
- Adds quit and play-again loop functionality

### feature2
- Implements max attempts and game over features

### feature3
- Adds hint system after 3 failed attempts

### hotfix
- Bugfix for randomInt logic

## Learning Summary

### Merge vs Rebase vs Squash vs Cherry-pick

#### Merge
- use this to combine branches by creating a merge commit
- merging dev into a feature branch helps catch conflicts early, if there are any
- if feature branch is already up to date with dev, git can perform a fast forward merge (no extra merge commit)
- use when you want to preserve history
- we used this for feature 1
- always test feature branch after the merge to ensure everything works
- we usually delete the feature branch after merging
	- the dev history will include the resolve feature

#### Rebase
- use this to avoid unnecessary merge commits and keep history linear
- avoid rebase if other people are working on branch (e.g. dev)
- we lose information about what branch the code is coming from
- must resolve conflicts for each commit
- resolve conflicts in feature branch before merging into dev
- we used this for feature2

#### Squash
- combine multiple commits into one
- reduces clutter and keeps dev history linear
- HEAD~X (e.g. HEAD~4) means "the last X commits from current position"
- internal development commits are cleaned up before merging to dev
- we used this in feature3 to clean up the 4 messy commits into one commit, cleaner log

#### Cherry-pick

- apply a specific commit to the current branch 
- apply single commit to main without disturbing dev 
- merge back into main to keep it up to date 
- resolve conflicts if hotfix overlaps with recent dev changes

### Observations from git history

#### feature1
 - created merge commit
 - preserved branch history
 - shows both parallel branches of development merged back into single point
 - we deleted branch 'feature1' after we were done
 
#### feature2

- linear history
- does not show the parallel development branches 
- commits appear sequential from a new point

#### feature3
- started with 4 commits that ended up as 1 squashed commit
- cleanest history but no context

### When to use strategies

#### Merge
- you want to preserve the complete history
- working with multipel devs

#### Rebase
- when you want a clean, linear history

#### Squash
- when you have many WIP commits you want to clean up

#### Cherry-pick
- when applying hotfixes
- backadding a feature to a specific Branch
- emergency fixes


# Branching Strategy

## Git flow (modified)

A simpler version of **git flow** will be used for the code branching strategy.

Two main branches will exists:

- **master**
  - All official releases will be built from this branch and tagged on the git repo in azure.
  - This branch will have strict rules to complete a pull request to and will require extensive QA analysis.
- **development**
  - The development branch will be the running branch all features go into.
  - This branch will become the **pre-release** branch and this is where _QA_ will perform testing.

## Before Releasing

- **pre-release**
  - This is essentially the QA branch.
  - Tests will be run on this branch and upon release, will be merged to master.

## Features

- **feature/XXX**
  - Features will live in feature branches. In a sprint features that aren't planned to be released to **master** should stay in feature branches until it is slated for release.
  - Once slated for release feature branches will be reviewed and merged into development.

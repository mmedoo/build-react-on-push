# Build React on Push

### This GitHub Action builds your React app on every push and publishes it to a branch and directory of your choice. It deletes all files and directories of your app and leaves the content of your React build in the given directory.

## Inputs

| Input   | Description                           | Required | Default |
|---------|---------------------------------------|:----------:| :-: |
| `GITHUB_TOKEN` | GitHub token for authentication  | Yes    | - |
| `TARGET_DIRECTORY` | Directory in which build files will be placed inside the branch | No | `root`
| `BRANCH_NAME` | Branch name to which build files will be published | No | `build`



## Usage

### paste this action to your workflow:


```yaml
name: Building App

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Building App
      uses: mmedoo/build-react-on-push@v1.1
      with:

        # build files directory inside branch.
        # if it doesn't exist, it will be created.
        # default: root
        # TARGET_DIRECTORY: ''

        # branch name, if doesn't exist, it will be created
        # if it doesn't exist, it will be created.
        # default: build
        # BRANCH_NAME: ''

        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

## Github Pages

You can deploy this build to Github Pages by choosing branch **`build`** as your deploying source.

### Steps

1. Go to this Repository Settings.
2. From the left bar, Go to Pages.
3. Set **Deploy from a branch** as your source.
4. Choose **`build`** as branch and **`root`** as folder.


## Configuration

### You can configure these options:

- **`TARGET_DIRECTORY`**: Directory in which build files will be placed inside the branch (default: `root`)

- **`BRANCH_NAME`**: Branch name to which build files will be published (default: `build`)
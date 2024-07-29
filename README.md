# Build React on Push
This GitHub Action builds your React app on every push and publishes it to a branch and directory of your choice. This Action ensures that all files and directories surrounding the specified directory are preserved without deletion. It facilitates the seamless publication of your build files to the designated directory.


## Inputs

| Input   | Description                           | Required | Default |
|---------|---------------------------------------|:----------:| :-: |
| `GITHUB_TOKEN` | GitHub token for authentication  | Yes    | - |
| `APP_DIRECTORY` | Directory of your React app | No | `root`
| `BRANCH_NAME` | Branch name to which build files will be published | No | `build`
| `TARGET_DIRECTORY` | Directory in which build files will be placed inside the branch | No | `root`


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
      uses: mmedoo/build-react-on-push@v1.3
      with:

        # build files directory inside branch.
        # if it doesn't exist, it will be created.
        # default: root
        # TARGET_DIRECTORY: '.'

        # branch name, if doesn't exist, it will be created
        # if it doesn't exist, it will be created.
        # default: build
        # BRANCH_NAME: 'build'

        # directory of your React app
        # default: .
        # APP_DIRECTORY: '.'

        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

## Github Pages

You can deploy this build to Github Pages by choosing the branch and directory specified in the configuration.

### Steps

1. Go to this Repository Settings.
2. From the left bar, go to Pages.
3. Set **Deploy from a branch** as your source.
4. Choose the configured branch name and directory as your branch and folder.


## Configuration

### You can configure these options:

- **`TARGET_DIRECTORY`**: Directory in which build files will be placed inside the branch (default: `root`)

- **`BRANCH_NAME`**: Branch name to which build files will be published (default: `build`)

- **`APP_DIRECTORY`**: Directory of your React app (default: `root`)
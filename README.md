# Build React on Push

This GitHub Action builds your React app on every push and publishes it to a branch named **`build`**. It deletes all files and directories of your app and leaves the content of **`build`** folder in the root directory.

## Inputs

| Input   | Description                           | Required |
|---------|---------------------------------------|----------|
| `GITHUB_TOKEN` | GitHub token for authentication  | Yes      |

## Usage

paste this action to your workflow:


```yaml
name: Build React on Push

description: 'Build your React App on every push to your main branch and publish it to a branch'

branding:
  icon: 'anchor'
  color: 'gray-dark'

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Build and Deploy
      uses: mmedoo/build-react-on-push@v1.1
      with:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

## Github Pages

You can deploy this build to Github Pages by choosing branch **`build`** as your deploying source.

### Steps

1. Go to this Repository Settings.
2. From the left bar, Go to Pages.
3. Set **Deploy from a branch** as your source.
4. Choose **`build`** as branch and **`root`** as folder.


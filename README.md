# Learning Github Packages

This repo is used to learn how to publish npm packages with Github Packages.

## General setup

1. Create new access token: https://github.com/settings/tokens/new
    - make sure it has `repo` and all `packages:*` scopes
    
2. If not exist create a global `~/.npmrc` file
    - add `//npm.pkg.github.com/:_authToken={YOUR_GITHUB_ACCESS_TOKEN}`

Resources:
- https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-npm-for-use-with-github-packages#authenticating-to-github-packages

## Repository/Package setup

A package gets always publish within a repository on github. You can publish __multiple packages__ within one repository. 
In the `package.json` the `repository` field is used for the repository in which the package gets uploaded and the `name` 
is used to determine the name.

1. In your repository, add an `.npmrc` file if not already present
    - for every package hosted on github, add `@{GITHUB_ORG}:registry=https://npm.pkg.github.com/{GITHUB_ORG}`
 
2. If you want to publish your repository make sure you have the correct `package.json` config:
    - `repository`: needs to point to the repo in which the package gets published (example: `git://github.com/{GITHUB_ORG}/{REPO_NAME}.git`)
    - `name`: if the package is scoped, the scope needs to be the same as the github org as the repo (example: `@{GIHTUB_ORG}/{REPO_NAME}`)
    
Resources:
- https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-npm-for-use-with-github-packages#publishing-a-package
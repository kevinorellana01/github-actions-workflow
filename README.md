# GitHub Actions Workflow (Hands-On)

This project demonstrates how to set up and use GitHub Actions for automating workflows. We will walk through the steps of creating a simple GitHub Actions workflow that gets triggered by a push event, and displays a message in the Actions tab of GitHub.

## Table of Contents

- [Overview](#overview)
- [Steps](#steps)
  - [Step 1: Create a New GitHub Repository](#step-1-create-a-new-github-repository)
  - [Step 2: Clone the Repository to Your Local Machine](#step-2-clone-the-repository-to-your-local-machine)
  - [Step 3: Create a Folder and File for Your Workflow](#step-3-create-a-folder-and-file-for-your-workflow)
  - [Step 4: Define Your GitHub Actions Workflow](#step-4-define-your-github-actions-workflow)
  - [Step 5: Make a Change to Trigger the Workflow](#step-5-make-a-change-to-trigger-the-workflow)
  - [Step 6: Commit and Push Your Changes to GitHub](#step-6-commit-and-push-your-changes-to-github)
  - [Step 7: View Your Workflow in GitHub](#step-7-view-your-workflow-in-github)
- [Commands Used](#commands-used)
- [GitHub Actions Workflow](#github-actions-workflow)

## Overview

In this hands-on tutorial, we will:
- Create a new repository on GitHub.
- Set up a GitHub Actions workflow that triggers on push events.
- Make a change to trigger the workflow and view the result in the Actions tab.

## Steps

### Step 1: Create a New GitHub Repository
- Create a new repository on GitHub and ensure to add a README.md file during the setup.
- The repository will be used to store the code for the workflow.

### Step 2: Clone the Repository to Your Local Machine
Clone the repository to your local machine using the following command:
```bash
git clone git@github.com:<your-github-username>/<repository-name>.git
```
### Step 3: Create a Folder and File for Your Workflow
Inside the cloned repository:

- Create a new folder named `.github/workflows`.
- Inside the `workflows` folder, create a file named `main.yaml`.

### Step 4: Define Your GitHub Actions Workflow
GitHub Actions workflows are defined using YAML files. In `main.yaml`, define the structure of the workflow:

- **Name**: A descriptive name for the workflow.
- **Trigger event**: Specify the event that will trigger the workflow (e.g., push, pull_request).
- **Jobs**: Define one or more jobs with unique names.
- **Runner**: Specify the execution environment (e.g., `ubuntu-latest`).
- **Steps**: Define the individual steps for the job.

Here’s an example of what `main.yaml` could look like:

```yaml
name: My First GitHub Actions Workflow

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Check out code
        uses: actions/checkout@v2
      - name: Display message
        run: echo "Hello, my workflow"
```
### Step 5: Make a Change to Trigger the Workflow
To trigger the workflow, edit the README.md file and add the line:
```bash
Hello, my workflow
```
### Step 6: Commit and Push Your Changes to GitHub
Use the following commands to commit and push the changes:
```bash
git add .
git status
git commit -m "message created"
git push
```
### Step 7: View Your Workflow in GitHub
Go to your GitHub repository.
Click on the "Actions" tab.
You will see the workflow listed, with details of each run and any log messages related to the run.
### Commands Used
git clone git@github.com:<your-github-username>/<repository-name>.git
git add .
git status
git commit -m "message created"
git push
### GitHub Actions Workflow
This repository contains a simple GitHub Actions workflow, triggered by a push event. You can monitor the execution of the workflow and check its results under the "Actions" tab in the repository.

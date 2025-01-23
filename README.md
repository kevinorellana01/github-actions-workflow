# GitHub Actions Workflow 
This project demonstrates how to set up and use GitHub Actions for automating workflows. We will walk through the steps of creating a simple GitHub Actions workflow that gets triggered by a push event, and displays a message in the Actions tab of GitHub.

For the full documentation of the project: [Medium](https://medium.com/@kevinn.orellana01/the-devops-revolution-culture-tools-and-automation-80fecd2e273f)

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

![image](https://github.com/user-attachments/assets/3262e36a-7458-46a5-b85a-c9e1168f7d59)

### Step 2: Clone the Repository to Your Local Machine
Clone the repository to your local machine using the following command:
```bash
git clone git@github.com:<your-github-username>/<repository-name>.git
```
![image](https://github.com/user-attachments/assets/2b585730-e7fd-407e-be2f-b592ae2d7051)

### Step 3: Create a Folder and File for Your Workflow
Inside the cloned repository:

- Create a new folder named `.github/workflows`.
- Inside the `workflows` folder, create a file named `main.yaml`.

![image](https://github.com/user-attachments/assets/65a9ba19-a113-4535-a70d-3bc404a347a0)

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

![image](https://github.com/user-attachments/assets/c89ceb6f-211c-45ce-9353-df223f876ded)

### Step 5: Make a Change to Trigger the Workflow
To trigger the workflow, edit the README.md file and add the line:
```bash
Hello, my workflow
```

![image](https://github.com/user-attachments/assets/0e5f34f0-f8e2-4c33-920f-e931adbdb45c)

### Step 6: Commit and Push Your Changes to GitHub
Use the following commands to commit and push the changes:
```bash
git add .
git status
git commit -m "message created"
git push
```

![image](https://github.com/user-attachments/assets/121cab6e-d24b-4bcf-8325-5bce8340e6b3)

### Step 7: View Your Workflow in GitHub
- Go to your GitHub repository.
- Click on the "Actions" tab.
- You will see the workflow listed, with details of each run and any log messages related to the run.

![image](https://github.com/user-attachments/assets/df67f8f3-e54a-4f37-8064-125e1b42bfe5)

### Commands Used
- git clone 
- git add .
- git status
- git commit -m "message created"
- git push

## Key Takeaways

- **GitHub Actions Workflow**: A simple automation tool for continuous integration and deployment (CI/CD) directly within your GitHub repository.
- **YAML Format**: Workflows in GitHub Actions are defined using YAML files, which specify triggers, jobs, and steps.
- **Trigger Events**: Workflows can be triggered by various events like `push`, `pull_request`, or on a schedule, allowing for automated tasks whenever code changes occur.
- **Jobs and Steps**: A job consists of a set of steps executed sequentially, which can include actions (predefined or custom) and shell commands.
- **Runner Environment**: Workflows can run on different operating system environments (e.g., `ubuntu-latest`, `windows-latest`) based on the needs of the workflow.
- **Actions Tab**: After pushing changes that trigger a workflow, you can track the progress and result in the GitHub repository’s "Actions" tab.

These key concepts form the foundation for automating tasks and streamlining workflows in your development process using GitHub Actions.

### GitHub Actions Workflow
This repository contains a simple GitHub Actions workflow, triggered by a push event. You can monitor the execution of the workflow and check its results under the "Actions" tab in the repository.

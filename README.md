# COSC2759 Assignment 1
## Notes App - CI Pipeline
- Full Name/Names: Nguyen Thanh Dat, Cao Le Hoang Minh
- Student ID/IDs: s3975867, s3979628

To run the CI pipeline for your Notes Application using GitHub Actions, follow these steps:
## 1. Triggering the Pipeline
### 1.1 Automatic Trigger: 
This GitHub Actions process will start automatically in 2 events:
#### - Push Events: 
If there is a push to any branch in the repository, the process will start. This is shown by the "**" wildcard pattern next to the push event in the on part of the YAML file.

#### - Pull Request Events: 
The process will also start when a pull request is made to any branch in the repository. In the same way, the wildcard pattern "**" under the pull_request event shows this.

### 1.2 Manual Trigger:
You can manually trigger the pipeline by clicking the "Run workflow" button in the GitHub Actions 
tab of your repository (if the workflow is configured to allow manual runs).

In Github Action, you can chose to re-run all jobs or only the failed jobs.

## 2. Commands to Run the Pipeline Locally
### 2.1 Linting:

#### - Install dependencies

Command: npm install --prefix src<br>
Installs the project dependencies defined in the package.json located in the src directory.

#### - Run lint

Command: npm run test-lint --prefix src<br>
Runs the linter (npm run test-lint)


### 2.2 Unit Testing:

#### - Install dependencies

Command: npm install --prefix src<br>
Installs the necessary dependencies for running the unit tests.

#### - Run Unit Tests

Command: npm run test-unit --prefix src<br>
Executes the unit tests (npm run test-unit).

### 2.3 Ensure Code Coverage is Checked:

#### - Install dependencies

Command: npm install --prefix src<br>
Installs the project dependencies.

#### - Run Code Coverage

Command: npm run test-unit -- --coverage<br>
Runs the unit tests with code coverage enabled (npm run test-unit -- --coverage).


### 2.4 End-to-End Testing:

#### - Use MongoDB in GitHub Actions

Action: uses: MongoCamp/mongodb-github-action@1.2.0<br>
Sets up MongoDB for use in the E2E tests.

#### - Install dependencies

Command: npm clean-install<br>
Installs the project dependencies with a clean installation.

#### - Install Playwright Browsers

Command: npx playwright install --with-deps<br>
Installs the browsers needed by Playwright.

#### - Run the application

Command: npm run start &<br>
Starts the application in the background.

#### - Run E2E tests

Command: npx playwright test<br>
Executes the E2E tests using Playwright.


### 2.5 Generate Deployable Artifacts:

#### - Install dependencies

Command: npm install --prefix src<br>
Installs the project dependencies.

#### - Build Project

Command: run: npm run build --prefix src<br>
Builds the application.

#### - Upload Build Artifact

Command: uses: actions/upload-artifact@v3<br>
Uploads the build artifacts to GitHub.


## 3. Expected Output from the CI Pipeline
### 3.1 Summary In GitHub Actions:
- This is the summary of run 109 of the pipeline in GitHub Actions. This is a result of committing directly to the main branch.<br>
- The  status is success, which means all the things in the pipeliine runs with out any error.<br>
- The entire pipeline takes 14m 13s to run.<br>
- Billable time: 19m. It accounts for actual usage of the pipeline.<br>
- Artifacts: 2<br>
It is expected that the first 3 jobs take approximately 20 seconds, the e2e is longer at about 2 minutes and the most time-consuming job is generating artifacts.
<img src="/img/summary.png" style="height: 400px"/>

### 3.1 Linting Results:
This is the expected results if the Lint job runs successfully. 

<img src="/img/lint.githubflow.png" style="height: 400px"/>

### 3.2 Unit Testing:
This is the expected results if the Unit Testing job runs successfully. 

<img src="/img/unittesting.githubflow.png" style="height: 400px"/>

### 3.3 Ensure Code Coverage is Checked:
This is the expected results if the Code Coverage job runs successfully. 

<img src="/img/ensurecodecoverage.githubflow.png" style="height: 400px"/>

### 3.4 End-to-End Testing:
This is the expected results if the End-to-End job runs successfully. 

<img src="/img/e2e.githubflow.png" style="height: 400px"/>

### 3.5 Generate Deployable Artifacts:
This is the expected results if the Generate Deployable Artifacts job runs successfully. 

<img src="/img/generateartifact.githubflow.png" style="height: 400px"/>

Artifacts can be find at the bottom of GitHub Actions Summary page.

<img src="/img/artifacts.png" style="height: 200px"/>

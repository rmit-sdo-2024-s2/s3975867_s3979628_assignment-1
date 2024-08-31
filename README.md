# COSC2759 Assignment 1
## Notes App - CI Pipeline
- Full Name/Names: Nguyen Thanh Dat, Cao Le Hoang Minh
- Student ID/IDs: s3975867, s3979628

### Guidance (remove this section before final submission)

1. Refer for assignment specification `Marking Guide` for details of what should appear in this README.

2. If you do not see an `Actions` tab in your GitHub, email matthew.cullen@rmit.edu.au with URL to your repository, so that it can be enabled.

3. Implement your CI pipeline in the directory `.github/workflows`.

4. Refer to [src/README.md](/src/README.md) for important details on building and testing the application.

5. Commit images to the `img` directory and add them like 
    ```html
    <img src="/img/md.png" style="height: 70px;"/>
    ```
    <img src="/img/md.png" style="height: 70px;"/>

6. Only edit THIS README.md - not the src/README.md
To run the CI pipeline for your Notes Application using GitHub Actions, follow these steps:
## 1. Triggering the Pipeline
### 1.1 Automatic Trigger:
The pipeline is automatically triggered when you push changes to the repository or create a pull request. 
This is defined in your GitHub Actions workflow file.
### 1.2 Manual Trigger:
You can manually trigger the pipeline by clicking the "Run workflow" button in the GitHub Actions 
tab of your repository (if the workflow is configured to allow manual runs).
In Github Action, you can chose to re-run all jobs or only the failed jobs.

## 2. Commands to Run the Pipeline Locally
### 2.1 Linting:
Run npm run test-lint to check your code for linting errors using ESLint.
Expected Output: The console will display linting errors or confirm that your code passed the linting process.
### 2.2 Unit Testing:
Run npm run test-unit to execute unit tests with Jest.
Expected Output: The console will display test results, including the number of tests passed, failed, and skipped.
### 2.3 Integration Testing:
Run npm run test-integration to execute integration tests with Jest.
Expected Output: Similar to unit testing, the console will show the results of your integration tests.
### 2.4 End-to-End Testing:
Run npm run test-e2e to execute end-to-end tests using Playwright.
Expected Output: The console will display results for the end-to-end tests, indicating which tests passed or failed.

## 3. Expected Output from the CI Pipeline
### 3.1 Linting Results:
If there are linting errors, the pipeline will fail at the linting stage, and the errors will be displayed in the GitHub Actions logs.
### 3.2 Unit and Integration Testing:
The results of the unit and integration tests will be displayed. If any tests fail, the pipeline will stop, and the test failures will be shown in the logs.
### 3.3 End-to-End Testing:
Similar to unit and integration testing, the results of the end-to-end tests will be displayed. Any failures will cause the pipeline to fail.
<img src="/img/e2e.githubflow.png" style="height: 70px;"/>
### 3.4 Success:
If all stages pass without errors, the pipeline will complete successfully, and you will see a green checkmark indicating that your code is ready for deployment.

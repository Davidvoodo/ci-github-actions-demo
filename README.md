
# ci-github-actions-demo -Demo for CI with GitHub Actions

This repository demonstrates the use of **GitHub Actions** for Continuous Integration (CI) and workflow automation.  
It was built step by step as part of an exercise.

---

## Part 1: Basic CI Setup

### Task 1: Basic Workflow
- Trigger: Runs whenever code is pushed to the `main` branch.
- Actions:
  - Checks out the code using `actions/checkout@v3`.
  - Prints `Hello, CI with GitHub Actions!` in the logs.
- **Expected Output:**  
  A successful workflow run showing the message in the Actions log.

### Task 2: Running Tests
- Files:
  - `main.py` with a simple function.
  - `test_main.py` with unit tests (using the `unittest` framework).
- Workflow updates:
  - Sets up Python 3.9 with `actions/setup-python@v4`.
  - Installs dependencies (from `requirements.txt` if present).
  - Runs unit tests.
- **Expected Output:**  
  The workflow runs the tests and displays the results (`OK`) in the logs.

---

## Part 2: Advanced GitHub Actions Features

### Task 3: Cron Scheduling
- Workflow: `.github/workflows/scheduled-build.yml`
- Trigger: Runs daily at midnight UTC (cron: `0 0 * * *`).
- Actions:
  - Checks out the code.
  - Logs `Scheduled build completed successfully!`.
- **Expected Output:**  
  The workflow executes daily and logs the scheduled build message.  
  (It can also be triggered manually using `workflow_dispatch`.)

### Task 4: Matrix Builds
- Workflow: `.github/workflows/ci.yml`
- Updated to run on multiple Python versions (currently 3.8, 3.9, 3.11, 3.12).
- Actions:
  - Checks out the code.
  - Sets up the specified Python version using `actions/setup-python@v4`.
  - Installs dependencies.
  - Runs the unit tests.
- **Expected Output:**  
  The workflow runs tests for each Python version in parallel.  
  Logs display the greeting message and the unit test results (`OK`) for every version.

---

## Repository Structure



# ci-github-actions-demo -Demo for CI with GitHub Actions

This repository is a simple demonstration of **Continuous Integration (CI) with GitHub Actions**.  
It was created as part of an exercise to learn how to set up and run workflows on GitHub.

## Workflows and Tasks

### Task 1: Basic GitHub Actions Workflow
- A workflow is defined in `.github/workflows/ci.yml`.
- It is triggered **whenever code is pushed to the `main` branch**.
- The workflow:
  - Checks out the repository using `actions/checkout@v3`.
  - Runs a simple shell command:
    ```
    echo "Hello, CI with GitHub Actions!"
    ```
- **Expected output:** The log should display the message above.

### Task 2: Running Tests
- A simple Python function is implemented in `main.py` (an `add(a, b)` function).
- Unit tests are defined in `test_main.py` using the `unittest` framework.
- The GitHub Actions workflow was extended to:
  - Set up Python 3.9 using `actions/setup-python@v4`.
  - Install dependencies from `requirements.txt` (if any).
  - Run all unit tests with:
    ```
    python -m unittest discover -v
    ```
- **Expected output:** The workflow log shows test discovery and results:
  - Each test marked as `ok`.
  - Final summary with `OK`.

## How to Run Tests Locally
To run the same tests on your local machine:
```bash
python -m unittest discover -v


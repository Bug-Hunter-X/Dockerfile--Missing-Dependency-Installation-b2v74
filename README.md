# Dockerfile Bug: Missing Dependency Installation
This repository demonstrates a common error in Dockerfiles: failing to install project dependencies before running the application or tests. The initial `Dockerfile` attempts to run unit tests using `unittest`, but fails because the necessary packages are not installed.

The `Dockerfile-fixed` version corrects this issue by installing dependencies listed in `requirements.txt` using `pip`.

## Reproducing the Bug
1. Clone this repository.
2. Build the initial Dockerfile: `docker build -t missing-deps -f Dockerfile .`
3. Attempt to run the container: `docker run missing-deps`. Observe the failure.
4. Build the fixed Dockerfile: `docker build -t fixed-deps -f Dockerfile-fixed .`
5. Run the fixed container: `docker run fixed-deps`. Observe the successful test execution.

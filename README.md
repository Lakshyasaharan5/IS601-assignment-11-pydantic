# IS601-assignment-11-pydantic
Calculation model using SQLAlchemy and factory design pattern

## Running tests

Be sure to create a pytest.ini file to specify the test directory paths and any additional Pytest configurations.

```bash
# Run integration tests
$ pytest tests/integration/

# Run end-to-end tests
$ pytest tests/e2e/

# Run unit tests for operations
$ pytest tests/unit/

# Run all tests (including those configured in conftest)
$ pytest
```

## Github Workflow Action

//screenshot

## DockerHub Deploy

URL: 

//screenshot

## Challenges

#### Security patch issue

Security action workflow fails when running Tivy vulnerability scanner. 
To fix this, I added .tiryignore files with following Vulnerabilities:

- CVE-2025-43859
- CVE-2024-33663
- CVE-2025-62727

#### Docker compose issue

Volume path for postgres inside the container had `data/` which causes issue in newer versions. So removing it solves the issue because postgresql automatically creates subdirectories as needed.

#### E2E test sometime fails

When we run `pytest` then E2E tests sometimes fails in the first run for no reason but successfully runs for the second time.
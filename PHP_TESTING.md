# PHP Testing & Quality Assurance Guidelines

## Test Framework & Organization

- **PHPUnit**: Standardize on PHPUnit as the primary testing framework.
- **Test Hierarchy**:
  - `tests/Unit/`: Pure unit tests. Fast, in-memory, completely isolated, with no database or network dependencies.
  - `tests/Integration/`: Integration tests verifying database transactions, API handlers, service interactions, and external integrations.
- **Naming Conventions**:
  - Test files must end with `Test.php` (e.g., `UserServiceTest.php`).
  - Test classes must match the file name and extend the project base test case (e.g., `TestCase`).
  - Test methods must be prefixed with `test` (e.g., `testUserCanBeCreated()`) or use the `@test` annotation.

## Fast Local Feedback Loop

- **Targeted & Fast Execution**:
  - During active coding, prioritize fast local runs for near-instant execution (< 1s):
    ```bash
    # Run only unit tests
    composer test:fast
    composer test:unit

    # Run tests relevant to changed git files
    composer test:changed

    # Run a specific targeted test file or method
    vendor/bin/phpunit tests/Unit/UserServiceTest.php
    vendor/bin/phpunit --filter testUserCanBeCreated
    ```
  - Reserve full integration suite runs (`composer test`) for pre-commit verification and CI pipelines.

## Test Isolation & State Management

- **Boundary Mocking**: Mock only external boundaries (HTTP APIs, external gateways, message queues). Avoid mocking internal domain logic.
- **State Cleanup**: Clean up any database fixtures, static state, or temporary files in `setUp()` and `tearDown()` methods to guarantee test independence.
- **Deterministic Tests**: Never use arbitrary `sleep()` delays in tests. Rely on explicit status assertions and synchronous test doubles.

# PHP Environment & Tooling Guidelines

## Runtime & Standards

- **PHP Version**: Target modern, supported PHP versions (PHP 8.1+ recommended). Ensure code adheres to strict type declarations where supported (`declare(strict_types=1);`).
- **Devcontainer Environments**: Prefer developing inside devcontainers to guarantee consistent runtime extensions, CLI tools, and background services across development environments.

## Composer & Dependency Management

1. **Dependency Management**:
   - Manage all project dependencies, dev tools, and library packages using Composer via `composer.json` and lockfile `composer.lock`.
   - Always commit `composer.lock` for application services and projects to ensure reproducible builds.
   - Run `composer install` when setting up or synchronizing dependencies.

2. **PSR-4 Autoloading**:
   - Register all application namespaces using PSR-4 autoloading in `composer.json`:
     ```json
     "autoload": {
       "psr-4": {
         "App\\": "src/"
       }
     },
     "autoload-dev": {
       "psr-4": {
         "App\\Tests\\": "tests/"
       }
     }
     ```
   - Run `composer dump-autoload` whenever new namespaces or class mapping paths are added.

3. **Composer Scripts**:
   - Standardize development commands into `composer.json` scripts:
     - `composer test`: Run the complete test suite.
     - `composer test:fast` / `composer test:unit`: Fast in-memory unit tests.
     - `composer test:changed`: Run tests relevant to modified files.
     - `composer lint`: Code style and static analysis checks.
     - `composer lint:fix`: Automated code style fixes.
     - `composer start`: Start local development services in the background.
     - `composer server:status`: Check runtime server/daemon status.

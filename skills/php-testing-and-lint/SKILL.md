---
name: php-testing-and-lint
description: Run fast local PHPUnit feedback loops, PHPCBF formatting, and PHPCS linting for PHP Implementer and Verifier roles.
---

# PHP Testing & Lint Skill

Use this skill when implementing or verifying PHP changes.

## Implementer Loop (Fast Local Feedback)
1. After editing PHP files, auto-fix formatting immediately:
   ```bash
   composer lint:fix
   ```
2. Run fast unit tests or git-changed tests:
   ```bash
   composer test:changed
   composer test:fast
   ```

## Verifier Loop (Independent Verification)
1. Run zero-tolerance PHPCS linting:
   ```bash
   composer lint
   ```
   All errors and warnings must be resolved.
2. Run the full PHPUnit suite (unit + integration):
   ```bash
   composer test
   ```
3. Confirm new functionality has unit or integration tests and modified functionality has updated tests.

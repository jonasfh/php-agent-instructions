# PHP Code Style & Quality Guidelines

## Coding Standards

- **PSR Standards**: Adhere to standard PHP conventions (PSR-1, PSR-12, or project-configured standards such as WordPress-Coding-Standards where appropriate).
- **Class and File Naming**: Match class name directly to file name (e.g. `UserRepository.php` for class `UserRepository`).
- **Method & Variable Conventions**: Use clear, descriptive names. Maintain project consistency for camelCase vs. snake_case.

## Linting & Formatting Tooling

1. **PHP CodeSniffer (PHPCS)**:
   - Run linting with `composer lint` (or `vendor/bin/phpcs`).
   - Configure rulesets in `phpcs.xml` or `phpcs.xml.dist` with caching and parallel execution enabled for sub-second feedback.
2. **PHP Code Beautifier (PHPCBF)**:
   - Routinely run `composer lint:fix` (or `vendor/bin/phpcbf`) on modified files during active development and always before committing to automatically fix formatting and whitespace violations.
3. **Zero-Lint Policy**:
   - Zero warnings and zero errors policy. All linting issues must be resolved before completing tasks or opening Pull Requests.
   - Do not disable linting rules via inline comments unless strictly necessary and accompanied by a clear explanatory comment.

## Formatting Hygiene

- **Whitespace**: Strip all trailing whitespaces across all lines.
- **End-of-File Newline**: Ensure exactly one trailing newline (`\n`) at EOF.
- **Indentation**: Use consistent indentation (spaces or tabs per project ruleset, never mixed).

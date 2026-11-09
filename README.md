# PHP Agent Instructions

## Purpose

This repository provides standardized development guidelines, architectural conventions, tooling standards, and testing practices for PHP projects across the ecosystem.

It builds upon the core standards defined in [common-agent-instructions](https://github.com/jonasfh/common-agent-instructions).

## Modular Sub-guidelines

- 🛠️ **[PHP Environment & Tooling](file:///./PHP_ENVIRONMENT_AND_TOOLING.md)**: Composer dependency management, PSR-4 autoloading standards, custom scripts, and runtime environment.
- 🎨 **[PHP Code Style & Quality](file:///./PHP_CODE_STYLE.md)**: PSR standards, PHPCS linting, PHPCBF auto-formatting, zero-lint policy, and formatting hygiene.
- 🧪 **[PHP Testing & QA](file:///./PHP_TESTING.md)**: PHPUnit testing framework, unit vs. integration separation, fast local feedback loops, and state isolation.
- 📐 **[PHP Architecture](file:///./PHP_ARCHITECTURE.md)**: Modular design, thin controllers, domain services, universal database timestamp rules, and safe query execution.
- 🖥️ **[PHP Server & Database](file:///./PHP_SERVER_AND_DATABASE.md)**: Dev-server execution in Apache, error logging inspection, database connectivity, and CLI tools.

## Using this Submodule in Consuming Projects

Add this repository as a git submodule in your project under `.agents/php-agent-instructions/`:

```bash
git submodule add https://github.com/jonasfh/php-agent-instructions.git .agents/php-agent-instructions
```

In the consuming project's `AGENTS.md`, link to these modular sub-guidelines alongside the general guidelines in `.agents/common-agent-instructions/`.

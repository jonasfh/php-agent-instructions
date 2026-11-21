---
name: php-migration-and-db
description: Checklist for PHP database tables, migrations, universal timestamp columns, and safe query execution.
---

# PHP Migration & Database Skill

Use this skill when creating or modifying custom database tables, repositories, or migrations in PHP.

## Checklist
1. **Mandatory Timestamps**:
   - Every custom database table MUST include `created_at` and `modified_at` timestamp columns.
2. **Safe Queries**:
   - Always use prepared statements (`$wpdb->prepare(...)` in WordPress or parameterized PDO/DBAL queries). Never interpolate variables directly into SQL.
3. **Thin Controllers & Service Separation**:
   - Keep database access in dedicated repository/service classes, not inside AJAX/REST controller handlers.
4. **Integration Tests**:
   - Cover schema creation, migrations, and query edge cases with integration tests (`$requires_db = true` where applicable).

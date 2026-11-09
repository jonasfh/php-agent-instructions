# PHP Architecture & Design Standards

## Layered Architecture & Separation of Concerns

Structure PHP applications into clear, decoupled layers:

1. **Transport / Entrypoint Layer**:
   - HTTP route handlers, REST/AJAX controllers, and CLI commands.
   - Responsible for request decoding, input validation, invoking domain services, and returning structured responses.
   - **Thin Controllers**: Keep controllers thin; delegate all business rules, calculations, and persistence logic to domain services.

2. **Domain & Business Logic Layer**:
   - Domain services, entities, value objects, and business workflows.
   - Completely independent of transport mechanisms and external presentation layers.

3. **Data Access & Repository Layer**:
   - Data repositories, database mappers, and external client integrations.
   - Encapsulate SQL queries and database access patterns behind dedicated repositories or query services.

## Universal Database Rules

- **Timestamp Auditing**: Always include `created_at` and `modified_at` datetime columns on custom database tables and domain entities.
- **Safe Queries & SQL Injection Prevention**:
  - Never concatenate or interpolate user input directly into SQL strings.
  - Always use prepared statements and parameterized queries (e.g. via PDO or prepared SQL placeholders).
- **Transactions**: Wrap multi-step database mutations in database transactions to guarantee data consistency and rollback on errors.

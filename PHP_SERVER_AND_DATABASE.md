# PHP Server & Database Guidelines

## Dev-Server Lifecycle & Apache

1. **Background Service Management**:
   - In containerized development environments, run Apache and database services in the background so the developer terminal remains free:
     ```bash
     composer start          # Start background services (Apache, database)
     composer server:status  # Check running status of server and database
     ```
2. **Error Logging & Debugging**:
   - Check the Apache and PHP error logs when encountering HTTP 500 errors or unexpected behavior:
     - Apache error log: `/var/log/apache2/error.log`
     - Quick filter for PHP fatal errors:
       ```bash
       tail -n 100 /var/log/apache2/error.log | grep -i "fatal error"
       ```
   - Inspect application-specific debug logs when debug logging is enabled.

## Database Connectivity

1. **Configuration & Credentials**:
   - Retrieve database credentials (host, port, database name, user, password) exclusively from environment variables or configuration files.
   - Never commit hardcoded database credentials to source control.
2. **Direct CLI Database Access**:
   - Use direct database client CLIs inside the container for quick inspection and troubleshooting:
     ```bash
     mariadb <dbname>
     # or:
     mysql -u <user> -p <dbname>
     ```

# Use the official MySQL 9.0 image from Docker Hub
FROM mysql:8.0

# Set environment variables for MySQL root user password and database creation
# Note: For production, avoid hardcoding passwords in the Dockerfile
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1
RUN groupadd expense && \
    useradd -g expense expense && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d
# ENV MYSQL_DATABASE=my_database
# ENV MYSQL_USER=my_user
# ENV MYSQL_PASSWORD=my_password

# Copy an optional init script to the container if needed
COPY scripts/*.sql /docker-entrypoint-initdb.d/
USER expense

# Expose the default MySQL port
EXPOSE 3306

# Start MySQL service
CMD ["mysqld"]

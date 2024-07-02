# Extract, Load and Transform Project

This repository contains a custom Extract, Load, Transform (ELT) project that utilizes Docker and PostgreSQL to demonstrate a simple ELT process.

## How It Works

1. **Docker Compose**: Using the `docker-compose.yaml` file, three Docker containers are spun up:
   - A source PostgreSQL database with sample data.
   - A destination PostgreSQL database.
   - A Python environment that runs the ELT script.

2. **ELT Process**: The `elt_script.py` waits for the source PostgreSQL database to become available. Once it's available, the script uses `pg_dump` to dump the source database to a SQL file. Then, it uses `psql` to load this SQL file into the destination PostgreSQL database.

3. **Database Initialization**: The `init.sql` script initializes the source database with sample data. It creates several tables and populates them with sample data.

## Getting Started

1. Ensure you have Docker and Docker Compose installed on your machine.
2. Clone this repository.
3. Navigate to the repository directory and run `docker-compose up`.
4. Once all containers are up and running, the ELT process will start automatically.
5. After the ELT process completes, you can access the source and destination PostgreSQL databases on ports 5433 and 5434, respectively.

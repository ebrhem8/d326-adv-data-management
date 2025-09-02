# D326 – Advanced Data Management

Portfolio repo for **D326** focused on **relational data modeling**, **SQL**, **constraints & indexing**, **transactions**, and practical **query patterns**.

> This is **not** a Java/Spring app. It’s a SQL-first repo (DDL/DML/queries + design notes).  
> CI uses a lightweight smoke check to keep the status green on each push.

[![Repo checks](https://github.com/sheenawhittier/d326-adv-data-management/actions/workflows/ci.yml/badge.svg)](https://github.com/sheenawhittier/d326-adv-data-management/actions/workflows/ci.yml)

---

## Tech Stack
- **Database:** MySQL 8 (portable to Postgres with minor tweaks)
- **Artifacts:** SQL (DDL/DML), stored procedures/triggers (if used), sample datasets
- **Docs:** ERD & design notes
- **CI:** GitHub Actions (repo smoke check)

---

## Getting Started

### Option A — Docker (fastest)
```bash
# Start MySQL 8 locally
docker run --name d326-mysql \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=d326 \
  -p 3306:3306 -d mysql:8

# Apply schema (adjust file names if yours differ)
mysql -h 127.0.0.1 -P 3306 -u root -p d326 < schema/00_create_schema.sql

# Optional: constraints/indexes if split into files
# mysql -h 127.0.0.1 -P 3306 -u root -p d326 < schema/01_constraints.sql
# mysql -h 127.0.0.1 -P 3306 -u root -p d326 < schema/02_indexes.sql

# Seed data
mysql -h 127.0.0.1 -P 3306 -u root -p d326 < data/seed.sql

# Try example queries
mysql -h 127.0.0.1 -P 3306 -u root -p d326 < queries/examples.sql



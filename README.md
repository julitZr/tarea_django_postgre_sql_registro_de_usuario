# Registro de Usuario con Django y PostgreSQL

## Requisitos
- Python 3.10+
- PostgreSQL
- pip

## Instalación y ejecución

### 1) Crear entorno virtual
```bash
python -m venv venv
# Windows (PowerShell)
venv\Scripts\activate
pip install django psycopg2-binary
Ejecutar en postgreSQL
CREATE DATABASE usuarios_db;
CREATE USER usuario_django WITH PASSWORD 'password123';
ALTER ROLE usuario_django SET client_encoding TO 'utf8';
ALTER ROLE usuario_django SET default_transaction_isolation TO 'read committed';
ALTER ROLE usuario_django SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE usuarios_db TO usuario_django;

<img width="1604" height="884" alt="image" src="https://github.com/user-attachments/assets/4bb6ef1a-18c1-4bd0-b236-df0a6a8292b7" />

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
```
### 2) Ejecutar en postgreSQL
```bash
CREATE DATABASE usuarios_db;
CREATE USER usuario_django WITH PASSWORD 'password123';
ALTER ROLE usuario_django SET client_encoding TO 'utf8';
ALTER ROLE usuario_django SET default_transaction_isolation TO 'read committed';
ALTER ROLE usuario_django SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE usuarios_db TO usuario_django;
```
### 3) En settings.py 
```bash
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'usuarios_db',
        'USER': 'usuario_django',
        'PASSWORD': 'password123',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```
### 4) Migraciones en la terminal
```bash
python manage.py makemigrations
python manage.py migrate
```
### 5) Ejecutar servidor
```bash
python manage.py runserver
```

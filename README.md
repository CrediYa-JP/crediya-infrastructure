# CrediYa Infrastructure

Infraestructura de contenedorización para el sistema de microservicios CrediYa.

## 📋 Prerequisitos

- Docker Desktop instalado y ejecutándose
- Git
- Al menos 4GB RAM disponibles

## 🚀 Setup Rápido

### 1. Clonar repositorios

```bash
# Crear carpeta del proyecto
mkdir crediya-project
cd crediya-project

# Clonar todos los repositorios como hermanos
git clone /crediya-microservice-authentication.git
git clone /crediya-microservice-applications.git
git clone /crediya-infrastructure.git

cd crediya-infrastructure
cp .env.example .env

# Ejemplo de valores
MYSQL_ROOT_PASSWORD=root_password_123
AUTH_DB_USER=auth_user
AUTH_DB_PASSWORD=auth_password_123
APP_DB_USER=app_user
APP_DB_PASSWORD=app_password_123
JWT_PRIVATE_KEY=tu_private_key_aqui
JWT_PUBLIC_KEY=tu_public_key_aqui

# Levantar todo el sistema
docker-compose up --build

# Authentication Service
curl http://localhost:8080/actuator/health

# Applications Service  
curl http://localhost:8081/actuator/health

# Verificar bases de datos
docker-compose logs mysql-auth
docker-compose logs mysql-applications

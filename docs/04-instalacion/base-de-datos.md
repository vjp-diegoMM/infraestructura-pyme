# Instalación y Configuración de MySQL

## Instalación

```bash
sudo apt install mysql-server -y
sudo systemctl enable mysql
sudo mysql_secure_installation
```

## Creación de bases de datos

```sql
-- Base de datos web
CREATE DATABASE db_web CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'web_user'@'localhost' IDENTIFIED BY 'password_seguro';
GRANT ALL PRIVILEGES ON db_web.* TO 'web_user'@'localhost';

-- Base de datos gestión interna
CREATE DATABASE db_gestion CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'gestion_user'@'localhost' IDENTIFIED BY 'password_seguro2';
GRANT ALL PRIVILEGES ON db_gestion.* TO 'gestion_user'@'localhost';

FLUSH PRIVILEGES;
```

## Verificación

```bash
mysql -u web_user -p -e "SHOW DATABASES;"
```
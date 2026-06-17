# Instalación del Servidor Web Apache con PHP

## Instalación de Apache

```bash
sudo apt update
sudo apt install apache2 -y
sudo systemctl enable apache2
sudo systemctl start apache2
```

## Instalación de PHP 8.1

```bash
sudo apt install php8.1 libapache2-mod-php8.1 php8.1-mysql -y
```

## Verificación

```bash
apache2 -v
php -v
```

## Configuración del VirtualHost

```bash
sudo nano /etc/apache2/sites-available/empresa.conf
```

```apache
<VirtualHost *:80>
    ServerName empresa.local
    DocumentRoot /var/www/empresa
    ErrorLog ${APACHE_LOG_DIR}/empresa_error.log
</VirtualHost>
```

```bash
sudo a2ensite empresa.conf
sudo systemctl reload apache2
```
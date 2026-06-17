## Configuración de HAProxy

### Instalación

```bash
sudo apt install haproxy -y
```

### Configuración `/etc/haproxy/haproxy.cfg`

frontend http_front

bind *:80

default_backend apache_back
backend apache_back

balance roundrobin

server web1 127.0.0.1:8080 check

### Cambiar Apache al puerto 8080

```bash
sudo nano /etc/apache2/ports.conf
# Cambiar: Listen 80 → Listen 8080
sudo systemctl restart apache2
sudo systemctl restart haproxy
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
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
```
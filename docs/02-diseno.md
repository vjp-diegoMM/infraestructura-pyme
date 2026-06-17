# Diseño de Infraestructura

## Diagrama de red

Internet → [Firewall UFW] → [Servidor Ubuntu 22.04]

├── Apache 2.4

├── PHP 8.1

├── MySQL 8.0

└── Netdata (monitorización)

## Tabla de componentes

| Componente | Versión | Función |
|------------|---------|---------|
| Ubuntu Server | 22.04 LTS | Sistema operativo base |
| Apache  | 2.4.60 | Servidor web (versión actualizada) |
| PHP | 8.1 | Lenguaje del lado servidor |
| MySQL | 8.0 | Base de datos |
| Certbot | 2.9    | SSL/TLS automático                 |
| UFW | 0.36 | Firewall |
| Netdata | 1.44 | Monitorización |

## Arquitectura actualizada con HAProxy

Internet → [HAProxy :80/:443] → [Apache :8080]

└── PHP 8.1

└── MySQL 8.0

| Componente | Versión | Función |
|------------|---------|---------|
| HAProxy | 2.8 | Balanceador de carga |
| Apache | 2.4.60 | Servidor web (backend) |
| PHP | 8.1 | Backend |
| MySQL | 8.0 | Base de datos |
| Certbot | 2.9 | SSL/TLS |
| Netdata | 1.44 | Monitorización |
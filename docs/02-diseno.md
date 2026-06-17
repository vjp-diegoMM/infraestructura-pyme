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
| Apache | 2.4.60 | Servidor web |
| PHP | 8.1 | Lenguaje del lado servidor |
| MySQL | 8.0 | Base de datos |
| UFW | 0.36 | Firewall |
| Netdata | 1.44 | Monitorización |
## Reglas UFW

- Permitir SSH solo desde la red de la oficina:
  `ufw allow from 192.168.1.0/24 to any port 22`
- Permitir tráfico web:
  `ufw allow 80/tcp`
  `ufw allow 443/tcp`
## Reglas UFW

- Permitir SSH solo desde la red de la oficina:
  `ufw allow from 192.168.1.0/24 to any port 22`
- Permitir tráfico web:
  `ufw allow 80/tcp`
  `ufw allow 443/tcp`

  ## Configuración completa UFW

```bash
ufw default deny incoming
ufw default allow outgoing
ufw allow 22/tcp     # SSH administración
ufw allow 80,443/tcp # Tráfico web
ufw enable
ufw status verbose
```
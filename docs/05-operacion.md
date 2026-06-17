## Mantenimiento de HAProxy

```bash
# Estado del balanceador
systemctl status haproxy

# Estadísticas en tiempo real
echo "show stat" | socat stdio /var/run/haproxy/admin.sock

# Recargar configuración sin downtime
sudo systemctl reload haproxy
```


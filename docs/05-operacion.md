## Mantenimiento de HAProxy

```bash
# Estado del balanceador
systemctl status haproxy

# Estadísticas en tiempo real
echo "show stat" | socat stdio /var/run/haproxy/admin.sock

# Recargar configuración sin downtime
sudo systemctl reload haproxy
```

# Guía de Operación y Mantenimiento

## Tareas diarias
- Comprobar el panel de Netdata: `http://IP:19999`
- Verificar logs de Apache: `tail -n 50 /var/log/apache2/error.log`
- Confirmar que el backup nocturno se ejecutó correctamente

## Tareas semanales
- Revisar espacio en disco: `df -h`
- Actualizar paquetes del sistema:

```bash
sudo apt update && sudo apt upgrade -y
```

## Tareas mensuales
- Rotar credenciales de base de datos
- Revisar reglas de firewall: `sudo ufw status verbose`
- Verificar que los backups son restaurables

## Comandos de diagnóstico rápido

```bash
systemctl status apache2    # Estado del servidor web
systemctl status mysql      # Estado de la base de datos
netstat -tlnp               # Puertos en escucha
journalctl -xe              # Logs del sistema
```

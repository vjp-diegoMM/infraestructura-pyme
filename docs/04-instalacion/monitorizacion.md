# Monitorización con Netdata

## Instalación

```bash
bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```

## Acceso al panel
- URL: `http://IP_SERVIDOR:19999`
- No requiere autenticación en red local

## Métricas monitorizadas
- Uso de CPU y RAM
- Tráfico de red
- Espacio en disco
- Procesos activos (Apache, MySQL)

## Alertas
Netdata incluye alertas predefinidas. Para configurar notificaciones por email:

```bash
nano /etc/netdata/health_alarm_notify.conf
# Activar: SEND_EMAIL="YES"
# Configurar: DEFAULT_RECIPIENT_EMAIL="admin@empresa.com"
```
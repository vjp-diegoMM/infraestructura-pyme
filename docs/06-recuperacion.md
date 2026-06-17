# Plan de Recuperación ante Desastres

## Escenarios contemplados

### 1. Caída del servidor Apache
```bash
sudo systemctl restart apache2
# Si no arranca:
sudo apache2ctl configtest
sudo journalctl -u apache2 --no-pager
```

### 2. Corrupción de base de datos
```bash
# Restaurar desde backup
mysql -u root -p < /backups/FECHA/mysql_FECHA.sql
```

### 3. Pérdida total del servidor
1. Provisionar nuevo Ubuntu Server 22.04
2. Ejecutar instalación desde esta documentación (sesiones 01→04)
3. Restaurar backup más reciente de `/backups/`
4. Verificar conectividad y servicios

## RTO y RPO
| Métrica | Objetivo |
|---------|----------|
| RTO (tiempo de recuperación) | < 4 horas |
| RPO (pérdida máxima de datos) | < 24 horas |
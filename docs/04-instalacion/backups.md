# Política de Copias de Seguridad

## Estrategia
- **Base de datos:** `mysqldump` diario a las 02:00
- **Archivos web:** `rsync` diario a las 03:00
- **Rotación:** 7 copias diarias, 4 semanales

## Script de backup

```bash
#!/bin/bash
FECHA=$(date +%Y%m%d)
DEST="/backups/$FECHA"
mkdir -p "$DEST"

# Backup MySQL
mysqldump -u root -p'PASSWORD' --all-databases > "$DEST/mysql_$FECHA.sql"

# Backup archivos web
rsync -av /var/www/html/ "$DEST/www/"

# Rotación: borrar backups de más de 7 días
find /backups/ -maxdepth 1 -type d -mtime +7 -exec rm -rf {} \;
```

## Programación con cron

```bash
crontab -e
# Añadir:
0 2 * * * /scripts/backup.sh
```
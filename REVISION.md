# Revisión del Proyecto

## Conflictos encontrados y resolución

### Conflicto 1 — `02-diseno.md` (Sesión 2)
Ambos editamos la tabla de versiones de Apache simultáneamente.
Resolvimos con **merge manual**: conservamos la versión más nueva (2.4.60) y añadimos la fila de Certbot del compañero.

### Conflicto 2 — `ssh-firewall.md` (Sesión 3)
Ambos añadimos reglas UFW en la misma zona del archivo.
Resolvimos con **git rebase**: combinamos las dos versiones en una configuración más completa.

## Comandos Git más usados
- `git checkout -b` para crear ramas
- `git pull origin main` para sincronizar
- `git pull --rebase origin main` para resolver conflictos linealmente
- `git push --force-with-lease` tras rebase

## ¿Qué haríamos diferente?
- Comunicarnos antes de editar el mismo archivo
- Hacer `git pull` más frecuente para evitar divergencias
- Dividir mejor los archivos desde el principio

## Intercambio de roles
Fue útil: al trabajar en los archivos del compañero, descubrimos cosas que faltaban y mejoramos la coherencia global del proyecto.
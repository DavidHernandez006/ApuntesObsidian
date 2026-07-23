---
lenguaje: SQL
tipo: Concepto
nombre: Backup en SQL
fecha: 2026-07-22
estado: en progreso
tags:
  - apuntes
  - concepto
relacionado:
  - "[[normalización de tabla]]"
  - "[[SQL]]"
---

## 📌 Definición
> Un backup (respaldo) en SQL es una copia de seguridad de la base de datos o de una tabla específica, guardada en un archivo `.sql`, que permite restaurar la información en caso de pérdida, error o corrupción de datos.

## 🖥️ Sintaxis
```bash
mysqldump -u usuario -p nombre_basededatos > backup.sql
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `-u usuario` | flag | Sí | Usuario de MySQL con permisos sobre la base de datos. |
| `-p` | flag | Sí | Solicita la contraseña del usuario de forma interactiva. |
| `nombre_basededatos` | texto | Sí | Nombre de la base de datos (o tabla) a respaldar. |
| `> backup.sql` | redirección | Sí | Archivo donde se guarda el respaldo generado. |

## 💡 Ejemplos prácticos
```bash
-- ejemplo 1: respaldar todas las tablas de una base de datos
mysqldump -u root -p universidad_db > backup.sql
```

```bash
-- ejemplo 2: respaldar solo una tabla específica
mysqldump -u root -p universidad_db estudiantes > backup_tabla.sql
```

## 🧪 Casos de uso comunes
- Antes de hacer cambios grandes en la estructura de una tabla (migraciones, alter table).
- Como rutina periódica de seguridad en proyectos en producción.
- Para mover una base de datos completa de un servidor a otro.

## ⚠️ Errores comunes
- Olvidar la contraseña o los permisos correctos del usuario (`Access denied`).
- No verificar que el archivo `.sql` generado no esté vacío o corrupto antes de confiar en él como respaldo.
- Confundir el respaldo (`mysqldump`) con la restauración, que usa un comando distinto:
```bash
mysql -u usuario -p nombre_basededatos < backup.sql
```

## 🔗 Ver también
- [[normalización de tabla]]
- [[SQL]]

## 📚 Referencias
- 

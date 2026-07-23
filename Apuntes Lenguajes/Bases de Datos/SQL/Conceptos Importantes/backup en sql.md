comando guardar todas las tablas
mysqldump -u root -p universidad_db > backup.sql
comando guardar una tabla en especifica
mysqldump -u root -p universidad_db estudiantes > backup_tabla.sql
---
lenguaje: SQL
tipo: Concepto
nombre: comandos
fecha: 2026-07-27
estado: en progreso
tags:
  - apuntes
  - concepto
relacionado:
  - "[[SQL]]"
  - "[[ETIQUETAS EN SQL]]"
  - "[[backup en sql]]"
---

# Comandos SQL (categorías principales)

## 📌 Definición
> SQL agrupa sus comandos en cuatro grandes categorías según lo que hacen: definir la estructura de la base de datos (DDL), manipular los datos dentro de las tablas (DML), controlar los permisos de acceso (DCL) y controlar las transacciones (TCL).

![[comandos-categorias.svg]]

## 🖥️ Sintaxis
```sql
-- estructura general: [COMANDO] [OBJETO] [CONDICIONES];
COMANDO objeto
[WHERE condicion];
```

## 🧩 Categorías y comandos
| Categoría | Nombre completo | Comandos principales |
| --------- | ---------------- | --------------------- |
| **DDL** | Data Definition Language (definición de datos) | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` |
| **DML** | Data Manipulation Language (manipulación de datos) | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| **DCL** | Data Control Language (control de acceso) | `GRANT`, `REVOKE` |
| **TCL** | Transaction Control Language (control de transacciones) | `COMMIT`, `ROLLBACK`, `SAVEPOINT` |

## 🔧 Comandos importantes en detalle
| Comando | Qué hace | Ejemplo |
| ------- | -------- | ------- |
| `CREATE TABLE` | Crea una tabla nueva | `CREATE TABLE Clientes (id INT PRIMARY KEY, nombre VARCHAR(50));` |
| `ALTER TABLE` | Modifica la estructura de una tabla existente | `ALTER TABLE Clientes ADD email VARCHAR(100);` |
| `DROP TABLE` | Elimina una tabla completa (estructura y datos) | `DROP TABLE Clientes;` |
| `INSERT INTO` | Agrega filas nuevas a una tabla | `INSERT INTO Clientes VALUES (1, 'Ana');` |
| `UPDATE` | Modifica filas existentes | `UPDATE Clientes SET nombre='Ana Pérez' WHERE id=1;` |
| `DELETE` | Elimina filas de una tabla | `DELETE FROM Clientes WHERE id=1;` |
| `GRANT` | Otorga permisos a un usuario | `GRANT SELECT ON Clientes TO usuario1;` |
| `COMMIT` | Confirma de forma permanente los cambios de la transacción actual | `COMMIT;` |
| `ROLLBACK` | Deshace los cambios de la transacción actual | `ROLLBACK;` |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: crear una tabla y llenarla (DDL + DML)
CREATE TABLE Productos (id INT PRIMARY KEY, nombre VARCHAR(50), precio DECIMAL(10,2));
INSERT INTO Productos VALUES (1, 'Teclado', 89.90);
```

```sql
-- ejemplo 2: transacción segura con TCL
BEGIN;
UPDATE Cuentas SET saldo = saldo - 100 WHERE id = 1;
UPDATE Cuentas SET saldo = saldo + 100 WHERE id = 2;
COMMIT; -- si algo falla antes de esto, se puede hacer ROLLBACK
```

## 🧪 Casos de uso comunes
- DDL: al diseñar o modificar el esquema de la base de datos (crear tablas nuevas, agregar columnas).
- DML: en el día a día de una aplicación (leer, insertar, actualizar y borrar registros).
- DCL: cuando varias personas o roles acceden a la misma base de datos y hay que limitar qué puede hacer cada uno.
- TCL: en operaciones que deben ejecutarse todas juntas o ninguna (ej. una transferencia bancaria).

## ⚠️ Errores comunes
- Ejecutar `DROP TABLE` pensando que solo borra los datos (en realidad borra también la estructura; para solo borrar datos se usa `DELETE` o `TRUNCATE`).
- Olvidar el `WHERE` en un `UPDATE` o `DELETE`, lo que afecta **todas** las filas de la tabla.
- No usar `COMMIT`/`ROLLBACK` en motores que requieren confirmar la transacción explícitamente, dejando cambios "colgados".

## 🔗 Ver también
- [[SQL]]
- [[ETIQUETAS EN SQL]]
- [[backup en sql]]

## 📚 Referencias
- https://www.w3schools.com/sql/

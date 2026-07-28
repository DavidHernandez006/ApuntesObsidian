---
lenguaje: SQL
tipo: Concepto
nombre: Etiquetas en SQL (Alias)
fecha: 2026-07-27
estado: en progreso
tags:
  - apuntes
  - concepto
relacionado:
  - "[[SQL]]"
  - "[[Joins en tablas]]"
  - "[[comandos]]"
---

# Etiquetas en SQL (Alias)

## 📌 Definición
> Una etiqueta (o **alias**) en SQL es un nombre temporal y más corto o legible que se le da a una columna o a una tabla **solo dentro de una consulta**, usando la palabra clave `AS` (en muchos motores es opcional). No cambia el nombre real en la base de datos: solo afecta cómo se muestra el resultado o cómo se referencia la tabla dentro de esa misma consulta.

## 🖥️ Sintaxis
```sql
-- alias de columna
SELECT columna AS alias_columna
FROM tabla;

-- alias de tabla
SELECT alias_tabla.columna
FROM tabla AS alias_tabla;
```

## 🧩 Parámetros / Atributos
| Elemento | Obligatorio | Descripción |
| -------- | ----------- | ----------- |
| `AS` | No (implícito en la mayoría de motores) | Palabra clave que introduce el alias; se puede omitir escribiendo el alias directamente después del nombre original. |
| Alias de columna | No | Renombra el encabezado de una columna en el resultado, útil sobre todo con columnas calculadas. |
| Alias de tabla | No | Da un nombre corto a una tabla, muy útil cuando se combinan varias tablas con `JOIN`. |
| Comillas (`" "`) | Solo si el alias tiene espacios | Necesarias cuando el alias contiene espacios o caracteres especiales, ej. `AS "Nombre Completo"`. |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: alias de columna, útil con funciones/cálculos
SELECT nombre AS nombre_cliente, COUNT(*) AS total_pedidos
FROM Clientes
GROUP BY nombre;
```

```sql
-- ejemplo 2: alias de tabla, para acortar nombres en un JOIN
SELECT c.nombre, p.monto
FROM Clientes AS c
INNER JOIN Pedidos AS p ON c.id_cliente = p.id_cliente;
```

## 🧪 Casos de uso comunes
- Renombrar columnas calculadas o con funciones de agregación (`COUNT(*) AS total`, `AVG(nota) AS promedio`).
- Acortar nombres largos de tabla cuando hay varios `JOIN` en la misma consulta.
- Hacer más legibles los reportes o exportaciones que verá otra persona (nombres en español, con espacios, etc.).

## ⚠️ Errores comunes
- Intentar usar el alias de una columna dentro del `WHERE` de la misma consulta: no funciona en la mayoría de motores porque `WHERE` se evalúa antes que `SELECT` (sí se puede usar en `ORDER BY` o `GROUP BY`, dependiendo del motor).
- Olvidar las comillas en un alias con espacios, lo que genera un error de sintaxis.
- Confundir el alias (temporal, solo dentro de la consulta) con renombrar una columna de forma permanente, que se hace con `ALTER TABLE ... RENAME COLUMN`.

## 🔗 Ver también
- [[SQL]]
- [[Joins en tablas]]
- [[comandos]]

## 📚 Referencias
- https://www.w3schools.com/sql/sql_alias.asp

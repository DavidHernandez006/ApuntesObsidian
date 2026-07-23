---
lenguaje: SQL
categoria: apuntes
fecha: 2026-07-22
estado: en progreso
tags:
  - programacion
  - apuntes
  - concepto
tipo: Joins en tablas
nombre: Joins en tablas
relacionado:
  - "[[normalización de tabla]]"
  - "[[Count()]]"
  - "[[SQL]]"
---

# Joins en tablas

## 📌 Definición
> Un JOIN combina filas de dos o más tablas en base a una columna relacionada entre ellas (normalmente una clave primaria y una clave foránea). Sirve para reconstruir información que está separada en varias tablas por normalización.

## 🖥️ Sintaxis
```sql
SELECT columnas
FROM TablaA
[TIPO] JOIN TablaB ON TablaA.columna = TablaB.columna;
```

## 🧩 Tipos de JOIN
| Tipo         | Qué hace                                                                          | Ejemplo                                         |
| ------------ | --------------------------------------------------------------------------------- | ----------------------------------------------- |
| `INNER JOIN` | Devuelve solo las filas que coinciden en ambas tablas                             | Clientes que sí tienen pedidos                  |
| `LEFT JOIN`  | Devuelve todas las filas de la tabla izquierda, con `NULL` si no hay coincidencia | Todos los clientes, tengan o no pedidos         |
| `RIGHT JOIN` | Devuelve todas las filas de la tabla derecha, con `NULL` si no hay coincidencia   | Todos los pedidos, tengan o no cliente asociado |
| `FULL JOIN`  | Devuelve todas las filas de ambas tablas, coincidan o no                          | Todos los clientes y todos los pedidos          |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: uso básico - clientes con sus pedidos
SELECT Clientes.nombre, Pedidos.monto
FROM Clientes
INNER JOIN Pedidos ON Clientes.id_cliente = Pedidos.id_cliente;
```

```sql
-- ejemplo 2: caso más elaborado - incluir clientes sin pedidos
SELECT Clientes.nombre, Pedidos.monto
FROM Clientes
LEFT JOIN Pedidos ON Clientes.id_cliente = Pedidos.id_cliente
WHERE Pedidos.id_cliente IS NULL;
```

## 🧪 Casos de uso comunes
- Unir tablas relacionadas por clave foránea (Clientes-Pedidos, Estudiantes-Cursos).
- Encontrar registros huérfanos (ej. clientes que nunca han hecho un pedido) usando `LEFT JOIN` + `WHERE ... IS NULL`.
- Construir reportes que combinan datos de varias tablas normalizadas.

## ⚠️ Errores comunes
- Olvidar la condición `ON`, lo que genera un producto cartesiano (todas las combinaciones posibles).
- Confundir `LEFT JOIN` y `RIGHT JOIN` según el orden de las tablas en el `FROM`.
- No usar alias cuando las columnas se llaman igual en ambas tablas, causando ambigüedad.

## 🔗 Ver también
- [[normalización de tabla]]
- [[NOTACION DE CHEN]]
- [[Count()]]
- [[SQL]]


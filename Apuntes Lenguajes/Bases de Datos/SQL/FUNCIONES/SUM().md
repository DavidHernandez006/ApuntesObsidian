---
lenguaje: SQL
tipo: Funciones
nombre: Suma
fecha: 2026-07-23
estado: en progreso
tags:
  - apuntes
  - concepto
  - funciones
relacionado:
  - "[[Count()]]"
  - "[[AVG()]]"
  - "[[SQL]]"
---

## 📌 Definición
> SUM() es una función de agregación que suma todos los valores numéricos de una columna en las filas devueltas por una consulta.

## 🖥️ Sintaxis
```sql
SUM ( [ALL | DISTINCT] expresion )
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `expresion` | columna numérica | Sí | Columna cuyos valores se van a sumar. |
| `DISTINCT` | modificador | No | Suma solo los valores distintos, sin repetir. |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: total vendido en todos los pedidos
SELECT SUM(monto) AS total_ventas
FROM Pedidos;
```

```sql
-- ejemplo 2: total vendido por cada cliente
SELECT id_cliente, SUM(monto) AS total_gastado
FROM Pedidos
GROUP BY id_cliente;
```

## 🧪 Casos de uso comunes
- Calcular el total de ventas, ingresos o gastos.
- Sumar cantidades en inventario (ej. total de unidades vendidas).
- Combinado con `GROUP BY`, sumar por categoría (por cliente, por mes, por producto).

## ⚠️ Errores comunes
- Usarlo sobre una columna de texto (da error o resultado inesperado).
- Olvidar que `SUM()` ignora los valores `NULL` (no los cuenta como 0, simplemente los omite).
- No usar `GROUP BY` cuando se mezcla `SUM()` con otra columna no agregada en el `SELECT`.

## 🔗 Ver también
- [[Count()]]
- [[AVG()]]
- [[MAX() y MIN()]]
- [[SQL]]

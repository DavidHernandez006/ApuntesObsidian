---
lenguaje: SQL
tipo: Funciones
nombre: Conteo
fecha: 2026-07-23
estado: en progreso
tags:
  - apuntes
  - concepto
  - funciones
relacionado:
  - "[[SUM()]]"
  - "[[AVG()]]"
  - "[[MAX() y MIN()]]"
  - "[[SQL]]"
---

## 📌 Definición
> COUNT() es una función de agregación en SQL que sirve para contar el número de filas o registros que devuelve una consulta.

## 🖥️ Sintaxis
```sql
COUNT ( [ALL | DISTINCT] expresion | * )
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `*` | símbolo | No | Cuenta todas las filas, incluyendo las que tienen valores `NULL`. |
| `expresion` | columna | No | Cuenta solo las filas donde esa columna no es `NULL`. |
| `DISTINCT` | modificador | No | Cuenta únicamente los valores distintos (sin repetir) de la columna indicada. |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: Cuenta el total de clientes en la base de datos
SELECT COUNT(*) AS total_clientes
FROM Clientes;
```

```sql
-- ejemplo 2: caso más elaborado, contar clientes distintos por ciudad
SELECT ciudad, COUNT(DISTINCT id_cliente) AS clientes_unicos
FROM Clientes
GROUP BY ciudad;
```

## 🧪 Casos de uso comunes
- Saber cuántos registros hay en una tabla (por ejemplo, cuántos pedidos existen).
- Contar cuántos valores no nulos tiene una columna específica.
- Combinado con `GROUP BY`, saber cuántos registros hay por categoría (ej. cuántos productos por marca).

## ⚠️ Errores comunes
- Usar `COUNT(columna)` esperando que cuente los `NULL` (no los cuenta, solo `COUNT(*)` los incluye).
- Olvidar `GROUP BY` cuando se combina `COUNT()` con otra columna en el `SELECT`.
- Confundir `COUNT(DISTINCT columna)` con `COUNT(columna)`, dando resultados distintos si hay valores repetidos.

## 🔗 Ver también
- [[SUM()]]
- [[AVG()]]
- [[MAX() y MIN()]]
- [[SQL]]

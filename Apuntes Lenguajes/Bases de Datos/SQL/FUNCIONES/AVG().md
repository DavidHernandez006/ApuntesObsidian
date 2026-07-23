---
lenguaje: SQL
tipo: Funciones
nombre: Promedio
fecha: 2026-07-23
estado: en progreso
tags:
  - apuntes
  - concepto
  - funciones
relacionado:
  - "[[SUM()]]"
  - "[[Count()]]"
  - "[[SQL]]"
---

## 📌 Definición
> AVG() es una función de agregación que calcula el promedio (media aritmética) de los valores numéricos de una columna.

## 🖥️ Sintaxis
```sql
AVG ( [ALL | DISTINCT] expresion )
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `expresion` | columna numérica | Sí | Columna sobre la que se calcula el promedio. |
| `DISTINCT` | modificador | No | Calcula el promedio solo de los valores distintos. |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: promedio de notas de todos los estudiantes
SELECT AVG(nota) AS promedio_general
FROM Calificaciones;
```

```sql
-- ejemplo 2: promedio de nota por curso
SELECT id_curso, AVG(nota) AS promedio_curso
FROM Calificaciones
GROUP BY id_curso;
```

## 🧪 Casos de uso comunes
- Calcular el promedio de calificaciones, precios o edades.
- Comparar promedios entre grupos usando `GROUP BY`.
- Detectar valores muy por encima o por debajo del promedio (junto con `WHERE` o subconsultas).

## ⚠️ Errores comunes
- Ignorar que `AVG()` no toma en cuenta los `NULL` al calcular el promedio (no los trata como 0).
- Aplicarlo sobre columnas de texto.
- Esperar decimales exactos sin redondear (conviene usar `ROUND(AVG(columna), 2)`).

## 🔗 Ver también
- [[SUM()]]
- [[Count()]]
- [[MAX() y MIN()]]
- [[SQL]]

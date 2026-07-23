---
lenguaje: SQL
tipo: Funciones
nombre: Máximo y Mínimo
fecha: 2026-07-23
estado: en progreso
tags:
  - apuntes
  - concepto
  - funciones
relacionado: [[AVG()]], [[Count()]]
---

## 📌 Definición
> MAX() devuelve el valor más alto de una columna y MIN() devuelve el valor más bajo, entre las filas que devuelve una consulta. Funcionan con números, fechas y texto (orden alfabético).

## 🖥️ Sintaxis
```sql
MAX ( expresion )
MIN ( expresion )
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `expresion` | columna | Sí | Columna sobre la que se busca el valor máximo o mínimo. |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: producto más caro y más barato
SELECT MAX(precio) AS mas_caro, MIN(precio) AS mas_barato
FROM Productos;
```

```sql
-- ejemplo 2: fecha del pedido más reciente por cliente
SELECT id_cliente, MAX(fecha_pedido) AS ultimo_pedido
FROM Pedidos
GROUP BY id_cliente;
```

## 🧪 Casos de uso comunes
- Encontrar el precio más alto/bajo de un catálogo.
- Saber la fecha más reciente o más antigua de un registro (último login, primer pedido, etc.).
- Combinado con `GROUP BY`, encontrar el máximo/mínimo por categoría.

## ⚠️ Errores comunes
- Pensar que `MAX()`/`MIN()` filtran filas completas automáticamente (solo devuelven el valor, no la fila entera; para eso se necesita un `JOIN` o subconsulta).
- Aplicarlos sin `GROUP BY` cuando se necesita el máximo/mínimo por grupo.

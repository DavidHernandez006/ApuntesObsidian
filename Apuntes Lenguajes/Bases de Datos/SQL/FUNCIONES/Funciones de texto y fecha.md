---
lenguaje: SQL
tipo: Funciones
nombre: Funciones de texto y fecha
fecha: 2026-07-23
estado: en progreso
tags:
  - apuntes
  - concepto
  - funciones
relacionado:
  - "[[Count()]]"
  - "[[SQL]]"
---

## 📌 Definición
> Además de las funciones de agregación (COUNT, SUM, AVG, MAX, MIN), SQL tiene funciones que sirven para manipular texto y fechas directamente en las consultas.

## 🖥️ Sintaxis
```sql
UPPER(texto)
LOWER(texto)
CONCAT(texto1, texto2, ...)
NOW()
```

## 🧩 Parámetros / Atributos
| Nombre | Tipo | Obligatorio | Descripción |
| ------ | ---- | ----------- | ----------- |
| `texto` | string o columna | Sí | Texto o columna de tipo texto sobre el que se aplica la función. |
| `texto1, texto2` | string o columna | Sí | Valores a unir con `CONCAT`. |

## 🔧 Métodos u operaciones relacionadas
| Método | Qué hace | Ejemplo |
| ------ | -------- | ------- |
| `UPPER()` | Convierte texto a mayúsculas | `UPPER('hola')` → `'HOLA'` |
| `LOWER()` | Convierte texto a minúsculas | `LOWER('HOLA')` → `'hola'` |
| `CONCAT()` | Une dos o más textos/columnas | `CONCAT(nombre, ' ', apellido)` |
| `NOW()` | Devuelve la fecha y hora actual | `SELECT NOW();` |
| `DATEDIFF()` | Calcula la diferencia en días entre dos fechas | `DATEDIFF(fecha_entrega, fecha_pedido)` |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: nombre completo del cliente en mayúsculas
SELECT UPPER(CONCAT(nombre, ' ', apellido)) AS nombre_completo
FROM Clientes;
```

```sql
-- ejemplo 2: pedidos hechos en los últimos 7 días
SELECT *
FROM Pedidos
WHERE DATEDIFF(NOW(), fecha_pedido) <= 7;
```

## 🧪 Casos de uso comunes
- Formatear nombres o textos para mostrarlos de forma consistente (mayúsculas/minúsculas).
- Combinar columnas en un solo campo (nombre completo, dirección completa).
- Calcular antigüedad, plazos o tiempos entre fechas (ej. días desde el último pedido).

## ⚠️ Errores comunes
- El nombre exacto de estas funciones puede variar según el motor de base de datos (MySQL, PostgreSQL, SQL Server tienen pequeñas diferencias, sobre todo en funciones de fecha).
- Olvidar comillas simples en los literales de texto (`'hola'` en vez de `hola`).
- Confundir `NOW()` (fecha y hora) con `CURDATE()`/`CURRENT_DATE` (solo fecha).

## 🔗 Ver también
- [[Count()]]
- [[SQL]]

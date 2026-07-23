---
lenguaje: SQL
tipo: Concepto
nombre: Normalización de tablas
fecha: 2026-07-22
estado: en progreso
tags:
  - apuntes
  - concepto
relacionado:
  - "[[Joins en tablas]]"
  - "[[NOTACION DE CHEN]]"
  - "[[SQL]]"
---

# Normalización de tablas

## 📌 Definición
> La normalización es un proceso de diseño de bases de datos que organiza las tablas y columnas para reducir la redundancia (datos repetidos) y evitar problemas de inconsistencia al insertar, actualizar o borrar información. Se aplica dividiendo una tabla en varias tablas relacionadas mediante claves.

## 🖥️ Sintaxis
```
No aplica código directo: es un proceso de diseño, no un comando SQL.
```

## 🧩 Formas normales principales
| Forma                          | Qué exige                                                                                      | Ejemplo de problema que resuelve                                                     |
| ------------------------------ | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **1FN** (Primera Forma Normal) | Cada columna debe tener valores atómicos (no listas ni valores repetidos en una celda)         | Evitar guardar `"Juan, Pedro, Ana"` en una sola celda de teléfonos                   |
| **2FN** (Segunda Forma Normal) | Cumple 1FN y todos los atributos dependen de la clave primaria completa (no de solo una parte) | Evitar repetir el nombre del profesor en cada fila de un curso                       |
| **3FN** (Tercera Forma Normal) | Cumple 2FN y no hay dependencias entre columnas que no sean clave (dependencias transitivas)   | Evitar guardar la ciudad y el código postal cuando ya existe la ciudad en otra tabla |

## 💡 Ejemplos prácticos
```sql
-- ejemplo 1: tabla sin normalizar (repite datos del curso en cada fila)
-- Estudiante | Curso     | Profesor
-- Juan       | Bases     | Ana
-- Pedro      | Bases     | Ana

-- ejemplo 2: tabla normalizada (separada en dos tablas relacionadas)
CREATE TABLE Cursos (
    id_curso INT PRIMARY KEY,
    nombre_curso VARCHAR(50),
    profesor VARCHAR(50)
);

CREATE TABLE Estudiantes_Cursos (
    id_estudiante INT,
    id_curso INT,
    FOREIGN KEY (id_curso) REFERENCES Cursos(id_curso)
);
```

## 🧪 Casos de uso comunes
- Diseñar una base de datos desde cero, partiendo de un modelo entidad-relación (ver [[NOTACION DE CHEN]]).
- Detectar y corregir tablas con datos repetidos o inconsistentes en un sistema ya existente.
- Preparar la base para usar `JOIN` entre tablas relacionadas en vez de tener todo en una sola tabla gigante.

## ⚠️ Errores comunes
- Sobre-normalizar (crear demasiadas tablas pequeñas), lo que complica las consultas con muchos `JOIN` innecesarios.
- No normalizar nada, lo que genera redundancia y riesgo de inconsistencia (ej. actualizar el nombre de un profesor en una fila y olvidarlo en otras).
- Confundir normalización con indexación: son conceptos distintos (una organiza los datos, la otra optimiza la búsqueda).

## 🔗 Ver también
- [[Joins en tablas]]
- [[NOTACION DE CHEN]]
- [[backup en sql]]
- [[SQL]]


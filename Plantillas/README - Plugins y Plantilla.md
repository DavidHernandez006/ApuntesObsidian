---
lenguaje:
categoria: apuntes
fecha: 2026-07-08
estado: en progreso
tags:
  - programacion
---

# README - Plugins y Plantilla

## 📌 Resumen
> Breve descripción de qué es y para qué se usa.

## 🧠 Conceptos clave
- 
- 
- 

## 🖥️ Sintaxis básica
```
// escribe aquí el código de ejemplo
```

## 🔧 Comandos / Funciones importantes
| Comando | Qué hace | Ejemplo |
| ------- | -------- | ------- |
|         |          |         |

## 💡 Ejemplos prácticos
```
// ejemplo 1
```

## ⚠️ Errores comunes
- 

## 🔗 Notas relacionadas
- [[]]

## 📚 Fuentes / Referencias
- 
# Plugins y plantilla agregados

## Plugins instalados (además de Obsidian Git, que ya tenías)

- **Templater**: permite crear plantillas dinámicas (fechas automáticas, título del archivo, cursores inteligentes). Es la base para que la plantilla de apuntes funcione.
- **Dataview**: permite hacer consultas sobre tus notas usando los metadatos (por ejemplo: listar todos los lenguajes con estado "en progreso", o generar una tabla con todos tus apuntes ordenados por fecha).
- **Advanced Tables (table-editor-obsidian)**: facilita crear y editar tablas en Markdown con atajos de teclado (Tab para moverte entre celdas, autoformateo). Útil para las tablas de comandos/funciones de cada lenguaje.

Al abrir el vault en Obsidian, los tres plugins ya deberían aparecer habilitados en **Configuración → Community plugins**. Si Obsidian pide confirmación de seguridad la primera vez, es normal (son plugins de código abierto descargados directo de sus repositorios oficiales en GitHub).

## Plantilla: "Plantilla - Apuntes de Lenguaje.md"

Ya está configurada como plantilla por defecto para cualquier nota nueva dentro de la carpeta `Apuntes Lenguajes` (vía Templater → Folder Templates).

Estructura de la plantilla:
- **Frontmatter**: lenguaje, categoría, fecha automática, estado, tags (para poder filtrar después con Dataview)
- Resumen
- Conceptos clave
- Sintaxis básica
- Comandos / Funciones importantes (tabla)
- Ejemplos prácticos
- Errores comunes
- Notas relacionadas (enlaces internos)
- Fuentes / Referencias

## Ejemplo de consulta con Dataview

Para listar todos tus apuntes de lenguajes en una tabla, puedes crear una nota y pegar esto:

```dataview
TABLE lenguaje, estado, fecha
FROM "Apuntes Lenguajes"
SORT fecha DESC
```

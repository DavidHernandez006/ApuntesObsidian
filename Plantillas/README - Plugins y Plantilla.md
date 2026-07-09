# Plugins y plantilla agregados

## Plugins instalados (además de Obsidian Git, que ya tenías)

- **Templater**: permite crear plantillas dinámicas (fechas automáticas, título del archivo, cursores inteligentes). Es la base para que la plantilla de apuntes funcione.
- **Dataview**: permite hacer consultas sobre tus notas usando los metadatos (por ejemplo: listar todos los lenguajes con estado "en progreso", o generar una tabla con todos tus apuntes ordenados por fecha).
- **Advanced Tables (table-editor-obsidian)**: facilita crear y editar tablas en Markdown con atajos de teclado (Tab para moverte entre celdas, autoformateo). Útil para las tablas de comandos/funciones de cada lenguaje.

Al abrir el vault en Obsidian, los tres plugins ya deberían aparecer habilitados en **Configuración → Community plugins**. Si Obsidian pide confirmación de seguridad la primera vez, es normal (son plugins de código abierto descargados directo de sus repositorios oficiales en GitHub).

## Plantilla 1: "Plantilla - Apuntes de Lenguaje.md" (introducción)

Ya está configurada como plantilla por defecto para cualquier nota nueva dentro de la carpeta `Apuntes Lenguajes` (vía Templater → Folder Templates). Úsala para presentar un lenguaje de forma **concisa**, sin profundizar: es la puerta de entrada.

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

## Plantilla 2: "Plantilla - Concepto de Lenguaje.md" (a detalle)

Pensada para profundizar en **un solo concepto por nota**: una función, una clase, una lista, un array, un diccionario, un método, etc. Es el complemento de la plantilla de introducción — mientras esa da el panorama general del lenguaje, esta te sirve para ir a fondo en cada pieza.

Estructura:
- **Frontmatter**: lenguaje, tipo de concepto, nombre, fecha, estado, tags, relacionado
- Definición
- Sintaxis
- Parámetros / Atributos (tabla)
- Métodos u operaciones relacionadas (tabla) — útil sobre todo en clases, listas, arrays y diccionarios
- Ejemplos prácticos (más de uno)
- Casos de uso comunes
- Errores comunes
- Ver también (enlaces a notas relacionadas, incluyendo la nota de introducción del lenguaje)
- Referencias

**Cómo usarla**: como esta plantilla no está asignada a una carpeta fija (porque cada nota de concepto puede vivir donde tú organices tus apuntes, ej. `Apuntes Lenguajes/Python/append.md`), insértala manualmente:
1. Crea la nota nueva (vacía)
2. Abre la paleta de comandos (`Ctrl/Cmd + P`)
3. Busca `Templater: Insert Template`
4. Selecciona `Plantilla - Concepto de Lenguaje.md`

Si organizas cada lenguaje en su propia subcarpeta (ej. `Apuntes Lenguajes/Python/`), puedo configurar esa subcarpeta para que use esta plantilla automáticamente — solo avísame la estructura que quieres.

## Ejemplo de consulta con Dataview

Para listar todos tus apuntes de lenguajes en una tabla, puedes crear una nota y pegar esto:

```dataview
TABLE lenguaje, estado, fecha
FROM "Apuntes Lenguajes"
SORT fecha DESC
```

---
lenguaje: Python
categoria: apuntes
fecha: 2026-07-08
estado: en progreso
tags:
  - programacion
---

# Python

## 📌 ¿Qué es y para que sirve?
> Python es un lenguaje de programación interpretado, de alto nivel y de propósito general. Se usa para desarrollo web (Django, Flask), análisis de datos, automatización de tareas, inteligencia artificial, scripting y aplicaciones de escritorio. Su sintaxis es muy legible, lo que lo hace popular para aprender a programar.

## 🧠 Conceptos clave
- **Interpretado**: no se compila a un ejecutable, se ejecuta línea por línea con el intérprete de Python.
- **Tipado dinámico**: no hay que declarar el tipo de una variable, Python lo infiere en tiempo de ejecución.
- **Indentación obligatoria**: los bloques de código (if, for, funciones, etc.) se definen por espacios/tabulaciones, no por llaves `{}`.

## 🖥️ Sintaxis básica
```python
# Variables
nombre = "David"
edad = 20

# Condicional
if edad >= 18:
    print("Es mayor de edad")
else:
    print("Es menor de edad")

# Ciclo for
for i in range(3):
    print(i)

# Función
def saludar(nombre):
    return f"Hola, {nombre}"

print(saludar("David"))
```

## 🔧 Comandos / Funciones importantes
| Comando | Qué hace | Ejemplo |
| ------- | -------- | ------- |
| `print()` | Muestra datos en consola | `print("Hola mundo")` |
| `len()` | Devuelve el tamaño de una lista, string, etc. | `len("Python")` → `6` |
| `range()` | Genera una secuencia de números | `for i in range(5):` |
| `input()` | Recibe texto que escribe el usuario | `nombre = input("Nombre: ")` |
| `type()` | Muestra el tipo de dato de una variable | `type(5)` → `<class 'int'>` |
| `append()` | Agrega un elemento al final de una lista | `lista.append(4)` |
| `sorted()` | Ordena una lista o iterable | `sorted([3,1,2])` → `[1,2,3]` |
| `str()`, `int()`, `float()` | Convierten entre tipos de dato | `int("5")` → `5` |

## 💡 Ejemplos prácticos
```python
# ejemplo 1: lista de números pares
numeros = [1, 2, 3, 4, 5, 6]
pares = [n for n in numeros if n % 2 == 0]
print(pares)  # [2, 4, 6]
```

```python
# ejemplo 2: función que calcula el promedio de una lista
def promedio(lista):
    return sum(lista) / len(lista)

notas = [4.5, 3.8, 5.0]
print(promedio(notas))  # 4.433...
```

## ⚠️ Errores comunes
- Mezclar espacios y tabulaciones en la indentación (provoca `IndentationError`).
- Olvidar los dos puntos `:` al final de `if`, `for`, `while` o al definir funciones.
- Comparar tipos distintos sin convertir (`"5" == 5` da `False`).
- Modificar una lista mientras se itera sobre ella con un `for`.

## 🔗 Notas relacionadas
- [[Java]]
- [[API]]

## 📚 Fuentes / Referencias
- https://docs.python.org/es/3/

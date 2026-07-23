---
lenguaje: Java
categoria: apuntes
fecha: 2026-07-08
estado: en progreso
tags:
  - programacion
---

# Java

## 📌 Resumen
> Java es un lenguaje de programación orientado a objetos, de propósito general y fuertemente tipado. Se compila a bytecode que corre sobre la JVM (Java Virtual Machine), lo que le permite ejecutarse en cualquier sistema operativo ("write once, run anywhere"). Se usa mucho en aplicaciones empresariales, backend, Android y sistemas grandes.

## 🧠 Conceptos clave
- **Orientado a objetos**: todo se organiza en clases y objetos (encapsulamiento, herencia, polimorfismo).
- **Tipado estático y fuerte**: hay que declarar el tipo de cada variable y no puede cambiar en tiempo de ejecución.
- **JVM (Java Virtual Machine)**: máquina virtual que ejecuta el bytecode generado al compilar (`.class`), lo que hace a Java portable entre sistemas operativos.

## 🖥️ Sintaxis básica
```java
public class Main {
    public static void main(String[] args) {
        String nombre = "David";
        int edad = 20;

        if (edad >= 18) {
            System.out.println("Es mayor de edad");
        } else {
            System.out.println("Es menor de edad");
        }

        for (int i = 0; i < 3; i++) {
            System.out.println(i);
        }
    }
}
```

## 🔧 Comandos / Funciones importantes
| Comando | Qué hace | Ejemplo |
| ------- | -------- | ------- |
| `System.out.println()` | Imprime texto en consola con salto de línea | `System.out.println("Hola");` |
| `.length()` | Devuelve el tamaño de un String | `"Java".length()` → `4` |
| `.length` | Devuelve el tamaño de un array (sin paréntesis) | `arreglo.length` |
| `Scanner` | Lee datos ingresados por el usuario | `Scanner sc = new Scanner(System.in);` |
| `.equals()` | Compara el contenido de dos objetos/Strings | `"a".equals("a")` → `true` |
| `.size()` | Devuelve el tamaño de una lista (`ArrayList`, etc.) | `lista.size()` |
| `Integer.parseInt()` | Convierte un String a número entero | `Integer.parseInt("5")` → `5` |

## 💡 Ejemplos prácticos
```java
// ejemplo 1: recorrer un arreglo
int[] numeros = {1, 2, 3, 4, 5};
for (int n : numeros) {
    System.out.println(n);
}
```

```java
// ejemplo 2: método que calcula el promedio de un arreglo
public static double promedio(int[] notas) {
    int suma = 0;
    for (int n : notas) {
        suma += n;
    }
    return (double) suma / notas.length;
}
```

## ⚠️ Errores comunes
- Usar `==` para comparar Strings en vez de `.equals()` (compara referencias, no contenido).
- Olvidar el punto y coma `;` al final de cada instrucción.
- Confundir mayúsculas/minúsculas en nombres de clases (Java es sensible a mayúsculas).
- No cerrar correctamente las llaves `{}` de clases, métodos o bloques condicionales.

## 🔗 Notas relacionadas
- [[Python]]
- [[API]]

## 📚 Fuentes / Referencias
- https://docs.oracle.com/javase/tutorial/

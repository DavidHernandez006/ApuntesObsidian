---
Lenguaje: SQL
categoria: apuntes
fecha:
estado: en progreso
tags:
  - programacion
---
## 📌¿QUÉ ES Y PARA QUE SE USA?
SQL ( STRUCTURED QUERY LENGUGAGE ) -  LENGUAJE DE CONSULTA ESTRUCTURADO
-Base de datos que permite hacer consultas masivamente donde realiza operaciones (CRUD) como 
-CREATE: Crear o insertar nuevos datos. (Como registrar un nuevo usuario)
-READ: Leer o consultar y extraer información. (Como ver la lista de productos mas vendidos)
-UPDATE: Actualizar o modificar datos existentes. (Cambiar un dato existente)
-DELETE: Borrar o eliminar registros  (Eliminar un registro, cuenta, numero o correo)

## CATEGORIAS FUNDAMENTALES DE COMANDOS EN SQL

| DML | Lenguaje modelado de datos           |
| --- | ------------------------------------ |
| DDL | lenguaje de definicion de datos      |
| DCL | lenguaje de control de datos         |
| TCL | lenguaje de control de transacciones |

## LA ESTRUCTURA DE LOS DATOS

## 1. La Estructura de los Datos

En SQL, la información no está flotando en el aire; se organiza de forma muy estricta en una jerarquía:

- **Base de datos (Database):** Es el contenedor principal. Imagínalo como el edificio de una gran biblioteca.
    
- **Tablas (Tables):** Son los "estantes" o carpetas dentro de la base de datos. Cada tabla guarda información sobre un tema específico (por ejemplo, una tabla de `Clientes`, otra de `Productos` y otra de `Pedidos`).
    
- **Columnas / Campos (Columns / Fields):** Son las categorías de información que definen a la tabla. Representan las características verticales (por ejemplo: `Nombre`, `Email`, `Fecha de nacimiento`).
    
- **Filas / Registros (Rows / Records):** Es cada elemento individual de la tabla. Representan los datos horizontales completos de un sujeto (por ejemplo, los datos específicos del cliente "Juan Pérez").
    

## 2. Claves (Keys): Los puentes entre datos

Como las bases de datos están compuestas por muchas tablas, necesitamos una forma de conectarlas entre sí sin que se mezclen los datos. Para eso usamos las **Claves**:

- **Clave Primaria (Primary Key - PK):** Es el identificador único e irrepetible de cada fila en una tabla. Piensa en ella como el número de cédula, DNI o el ID de usuario. No puede haber dos clientes con el mismo ID.
    
- **Clave Foránea o Extranjera (Foreign Key - FK):** Es una columna en una tabla que se conecta con la Clave Primaria de _otra_ tabla. Es el "ancla" que une ambas tablas. Por ejemplo, en la tabla `Pedidos`, guardas el `ID_Cliente` para saber exactamente quién hizo la compra sin tener que volver a escribir todo su nombre y dirección.
    

## 3. Relaciones (Relationships)

Gracias a las claves, las tablas pueden relacionarse entre sí. Existen tres tipos de relaciones fundamentales:

- **Uno a Uno (1:1):** Un registro de la Tabla A se relaciona con solo un registro de la Tabla B. _(Ejemplo: Un `Usuario` tiene un solo `Perfil` de preferencias)._
    
- **Uno a Muchos (1:N):** El tipo más común. Un registro de la Tabla A se relaciona con muchos de la Tabla B. _(Ejemplo: Un `Cliente` puede realizar muchos `Pedidos`, pero cada pedido pertenece a un solo cliente)._
    
- **Muchos a Muchos (N:M):** Muchos registros de la Tabla A se relacionan con muchos de la Tabla B. _(Ejemplo: Muchos `Estudiantes` pueden inscribirse en muchos `Cursos`). En la práctica, esto se resuelve creando una tabla intermedia._
    

## 4. Tipos de Datos (Data Types)

Cada columna en SQL debe tener definido qué tipo de información va a guardar. Esto evita errores (como intentar sumar un texto a un número). Los más comunes son:

| **Tipo de Datos**   | **¿Para qué sirve?**                  | **Ejemplo**                           |
| ------------------- | ------------------------------------- | ------------------------------------- |
| **INT / INTEGER**   | Números enteros sin decimales.        | `Edad: 28`, `ID: 504`                 |
| **DECIMAL / FLOAT** | Números con decimales precisos.       | `Precio: 19.99`                       |
| **VARCHAR / CHAR**  | Texto (letras, números y símbolos).   | `Nombre: 'María'`, `Email: 'a@b.com'` |
| **DATE / DATETIME** | Fechas y horas.                       | `Fecha_Compra: '2026-07-09'`          |
| **BOOLEAN**         | Valores lógicos de verdadero o falso. | `Activo: TRUE`                        |

## 5. El Lenguaje: Los subconjuntos de SQL

Cuando escribes en SQL, tus comandos se dividen en diferentes "familias" según lo que le estás pidiendo al sistema:

- **DDL (Data Definition Language):** Sirve para definir la estructura (crear el cascarón). Comandos: `CREATE TABLE` (crear tabla), `ALTER TABLE` (modificar tabla).
    
- **DML (Data Manipulation Language):** Sirve para gestionar los datos que están dentro de esa estructura. Comandos: `SELECT` (buscar), `INSERT` (añadir), `UPDATE` (modificar), `DELETE` (borrar).
    




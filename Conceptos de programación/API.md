---
concepto: API
categoria: Conceptos Programación
fecha: 2026-07-23
tags:
  - programacion
  - dev
  - conceptos
nivel: básico-intermedio
estado: en-progreso
---

# 💻 API (Application Programming Interface)

## 🧠 ¿Qué es?
> Una API es un conjunto de reglas y funciones que permite que dos programas o servicios se comuniquen entre sí, sin que uno necesite conocer los detalles internos del otro. Define qué datos se pueden pedir, cómo pedirlos y qué respuesta se recibe.

## 🎯 ¿Para qué sirve / qué problema resuelve?

Se utiliza como un medio de transporte de datos o información hacia diferentes tipos de servicios (aplicaciones, páginas web o bases de datos) sin necesidad de conocer su funcionamiento.
> Es como un traductor o un mensajero que permite que una aplicación pida algo a otra aplicación y reciba una respuesta, sin necesidad de saber cómo funciona el "motor" interno de la otra.

Resuelve el problema de tener que reconstruir funcionalidades ya existentes (por ejemplo, un mapa, un sistema de pagos o el clima) y permite que distintos sistemas, escritos incluso en lenguajes diferentes, se conecten entre sí.

## 🏢 ¿Dónde y quién lo usa en la vida real?
> Empresas, roles o tipos de proyecto donde es común encontrarlo.

- Desarrolladores backend, que exponen APIs para que apps móviles o webs consuman datos.
- Desarrolladores frontend, que consumen APIs para mostrar información en pantalla (clima, mapas, pagos).
- Empresas como Google Maps, Spotify o pasarelas de pago (Stripe, PayPal) que ofrecen APIs públicas para que otros desarrolladores las integren.

## ⚙️ ¿Cómo funciona? (a alto nivel)

1. El cliente (una app, un navegador) hace una **petición** (request) a una URL específica de la API, indicando qué quiere (ej. "dame el clima de Bogotá").
2. La API recibe esa petición, la procesa (a veces consulta una base de datos) y genera una **respuesta** (response), normalmente en formato JSON.
3. El cliente recibe la respuesta y la usa para mostrar la información al usuario final.

Las APIs web más comunes siguen el estilo **REST**, que usa verbos HTTP (`GET`, `POST`, `PUT`, `DELETE`) para representar acciones sobre los datos (leer, crear, actualizar, borrar).

## 🧾 Ejemplo práctico
```javascript
// Ejemplo: consumir una API pública de clima con fetch en JavaScript
fetch("https://api.ejemplo.com/clima?ciudad=Bogota")
  .then(respuesta => respuesta.json())
  .then(datos => console.log(datos.temperatura))
  .catch(error => console.error("Error al consultar la API:", error));
```

## 🔧 Herramientas / tecnologías relacionadas
- **JSON**: formato de datos más usado para las respuestas de una API.
- **Postman / Insomnia**: herramientas para probar peticiones a una API sin escribir código.
- **REST** y **GraphQL**: dos estilos distintos de diseñar APIs.
- **HTTP**: protocolo sobre el que viajan la mayoría de las peticiones de una API web.

## ✅ Ventajas
- Permite reutilizar funcionalidades sin reinventarlas (ej. no programar un sistema de mapas desde cero).
- Facilita que distintos sistemas y lenguajes se comuniquen entre sí.
- Separa el frontend del backend: cada uno puede cambiar internamente sin romper al otro, mientras la API se mantenga igual.

## ⚠️ Desventajas / limitaciones
- Depende de que el servicio externo esté disponible (si la API cae, la app que la consume también se ve afectada).
- Puede tener límites de uso (rate limits) o requerir pago según la cantidad de peticiones.
- Requiere manejar errores de red, tiempos de espera y cambios de versión de la API.

## 🆚 Comparación con conceptos similares
| Concepto | Diferencia clave |
|---|---|
| API vs SDK | La API define cómo comunicarse; el SDK es un conjunto de herramientas/librerías listas para usar esa API más fácilmente. |
| REST vs GraphQL | REST expone varios endpoints fijos; GraphQL usa un solo endpoint donde el cliente pide exactamente los datos que necesita. |
| API vs Webhook | La API se consulta cuando el cliente lo pide; el webhook es el servidor el que avisa al cliente cuando ocurre un evento. |

## 🔗 Conceptos relacionados
- [[Python]]
- [[Java]]

## ❓ Preguntas de entrevista / autoevaluación
1. ¿Qué diferencia hay entre una API REST y una API GraphQL?
2. ¿Qué significan los verbos HTTP `GET`, `POST`, `PUT` y `DELETE` en el contexto de una API?
3. ¿Por qué es importante manejar los errores al consumir una API externa?

## 📚 Fuentes / documentación oficial
- 

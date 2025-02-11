# **APIs REST: Todo lo que necesitas saber🔥**  

## 🚀 **¿Qué es una API?**  

### ¿API?
Una **API** (Application Programming Interface) es un conjunto de reglas y protocolos que permite que diferentes aplicaciones se comuniquen entre sí. Actúa como un intermediario que facilita el intercambio de información entre sistemas.


### 📌 **¿Por qué son clave en el desarrollo?**  
✅ Te ahorran tiempo y esfuerzo.  
✅ Hacen que sistemas diferentes se entiendan entre sí.  
✅ Son la base de las apps modernas (redes sociales, pasarelas de pago, geolocalización).  

---

## 🔄 **¿Qué significa REST?**  

**REST** (Representational State Transfer) es un conjunto de principios arquitectónicos que permite el desarrollo de servicios web escalables y eficientes. Una **API REST** sigue estos principios para estructurar la comunicación entre cliente y servidor de forma sencilla y organizada.


### 🎯 **Principios de REST:**  
- **Cliente-Servidor:** Separa la interfaz de usuario (frontend) del procesamiento de datos (backend).  
- **Stateless (Sin estado):** Cada solicitud es independiente, el servidor no recuerda datos de peticiones anteriores.  
- **Caché:** Se pueden almacenar respuestas para mejorar rendimiento.  
- **Interfaz uniforme:** Reglas claras sobre cómo se estructuran las peticiones y respuestas.  
- **Sistema en capas:** Puedes meter intermediarios (como proxies o gateways) sin que afecte al cliente.  

Básicamente, REST busca que todo fluya sin fricciones.  

---

## 🌍 **APIs Locales vs. Remotas**  

- **APIs Locales:** Se ejecutan en el mismo sistema (Ej: una API para gestionar archivos en tu PC).  
- **APIs Remotas:** Se comunican con servidores externos a través de internet (Ej: API de clima, pagos, mapas).  

La mayoría de APIs REST modernas son **remotas**.  

---

## 📡 **Estructura de una API REST**  

Cuando consumes una API REST, interactúas con estos elementos:  

- **Cliente:** Quien hace la petición (puede ser una app, una web o Postman).  
- **Servidor:** Procesa la solicitud y devuelve una respuesta.  
- **Recursos:** Datos expuestos en la API (usuarios, productos, etc.).  
- **Endpoints:** URLs que permiten acceder a los recursos.  
- **Métodos HTTP:** Definen qué acción ejecutar sobre el recurso.  
- **Formato de datos:** JSON es el más usado porque es ligero y fácil de leer.  

---

## 📬 **Métodos HTTP y sus funciones**  

Las APIs REST usan los métodos HTTP para definir qué hacer con los datos:  

- **GET:** Recuperar datos (Ej: obtener un usuario).  
- **POST:** Crear un nuevo recurso (Ej: registrar un usuario).  
- **PUT:** Actualizar un recurso existente (Ej: modificar el email de un usuario).  
- **DELETE:** Borrar un recurso (Ej: eliminar un usuario).  

Nada de inventar nuevos métodos, REST ya te da las herramientas necesarias.  

---

## 🚦 **Códigos de estado HTTP**  

Cuando haces una petición, el servidor responde con un código que indica el resultado:  

✅ **2xx (Éxito)**  
- `200 OK`: Todo bien.  
- `201 Created`: Recurso creado correctamente.  
- `204 No Content`: Se procesó la solicitud, pero no hay contenido para devolver.  

⚠️ **4xx (Errores del cliente)**  
- `400 Bad Request`: Algo hiciste mal en la solicitud.  
- `401 Unauthorized`: Te falta autenticación.  
- `403 Forbidden`: No tienes permisos.  
- `404 Not Found`: El recurso no existe.  

❌ **5xx (Errores del servidor)**  
- `500 Internal Server Error`: Algo falló en el servidor.  
- `502 Bad Gateway`: Problema con un servidor intermedio.  
- `503 Service Unavailable`: Servidor fuera de servicio temporalmente.  

Si ves un **500**, alguien en backend está sufriendo.  

---

## 🛠️ **Formatos de Datos: JSON vs XML**  

**JSON (JavaScript Object Notation)**  
✅ Ligero y fácil de leer.  
✅ Compatible con casi todos los lenguajes.  
✅ Más eficiente en rendimiento.  

**XML (Extensible Markup Language)**  
⚠️ Más pesado.  
⚠️ Se usaba más antes, pero ha sido reemplazado por JSON en la mayoría de casos.  

💡 **Conclusión:** Usa **JSON**, a menos que un dinosaurio te obligue a usar XML.  

---
> [!WARNING]
> ## 🔐 **Seguridad en APIs REST**
>
> Si no proteges tu API, alguien se meterá y hará desastre. Aquí van algunas reglas básicas:
>
> - **Autenticación y Tokens (JWT, OAuth)**  
>     Un token es como una llave que verifica quién eres.  
>    **JWT (JSON Web Token)** es de los más usados porque es rápido y seguro.  
>
>- **HTTPS Siempre**  
>   No uses HTTP, los datos deben viajar cifrados con SSL/TLS.  
>
>- **Rate Limiting**  
>   Evita abusos limitando la cantidad de peticiones por usuario en un tiempo determinado.  
>
>- **No exponer datos sensibles en la URL**  
>    ❌ `GET /users?password=123456`  
>    ✅ `POST /login` con los datos en el **body**  
>
>- **Control de permisos (Roles y Scopes)**  
>    No todos los usuarios deben tener acceso a todo.  
>
>Si sigues estas prácticas, evitas que alguien borre tu base de datos "por accidente".  

---

## 🔥 **Buenas Prácticas al Construir una API REST**  

✅ **Documenta todo** (Swagger es tu amigo).  
✅ **Estructura bien los endpoints** (`/users` en lugar de `/getUsers`).  
✅ **Usa versionado** (`/api/v1/users`).  
✅ **Retorna mensajes claros de error**, no un simple `500`.  
✅ **Optimiza las consultas** para evitar respuestas pesadas.  
✅ **Piensa en la escalabilidad** desde el inicio.  

Hacerlo bien desde el principio te ahorrará dolores de cabeza después.  

---
## 🔍 Ejemplo: API de Pokémon
Podemos obtener datos sobre Pokémon a través de la API pública [PokéAPI](https://pokeapi.co/).

Ejemplo de solicitud para obtener información de Pikachu:
```bash
GET https://pokeapi.co/api/v2/pokemon/pikachu
```
Respuesta (formato JSON):
```json
{
  "name": "pikachu",
  "id": 25,
  "height": 4,
  "weight": 60,
  "types": [
    {
      "type": {
        "name": "electric"
      }
    }
  ]
}
```
<table>
<tr>
<td>
<img height="450" src="https://media.giphy.com/media/lM86pZcDxfx5e/giphy.gif?cid=ecf05e4729reyarjodclfy2u7un2yh5o1wxa70rl1s9wsz3r&ep=v1_gifs_search&rid=giphy.gif&ct=g)" align="center">
</td>
</tr>
</table>

---

> [!IMPORTANT]
> ## 🎯 **Conclusión**
> Las **APIs REST son la columna vertebral de la web moderna**. Sin ellas, no existirían muchas de las apps y plataformas que usamos a diario.
> Si sigues los principios y buenas prácticas que te mencioné, no solo construirás una API funcional, sino una API **robusta, segura y escalable**.  

---
## 📚 Recursos
- [Swagger Editor](https://editor.swagger.io/)
- [Open Gateway Telefónica - Sandbox](https://opengateway.telefonica.com/perfil/technical-toolbox/sandbox)

---

> [!TIP]
> Siempre prueba tus endpoints con herramientas como Postman o Insomnia antes de lanzar tu API al mundo. ¡La prevención es clave! 🛡️


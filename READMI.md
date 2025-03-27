
<h1 align="center">
  <img src="https://img.shields.io/static/v1?label=&message=Spring-Boot&color=grey&logo=spring" alt="Spring Boot" width="200">
</h1>



# ¿Cómo funciona la web?

* La "Web" se basa en  __peticiones o consultas__   que hace un <u>cliente</u> hacia un <u>servidor</u>.
* Ese  __Cliente__  se comunica con un  __Servidor__ , mediante un  __Protocolo__ que se llama __HTTP__ o Protocolo de transferencia de hipertexto.
* Mediante este protocolo, el cliente realiza consultas (__Request__) y recibe respuestas (__responses__).

### Cliente y Servidores

| Clientes                                                                                                                      | Servidores |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------|
| En una arquitectura Cliente-servidor, un navegador es la mejor representación de un cliente que solicita pedidos a un seridor |Un servidor web o servidor HTTP representa al servidor que se encarga de procesar los pedidos de distintos clientes en una aplicación
| El cliente "comprende" las respuestas provenientes del servidor, las interpreta y muestra en pantalla al usuario.             |Tiene la capacidad de recibir y administrar pedidos, para determinar la respuesta a enviar.

___
## HTTP (HyperText Transfer Protocol)

El **HTTP** es un protocolo de comunicación que permite la transferencia de información en la web, siguiendo un modelo **cliente-servidor**.

### Funcionamiento Básico:
1. **Cliente:** Envía una solicitud HTTP (request) al servidor.
2. **Servidor:** Procesa la solicitud y responde con el contenido solicitado (response).

### Componentes Clave:
- **URL (Uniform Resource Locator):** Dirección que apunta a un recurso web (Ej.: `https://www.ejemplo.com/pagina`).
- **Métodos HTTP:**
    - **GET:** Solicita datos.
    - **POST:** Envía datos al servidor.
    - **PUT:** Actualiza datos.
    - **DELETE:** Elimina recursos.

- **Códigos de Estado HTTP:**
    - **200 OK:** Solicitud exitosa.
    - **404 Not Found:** Recurso no encontrado.
    - **500 Internal Server Error:** Error en el servidor.
---
## ¿Qué es una URL?

La **URL (Uniform Resource Locator)** es la dirección única que identifica un recurso en internet, como páginas web, imágenes o archivos.

#### Estructura de una URL:
````
protocolo://dominio/ruta?parametros#fragmento
````

#### Componentes:
1. **Protocolo:** Define cómo se realiza la comunicación (ej. HTTP, HTTPS).
2. **Dominio:** Nombre del servidor o sitio web (ej. `www.google.com`).
3. **Ruta:** Especifica el recurso dentro del servidor (ej. `/blog/articulo.html`).
4. **Parámetros:** Datos adicionales enviados al servidor, en formato clave-valor (`?id=123`).
5. **Fragmento:** Sección específica dentro de la página (`#comentarios`).

---

## Arquitectura Cliente-Servidor

La **arquitectura cliente-servidor** es un modelo de comunicación en el que dos partes principales interactúan:

### Cliente:
- Es quien realiza las solicitudes.
- Generalmente, es un navegador web, una aplicación móvil u otro programa que pide recursos (páginas web, datos, etc.) al servidor.
- Muestra la información procesada al usuario final.

### Servidor:
- Es quien recibe, procesa las solicitudes del cliente y envía las respuestas.
- Puede ser un servidor web, de bases de datos, de correo, etc.
- Gestiona recursos compartidos y asegura que múltiples clientes puedan acceder a ellos simultáneamente.

### Proceso Básico:
1. El cliente envía una solicitud (*request*) al servidor.
2. El servidor procesa la solicitud, accede a los recursos necesarios y genera una respuesta (*response*).
3. El cliente recibe la respuesta y la muestra al usuario.

Este modelo es la base de aplicaciones web, servicios en la nube, y muchos otros sistemas distribuidos.

___


# ¿Qué son las APIs? 🧩

**API** significa **Application Programming Interface** o **Interfaz de Programación de Aplicaciones**.  
Básicamente, una API es un **puente de comunicación** que permite que dos aplicaciones o sistemas diferentes se conecten y se comuniquen entre sí.

---

## Explicación Simple
Imagina que estás en un restaurante y tú eres el cliente. El menú es la aplicación que te muestra opciones (los datos). Tú decides qué plato quieres y haces el pedido al **mesero**. Este mesero sería la **API**: toma tu pedido, lo lleva a la cocina (el servidor) y, cuando tu plato está listo, te lo trae de vuelta a tu mesa.

---

## ¿Qué hace una API?
- **Envía solicitudes**: La API toma tu pedido (información solicitada) y lo envía al servidor.
- **Recibe respuestas**: Luego devuelve la respuesta del servidor (por ejemplo, datos, resultados de búsqueda, imágenes, etc.).

---

## Tipos de APIs más comunes
1. **APIs REST**:
  - Las más utilizadas en el desarrollo web. Usan protocolos HTTP como GET, POST, PUT, DELETE para la comunicación.
  - **Ejemplo**: APIs de redes sociales como la API de Twitter, que te permite publicar tweets desde una app externa.

2. **APIs SOAP**:
  - Más antiguas y complejas que REST. Utilizan XML para el intercambio de datos.
  - Se suelen usar en grandes corporaciones por su seguridad adicional.

3. **APIs de Terceros**:
  - APIs creadas por terceros para que otros desarrolladores las usen.
  - **Ejemplo**: La API de Google Maps, que puedes integrar en una página web para mostrar mapas.

---

## Ejemplo de API REST
Supón que quieres acceder a los datos de una API que proporciona un pokemón:

Si haces una solicitud **GET** a esta URL:
```bash
https://pokeapi.co/api/v2/pokemon/pikachu
````
Retornará
```bash
{
  "id": 117,
  "advice": "If you're feeling tired, take a break."
}
```

# ¿Qué es una API REST?

Una **API REST (Representational State Transfer)** es un conjunto de reglas que permite la comunicación entre diferentes sistemas mediante el protocolo HTTP. REST define cómo deben estructurarse las solicitudes y respuestas para facilitar la interoperabilidad entre aplicaciones.

---

## Principios de REST

Para que una API sea considerada RESTful, debe seguir ciertos principios:

1. **Cliente-Servidor**
  - La API REST separa la interfaz del cliente (front-end) y el almacenamiento de datos (back-end), lo que permite que ambos evolucionen de manera independiente.

2. **Stateless (Sin estado)**
  - Cada solicitud HTTP realizada al servidor debe contener toda la información necesaria, ya que el servidor no guarda el estado de las solicitudes previas.

3. **Cacheable (Almacenamiento en caché)**
  - Las respuestas de la API pueden ser cacheadas para mejorar la eficiencia y reducir la carga del servidor.

4. **Interfaz uniforme (Uniform Interface)**
  - Debe haber consistencia en cómo se estructuran y acceden los recursos.

---

## Métodos HTTP más comunes

Las API RESTful utilizan métodos HTTP estándar para realizar operaciones sobre los recursos:

| **Método**   | **Descripción**                          | **Ejemplo**                  |
|---------------|------------------------------------------|------------------------------|
| **GET**       | Obtener datos de un recurso              | `/api/usuarios`              |
| **POST**      | Crear un nuevo recurso                   | `/api/usuarios`              |
| **PUT**       | Actualizar un recurso existente          | `/api/usuarios/1`            |
| **DELETE**    | Eliminar un recurso                      | `/api/usuarios/1`            |

---

## Ejemplo de JSON en una API RESTful

### Solicitud GET a `/api/pokemon/1`
```json
{
  "id": 1,
  "nombre": "Bulbasaur",
  "tipo": "Planta",
  "nivel": 5
}
```
## Diferencia entre REST y RESTful
Una API RESTful es aquella que sigue las reglas y principios REST al pie de la letra. No todas las APIs basadas en HTTP son RESTful, ya que podrían no cumplir con todos los principios mencionados.

### Principios de REST
- La separación cliente-servidor.
- El uso de métodos HTTP adecuados (GET, POST, PUT, DELETE, etc.).
- La falta de estado en el servidor (stateless).
- El uso de URLs consistentes y coherentes para los recursos.

---
# ¿Qué es Spring platform?
- Es un conjunto de proyectos open source desarrollados en JAva con el objetivo de agilizar el proceso de desarrollo de aplicaciones.
- Cuenta con una cantidad de herramientas que tienen como ojetivo facilitar el trabajo de los desarrolladores.

# Spring vs Spring Boot

## **Spring Framework**
**Spring** es un framework de desarrollo de aplicaciones para Java que proporciona una infraestructura completa para la creación de aplicaciones empresariales. Es modular, lo que te permite usar solo los módulos necesarios.

### **Características de Spring Framework:**
- **Inyección de dependencias (DI)**: Facilita la creación de aplicaciones desacopladas.
- **Configuración manual**: Requiere más intervención del desarrollador en la configuración (XML o clases Java).
- **Flexibilidad**: Gran control sobre la configuración y la integración de tecnologías.

### **Ventajas:**
- Gran control sobre la configuración.
- Ideal para aplicaciones grandes y complejas.

### **Desventajas:**
- Configuración tediosa y compleja.
- Mayor curva de aprendizaje.

---

## **Spring Boot**
**Spring Boot** es una extensión del framework Spring que simplifica el desarrollo de aplicaciones Java al proporcionar configuraciones predeterminadas y eliminar gran parte de la configuración manual.

### **Características de Spring Boot:**
- **Configuración automática**: Elimina la necesidad de configuraciones manuales.
- **Aplicaciones autónomas**: Incluye un servidor web embebido (Tomcat, Jetty).
- **Arranque rápido**: Ideal para el desarrollo ágil de aplicaciones.

### **Ventajas:**
- Fácil de usar y configurar.
- Desarrollo rápido y simplificado.
- Incluye servidores embebidos para facilitar el despliegue.

### **Desventajas:**
- Menos control sobre la configuración detallada.
- Puede ser más pesado debido a las dependencias predeterminadas.

---

## **Comparación Rápida**

| Característica               | **Spring Framework**                   | **Spring Boot**                        |
|------------------------------|----------------------------------------|----------------------------------------|
| **Configuración**             | Requiere configuración manual         | Configuración automática               |
| **Curva de aprendizaje**      | Más pronunciada                       | Fácil y rápida de aprender             |
| **Tamaño de la aplicación**    | Mayor                                  | Menor                                  |
| **Dependencias**              | Requiere declarar cada dependencia    | Proporciona "Starters" para simplificar |
| **Servidor embebido**         | Requiere configuración de servidor externo | Viene con servidor embebido (Tomcat, Jetty) |
| **Despliegue**                | Requiere servidor externo             | Despliegue como JAR autónomo           |

---

## **¿Cuándo usar Spring y cuándo usar Spring Boot?**

- **Usar Spring Framework**:
  - Para mayor control y personalización de la configuración.
  - Para aplicaciones grandes y complejas.

- **Usar Spring Boot**:
  - Para desarrollar rápidamente con configuración mínima.
  - Para crear microservicios y aplicaciones independientes.
<!-- ENCABEZADO animado con ola -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=140&color=0:0EA5E9,100:0F766E&text=📗%20Cuaderno%20Digital%20—%20Semana%2009&fontAlign=50&fontAlignY=35&fontSize=34&fontColor=ffffff&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/logos/uncp.jpg" width="90" alt="Logo UNCP" style="margin:10px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/logos/logoFIS.png" width="90" alt="Logo FIS" style="margin:10px;">
</p>

<p align="center">
  <img
    alt="Semana 09 — Desarrollo Backend y Arquitecturas Web"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3500&pause=1200&color=14B8A6&center=true&vCenter=true&width=980&lines=%F0%9F%9A%80%20Semana%2009%20%E2%80%94%20Desarrollo%20Backend%20%26%20Arquitecturas%20Web"
  />
</p>

<p align="center">
  <img
    alt="Macha Pariona Angel Yoelver — Desarrollo de Aplicaciones Web"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3500&pause=1200&color=14B8A6&center=true&vCenter=true&width=980&lines=Macha%20Pariona%20Angel%20Yoelver%20%E2%80%94%20Desarrollo%20de%20Aplicaciones%20Web"
  />
</p>

---

# 🧭 Introducción

Durante esta semana se exploró el **Desarrollo Backend**, la parte invisible pero esencial que se encarga de procesar datos, ejecutar la lógica del negocio y servir la información al cliente.  
Este módulo abordó desde los **fundamentos de las arquitecturas web**, hasta el **funcionamiento interno de los servidores**, el **uso del servidor Apache Tomcat**, y la **gestión de proyectos con Maven**.

> El propósito fue comprender cómo se organiza el código, se estructura el flujo de datos y se despliegan aplicaciones web reales dentro de un entorno controlado y seguro.

---

# 🧩 Arquitecturas Web — Modelos Cliente/Servidor

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/arquitecturas/arquitectura_mpa.png" width="380" alt="Arquitectura MPA" />
</p>

Las **arquitecturas web** determinan cómo se comunican los clientes y los servidores. Entre las principales tenemos:

| Tipo de Arquitectura | Descripción | Ventajas | Ejemplo |
|----------------------|--------------|-----------|----------|
| **MPA (Multi Page Application)** | Cada página es renderizada en el servidor y enviada completa al navegador. | SEO óptimo, estructura tradicional. | PHP, JSP, Laravel |
| **SPA (Single Page Application)** | Solo se carga una página y los datos se actualizan dinámicamente mediante APIs. | Navegación fluida, experiencia moderna. | React, Angular, Vue |
| **Híbrida (SPA/MPA)** | Combina ambas: SSR con APIs. Ideal para sitios escalables. | SEO + rendimiento. | Next.js, Nuxt.js |
| **Hexagonal** | Organiza el software en capas independientes (dominio, puertos, adaptadores). | Escalabilidad, mantenibilidad. | Arquitectura moderna Java/Spring |

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/arquitecturas/arquitectura_hexagonal.png" width="400" alt="Arquitectura Hexagonal" />
</p>

La **Arquitectura Hexagonal** fomenta un diseño limpio, separando el núcleo lógico (dominio) de las dependencias externas como bases de datos, servicios web o interfaces gráficas.

---

# ⚙️ Funcionamiento del Lado Servidor (Server Side)

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/conceptos/server_side_flujo.png" width="380" alt="Flujo Server Side" />
</p>

El backend procesa las solicitudes del cliente y devuelve respuestas con información dinámica.

**Flujo general:**  
1. El navegador envía una solicitud HTTP al servidor.  
2. El servidor interpreta la petición y ejecuta código backend (Java, PHP, Python, etc.).  
3. Se consulta la base de datos o servicios externos.  
4. El servidor devuelve un resultado en formato HTML o JSON.  
5. El navegador lo renderiza visualmente al usuario.

Esto se conoce como **arquitectura cliente-servidor**, donde el cliente consume y el servidor provee.

---

# ☁️ Servidores, Hosting y Cloud

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/servidores/cloud_hosting.png" width="400" alt="Cloud Hosting" />
</p>

Los **servidores web** son computadoras diseñadas para responder solicitudes HTTP de múltiples clientes a la vez.

## 🔹 Tipos de Servidores y Hosting

| Tipo | Descripción | Uso recomendado |
|------|--------------|----------------|
| **Compartido** | Varios sitios comparten recursos del mismo servidor. | Páginas pequeñas o personales. |
| **VPS (Virtual Private Server)** | Servidor virtual con recursos dedicados. | Aplicaciones medianas. |
| **Dedicado** | Hardware exclusivo para un solo cliente. | Sistemas empresariales. |
| **Cloud Hosting** | Recursos distribuidos en la nube, pago por uso. | Aplicaciones escalables. |

Los **proveedores de nube** como **AWS, Azure, Supabase o Google Cloud** ofrecen entornos seguros y escalables.  

El **dominio web (DNS)** es la puerta de entrada, asignando una dirección amigable (ejemplo: `www.municipalidadjarpa.gob.pe`) a una IP del servidor.

---

# 🐱 Servidor Apache Tomcat y JSP

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/servidores/servidor_tomcat.png" width="380" alt="Servidor Tomcat" />
</p>

**Apache Tomcat** es un contenedor de *servlets* y JSP que ejecuta aplicaciones web desarrolladas en **Java**.  

## 🔸 Estructura principal de Tomcat

| Carpeta | Descripción |
|----------|--------------|
| `bin/` | Scripts para iniciar o detener el servidor |
| `conf/` | Archivos de configuración (`server.xml`) |
| `webapps/` | Aplicaciones desplegadas |
| `logs/` | Registros de actividad |
| `work/` | Código JSP compilado en servlets |

**Flujo interno:**  
1. Un archivo `.jsp` se traduce a un **servlet Java**.  
2. El servlet se compila y ejecuta.  
3. Se genera una página HTML dinámica enviada al navegador.

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/conceptos/jsp_flujo.png" width="400" alt="Flujo JSP Tomcat" />
</p>

---

# 🧱 Maven — Gestión de Dependencias

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/maven/maven_ciclo.png" width="360" alt="Ciclo Maven" />
</p>

**Apache Maven** automatiza la construcción, compilación y despliegue de proyectos Java.  
Se basa en un archivo de configuración llamado `pom.xml` (*Project Object Model*).

Ejemplo básico:

```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>org.example</groupId>
  <artifactId>miwebapp</artifactId>
  <version>1.0-SNAPSHOT</version>
</project>
```

## 🔹 Comandos esenciales de Maven

| Comando | Función |
|----------|----------|
| `mvn clean` | Limpia los archivos temporales del proyecto |
| `mvn compile` | Compila el código fuente |
| `mvn package` | Genera el archivo `.jar` o `.war` |
| `mvn install` | Instala el artefacto en el repositorio local |
| `mvn deploy` | Envía la app a un servidor remoto |

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/maven/maven_repo.png" width="360" alt="Repositorio Maven" />
</p>

---

# 💡 Ejemplo Práctico: JSP + Maven + Tomcat

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
  <head><title>Hola Tomcat</title></head>
  <body>
    <h1><%= "Hola desde JSP @ " + new java.util.Date() %></h1>
  </body>
</html>
```

> 🔧 Despliegue con Maven:
> ```bash
> mvn clean install tomcat7:deploy
> ```
> Luego acceder a [http://localhost:8080/miwebapp](http://localhost:8080/miwebapp)

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/maven/maven_console.png" width="400" alt="Consola Maven" />
</p>

---

# 🖼️ Evidencias del Laboratorio

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/evidencias/evidencia_01.jpg" width="360" alt="Instalación JDK" />
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/evidencias/evidencia_02.jpg" width="360" alt="Servidor Tomcat" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/evidencias/evidencia_03.jpg" width="360" alt="pom.xml IntelliJ" />
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana09_imagenes/evidencias/evidencia_04.jpg" width="360" alt="Ejecución Maven" />
</p>

---

# 🧭 Reflexión Final

El **desarrollo backend** es el motor que impulsa las aplicaciones web modernas.  
Comprender cómo funcionan las **arquitecturas multicapa**, los **servidores Tomcat**, y herramientas como **Maven** permite diseñar sistemas **robustos, seguros y escalables**.

> La combinación entre teoría y práctica de esta semana proporciona la base para construir soluciones reales dentro de un entorno institucional.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:0F766E,100:0EA5E9&section=footer" />
</p>

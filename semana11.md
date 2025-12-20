<!-- ======================================================================
      📘 CUADERNO DIGITAL — SEMANA 11
      SPRING BOOT • INTELLIGENT CRUD DOCENTES • SWAGGER • POSTMAN • EVIDENCIAS
====================================================================== -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=150&color=0:7C3AED,100:2563EB&text=📘%20Cuaderno%20Digital%20—%20Semana%2011%20&fontAlign=50&fontAlignY=35&fontSize=34&fontColor=ffffff&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_uncp.png" width="90" alt="Logo UNCP" style="margin:10px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_fis.png" width="90" alt="Logo FIS" style="margin:10px;">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_spring.png" width="70" alt="Logo Spring Boot" style="margin:5px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_mysql.png" width="70" alt="Logo MySQL" style="margin:5px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_swagger.png" width="70" alt="Logo Swagger" style="margin:5px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_postman.png" width="70" alt="Logo Postman" style="margin:5px;">
</p>

<!-- Encabezado animado (typing) + fallback de texto -->
<p align="center">
  <img
    alt="alumno: Macha Pariona Angel Yoelver — Curso y Tema"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=2800&pause=1000&color=2563EB&center=true&vCenter=true&width=980&lines=Macha%20Pariona%20Angel%20Yoelver;Curso%3A%20Desarrollo%20de%20Aplicaciones%20Web;Tema%3A%20Intelligent%20CRUD%20Docentes%20(Spring%20Boot%20%2B%20MySQL)%20%E2%80%94%20Semana%2011"
  />
</p>



---

## 📌 Datos generales

| Ítem | Detalle |
|---|---|
| **Semana** | 11 |
| **Producto** | API REST — CRUD Inteligente de Docentes |
| **Backend** | Spring Boot + Spring Web |
| **Persistencia** | Spring Data JPA + MySQL |
| **Documentación** | Swagger / OpenAPI |
| **Pruebas** | Postman |
| **Funciones avanzadas** | Validación, filtros, paginación, KPIs |
| **Fecha** | 12/11/2025 |

---

# 1. Introducción

La **Semana 11** estuvo orientada al desarrollo de una **API REST profesional** para la gestión de docentes, evolucionando desde un CRUD básico hacia un **CRUD inteligente**.  
El enfoque fue integrar prácticas reales de backend: **arquitectura en capas**, **validación robusta**, **filtros dinámicos**, **paginación**, **documentación automática** y **pruebas sistemáticas**.

El resultado es un backend que puede ser consumido por cualquier cliente (web, móvil o escritorio) y que además deja trazabilidad técnica mediante Swagger y una colección Postman, lo cual facilita el mantenimiento y la escalabilidad.

---

# 2. Objetivos

## 2.1 Objetivo general

Desarrollar una **API REST inteligente** para gestionar docentes con Spring Boot y MySQL, aplicando validación, filtros dinámicos, paginación, documentación Swagger y pruebas con Postman.

## 2.2 Objetivos específicos

- Definir el **modelo de datos** para la entidad Docente y su implementación en MySQL.
- Implementar el CRUD completo usando **Spring Web**.
- Aplicar validaciones con **Jakarta Validation** (control de formato, rangos, nulos).
- Incorporar **paginación y ordenamiento** con Spring Data JPA.
- Implementar **filtros inteligentes** por ciudad, experiencia y nombre.
- Generar una documentación navegable con **Swagger UI**.
- Preparar pruebas de endpoints y escenarios con **Postman**.
- Establecer KPIs para análisis (cantidad de registros, distribución por ciudad, promedio de experiencia, etc.).

---

# 3. Arquitectura del proyecto

La arquitectura se basó en el patrón **Controller – Service – Repository**, separando responsabilidades:

- **Controller:** define rutas (endpoints) y estructura de respuesta.
- **Service:** lógica de negocio (reglas, validaciones complementarias, KPIs).
- **Repository:** acceso a datos y consultas (Spring Data JPA).
- **DTO:** contratos de entrada/salida para no exponer la entidad directamente.
- **Config:** Swagger/OpenAPI, CORS y configuración adicional.

## 3.1 Estructura de carpetas

```text
src/main/java/
└── com.ejemplo.docentes/
    ├── controller/        # Controladores REST (DocenteController)
    ├── service/           # Servicios (DocenteService, ServiceImpl)
    ├── repository/        # Interfaces JPA (DocenteRepository)
    ├── entity/            # Entidades JPA (Docente)
    ├── dto/               # DTOs para requests/responses
    ├── config/            # Swagger, CORS, etc.
    └── exception/         # Manejo centralizado de errores (opcional)
```

## 3.2 Flujo lógico de una petición

1. El cliente envía una solicitud HTTP (Postman / Swagger / Frontend).
2. El Controller recibe la petición y valida el DTO.
3. El Service aplica reglas (si corresponde) y llama al Repository.
4. El Repository ejecuta consultas JPA hacia MySQL.
5. Se devuelve respuesta JSON con código HTTP adecuado (200, 201, 400, 404, etc.).

### 📷 Evidencia — Proyecto en IntelliJ IDEA

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_proyecto_intellij.png" width="360"/>

---

# 4. Modelo de Datos – MySQL

El modelo de datos se diseñó para garantizar **integridad**, **eficiencia** y **facilidad de consulta**.  
La tabla principal **`docentes`** contiene la información que será manipulada por la API REST del CRUD inteligente.

---

## 4.1 Características del modelo

- **Llave primaria autoincremental** (`id_docente`) para identificar registros de forma única.
- Restricciones de integridad:
  - `NOT NULL` para campos obligatorios.
  - `UNIQUE` para evitar duplicidad en correos.
  - `CHECK` para validar rangos de valores (ej. años de servicio).
- Campos pensados para filtros y KPIs (ciudad, tiempo de servicio, fecha de registro).
- Compatible con Spring Data JPA, facilitando el mapeo de entidad y consultas.

---

## 4.2 Script SQL implementado

```sql
CREATE TABLE docentes (
    id_docente       INT AUTO_INCREMENT PRIMARY KEY,
    nom_docente      VARCHAR(120) NOT NULL,
    dir_docente      VARCHAR(150) NOT NULL,
    ciu_docente      VARCHAR(100) NOT NULL,
    email_docente    VARCHAR(150) NOT NULL UNIQUE,
    fec_nacimiento   DATE NOT NULL,
    tiempo_servicio  INT NOT NULL CHECK (tiempo_servicio >= 0),
    creado_en        TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Este script se ejecutó en MySQL para crear la tabla **docentes**, que luego se mapea en Spring Boot mediante JPA.  
Toda la lógica del CRUD inteligente (validaciones, filtros, KPIs y paginación) opera sobre esta estructura.

---

## 4.3 Explicación de los campos

| Campo | Tipo / Restricción | Descripción |
|---|---|---|
| `id_docente` | INT, PK, AUTO_INCREMENT | Identificador único del docente. |
| `nom_docente` | VARCHAR(120), NOT NULL | Nombre completo del docente. |
| `dir_docente` | VARCHAR(150), NOT NULL | Dirección o domicilio del docente. |
| `ciu_docente` | VARCHAR(100), NOT NULL | Ciudad; base para filtros y KPIs. |
| `email_docente` | VARCHAR(150), UNIQUE, NOT NULL | Correo institucional único validado. |
| `fec_nacimiento` | DATE, NOT NULL | Fecha de nacimiento; validada con `@Past` en la API. |
| `tiempo_servicio` | INT, CHECK (>= 0) | Años trabajados; útil para indicadores y análisis. |
| `creado_en` | TIMESTAMP, DEFAULT NOW() | Fecha y hora de creación del registro. |

---

## 4.4 Evidencia – Tabla MySQL

La evidencia muestra que la tabla se creó correctamente en MySQL, visualizando los campos definidos y datos reales utilizados para pruebas.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_tabla_mysql_docentes.png" width="360"/>

---

# 5. Diseño del CRUD Inteligente (API REST)

El CRUD se implementó bajo la ruta base:

```text
/api/docentes
```

A nivel funcional, se incorporaron comportamientos “inteligentes” que van más allá del CRUD tradicional:

- **Paginación** para listas grandes.
- **Filtros dinámicos** combinables (ciudad, nombre, tiempo de servicio).
- **Validación** y mensajes de error entendibles.
- **Documentación interactiva** con Swagger.
- **Pruebas repetibles** con Postman.
- **KPIs** para análisis administrativo.

---

## 5.1 Tabla de Endpoints

| Método | Ruta | Funcionalidad | Respuesta típica |
|---|---|---|---|
| GET | `/api/docentes` | Listado con filtros y paginación | 200 OK |
| POST | `/api/docentes` | Crear docente (validado) | 201 Created |
| GET | `/api/docentes/{id}` | Obtener docente por ID | 200 / 404 |
| PUT | `/api/docentes/{id}` | Actualizar docente | 200 / 400 / 404 |
| DELETE | `/api/docentes/{id}` | Eliminar docente | 204 No Content / 404 |

---

## 5.2 Ejemplos de uso (Requests y Responses)

### A) Crear docente (POST)

**Request (JSON):**
```json
{
  "nomDocente": "Ana Perez",
  "dirDocente": "Jr. Los Olivos 123",
  "ciuDocente": "Huancayo",
  "emailDocente": "ana.perez@uncp.edu.pe",
  "fecNacimiento": "1993-05-21",
  "tiempoServicio": 5
}
```

**Response esperada:**
- **201 Created** + JSON del docente creado (con id asignado).

---

### B) Listar con filtros y paginación (GET)

Ejemplo de consulta:
```text
GET /api/docentes?page=0&size=5&ciu=Huancayo&minServicio=3&nombre=ana
```

**Interpretación de parámetros:**
- `page`: número de página (0…n)
- `size`: tamaño de página
- `ciu`: filtra por ciudad
- `minServicio`: filtra por mínimo de años
- `nombre`: filtra por coincidencia en nombre

**Response (estructura típica de Page):**
```json
{
  "content": [{ "...": "..." }],
  "pageable": { "pageNumber": 0, "pageSize": 5 },
  "totalElements": 12,
  "totalPages": 3
}
```

### 📷 Evidencia — Filtros + paginación en ejecución

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_filtros_paginacion.png" width="360"/>

---

## 5.3 Validaciones aplicadas (Jakarta Validation)

Se aplicaron validaciones para garantizar calidad de datos. Ejemplos típicos:

- `@NotBlank` en nombre, dirección y ciudad.
- `@Email` en correo.
- `@Past` en fecha de nacimiento.
- `@Min(0)` en tiempo de servicio.

### 📷 Evidencia — Errores por validación

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/logo_validacion.png" width="360"/>

---

# 6. Documentación con Swagger UI

Swagger UI permite inspeccionar, probar y validar la API sin depender de un frontend.  
Ruta típica (según configuración):  
- `http://localhost:8080/swagger-ui.html` o `http://localhost:8080/swagger-ui/index.html`

### 📷 Evidencia — Swagger UI

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_swagger_ui.png" width="360"/>

---

# 7. Pruebas con Postman

Se preparó una colección para asegurar que las pruebas se repitan en cualquier entorno (clase, laboratorio o PC personal).  
La colección incluye:

- Pruebas de listado paginado.
- Creación correcta e incorrecta (validaciones).
- Lectura por ID existente e inexistente.
- Actualización parcial/total.
- Eliminación y verificación posterior.

### 📷 Evidencia — Colección Postman

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_postman_collection.png" width="360"/>

---

# 8. KPIs y análisis del sistema

Los KPIs propuestos para un contexto académico-administrativo permiten responder preguntas como:

- ¿Cuántos docentes hay registrados?
- ¿En qué ciudad hay más docentes?
- ¿Cuál es el promedio de años de servicio?
- ¿Qué rango de experiencia predomina?

## 8.1 KPIs sugeridos

| KPI | Descripción | Fórmula / Criterio |
|---|---|---|
| Total de docentes | Cantidad total de registros | `COUNT(*)` |
| Docentes por ciudad | Distribución geográfica | `GROUP BY ciu_docente` |
| Promedio de servicio | Experiencia promedio | `AVG(tiempo_servicio)` |
| Máximo / mínimo servicio | Rango de experiencia | `MAX/MIN(tiempo_servicio)` |

### 📷 Evidencia — KPIs

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/evid_kpis_docentes.png" width="360"/>

---

# 9. Resultados y evidencias principales

A continuación se resumen las evidencias mínimas que demuestran el desarrollo completo:

| Evidencia | Qué demuestra |
|---|---|
| IntelliJ (estructura) | Organización por capas y dependencias |
| MySQL (tabla) | Modelo de datos correcto |
| Filtros + paginación | CRUD “inteligente” funcionando |
| Swagger UI | Documentación funcional |
| Postman | Pruebas repetibles y control de respuestas |
| KPIs | Análisis de datos y valor agregado |

---

# 10. Conclusiones

1. Se construyó una API REST sólida con Spring Boot, aplicando arquitectura por capas y persistencia con MySQL.  
2. El CRUD evolucionó a un enfoque inteligente incorporando filtros, paginación y validación robusta.  
3. Swagger UI y Postman facilitaron la verificación, documentación y pruebas completas de los endpoints.  
4. Los KPIs demuestran que el sistema no solo administra datos, sino que también permite análisis útil para decisiones académicas.  
5. El proyecto queda listo para integrar un frontend (React/Vue) o para crecer con autenticación (JWT) y roles.

---

# 11. Reflexión (aprendizajes)

- Comprendí la importancia de separar responsabilidades (Controller, Service, Repository).
- Validar datos en backend evita errores, inconsistencias y datos basura en la base.
- La paginación mejora rendimiento y experiencia cuando existen grandes volúmenes.
- Swagger y Postman son herramientas indispensables en el desarrollo profesional.
- Los KPIs agregan valor al sistema y lo vuelven más orientado a gestión y análisis.

---

# 12. Anexos

## 12.1 Lista de imágenes usadas (ruta única)

> Todas las imágenes se consumen desde:  
> `https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/Semana11_imagenes/NOMBRE.png`

| Archivo | Uso |
|---|---|
| `logo_uncp.png` | Logo institucional UNCP |
| `logo_fis.png` | Logo facultad FIS |
| `logo_spring.png` | Tecnología Spring |
| `logo_java.png` | Tecnología Java |
| `logo_mysql.png` | Tecnología MySQL |
| `logo_swagger.png` | Tecnología Swagger |
| `logo_postman.png` | Tecnología Postman |
| `logo_validacion.png` | Evidencia de validación |
| `evid_proyecto_intellij.png` | Evidencia de estructura en IDE |
| `evid_tabla_mysql_docentes.png` | Evidencia del modelo de datos |
| `evid_filtros_paginacion.png` | Evidencia filtros y paginación |
| `evid_swagger_ui.png` | Evidencia documentación |
| `evid_postman_collection.png` | Evidencia de pruebas |
| `evid_kpis_docentes.png` | Evidencia KPIs |

## 12.2 Recomendaciones de mejora (siguiente iteración)

- Implementar **borrado lógico** (campo `estado` o `activo`).
- Agregar **auditoría** completa (usuario creador, usuario editor, fecha de modificación).
- Aplicar **JWT** con roles (admin/usuario) para proteger endpoints.
- Crear endpoint dedicado para KPIs (`/api/docentes/kpis`).
- Agregar pruebas unitarias y de integración (JUnit + MockMvc).

---

✅ **Fin del informe — Semana 11**

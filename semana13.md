<!-- ======================================================================
      📘 CUADERNO DIGITAL — SEMANA 13
      CRUD EMPLEADOS MOVISTAR • REACT • LARAVEL • MYSQL • EVIDENCIAS
====================================================================== -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=170&color=0:00A9E0,50:019DF4,100:5CB615&text=📘%20Cuaderno%20Digital%20—%20Semana%2013&fontAlign=50&fontAlignY=36&fontSize=38&fontColor=ffffff&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_uncp.png" width="95" alt="Logo UNCP" style="margin:10px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_fis.png" width="95" alt="Logo FIS" style="margin:10px;">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_react.png" width="72" alt="React" style="margin:6px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_vite.png" width="72" alt="Vite" style="margin:6px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_laravel.png" width="72" alt="Laravel" style="margin:6px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_php.png" width="72" alt="PHP" style="margin:6px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_mysql.png" width="72" alt="MySQL" style="margin:6px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/logo_movistar.png" width="72" alt="Movistar" style="margin:6px;">
</p>


<p align="center">
  <img
    alt="Macha Pariona Angel Yoelver — Semana 13"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=2600&pause=900&color=019DF4&center=true&vCenter=true&width=980&lines=Macha%20Pariona%20Angel%20Yoelver;Curso%3A%20Desarrollo%20de%20Aplicaciones%20Web;Tema%3A%20CRUD%20Empleados%20Movistar%20con%20React%20%2B%20Laravel%20%2B%20MySQL%20(Semana%2013)"
  />
</p>

---

# 🧩 semana 13 

**Autor:** Angel Yoelver Macha  
**Universidad:** Universidad Nacional del Centro del Perú (UNCP)  
**Facultad:** Facultad de Ingeniería de Sistemas (FIS)  
**Curso / Área:** Desarrollo de apliciones Web  
**Semana:** 13  


---

## ✅ Tabla de contenido

1. [Resumen ejecutivo](#1-resumen-ejecutivo)  
2. [Objetivos](#2-objetivos)  
3. [Alcance y supuestos](#3-alcance-y-supuestos)  
4. [Stack tecnológico](#4-stack-tecnológico)  
5. [Arquitectura e integración](#5-arquitectura-e-integración)  
6. [Modelo de datos (MySQL)](#6-modelo-de-datos-mysql)  
7. [API REST (Laravel)](#7-api-rest-laravel)  
8. [Frontend (React + Vite)](#8-frontend-react--vite)  
9. [Instalación y ejecución](#9-instalación-y-ejecución)  
10. [Evidencias comentadas](#10-evidencias-comentadas)  
11. [Resultados](#11-resultados)  
12. [Lecciones aprendidas](#12-lecciones-aprendidas)  
13. [Conclusiones](#13-conclusiones)  
14. [Recomendaciones y mejoras](#14-recomendaciones-y-mejoras)  
15. [Anexos](#15-anexos)  

---

## 1. Resumen ejecutivo

En la **Semana 13** se implementó un **Sistema CRUD de Empleados Movistar** aplicando una arquitectura **Full Stack desacoplada**:

- **React + Vite** como *Frontend*: interfaz, formularios, tabla de empleados, manejo de estado y consumo de API.  
- **Laravel (PHP)** como *Backend*: API REST con rutas, controladores, validaciones y respuestas JSON.  
- **MySQL** como *Base de datos*: persistencia de registros y soporte del ciclo CRUD.

El proyecto demuestra un flujo real de desarrollo profesional, donde la UI no se conecta directamente a la BD: en su lugar, consume endpoints HTTP del backend, el backend aplica validaciones y opera la BD con un ORM (Eloquent), respondiendo en JSON para actualizar la UI sin recargar.

---

## 2. Objetivos

### 2.1 Objetivo general
Construir e integrar una aplicación web Full Stack que administre empleados Movistar mediante operaciones **Crear, Listar, Editar y Eliminar**, usando **React + Laravel + MySQL**.

### 2.2 Objetivos específicos

| Código | Objetivo específico |
|---|---|
| OE-01 | Verificar y configurar el entorno backend con **PHP + Composer** |
| OE-02 | Verificar y configurar el entorno frontend con **Node + NPM + Vite** |
| OE-03 | Configurar conexión a **MySQL** mediante `.env` |
| OE-04 | Implementar **migraciones** para versionar la estructura de la BD |
| OE-05 | Definir **rutas API** y endpoints REST para CRUD |
| OE-06 | Consumir la API desde React y renderizar datos en UI |
| OE-07 | Aplicar **validaciones** y manejo de errores en backend |
| OE-08 | Documentar el proceso con evidencias y explicación técnica |

---

## 3. Alcance y supuestos

### 3.1 Alcance funcional (CRUD)
- **Crear empleado** (formulario → POST API → MySQL).  
- **Listar empleados** (GET API → tabla React).  
- **Editar empleado** (formulario precargado → PUT/PATCH).  
- **Eliminar empleado** (confirmación → DELETE).  

### 3.2 Supuestos técnicos
- Backend y frontend se ejecutan en **puertos distintos** durante desarrollo (ej.: `5173` y `8000`).  
- La comunicación se realiza con **JSON**.  
- Se habilita **CORS** (recomendado) para permitir consumo desde React.

### 3.3 Fuera de alcance (para futuras mejoras)
- Autenticación y autorización (tokens, roles).  
- Auditoría avanzada (bitácora de cambios).  
- Despliegue productivo (dominio/hosting).  

---

## 4. Stack tecnológico

### 4.1 Tecnologías principales

| Capa | Tecnología | Rol |
|---|---|---|
| Frontend | React | UI por componentes y estado |
| Frontend | Vite | Servidor dev + build rápido |
| Backend | Laravel | API REST, validaciones, controladores |
| Backend | PHP | Lenguaje base del backend |
| Backend | Composer | Dependencias de PHP/Laravel |
| Datos | MySQL | Persistencia relacional |
| Integración | HTTP + JSON | Comunicación frontend ↔ backend |

### 4.2 Beneficios de esta combinación
- **React** ofrece UI dinámica (sin recargar).  
- **Laravel** simplifica el diseño de una API robusta con buenas prácticas.  
- **MySQL** asegura persistencia y consistencia de datos.  
- Separación por capas facilita **mantenimiento**, **escalabilidad** y **trabajo en equipo**.

---

## 5. Arquitectura e integración

### 5.1 Esquema general (desacoplado)

```text
┌──────────────────────────┐         HTTP/JSON         ┌──────────────────────────┐
│   Frontend (React + Vite)│  ───────────────────────▶ │   Backend (Laravel API)  │
│  - UI / Formularios      │                           │  - Rutas / Controladores │
│  - Estado / Tabla        │  ◀─────────────────────── │  - Validaciones / Lógica  │
└──────────────────────────┘         Respuesta JSON     └───────────┬──────────────┘
                                                                    │
                                                                    │ Eloquent ORM
                                                                    ▼
                                                          ┌───────────────────────┐
                                                          │       MySQL (BD)       │
                                                          │  - Tablas / Registros  │
                                                          └───────────────────────┘
```

### 5.2 ¿Cómo se relacionan React, Laravel y MySQL?

**React (cliente):**
- Captura datos del formulario.  
- Envía solicitudes `GET/POST/PUT/DELETE`.  
- Recibe JSON y actualiza el estado para re-renderizar.

**Laravel (servidor API):**
- Recibe solicitudes HTTP desde React.  
- Valida datos (reglas).  
- Ejecuta operaciones con Eloquent (MySQL).  
- Responde con JSON estandarizado.

**MySQL (almacenamiento):**
- Guarda empleados y asegura integridad de registros.  
- Se gestiona por migraciones (estructura versionada).

### 5.3 Flujo CRUD (paso a paso)

| Operación | Acción en React | Petición | Acción en Laravel | Acción en MySQL | Respuesta |
|---|---|---|---|---|---|
| Listar | Renderiza tabla | GET `/api/empleados` | Consulta | SELECT | JSON lista |
| Crear | Envía formulario | POST `/api/empleados` | Valida + crea | INSERT | JSON registro |
| Editar | Actualiza form | PUT `/api/empleados/{id}` | Valida + actualiza | UPDATE | JSON registro |
| Eliminar | Confirma | DELETE `/api/empleados/{id}` | Elimina | DELETE | JSON ok |

### 5.4 CORS (muy importante en desarrollo)

En local suele ocurrir:  
- React: `http://localhost:5173`  
- Laravel: `http://127.0.0.1:8000`

Como son **orígenes distintos**, el navegador puede bloquear peticiones.  
Por eso se recomienda permitir CORS.

**Checklist CORS:**
- Permitir origen: `http://localhost:5173`  
- Permitir métodos: `GET, POST, PUT, DELETE`  
- Permitir headers: `Content-Type, Authorization` (si aplica)  

---

## 6. Modelo de datos (MySQL)

> **Nota:** Como los campos exactos dependen de tu implementación, abajo se muestra un modelo típico de “empleado”.  
> Si en tu proyecto usaste otros campos, reemplázalos y mantén la misma lógica.

### 6.1 Tabla propuesta: `empleados`

| Campo | Tipo | Descripción |
|---|---|---|
| id | BIGINT (PK) | Identificador |
| nombres | VARCHAR | Nombres del empleado |
| apellidos | VARCHAR | Apellidos |
| dni | VARCHAR | Documento (opcional según caso) |
| cargo | VARCHAR | Puesto / cargo |
| telefono | VARCHAR | Teléfono |
| email | VARCHAR | Correo |
| created_at | TIMESTAMP | Registro de creación |
| updated_at | TIMESTAMP | Registro de actualización |

### 6.2 SQL referencial (opcional)

```sql
CREATE TABLE empleados (
  id BIGINT AUTO_INCREMENT PRIMARY KEY,
  nombres VARCHAR(120) NOT NULL,
  apellidos VARCHAR(120) NOT NULL,
  dni VARCHAR(15) NULL,
  cargo VARCHAR(80) NULL,
  telefono VARCHAR(20) NULL,
  email VARCHAR(120) NULL,
  created_at TIMESTAMP NULL,
  updated_at TIMESTAMP NULL
);
```

### 6.3 Migraciones (por qué se usan)
Las migraciones permiten:
- Versionar la estructura (como “historial” de la BD).  
- Reproducir el proyecto en otro equipo sin crear tablas manualmente.  
- Mantener consistencia en equipos y despliegues.

---

## 7. API REST (Laravel)

### 7.1 Endpoints recomendados

| Método | Endpoint | Descripción | Entrada | Salida |
|---|---|---|---|---|
| GET | `/api/empleados` | Listar empleados | - | JSON lista |
| POST | `/api/empleados` | Crear empleado | JSON empleado | JSON creado |
| GET | `/api/empleados/{id}` | Obtener uno | id | JSON uno |
| PUT/PATCH | `/api/empleados/{id}` | Actualizar | JSON + id | JSON actualizado |
| DELETE | `/api/empleados/{id}` | Eliminar | id | JSON ok |

### 7.2 Estructura JSON sugerida (estándar)

**Respuesta éxito:**
```json
{
  "ok": true,
  "message": "Operación exitosa",
  "data": { }
}
```

**Respuesta error:**
```json
{
  "ok": false,
  "message": "Error de validación",
  "errors": {
    "nombres": ["El campo nombres es obligatorio"]
  }
}
```

### 7.3 Validaciones (importancia)
Aunque React valide en UI, **Laravel debe validar siempre** porque:
- La UI puede ser alterada por el usuario (o por herramientas).  
- Evita guardar datos incompletos o inválidos en MySQL.  
- Protege la integridad del sistema.

**Ejemplo de reglas típicas:**
- `nombres`: requerido, mínimo 2 caracteres  
- `apellidos`: requerido  
- `email`: formato válido (si se usa)  

---

## 8. Frontend (React + Vite)

### 8.1 Responsabilidades
- Mostrar un **listado** de empleados (tabla).  
- Mostrar **formulario** crear/editar.  
- Consumir API con `fetch`/`axios`.  
- Manejar estado (ej.: `empleados`, `loading`, `error`).  
- Actualizar UI sin recargar (re-render por estado).

### 8.2 Flujo típico en React (idea)
1. Al cargar pantalla: `GET /api/empleados`.  
2. Al guardar: `POST` y se refresca tabla.  
3. Al editar: se carga formulario con datos y se manda `PUT`.  
4. Al eliminar: `DELETE` y se quita del estado.

---

## 9. Instalación y ejecución

### 9.1 Backend (Laravel)

| Acción | Comando |
|---|---|
| Instalar dependencias | `composer install` |
| Generar key (si aplica) | `php artisan key:generate` |
| Migrar BD | `php artisan migrate` |
| Servidor local | `php artisan serve` |

### 9.2 Frontend (React)

| Acción | Comando |
|---|---|
| Instalar dependencias | `npm install` |
| Servidor local | `npm run dev` |

### 9.3 Verificación rápida (checklist)

- [ ] PHP y Composer instalados  
- [ ] Node y NPM instalados  
- [ ] `.env` con datos correctos de MySQL  
- [ ] Migraciones ejecutadas sin error  
- [ ] Backend corriendo en `:8000`  
- [ ] Frontend corriendo en `:5173`  
- [ ] CORS habilitado si hay bloqueo  
- [ ] CRUD responde con JSON correctamente  

---

## 10. Evidencias comentadas

### 10.1 Base RAW de evidencias (para que se vean directo)
```
https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/
```

---

### 10.2 Tabla resumen de evidencias (con miniaturas)

| # | Evidencia | Comentario técnico | Miniatura |
|---:|---|---|---|
| 01 | Entorno PHP + Composer | Confirma que el backend Laravel puede instalar dependencias y ejecutarse correctamente. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_01_entorno_php_composer.png" width="320" alt="Evidencia 01" /> |
| 02 | Node + NPM + Vite | Habilita el entorno frontend para compilar/servir React con recarga en caliente. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_02_npm_node_vite.png" width="320" alt="Evidencia 02" /> |
| 03 | Config `.env` (MySQL) | Configura credenciales y host de BD para que Laravel pueda operar MySQL. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_03_config_env_db.png" width="320" alt="Evidencia 03" /> |
| 04 | Migraciones OK | Garantiza que la estructura de tablas quedó creada y versionada. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_04_migrate_ok.png" width="320" alt="Evidencia 04" /> |
| 05 | Rutas API | Verifica que los endpoints están definidos y disponibles para consumo desde React. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_05_routes_api.png" width="320" alt="Evidencia 05" /> |
| 06 | Frontend en ejecución | Confirma que React/Vite está activo y listo para consumir la API. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_06_front_npm_run_dev.png" width="320" alt="Evidencia 06" /> |
| 07 | Backend en ejecución | Confirma que Laravel está atendiendo HTTP (API disponible). | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_07_back_php_artisan_serve.png" width="320" alt="Evidencia 07" /> |
| 08 | CRUD: listado | Evidencia la lectura (Read) mediante GET y renderizado reactivo en tabla. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_08_crud_listado.png" width="320" alt="Evidencia 08" /> |
| 09 | CRUD: crear/editar | Evidencia create/update: envío de formulario, validación y persistencia. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_09_crud_crear_editar.png" width="320" alt="Evidencia 09" /> |
| 10 | CRUD: eliminar | Evidencia delete: confirmación y actualización del estado en UI. | <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_10_crud_eliminar_resultado.png" width="320" alt="Evidencia 10" /> |

---

### 10.3 Evidencias en formato “Figura” (comentadas)

> Para informes, este formato facilita la referencia: **Figura X — descripción** + comentario.

#### Figura 10.1 — Entorno PHP y Composer  
La evidencia confirma que el entorno backend está correctamente preparado. Composer permite instalar Laravel y sus dependencias; PHP ejecuta el servidor y comandos artisan.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_01_entorno_php_composer.png" width="400" alt="Figura 10.1" />

#### Figura 10.2 — Node, NPM y Vite  
Evidencia del entorno frontend. NPM administra dependencias de React y Vite levanta el servidor de desarrollo con recarga automática.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_02_npm_node_vite.png" width="400" alt="Figura 10.2" />

#### Figura 10.3 — Configuración `.env` y conexión MySQL  
Se valida la configuración de conexión a BD. Esto es crítico: si el `.env` es incorrecto, migraciones y operaciones CRUD fallarán.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_03_config_env_db.png" width="400" alt="Figura 10.3" />

#### Figura 10.4 — Migraciones ejecutadas  
Confirma que la estructura de tablas está lista para almacenar empleados. Migraciones exitosas implican que Laravel y MySQL están bien conectados.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_04_migrate_ok.png" width="400" alt="Figura 10.4" />

#### Figura 10.5 — Rutas del API  
Verifica que el CRUD está expuesto por endpoints que React puede consumir.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_05_routes_api.png" width="400" alt="Figura 10.5" />

#### Figura 10.6 — Frontend activo con Vite  
Confirma que la interfaz está disponible en el navegador y lista para consumir la API.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_06_front_npm_run_dev.png" width="400" alt="Figura 10.6" />

#### Figura 10.7 — Backend activo con Artisan  
Muestra el servidor Laravel ejecutándose. Esto habilita que React haga peticiones.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_07_back_php_artisan_serve.png" width="400" alt="Figura 10.7" />

#### Figura 10.8 — CRUD: Listado  
Demuestra el Read: el frontend consulta el backend y renderiza datos sin recarga.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_08_crud_listado.png" width="400" alt="Figura 10.8" />

#### Figura 10.9 — CRUD: Crear/Editar  
Demuestra Create/Update: datos enviados, validados, y guardados/actualizados en BD.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_09_crud_crear_editar.png" width="400" alt="Figura 10.9" />

#### Figura 10.10 — CRUD: Eliminar  
Demuestra Delete: eliminación confirmada por API y actualización inmediata de la interfaz.

<img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/c9ed1ec80a1f2e45637c926a689ba075ba20afb5/semana13_imagenes/evid_10_crud_eliminar_resultado.png" width="400" alt="Figura 10.10" />

---

## 11. Resultados

### 11.1 Resultados técnicos

| Resultado | Evidencia / Sustento |
|---|---|
| Entorno backend operativo (PHP/Composer) | Evidencia 01 |
| Entorno frontend operativo (Node/NPM/Vite) | Evidencia 02 |
| Conexión a MySQL configurada en `.env` | Evidencia 03 |
| BD creada con migraciones | Evidencia 04 |
| Endpoints API definidos | Evidencia 05 |
| Frontend corriendo y consumiendo API | Evidencia 06 + 08 |
| Backend corriendo y atendiendo requests | Evidencia 07 |
| CRUD completo funcionando | Evidencias 08–10 |

### 11.2 Verificación funcional (checklist)

- [x] Listado de empleados (Read)  
- [x] Crear empleado (Create)  
- [x] Editar empleado (Update)  
- [x] Eliminar empleado (Delete)  
- [x] Respuesta JSON y UI reactiva (sin recargar)  

---

## 12. Lecciones aprendidas

1. **Separar frontend y backend** reduce acoplamiento y facilita mantenimiento.  
2. **Backend siempre valida**: aunque React valide, Laravel debe ser la validación final.  
3. **Migraciones** agilizan el trabajo en equipo y evitan “crear tablas a mano”.  
4. **CORS** es clave cuando frontend y backend usan distintos puertos.  
5. Respuestas **JSON estandarizadas** facilitan manejo de errores y estados en React.

---

## 13. Conclusiones

1. Se implementó un CRUD completo de empleados con una arquitectura desacoplada moderna.  
2. React cumplió el rol de interfaz dinámica, consumiendo endpoints REST sin recargar páginas.  
3. Laravel centralizó las reglas de negocio, validaciones y operaciones sobre MySQL.  
4. MySQL aseguró persistencia y consistencia, reforzada por migraciones ejecutadas correctamente.  
5. La documentación mediante evidencias publicadas respalda la trazabilidad del proceso.

---

## 14. Recomendaciones y mejoras

| Área | Mejora propuesta | Beneficio |
|---|---|---|
| Seguridad | Autenticación (Sanctum/JWT) | Proteger endpoints |
| Roles | Admin/Operador | Control de acceso |
| UX | Búsqueda + paginación | Mejor experiencia |
| Datos | Validación más estricta | Calidad de información |
| Auditoría | Historial de cambios | Trazabilidad |
| Deploy | Publicar en Render/VPS | Acceso remoto real |



---

✅ **Fin del documento — Semana 13**

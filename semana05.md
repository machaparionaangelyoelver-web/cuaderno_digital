<!-- ENCABEZADO animado con ola -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=140&color=0:0F766E,100:0EA5E9&text=📕%20Cuaderno%20Digital%20—%20Semana%2005&fontAlign=50&fontAlignY=35&fontSize=34&fontColor=ffffff&animation=fadeIn" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana03_imagenes/uncp.jpg" width="96" height="96" alt="Logo UNCP" style="margin:10px;">
  <img src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/f0cdbb12c97509f0e36e35dbcf156ae2eec47634/semana03_imagenes/logoFIS.png" width="96" height="96" alt="Logo FIS" style="margin:10px;">
</p>

<!-- Animación con el nombre del estudiante -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=26&duration=2500&pause=1000&color=0EA5E9&center=true&vCenter=true&width=920&lines=Estudiante%3A%20Macha%20Pariona%20Angel%20Yoelver;IX%20Semestre%20%E2%80%94%20Facultad%20de%20Ingenier%C3%ADa%20de%20Sistemas;Universidad%20Nacional%20del%20Centro%20del%20Per%C3%BA" />
</p>

<!-- Animación adicional con el título largo de la semana -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&amp;size=24&amp;duration=2400&amp;pause=900&amp;color=14B8A6&amp;center=true&amp;vCenter=true&amp;width=980&amp;lines=%F0%9F%8C%8C%20Semana%2005%20%E2%80%94%20Node.js%2C%20npm%2C%20React%2C%20Vite%2C%20Next.js%20%2B%20Pr%C3%A1ctica%20Calificada%203" alt="🌌 Semana 05 — Node.js, npm, React, Vite, Next.js + Práctica Calificada 3" />
</p>

---

# 🌌 Semana 05 — **Node.js, npm, React, Vite, Next.js **
---

## 🎯 Objetivos
- Dominar **Node.js** y **npm** como base del ecosistema JS (instalación, scripts, dependencias).
- Crear proyectos en **React** (CRA) y con **Vite** (flujo moderno, rápido y modular).
- Entender **Next.js** (SSR/SSG, rutas, API Routes, optimización y SEO).
- Aplicar JS en la **Práctica Calificada 3** (ruleta y sorteo de equipos) reforzando DOM, eventos y `localStorage`.
- Documentar con un cuaderno digital **ordenado, visual y didáctico**.

---

# 📚 Parte 1 — Node.js y npm

### 🔹 ¿Qué es Node.js?
Node.js es un **entorno de ejecución** que permite correr JavaScript **fuera del navegador** (en el servidor). Basado en el motor **V8** de Chrome, destaca por su **alto rendimiento** y un modelo **no bloqueante**.
- Se usa para **APIs REST**, websockets en **tiempo real**, **microservicios** y scripts de automatización.

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Logo de Node.js y verificación de versiones en consola.</div>
  <img alt="Node.js" width="120" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/nodejs.png" />
</div>

**Instalación y verificación**
```bash
node -v
npm -v
```

**Hola mundo con http nativo**
```js
// server.js
const http = require('http');
const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hola desde Node.js!');
});
server.listen(3000, () => console.log('Servidor en http://localhost:3000'));
```

**Servidor con Express**
```bash
npm init -y
npm install express
```
```js
// index.js
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('API ok ✅'));
app.listen(3000, () => console.log('http://localhost:3000'));
```

---

### 🔹 npm (Node Package Manager)
npm es el **gestor de paquetes** de Node. Permite **instalar, actualizar** y **eliminar** librerías, además de definir **scripts**.

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Logo de npm y flujo de instalación de paquetes.</div>
  <img alt="npm" width="120" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/npm.png" />
</div>

**Comandos clave**
```bash
npm init -y                   # crea package.json
npm install axios             # dependencia de producción
npm install -D vite           # dependencia de desarrollo
npm uninstall axios           # desinstalar
npm update                    # actualizar
npx create-react-app miApp    # ejecuta binarios sin instalar global
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Ejemplo real de instalación en consola.</div>
  <img alt="npm install consola" width="320" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/npm-install.png" />
</div>

**Scripts útiles en package.json**
```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  }
}
```

---

# 📚 Parte 2 — React

### 🔹 Conceptos base
- **Componentes**: piezas reutilizables (funcionales son los más usados).
- **JSX**: escribir HTML dentro de JS.
- **Props**: datos que recibe un componente.
- **Estado** con **Hooks**: `useState`, `useEffect`.

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Logo de React: UI declarativa basada en componentes.</div>
  <img alt="React logo" width="120" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/react-logo.png" />
</div>

**Crear app con CRA**
```bash
npx create-react-app mi-app
cd mi-app
npm start
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Consola creando proyecto con Create React App.</div>
  <img alt="Create React App" width="320" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/create-react..png" />
</div>

**Componente + props + estado**
```jsx
function Saludo({ nombre }) {
  const [conteo, setConteo] = React.useState(0);
  return (
    <div>
      <h3>Hola, {nombre} 👋</h3>
      <button onClick={() => setConteo(conteo + 1)}>Clicks: {conteo}</button>
    </div>
  );
}
```

**Efectos y fetch**
```jsx
function Usuarios() {
  const [datos, setDatos] = React.useState([]);
  React.useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(r => r.json()).then(setDatos);
  }, []);
  return <ul>{datos.map(u => <li key={u.id}>{u.name}</li>)}</ul>;
}
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Visual de componentes y jerarquía.</div>
  <img alt="React Components" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/react-components.png" />
</div>

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Esquema de hooks más usados.</div>
  <img alt="React Hooks" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/react-hooks.png" />
</div>

---

# 📚 Parte 3 — Vite

### 🔹 ¿Por qué Vite?
- **Arranque ultrarrápido** (ESM nativo).
- **HMR** (hot reload) inmediato.
- Plantillas para **React, Vue, Svelte, TS**.

**Crear proyecto con Vite**
```bash
npm create vite@latest mi-app
cd mi-app
npm install
npm run dev
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Logo Vite y arranque del servidor dev.</div>
  <img alt="Vite" width="120" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/vite.png" />
</div>

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Consola mostrando URL local y HMR activo.</div>
  <img alt="Vite consola" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/vite-console.png" />
</div>

**vite.config.js con React**
```js
// vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
export default defineConfig({
  plugins: [react()],
})
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Estructura típica en proyectos Vite (src, main.jsx, index.html).</div>
  <img alt="Vite estructura" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/vite-structure.png" />
</div>

---

# 📚 Parte 4 — Next.js

### 🔹 Puntos clave
- **SSR/SSG/ISR**: distintas estrategias de renderizado.
- **Rutas por archivos** en `/pages` (y App Router en `/app` en versiones modernas).
- **API Routes** en `/pages/api`.
- Optimización de imágenes con `next/image`.

**Crear app**
```bash
npx create-next-app mi-app
cd mi-app
npm run dev
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Logo Next.js.</div>
  <img alt="Next.js" width="120" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/nextjs.png" />
</div>

**Páginas y rutas (Pages Router)**
```jsx
// pages/index.js
export default function Home() { return <h1>Inicio</h1>; }
// pages/about.js
export default function About() { return <h1>Acerca de</h1>; }
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Estructura de carpetas habitual: pages, public, styles.</div>
  <img alt="Next estructura" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/nextjs-structure.png" />
</div>

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Ejemplo de rutas en Pages Router.</div>
  <img alt="Next páginas" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/nextjs-pages.png" />
</div>

**Datos en SSR/SSG**
```jsx
// SSR
export async function getServerSideProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/users');
  const users = await res.json();
  return { props: { users } };
}

// SSG + ISR
export async function getStaticProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  const posts = await res.json();
  return { props: { posts }, revalidate: 60 };
}
```

**API Route básico**
```js
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hola desde API Route' });
}
```

---

# 📚 Parte 5 — Comparación rápida

| Herramienta | Ventajas | Limitaciones | Uso recomendado |
|-------------|----------|--------------|-----------------|
| **CRA** | Sencillo para empezar, oficial | Arranque y builds más lentos | Educación, prototipos |
| **Vite** | Arranque veloz, HMR instantáneo | Menos guías antiguas | Proyectos modernos |
| **Next.js** | SSR/SSG/ISR, SEO, API Routes | Más curva de aprendizaje | Producción y SEO |

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Tabla visual comparativa (logos CRA, Vite, Next).</div>
  <img alt="Comparación" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/comparacion.png" />
</div>

---

# 📝 Parte 6 — Práctica Calificada 3 (PC3)

### 1) Ruleta dinámica
**Requisitos clave**
- Lista editable en TextArea.
- Botón/tecla **SPACE** para girar, **R** reinicia, **S** oculta ítem, **E** edita.
- Persistencia en `localStorage`.

**Pseudocódigo del giro**
```js
elementos = cargarDesdeLocalStorage() || ["A", "B", "C"];
angulo = 0;
function girar() {
  const vueltas = 360 * (3 + Math.floor(Math.random()*4));
  const target = Math.floor(Math.random()*elementos.length);
  const porcion = 360 / elementos.length;
  angulo = vueltas + target * porcion;
  rueda.style.transform = `rotate(${angulo}deg)`;
}
```

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Ruleta lista para girar.</div>
  <img alt="Ruleta" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/ruleta.png" />
</div>

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Ruleta girando y seleccionando un elemento.</div>
  <img alt="Ruleta girando" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/ruleta-girando.gif" />
</div>

### 2) Sorteo de equipos
**Lógica de reparto**
```js
function sortear(participantes, nEquipos) {
  const mezcla = [...participantes].sort(() => Math.random()-0.5);
  const equipos = Array.from({length: nEquipos}, () => []);
  let i = 0;
  for (const p of mezcla) { equipos[i % nEquipos].push(p); i++; }
  return equipos;
}
```

**Acciones finales**
- **Descargar JPG** de la grilla.
- **Copiar** resultados al portapapeles.
- **Copiar en columnas** (separadas por tabulaciones).

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Interfaz de sorteo con participantes y opciones.</div>
  <img alt="Sorteo" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/sorteo-equipos.png" />
</div>

<div align="center" style="max-width:760px; margin:12px auto; padding:16px; border:1px solid #e2e8f0; border-radius:14px; background:#f8fafc;">
  <div align="left"><b>Comentario:</b> Equipos generados.</div>
  <img alt="Equipos generados" width="420" src="https://github.com/machaparionaangelyoelver-web/fotosdecuaderno/blob/acf948833fa1ec7311c624f21b5fc1621805dac8/semana05_imagenes/equipos-generados.png" />
</div>

---

# ✅ Conclusiones
Esta semana consolidé la base del ecosistema **JavaScript** desde el backend hasta el frontend. Con **Node.js** y **npm** aprendí a iniciar proyectos, gestionar dependencias y scripts. En **React** reforcé componentes, props, estado y efectos; con **Vite** entendí por qué el flujo moderno acelera el desarrollo; y con **Next.js** vi cómo optimizar SEO y rendimiento con SSR/SSG e **API Routes**.

La **PC3** me permitió aplicar JavaScript puro para crear interfaces interactivas (ruleta y sorteo), trabajar el **DOM**, eventos del teclado, animaciones CSS y **persistencia** con `localStorage`. Siento que ahora tengo mejores herramientas para construir aplicaciones desde cero, elegir el **stack** adecuado y organizar mejor mi trabajo.

---

<p align="center">
✨ Elaborado por <b>Macha Pariona Angel Yoelver</b> · Cuaderno Digital — Semana 05 ✨
</p>

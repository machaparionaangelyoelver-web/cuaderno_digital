<!-- ENCABEZADO animado con ola -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=140&color=0:0EA5E9,100:0F766E&text=📗%20Cuaderno%20Digital%20—%20Semana%2007&fontAlign=50&fontAlignY=35&fontSize=34&fontColor=ffffff&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana03_imagenes/uncp.jpg" width="90" alt="Logo UNCP" style="margin:10px;">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana03_imagenes/logoFIS.png" width="90" alt="Logo FIS" style="margin:10px;">
</p>

<p align="center">
  <img
    alt="Semana 07 — React Hooks + Comunicación Padre-Hijo"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3500&pause=1200&color=14B8A6&center=true&vCenter=true&width=980&lines=%E2%9A%9B%EF%B8%8F%20Semana%2007%20%E2%80%94%20React%20Hooks%20%2B%20Comunicaci%C3%B3n%20Padre-Hijo"
  />
</p>



<p align="center">
  <img
    alt="Macha Pariona Angel Yoelver — Desarrollo de Aplicaciones Web"
    src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3500&pause=1200&color=14B8A6&center=true&vCenter=true&width=980&lines=Macha%20Pariona%20Angel%20Yoelver%20%E2%80%94%20Desarrollo%20de%20Aplicaciones%20Web"
  />
</p>



---

## 🧭 Introducción

Durante esta semana se abordaron dos temas claves del desarrollo con **React**:

1. El uso de **Hooks**, que permiten manejar el estado y el ciclo de vida de los componentes funcionales.  
2. La **comunicación entre componentes**, que asegura un flujo de datos estructurado entre elementos **Padre, Hijo y Children**.

Ambos conceptos fortalecen la arquitectura del código, promoviendo la reutilización, la claridad y la eficiencia.

---

## 💡 Conceptos Fundamentales

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/conceptos/concepto_01.png" width="380" alt="Concepto Hooks" />
</p>

Los **Hooks** son funciones especiales introducidas en React 16.8 que permiten a los componentes funcionales usar características como el **estado**, el **ciclo de vida** y el **contexto** sin necesidad de clases.  
El más común es `useState`, pero existen otros que ayudan en la gestión de datos, efectos y optimización.

| Hook | Propósito | Ejemplo breve |
|------|------------|----------------|
| **useState** | Manejar estados locales | `const [x, setX] = useState(0)` |
| **useEffect** | Ejecutar efectos secundarios | `useEffect(() => {...}, [])` |
| **useRef** | Referenciar elementos sin renderizar | `inputRef.current.focus()` |
| **useMemo** | Memorizar valores calculados | `useMemo(() => calc(a), [a])` |
| **useCallback** | Memorizar funciones | `useCallback(fn, [dep])` |
| **useContext** | Compartir datos globales | `useContext(UserContext)` |

---

## ⚙️ Hooks esenciales y sus diagramas

### 🔹 useState – Manejo de estado

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/hooks/useState_flujo.png" width="380" alt="Flujo useState" />
</p>

```jsx
import { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);
  return (
    <div>
      <p>Has hecho clic {contador} veces</p>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
    </div>
  );
}
```

`useState` retorna un valor y una función para actualizarlo sin modificar el estado original directamente.

---

### 🔹 useEffect – Efectos secundarios

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/hooks/useEffect_ciclo.png" width="380" alt="Ciclo useEffect" />
</p>

```jsx
import { useEffect, useState } from "react";

function Reloj() {
  const [hora, setHora] = useState(new Date().toLocaleTimeString());

  useEffect(() => {
    const intervalo = setInterval(() => {
      setHora(new Date().toLocaleTimeString());
    }, 1000);

    return () => clearInterval(intervalo);
  }, []);

  return <h3>🕒 Hora actual: {hora}</h3>;
}
```

**Conclusión:** `useEffect` se ejecuta después del renderizado, ideal para sincronizar datos o ejecutar tareas temporales.

---

### 🔹 useRef – Referencias sin re-render

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/hooks/useRef_diagrama.png" width="380" alt="useRef Diagrama" />
</p>

Permite acceder a elementos del DOM sin provocar nuevos renderizados.

```jsx
import { useRef } from "react";

function EnfocarInput() {
  const inputRef = useRef();
  const enfocar = () => inputRef.current.focus();

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Escribe aquí..." />
      <button onClick={enfocar}>Enfocar</button>
    </div>
  );
}
```

---

### 🔹 useMemo y useCallback – Optimización de rendimiento

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/hooks/useMemo_vs_useCallback.png" width="380" alt="useMemo vs useCallback" />
</p>

| Hook | Enfocado en | Descripción |
|------|--------------|-------------|
| **useMemo** | Valores | Memoriza el resultado de una función costosa |
| **useCallback** | Funciones | Memoriza la referencia de una función |

---

### 🔹 useContext – Comunicación global

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/hooks/context_provider_tree.png" width="380" alt="Context Provider Tree" />
</p>

```jsx
const TemaContext = createContext();

function App() {
  return (
    <TemaContext.Provider value="oscuro">
      <Barra />
    </TemaContext.Provider>
  );
}
```

El contexto evita la necesidad de pasar `props` manualmente entre muchos componentes anidados.

---

## 🧩 Comunicación entre componentes

### 🧠 Concepto

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/conceptos/concepto_02.png" width="380" alt="Concepto Children y Padre-Hijo" />
</p>

La **comunicación entre componentes** es el proceso mediante el cual los datos y eventos se transfieren entre diferentes niveles del árbol de componentes.

| Tipo | Dirección | Ejemplo |
|------|------------|----------|
| **Padre → Hijo** | Descendente | Props |
| **Hijo → Padre** | Ascendente | Callbacks |
| **Hermano ↔ Hermano** | Lateral | Context / Estado global |

---

### 🧱 Ejemplo clásico: Padre–Hijo

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/componentes/padre_hijo.png" width="380" alt="Diagrama Padre Hijo" />
</p>

```jsx
function Hijo({ nombre }) {
  return <p>👶 Hola, soy el hijo. Me llamo {nombre}.</p>;
}

function Padre() {
  return (
    <div>
      <h3>👨 Componente Padre</h3>
      <Hijo nombre="Yoelver" />
    </div>
  );
}
```

---

### 🧩 Uso de Children

Permite renderizar contenido dinámico pasado entre etiquetas.

<p align="center">
  <img src="https://raw.githubusercontent.com/machaparionaangelyoelver-web/fotosdecuaderno/main/semana07_imagenes/componentes/children_example.png" width="380" alt="Children Example" />
</p>

```jsx
function Contenedor({ children }) {
  return <div className="caja">{children}</div>;
}

function App() {
  return (
    <Contenedor>
      <h2>🌟 Soy un contenido pasado como children</h2>
    </Contenedor>
  );
}
```

---

## 🧠 Práctica Integrada

Desarrolla una mini aplicación con las siguientes características:

| Elemento | Descripción |
|-----------|--------------|
| 🧩 useState | Contador de clics |
| 🕓 useEffect | Temporizador dinámico |
| 🔍 useRef | Input que se enfoca automáticamente |
| 👨‍👦 Props | Comunicación Padre–Hijo |
| 🧱 Children | Renderizado de elementos hijos |

Objetivo: integrar todos los hooks vistos y reflejar el flujo de datos entre componentes.

---

## 📊 Comparación general

| Aspecto | Hooks | Comunicación Padre-Hijo |
|----------|--------|--------------------------|
| Propósito | Control del estado y ciclo de vida | Transferencia de datos |
| Naturaleza | Interna (componente) | Externa (entre componentes) |
| Ejemplo | `useState`, `useEffect` | `props`, `children` |
| Ventaja | Reutilización de lógica | Organización del flujo de datos |

---

## 🧭 Reflexión final

Los **Hooks** transformaron la forma en que React maneja el estado y la lógica.  
Entender cómo un **Padre comunica información a sus Hijos** y cómo los **Children** permiten flexibilidad estructural es clave para desarrollar aplicaciones modulares, reutilizables y eficientes.  

Este conocimiento sienta las bases para el uso avanzado de **Context API**, **Custom Hooks** y **manejo global de estados** en React.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:0F766E,100:0EA5E9&section=footer" />
</p>

# 🥗 NutriTrack PRO - Planificador de Comidas y Macronutrientes

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/Licencia-MIT-green.svg?style=flat-square)](LICENSE)

> Aplicación web moderna, interactiva y ligera para el cálculo de gasto energético (TDEE), planificación diaria de comidas y control en tiempo real de macronutrientes y calorías.

---

## 📌 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Demostración Visual y Funcional](#-demostración-visual-y-funcional)
- [Arquitectura Técnica](#-arquitectura-técnica)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Instalación y Uso](#-instalación-y-uso)
- [Modelo Científico y Algoritmos](#-modelo-científico-y-algoritmos)
- [Almacenamiento y Privacidad](#-almacenamiento-y-privacidad)
- [Roadmap de Mejoras](#-roadmap-de-mejoras)
- [Licencia](#-licencia)

---

## ✨ Características Principales

### 🎯 Calculadora Metabólica y Metas Nutricionales
- **Ecuación de Mifflin-St Jeor**: Estima de forma precisa la Tasa Metabólica Basal (TMB) y el Gasto Energético Total Diario (TDEE) considerando género, edad, peso, estatura y nivel de actividad física (1.2 a 1.9).
- **Ajustes de Objetivo Calórico**:
  - Déficit Agresivo (-20% kcal)
  - Déficit Moderado (-15% kcal)
  - Mantenimiento (0%)
  - Superávit Limpio / Volumen (+10% kcal)
  - Superávit Intenso (+18% kcal)
- **Perfiles de Distribución de Macros**: Equilibrado (30/45/25), Alto en Proteína (35/40/25), Bajo en Carbohidratos (35/25/40) y Rendimiento Deportivo (25/55/20).
- **Modo Manual**: Opción para configurar directamente calorías y gramos objetivo con validación cruzada energética ($4 \times \text{P} + 4 \times \text{C} + 9 \times \text{G}$).

### 📊 Dashboard Dinámico en Tiempo Real
- **Anillo de Progreso SVG Interactivo**: Visualiza calorías restantes o excedidas con cambio dinámico de color (esmeralda a rojo si hay superávit excedido).
- **Control de Macronutrientes**: Tarjetas individuales para Proteínas, Carbohidratos y Grasas con porcentaje de cumplimiento, barras animadas y gramos faltantes/excedidos.
- **Gráfico de Distribución Calórica Real**: Barra segmentada porcentual que muestra la proporción actual de macros consumidos.
- **Rastreador de Hidratación**: Contador rápido de vasos de agua diarios (0 a 8+ vasos).

### 🍽️ Planificador de Comidas por Tiempos
- División en 4 comidas clave: **Desayuno**, **Almuerzo**, **Cena** y **Snacks/Meriendas**.
- Métricas independientes por cada comida (Kcal totales, P, C, G).
- **Edición en línea de porciones**: Modificación directa de gramos en cualquier alimento registrado con recálculo instantáneo.
- Eliminación individual de alimentos o vaciado controlado del día mediante modal seguro.

### 🔍 Base de Datos de Alimentos y Creación Personalizada
- **28 alimentos base precargados** en español con densidad nutricional por porción estándar.
- **Buscador instantáneo** con filtros por categorías (Proteínas, Carbohidratos, Grasas y Lácteos, Frutas y Verduras, Creados).
- **Modal de Porciones con Multiplicadores**: Previsualización inmediata en ½x, 1x, 1.5x, 2x o ingreso manual en gramos/ml.
- **Creador de Alimentos Personalizados**: Agrega tus propios alimentos indicando porción base, unidad (g, ml, porción), macros y calorías calculadas automáticamente.

### 🎨 Experiencia de Usuario (UX/UI)
- **Tema Oscuro / Claro**: Detección y cambio fluido con persistencia en preferencias.
- **Diseño Responsivo**: Optimizado para dispositivos móviles, tablets y monitores de escritorio.
- **Sistema de Alertas Toast**: Notificaciones flotantes no invasivas para confirmar acciones.
- **Día de Ejemplo**: Botón de carga demostrativa con un plan balanceado de 4 comidas preconfiguradas.

---

## 🛠️ Arquitectura Técnica

NutriTrack Pro está desarrollado bajo la filosofía de **Zero-Dependency Runtime**:

| Componente | Tecnología / Librería | Descripción |
| :--- | :--- | :--- |
| **Estructura** | HTML5 Semántico | Marcado accesible con contenedores semánticos (`<main>`, `<header>`, `<section>`). |
| **Estilos** | Tailwind CSS CDN + CSS Nativo | Maquetación responsiva, flexbox, grid y transiciones CSS fluidas. |
| **Tipografía** | Google Fonts (Inter) | Fuente tipográfica moderna de alta legibilidad. |
| **Iconos** | Lucide Icons | Conjunto de iconos vectoriales ligeros. |
| **Lógica** | Vanilla JavaScript (ES6+) | Gestión de estado reactiva unidireccional y manipulación eficiente del DOM. |
| **Persistencia** | Web Storage API (`localStorage`) | Almacenamiento local persistente sin backend ni base de datos externa. |

---

## 📂 Estructura del Proyecto

```text
nutritrack/
│
├── nutritrack.html        # Aplicación monolítica completa (HTML, Tailwind CSS, JS)
└── README.md              # Documentación técnica completa del proyecto
```

---

## 🚀 Instalación y Uso

No requiere Node.js, compiladores ni dependencias locales.

### Opción 1: Ejecución Directa en el Navegador
1. Clona o descarga este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/nutritrack.git
   ```
2. Abre el archivo `nutritrack.html` en tu navegador web preferido (Chrome, Edge, Firefox, Safari):
   ```bash
   # En Windows PowerShell:
   Start-Process .\nutritrack.html
   ```

### Opción 2: Servidor Local Ligero (Opcional)
Si deseas servirlo mediante un servidor web local:
```bash
# Con Python 3:
python -m http.server 8080

# Con Node.js (npx serve):
npx serve .
```
Luego visita `http://localhost:8080/nutritrack.html`.

---

## 🔬 Modelo Científico y Algoritmos

### 1. Tasa Metabólica Basal (TMB) - Fórmula Mifflin-St Jeor
Reconocida por la *American Dietetic Association* como una de las estimaciones más precisas para población general:

$$\text{Hombres: } \text{TMB} = (10 \times \text{peso [kg]}) + (6.25 \times \text{altura [cm]}) - (5 \times \text{edad [años]}) + 5$$

$$\text{Mujeres: } \text{TMB} = (10 \times \text{peso [kg]}) + (6.25 \times \text{altura [cm]}) - (5 \times \text{edad [años]}) - 161$$

### 2. Gasto Energético Total Diario (TDEE)
$$\text{TDEE} = \text{TMB} \times \text{Factor de Actividad}$$

Factores de actividad aplicados:
- **Sedentario**: $1.2$
- **Ligero** (1-3 días/sem): $1.375$
- **Moderado** (3-5 días/sem): $1.55$
- **Activo** (6-7 días/sem): $1.725$
- **Muy Activo / Atleta**: $1.9$

### 3. Equivalencias Energéticas de Macronutrientes
- **Proteína**: $4 \text{ kcal/g}$
- **Carbohidratos**: $4 \text{ kcal/g}$
- **Grasas**: $9 \text{ kcal/g}$

---

## 🔒 Almacenamiento y Privacidad

- **100% Privado y Local**: Todos tus datos corporales, comidas ingresadas y alimentos creados se almacenan únicamente en el `localStorage` de tu navegador bajo la clave `nutritrack_pro_state_v1`.
- **Cero telemetría**: No se envían datos personales, pesos ni hábitos alimenticios a ningún servidor externo.
- **Protección XSS**: Toda entrada de texto proporcionada por el usuario (nombres de alimentos, notas) es sanitizada mediante una función dedicada `escapeHtml()` antes de insertarse en el DOM.

---

## 🗺️ Roadmap de Mejoras Recomendadas

- [ ] **Historial Multi-Día**: Selector de fechas tipo calendario para revisar días previos y promedios semanales.
- [ ] **Exportación / Importación**: Descarga y carga de datos en formato JSON o exportación de reportes en PDF/CSV.
- [ ] **Desacoplamiento Modular**: Separar `nutritrack.html` en archivos independientes (`index.html`, `styles.css`, `app.js`) o migrar a un framework como Vite/React si la escala lo requiere.
- [ ] **PWA (Progressive Web App)**: Service Worker y `manifest.json` para permitir instalación en el móvil y funcionamiento 100% offline sin conexión a CDN.
- [ ] **Integración de API de Alimentos**: Conexión opcional con APIs abiertas como *Open Food Facts* para lectura mediante código de barras.

---

## 📄 Licencia

Este proyecto se distribuye bajo los términos de la Licencia **MIT**. Consulta el archivo `LICENSE` para más información.

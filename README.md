# MVP Agente de Solicitud de Préstamos (Sprint 3 – v1)
Prototipo funcional de una **web app con agente IA** para la **solicitud de préstamos**, desarrollado en Replit como parte del Sprint 3 del proyecto.

La solución integra:
- **Landing page** orientada a conversión
- **Formulario progresivo de 4 pasos**
- **Backend en Node.js** para procesar la solicitud
- **Integración con GPT-4o-mini** para respuestas conversacionales
- **Pantalla de confirmación** con número de solicitud único

> **Objetivo del MVP:** validar una experiencia digital de onboarding de préstamo que combine captura de datos + orientación inteligente en tono humano, cálido y accionable.

---

## ✨ Demo del MVP (qué hace)

La aplicación permite que un usuario:

1. Ingrese a una **landing page** moderna con enfoque en confianza y conversión.
2. Complete un **formulario progresivo de 4 pasos** con datos de solicitud.
3. Envíe su información sin recargar la página.
4. Reciba una **respuesta del agente IA** con:
   - resumen de su solicitud
   - orientación inicial
   - próximos pasos sugeridos
5. Visualice una **pantalla de confirmación** con:
   - mensaje de éxito
   - número de solicitud generado (`SOL-YYYY-XXXXX`)
   - opción para iniciar una nueva solicitud

---

## 🧠 Enfoque del Agente IA

El agente está diseñado para comportarse como un **asistente de onboarding de créditos**, con foco en:

- guía paso a paso
- lenguaje claro y profesional
- tono cercano y empático
- respuestas naturales (no robóticas)
- orientación referencial (sin prometer aprobación)

### Principios de comportamiento (respetados en el MVP)
- No promete aprobación del préstamo.
- No reemplaza la evaluación crediticia formal.
- Entrega orientación y próximos pasos.
- Mantiene un tono humano y conversacional.

---

## 🧩 Funcionalidades implementadas (v1)

### 1) Landing Page (estilo banca digital)
- Hero section con propuesta de valor
- CTA principales:
  - **Solicitar Ahora**
  - **Ver Requisitos**
- Indicadores de confianza (ej. aprobación, tiempo de respuesta, transparencia)
- Estética moderna con:
  - gradientes azules
  - glassmorphism
  - animaciones suaves

### 2) Formulario progresivo de 4 pasos
Captura información en secuencia:

- **Paso 1:** Tipo de usuario y producto
- **Paso 2:** Identificación (KYC)
- **Paso 3:** Datos de la solicitud
- **Paso 4:** Datos económicos + aceptación de términos

Incluye:
- validación por paso
- navegación con botones **Anterior / Siguiente**
- indicadores visuales de progreso
- submit sin recarga de página (`preventDefault`)

### 3) Agente Inteligente con IA (GPT-4o-mini)
- El backend en Node.js recibe el payload del formulario.
- Se construye un prompt contextualizado.
- Se consulta a **GPT-4o-mini** (vía integración nativa de Replit AI).
- Se devuelve una respuesta conversacional y accionable.

### 4) Pantalla de confirmación
- Confirmación visual de envío
- Número de solicitud único (`SOL-YYYY-XXXXX`)
- Recomendación/resultado del agente IA
- Opción para reiniciar flujo

---

## 🏗️ Arquitectura (alto nivel)

```text
Usuario (Web App)
   │
   ├── Landing Page (UI)
   ├── Formulario 4 pasos (Frontend)
   │       │
   │       └── Envío de datos (fetch / async)
   │
   └── Backend Node.js (Replit)
           │
           ├── Construcción de prompt contextualizado
           ├── Llamada a GPT-4o-mini (Replit AI)
           └── Respuesta al frontend (texto natural + sugerencias)

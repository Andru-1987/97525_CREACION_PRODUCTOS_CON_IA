## APP a realizar : Una aplicacion de reservas de espacios comunes para edificios.

# Prompt para Definir el Problema y el User Journey de la App de Reservas

## **1. Prompt para Mini-Investigación y Descripción del Problema**

````
**Contexto:** Estoy desarrollando una aplicación web/móvil para reservar espacios comunes en edificios residenciales (SUM, parrilla, quincho, cine, gimnasio, sala de reuniones, etc.). Necesito una descripción completa del problema actual para presentar a stakeholders.

**Instrucciones:**
1. **Describe el problema actual** que enfrentan residentes y administradores de edificios al gestionar reservas de espacios comunes, incluyendo:
   - **Dolores funcionales** (logística, comunicación, disponibilidad)
   - **Dolores emocionales** (frustración, ansiedad, conflicto)
   - **Dolores sociales** (relaciones vecinales, equidad de acceso)

2. **Enumera las alternativas actuales** que usan los residentes (ej: WhatsApp, pizarras físicas, llamadas al administrador) y sus limitaciones específicas.

3. **Identifica consecuencias** de no resolver el problema (pérdida de tiempo, dinero, conflictos vecinales, infrautilización de espacios).

4. **Destaca la oportunidad** de una solución digital centralizada.

**Formato de respuesta:** Lista estructurada con viñetas claras y ejemplos concretos.
````

---

## **2. Prompt para Generar User Journey**

````
 **Contexto:** Para una app de reserva de espacios comunes en edificios, necesito mapear el viaje completo del usuario desde que decide reservar hasta que usa el espacio.

 **Instrucciones:**
 Crea un User Journey detallado para **dos perfiles diferentes**:
 
 **A. PARA EL RESIDENTE (ej: "María", madre que quiere reservar el SUM para cumpleaños):**
 1. **Etapa 1: Descubrimiento de la necesidad** (necesita un espacio para evento)
 2. **Etapa 2: Investigación de disponibilidad** (cómo verifica hoy si está libre)
 3. **Etapa 3: Proceso de reserva** (pasos actuales para asegurar el espacio)
 4. **Etapa 4: Confirmación y recordatorios** (cómo se asegura de que quedó reservado)
 5. **Etapa 5: Uso del espacio** (qué pasa al llegar al espacio)
 6. **Etapa 6: Post-uso** (devolución de llaves, comentarios, etc.)
 
 **B. PARA EL ADMINISTRADOR (ej: "Roberto", encargado del edificio):**
 1. **Etapa 1: Recepción de solicitudes** (cómo le llegan las peticiones)
 2. **Etapa 2: Verificación y aprobación** (cómo verifica disponibilidad y aprueba)
 3. **Etapa 3: Registro manual** (cómo lleva el control actual)
 4. **Etapa 4: Comunicación** (cómo notifica a residentes)
 5. **Etapa 5: Gestión de conflictos** (qué hace cuando hay superposiciones)
 
 **Para cada etapa, incluye:**
 - **Puntos de dolor** específicos
 - **Emociones** asociadas
 - **Oportunidades de mejora** (formato "¿Cómo podríamos...?")

 **Formato de respuesta:** Tabla o diagrama de etapas claramente separadas.
````
---

## **3. Prompt para Analizar Herramientas y Casos de Uso**

````
 **Contexto:** Evaluando la implementación técnica y casos de uso real de una app de reservas para edificios.

 **Instrucciones:**
 1. **Herramientas recomendadas para cada etapa:**
    - **Research/Validación:** (ej: entrevistas con The Mom Test, Google Forms)
    - **Prototipado rápido:** (ej: v0.dev, Lovable)
    - **Desarrollo MVP:** (ej: Next.js + Supabase + Vercel)
    - **Base de datos:** (ej: Supabase)
    - **Notificaciones:** (ej: EmailJS o aplicaciones Open-Source)
 
 2. **Casos de uso en tiempo real:**
    - **Reserva de último momento** (ej: vecino quiere la parrilla esta misma noche)
    - **Cancelación urgente** (y liberación automática del espacio)
    - **Verificación in situ** (al llegar al espacio, ver QR con reserva confirmada)
    - **Alertas automáticas** (recordatorio 1 hora antes, alerta de limpieza pendiente)
 
 3. **Rentabilidad en diferentes plazos:**
    - **Corto plazo (0-6 meses):** Modelo B2B - Suscripción mensual por edificio (ej: $50-200/mes por edificio según cantidad de unidades). Validación con 5-10 edificios piloto.
    - **Mediano plazo (6-18 meses):** Upselling con módulos premium (pagos, gestión de multas, integración con contabilidad). Expansión a condominios y countries.
    - **Largo plazo (18+ meses):** Marketplace de proveedores (catering, limpieza, mantenimiento) con comisión. Datos agregados de uso de espacios para desarrolladoras inmobiliarias.

 **Formato de respuesta:** Listas organizadas por categoría con justificación breve para cada punto.
````
---

## **Prompt Integrado (Todo en Uno)**

````
 **Contexto completo:** Soy un desarrollador/product manager creando una aplicación para reservar espacios comunes en edificios (SUM, parrilla, quincho, cine, gimnasio, etc.). La app tendrá dos interfaces principales: una para residentes y otra para administradores.

 **Necesito que me ayudes con:**
 
 **1. DESCRIPCIÓN DEL PROBLEMA**
 - Analiza los dolores actuales de residentes y administradores
 - Lista las soluciones actuales y sus fallas
 - Describe las consecuencias de no resolverlo
 
 **2. USER JOURNEY COMPLETO**
 - Para el residente: desde "necesito un espacio" hasta "dejo el espacio limpio"
 - Para el administrador: desde "recibo una solicitud" hasta "cierro el mes"
 - Incluye puntos de dolor y emociones en cada paso
 
 **3. HERRAMIENTAS Y CASOS DE USO**
 - Recomienda herramientas técnicas para cada fase del proyecto
 - Describe casos de uso en tiempo real que agreguen valor inmediato
 - Propón un modelo de rentabilidad escalable (corto, mediano y largo plazo)
 
 **4. HIPÓTESIS CRÍTICA PARA EL MVP**
 - Formula la hipótesis principal que debemos validar con la primera versión
 - Sugiere 2-3 métricas clave para medir éxito
 
 **Formato final:** Un documento estructurado con secciones claras, ideal para presentar a un equipo o inversores.
````

## Prompt para empezar con el front end de la app

```
Eres un desarrollador fullstack senior, necesito que me desarrolles un prompt muy completo para crear una solución para el siguiente problema: un edificio o administracion de edificios con espacions comunes, me pregunto de realizar una app que permita reservar de forma sencilla esos espacios comunes.

La app web la voy a crear en <colocar la herramienta de vibecoding predilecto> con supabase conectado, por lo que también necesito que crees las tablas necesarias.

Debe existir un dashboard “administrador” para administrador. Ahí, esa persona gestionará las altas de sus residentes permitidos, eventos importantes, fechas que no estaran disponibles, calendario interactivo para observar por dia, semana y mes, etc.

Al crear el alta al residente, se asignará un usuario y contraseña con el que podrá entrar el residente. El residente lo que va a haber será un panel tipo calendario, donde podrá reservar los espacios de acuerdo al día y horario disponible.

Luego, el administrador, podrá ver quienes están en la lista reservadas.

Tareas que deberia cumplirse:

- Desplegar un esta app para gestionar los residentes.
- Es posible ingresar residentes importando archivos .csv o ingresando múltiples datos separados por coma.
- no usaremos AI al inicio.
- el estilo de la app debe usar la imagen que este pasando o en su defecto hacer uso de la siguiente paleta de colores: usar el archivo css en cuestion
- Función de modos claro/oscuro.
- Formato PWA (Progressive Web App)
- Servicios de Supabase: app hosting, realtime database y authentication.
```

<details>
<summary>Template de estilos para la app</summary>

```css
/* ==========================================================================
CSS TEMPLATE: APP RESERVAS ESPACIOS - ESTILO ELEGANTE MODERNO
========================================================================== */

/* ==========================================================================
1. VARIABLES Y CONFIGURACIÓN GLOBAL
========================================================================== */

:root {
/* ================================
    PALETA ELEGANTE MODERNA
    ================================ */

/* Modo Oscuro (Default) */
--color-bg-primary: #0F172A;
--color-bg-secondary: #1E293B;
--color-bg-card: #334155;
--color-bg-elevated: #475569;
--color-bg-surface: #1E293B;

--color-text-primary: #F1F5F9;
--color-text-secondary: #CBD5E1;
--color-text-muted: #94A3B8;
--color-text-on-accent: #FFFFFF;

/* Colores por tipo de espacio */
--color-space-sum: #3B82F6;      /* Azul - SUM */
--color-space-parrilla: #10B981; /* Verde - Parrilla */
--color-space-quincho: #F59E0B;  /* Ámbar - Quincho */
--color-space-cine: #8B5CF6;     /* Violeta - Cine */
--color-space-gimnasio: #EF4444; /* Rojo - Gimnasio */
--color-space-sala: #06B6D4;     /* Cian - Sala reuniones */
--color-space-piscina: #0EA5E9;  /* Azul claro - Piscina */

--color-accent-primary: #6366F1;   /* Índigo elegante */
--color-accent-secondary: #8B5CF6; /* Violeta */
--color-accent-success: #10B981;   /* Esmeralda */
--color-accent-warning: #F59E0B;   /* Ámbar */
--color-accent-danger: #EF4444;    /* Rojo coral */
--color-accent-info: #3B82F6;      /* Azul cielo */

--color-border: #475569;
--color-border-light: #64748B;
--color-divider: rgba(148, 163, 184, 0.2);

/* Sombras sutiles */
--shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
--shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
--shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06);
--shadow-accent: 0 0 0 3px rgba(99, 102, 241, 0.1);

/* Gradientes */
--gradient-primary: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
--gradient-secondary: linear-gradient(135deg, #10B981 0%, #06B6D4 100%);
--gradient-dark: linear-gradient(135deg, #1E293B 0%, #0F172A 100%);

/* ================================
    TIPOGRAFÍA ELEGANTE MODERNA
    ================================ */
--font-heading: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-mono: 'JetBrains Mono', 'SF Mono', monospace;

/* Escala tipográfica moderna */
--text-xs: 0.75rem;      /* 12px */
--text-sm: 0.875rem;     /* 14px */
--text-base: 1rem;       /* 16px */
--text-lg: 1.125rem;     /* 18px */
--text-xl: 1.25rem;      /* 20px */
--text-2xl: 1.5rem;      /* 24px */
--text-3xl: 1.875rem;    /* 30px */
--text-4xl: 2.25rem;     /* 36px */
--text-5xl: 3rem;        /* 48px */

/* Espaciado modular */
--space-0: 0;
--space-1: 0.25rem;
--space-2: 0.5rem;
--space-3: 0.75rem;
--space-4: 1rem;
--space-5: 1.25rem;
--space-6: 1.5rem;
--space-8: 2rem;
--space-10: 2.5rem;
--space-12: 3rem;
--space-16: 4rem;

/* Border radius */
--radius-none: 0;
--radius-sm: 0.125rem;
--radius-md: 0.375rem;
--radius-lg: 0.5rem;
--radius-xl: 0.75rem;
--radius-2xl: 1rem;
--radius-3xl: 1.5rem;
--radius-full: 9999px;

/* Transiciones suaves */
--transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1);
--transition-normal: 250ms cubic-bezier(0.4, 0, 0.2, 1);
--transition-slow: 350ms cubic-bezier(0.4, 0, 0.2, 1);

/* Animaciones */
--animation-bounce: bounce 1s infinite;
--animation-pulse: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
--animation-spin: spin 1s linear infinite;
--animation-ping: ping 1s cubic-bezier(0, 0, 0.2, 1) infinite;

/* Z-index layers */
--z-0: 0;
--z-10: 10;
--z-20: 20;
--z-30: 30;
--z-40: 40;
--z-50: 50;
--z-auto: auto;
}

/* ==========================================================================
2. MODO CLARO - OVERRIDES
========================================================================== */

[data-theme="light"] {
--color-bg-primary: #FFFFFF;
--color-bg-secondary: #F8FAFC;
--color-bg-card: #FFFFFF;
--color-bg-elevated: #F1F5F9;
--color-bg-surface: #F8FAFC;

--color-text-primary: #1E293B;
--color-text-secondary: #475569;
--color-text-muted: #64748B;
--color-text-on-accent: #FFFFFF;

/* Colores por espacio (más saturados en modo claro) */
--color-space-sum: #2563EB;
--color-space-parrilla: #059669;
--color-space-quincho: #D97706;
--color-space-cine: #7C3AED;
--color-space-gimnasio: #DC2626;
--color-space-sala: #0891B2;
--color-space-piscina: #0284C7;

--color-accent-primary: #4F46E5;
--color-accent-secondary: #7C3AED;

--color-border: #E2E8F0;
--color-border-light: #F1F5F9;
--color-divider: rgba(148, 163, 184, 0.1);

/* Sombras más pronunciadas en modo claro */
--shadow-sm: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
--shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
--shadow-accent: 0 0 0 3px rgba(79, 70, 229, 0.1);
}

/* ==========================================================================
3. RESET Y ESTILOS BASE
========================================================================== */

*,
*::before,
*::after {
box-sizing: border-box;
margin: 0;
padding: 0;
}

html {
font-size: 16px;
scroll-behavior: smooth;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
}

body {
font-family: var(--font-body);
font-size: var(--text-base);
line-height: 1.5;
color: var(--color-text-primary);
background-color: var(--color-bg-primary);
transition: background-color var(--transition-normal),
            color var(--transition-normal);
min-height: 100vh;
overflow-x: hidden;
}

/* ==========================================================================
4. TIPOGRAFÍA ELEGANTE
========================================================================== */

/* Encabezados con tracking negativo para elegancia */
h1, h2, h3, h4, h5, h6 {
font-family: var(--font-heading);
font-weight: 600;
line-height: 1.25;
margin-bottom: var(--space-4);
color: var(--color-text-primary);
letter-spacing: -0.025em;
}

h1 {
font-size: var(--text-5xl);
font-weight: 700;
background: var(--gradient-primary);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}

h2 {
font-size: var(--text-3xl);
font-weight: 600;
}

h3 {
font-size: var(--text-2xl);
}

h4 {
font-size: var(--text-xl);
}

h5 {
font-size: var(--text-lg);
font-weight: 500;
}

h6 {
font-size: var(--text-base);
font-weight: 500;
text-transform: uppercase;
letter-spacing: 0.1em;
color: var(--color-text-muted);
}

/* Texto de cuerpo */
p {
margin-bottom: var(--space-4);
color: var(--color-text-secondary);
line-height: 1.625;
}

.lead {
font-size: var(--text-xl);
font-weight: 300;
line-height: 1.625;
color: var(--color-text-secondary);
}

.small {
font-size: var(--text-sm);
color: var(--color-text-muted);
}

/* Enlaces elegantes */
a {
color: var(--color-accent-primary);
text-decoration: none;
font-weight: 500;
transition: color var(--transition-fast);
position: relative;
}

a:hover {
color: var(--color-accent-secondary);
}

a.underline {
text-decoration: underline;
text-decoration-thickness: 2px;
text-underline-offset: 2px;
text-decoration-color: var(--color-accent-primary);
}

/* ==========================================================================
5. COMPONENTES UI ESPECÍFICOS PARA RESERVAS
========================================================================== */

/* Tarjetas de espacio */
.space-card {
background: var(--color-bg-card);
border-radius: var(--radius-xl);
padding: var(--space-6);
border: 1px solid var(--color-border);
transition: all var(--transition-normal);
cursor: pointer;
position: relative;
overflow: hidden;
}

.space-card::before {
content: '';
position: absolute;
top: 0;
left: 0;
width: 4px;
height: 100%;
background: var(--space-color, var(--color-accent-primary));
}

.space-card:hover {
transform: translateY(-2px);
box-shadow: var(--shadow-lg);
border-color: var(--color-accent-primary);
}

.space-card.selected {
box-shadow: var(--shadow-accent);
border-color: var(--color-accent-primary);
background: var(--color-bg-elevated);
}

.space-header {
display: flex;
align-items: center;
gap: var(--space-3);
margin-bottom: var(--space-4);
}

.space-icon {
width: 48px;
height: 48px;
border-radius: var(--radius-lg);
display: flex;
align-items: center;
justify-content: center;
color: white;
font-size: var(--text-xl);
background: var(--space-color, var(--color-accent-primary));
}

.space-title {
font-size: var(--text-lg);
font-weight: 600;
color: var(--color-text-primary);
margin: 0;
}

.space-capacity {
display: inline-flex;
align-items: center;
gap: var(--space-1);
font-size: var(--text-sm);
color: var(--color-text-muted);
background: var(--color-bg-secondary);
padding: var(--space-1) var(--space-2);
border-radius: var(--radius-full);
}

/* Calendario de reservas */
.calendar {
background: var(--color-bg-card);
border-radius: var(--radius-xl);
padding: var(--space-6);
border: 1px solid var(--color-border);
}

.calendar-header {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: var(--space-6);
}

.calendar-nav {
display: flex;
align-items: center;
gap: var(--space-2);
}

.calendar-grid {
display: grid;
grid-template-columns: repeat(7, 1fr);
gap: var(--space-2);
}

.calendar-day {
aspect-ratio: 1;
display: flex;
align-items: center;
justify-content: center;
border-radius: var(--radius-md);
font-weight: 500;
cursor: pointer;
transition: all var(--transition-fast);
}

.calendar-day:hover {
background: var(--color-bg-secondary);
}

.calendar-day.today {
background: var(--color-accent-primary);
color: var(--color-text-on-accent);
}

.calendar-day.selected {
background: var(--gradient-primary);
color: var(--color-text-on-accent);
box-shadow: var(--shadow-md);
}

.calendar-day.disabled {
opacity: 0.3;
cursor: not-allowed;
background: transparent;
}

/* Selector de horarios */
.time-slots {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
gap: var(--space-3);
margin-top: var(--space-4);
}

.time-slot {
padding: var(--space-3) var(--space-2);
text-align: center;
border: 1px solid var(--color-border);
border-radius: var(--radius-lg);
background: var(--color-bg-card);
cursor: pointer;
transition: all var(--transition-fast);
font-weight: 500;
}

.time-slot:hover {
border-color: var(--color-accent-primary);
transform: translateY(-1px);
}

.time-slot.selected {
background: var(--gradient-primary);
color: var(--color-text-on-accent);
border-color: transparent;
box-shadow: var(--shadow-md);
}

.time-slot.disabled {
opacity: 0.4;
cursor: not-allowed;
background: var(--color-bg-secondary);
}

.time-slot.booked {
background: var(--color-accent-danger);
color: var(--color-text-on-accent);
border-color: transparent;
cursor: not-allowed;
}

/* Panel de reservas activas */
.reservation-card {
background: var(--color-bg-card);
border-radius: var(--radius-lg);
padding: var(--space-4);
border-left: 4px solid var(--space-color, var(--color-accent-primary));
margin-bottom: var(--space-3);
transition: all var(--transition-normal);
}

.reservation-card:hover {
transform: translateX(4px);
box-shadow: var(--shadow-md);
}

.reservation-status {
display: inline-flex;
align-items: center;
gap: var(--space-1);
font-size: var(--text-xs);
font-weight: 600;
padding: var(--space-1) var(--space-2);
border-radius: var(--radius-full);
text-transform: uppercase;
letter-spacing: 0.05em;
}

.status-confirmed {
background: rgba(16, 185, 129, 0.1);
color: var(--color-accent-success);
}

.status-pending {
background: rgba(245, 158, 11, 0.1);
color: var(--color-accent-warning);
}

.status-cancelled {
background: rgba(239, 68, 68, 0.1);
color: var(--color-accent-danger);
}

/* ==========================================================================
6. COMPONENTES GENERALES REUTILIZABLES
========================================================================== */

/* Botones modernos */
.btn {
display: inline-flex;
align-items: center;
justify-content: center;
padding: var(--space-3) var(--space-6);
font-family: var(--font-body);
font-size: var(--text-base);
font-weight: 500;
line-height: 1;
text-align: center;
white-space: nowrap;
border: none;
border-radius: var(--radius-lg);
cursor: pointer;
transition: all var(--transition-normal);
background: var(--color-bg-secondary);
color: var(--color-text-primary);
position: relative;
overflow: hidden;
}

.btn::after {
content: '';
position: absolute;
inset: 0;
background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
transform: translateX(-100%);
transition: transform 0.6s;
}

.btn:hover::after {
transform: translateX(100%);
}

.btn-primary {
background: var(--gradient-primary);
color: var(--color-text-on-accent);
}

.btn-primary:hover {
transform: translateY(-1px);
box-shadow: var(--shadow-lg);
}

.btn-secondary {
background: transparent;
color: var(--color-accent-primary);
border: 1px solid var(--color-accent-primary);
}

.btn-secondary:hover {
background: var(--color-accent-primary);
color: var(--color-text-on-accent);
}

.btn-lg {
padding: var(--space-4) var(--space-8);
font-size: var(--text-lg);
border-radius: var(--radius-xl);
}

.btn-sm {
padding: var(--space-2) var(--space-4);
font-size: var(--text-sm);
}

.btn-full {
width: 100%;
}

/* Badges para estados */
.badge {
display: inline-flex;
align-items: center;
padding: var(--space-1) var(--space-3);
font-size: var(--text-xs);
font-weight: 600;
line-height: 1;
border-radius: var(--radius-full);
text-transform: uppercase;
letter-spacing: 0.05em;
}

.badge-space {
background: var(--space-color, var(--color-accent-primary));
color: var(--color-text-on-accent);
}

/* Tarjetas de estadísticas */
.stats-card {
background: var(--color-bg-card);
border-radius: var(--radius-xl);
padding: var(--space-6);
border: 1px solid var(--color-border);
}

.stats-value {
font-size: var(--text-4xl);
font-weight: 700;
line-height: 1;
margin: var(--space-2) 0;
background: var(--gradient-primary);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}

.stats-label {
font-size: var(--text-sm);
color: var(--color-text-muted);
text-transform: uppercase;
letter-spacing: 0.1em;
}

/* ==========================================================================
7. LAYOUT Y NAVEGACIÓN
========================================================================== */

/* Header de la app */
.app-header {
background: var(--color-bg-surface);
border-bottom: 1px solid var(--color-border);
padding: var(--space-4) 0;
position: sticky;
top: 0;
z-index: var(--z-40);
backdrop-filter: blur(8px);
}

/* Navegación principal */
.nav-container {
display: flex;
justify-content: space-between;
align-items: center;
max-width: 1280px;
margin: 0 auto;
padding: 0 var(--space-6);
}

.nav-brand {
display: flex;
align-items: center;
gap: var(--space-3);
font-size: var(--text-xl);
font-weight: 700;
color: var(--color-text-primary);
text-decoration: none;
}

.nav-menu {
display: flex;
align-items: center;
gap: var(--space-6);
}

.nav-link {
color: var(--color-text-secondary);
font-weight: 500;
transition: color var(--transition-fast);
}

.nav-link:hover {
color: var(--color-accent-primary);
}

.nav-link.active {
color: var(--color-accent-primary);
position: relative;
}

.nav-link.active::after {
content: '';
position: absolute;
bottom: -8px;
left: 0;
right: 0;
height: 2px;
background: var(--gradient-primary);
border-radius: var(--radius-full);
}

/* Toggle modo claro/oscuro */
.theme-toggle {
width: 44px;
height: 44px;
border-radius: var(--radius-full);
display: flex;
align-items: center;
justify-content: center;
background: var(--color-bg-card);
border: 1px solid var(--color-border);
color: var(--color-text-primary);
cursor: pointer;
transition: all var(--transition-fast);
}

.theme-toggle:hover {
background: var(--color-bg-elevated);
transform: rotate(15deg);
}

/* Contenedor principal */
.main-container {
max-width: 1280px;
margin: 0 auto;
padding: var(--space-8) var(--space-6);
}

/* Grid para espacios */
.spaces-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
gap: var(--space-6);
margin-top: var(--space-8);
}

/* ==========================================================================
8. FORMULARIOS Y MODALES
========================================================================== */

/* Formulario de reserva */
.reservation-form {
background: var(--color-bg-card);
border-radius: var(--radius-xl);
padding: var(--space-8);
border: 1px solid var(--color-border);
}

.form-group {
margin-bottom: var(--space-6);
}

.form-label {
display: block;
margin-bottom: var(--space-2);
font-weight: 500;
color: var(--color-text-primary);
}

.form-control {
width: 100%;
padding: var(--space-3) var(--space-4);
font-family: var(--font-body);
font-size: var(--text-base);
color: var(--color-text-primary);
background: var(--color-bg-secondary);
border: 1px solid var(--color-border);
border-radius: var(--radius-lg);
transition: all var(--transition-fast);
}

.form-control:focus {
outline: none;
border-color: var(--color-accent-primary);
box-shadow: var(--shadow-accent);
}

/* Modal de confirmación */
.modal {
position: fixed;
inset: 0;
z-index: var(--z-50);
display: none;
align-items: center;
justify-content: center;
padding: var(--space-6);
}

.modal.show {
display: flex;
}

.modal-backdrop {
position: absolute;
inset: 0;
background: rgba(0, 0, 0, 0.5);
backdrop-filter: blur(4px);
}

.modal-content {
position: relative;
background: var(--color-bg-card);
border-radius: var(--radius-xl);
padding: var(--space-8);
width: 100%;
max-width: 500px;
border: 1px solid var(--color-border);
box-shadow: var(--shadow-xl);
animation: modalSlideIn 0.3s ease-out;
}

@keyframes modalSlideIn {
from {
    opacity: 0;
    transform: translateY(-20px);
}
to {
    opacity: 1;
    transform: translateY(0);
}
}

/* ==========================================================================
9. UTILIDADES
========================================================================== */

/* Utilidades de espaciado */
.mt-1 { margin-top: var(--space-1); }
.mt-2 { margin-top: var(--space-2); }
.mt-4 { margin-top: var(--space-4); }
.mt-6 { margin-top: var(--space-6); }
.mt-8 { margin-top: var(--space-8); }

.mb-1 { margin-bottom: var(--space-1); }
.mb-2 { margin-bottom: var(--space-2); }
.mb-4 { margin-bottom: var(--space-4); }
.mb-6 { margin-bottom: var(--space-6); }
.mb-8 { margin-bottom: var(--space-8); }

/* Utilidades de texto */
.text-center { text-align: center; }
.text-right { text-align: right; }
.text-left { text-align: left; }

.font-light { font-weight: 300; }
.font-normal { font-weight: 400; }
.font-medium { font-weight: 500; }
.font-semibold { font-weight: 600; }
.font-bold { font-weight: 700; }

/* Utilidades de flex */
.flex { display: flex; }
.items-center { align-items: center; }
.justify-between { justify-content: space-between; }
.gap-2 { gap: var(--space-2); }
.gap-4 { gap: var(--space-4); }
.gap-6 { gap: var(--space-6); }

/* Utilidades de grid */
.grid { display: grid; }
.grid-cols-2 { grid-template-columns: repeat(2, 1fr); }
.grid-cols-3 { grid-template-columns: repeat(3, 1fr); }
.grid-cols-4 { grid-template-columns: repeat(4, 1fr); }

/* ==========================================================================
10. RESPONSIVE
========================================================================== */

@media (max-width: 768px) {
:root {
    --text-5xl: 2.25rem;
    --text-4xl: 1.875rem;
    --text-3xl: 1.5rem;
    --text-2xl: 1.25rem;
}

.nav-menu {
    display: none;
}

.spaces-grid {
    grid-template-columns: 1fr;
}

.calendar-grid {
    gap: var(--space-1);
}

.time-slots {
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
}

.modal-content {
    padding: var(--space-6);
}
}

@media (max-width: 1024px) {
.spaces-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}
}

/* ==========================================================================
11. ANIMACIONES
========================================================================== */

@keyframes pulse {
0%, 100% { opacity: 1; }
50% { opacity: 0.5; }
}

@keyframes spin {
from { transform: rotate(0deg); }
to { transform: rotate(360deg); }
}

@keyframes bounce {
0%, 100% { transform: translateY(-25%); animation-timing-function: cubic-bezier(0.8,0,1,1); }
50% { transform: none; animation-timing-function: cubic-bezier(0,0,0.2,1); }
}

/* Animación para nuevas reservas */
@keyframes highlight {
0% { background-color: var(--color-accent-success); }
100% { background-color: transparent; }
}

.new-reservation {
animation: highlight 2s ease-out;
}
```
</details>


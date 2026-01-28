# Herramientas Complementarias para Construir un Producto

## Puntos Principales

- **Evolución a Producto Real:** Un software funcional requiere capas adicionales como modelo de negocio, analíticas y sistemas de comunicación para ser viable.
- **Ecosistema Conectado:** Prioriza la integración de servicios especializados (SaaS externos) frente al desarrollo interno de soluciones genéricas (ej. Stripe para pagos).
- **Gestión de Integraciones:** Decisión técnica constante entre usar soluciones nativas (mayor velocidad) o integraciones manuales vía API/SDK (mayor control).
- **Arquitectura Orientada al Negocio:** El modelo de monetización (B2B vs B2C) impacta directamente la estructura de la base de datos y la lógica de la aplicación.
- **Caso de Estudio B2B:** Migrar una app de reservas hacia un modelo que cobra a organizaciones (consorcios) y no a usuarios finales, requiriendo tablas para organizaciones y suscripciones.
- **Medición Estratégica:** Las analíticas deben centrarse en eventos significativos (KPIs) que reflejen valor real, más allá de métricas de vanidad.
- **Extensiones del Producto:** El sistema debe salir de la interfaz gráfica propia mediante emails transaccionales y notificaciones que mantengan al usuario enganchado (retención).
- **Ética de Datos:** La privacidad y el consentimiento explícito son requisitos no funcionales críticos al implementar herramientas de seguimiento.
- **Coherencia Sistémica:** El éxito depende de que todas estas capas externas se integren de forma transparente para el usuario final.

## Tabla de Ideas Principales

| Concepto Clave | Descripción Técnica / Estratégica |
|---|---|
| **Integración como Estrategia** | Uso de servicios de terceros (Stripe, PostHog, Resend) para acelerar el desarrollo y reducir deuda técnica. |
| **Modelado B2B** | Reestructuración de bases de datos para soportar entidades "Organización" como clientes pagadores, jerarquizando a los usuarios debajo de ellas. |
| **Analítica de Producto** | Implementación de medición basada en eventos (no solo pageviews) para entender funnels de conversión y comportamiento real. |
| **Comunicación Externa** | Uso de emails y notificaciones push como extensión de la UX para aumentar la retención y confirmar acciones críticas. |
| **Privacidad por Diseño** | Implementación de capas de consentimiento y anonimización de datos como pilar fundamental de la confianza del usuario. |

## Prompts para Vibe Coding (Incremental)

### 1. Implementación del Modelo B2B (Organizaciones y Pagos)
> "Actúa como experto en arquitectura de software. Toma el archivo `prompt.vibe.md` actual y refactoriza el esquema de base de datos de Supabase para soportar un modelo Multi‑Tenant B2B.
> 1. Crea una tabla `organizations` (id, nombre, stripe_customer_id, estado_suscripcion).
> 2. Modifica la tabla `profiles` para incluir una Foreign Key `organization_id` y elimina el campo `unit` (o muévelo a una relación por organización si un usuario puede estar en varios edificios).
> 3. Modifica la tabla `amenities` y `bookings` para que pertenezcan a una `organization_id`.
> 4. Actualiza las políticas RLS: Un usuario solo puede ver data (amenities, bookings, perfiles) que coincida con su `organization_id`.
> 5. Agrega lógica para validar que la organización tenga `estado_suscripcion = 'active'` antes de permitir crear nuevas `bookings`.
> Genera el SQL actualizado y explica los cambios en la lógica de seguridad RLS."

### 2. Integración de Analytics (PostHog)
> "Sobre la base actual del proyecto (Next.js + Supabase), genera el código necesario para integrar PostHog como herramienta de analytics.
> 1. Crea un componente cliente `PostHogProvider` para la inicialización en `layout.tsx`.
> 2. Genera un hook personalizado `useAnalytics` que exponga una función `trackEvent(name, properties)`.
> 3. Instrumenta los siguientes eventos clave en la UI existente:
>    - `booking_created`: Al confirmar una reserva exitosa (enviar tipo de amenity y fecha).
>    - `booking_cancelled`: Al cancelar una reserva.
>    - `session_start`: Al hacer login exitoso.
> 4. Asegúrate de identificar al usuario en PostHog usando su ID de Supabase al loguearse.
> Entrégame los componentes de React y los snippets necesarios para insertar en los Server Actions de reserva."

### 3. Sistema de Notificaciones (Resend)
> "Integra un sistema de emails transaccionales usando Resend para mejorar la experiencia de las reservas definidas en el `prompt.vibe.md`.
> 1. Diseña una Server Action `sendBookingConfirmation(email, bookingDetails)` que use el SDK de Resend.
> 2. Crea un template de email minimalista en React (usando `@react-email/components`) que muestre: Info del Amenity, Fecha, Hora y un botón para 'Ver en la App'.
> 3. Modifica la lógica de creación de reservas (`createBooking`) para disparar este email de forma asíncrona tras una inserción exitosa en Supabase.
> 4. Agrega una tabla `notification_logs` en el esquema SQL para guardar registro de los emails enviados (status, fecha, destinatario).
> Genera el código del template, la función de envío y la modificación en el flujo de reserva."

### 4. Privacidad y Consentimiento
> "Implementa un banner de consentimiento de cookies y privacidad para cumplir con regulaciones éticas de datos.
> 1. Crea un componente `CookieConsentBanner` que aparezca en la parte inferior si el usuario no ha configurado preferencias.
> 2. Debe tener dos opciones: 'Aceptar todo' y 'Solo necesarios'.
> 3. Si el usuario elige 'Solo necesarios', deshabilita la inicialización de PostHog o configura el flag de `opt_out_capturing`.
> 4. Guarda la preferencia del usuario en `localStorage` y en una nueva columna `privacy_settings` JSONB en la tabla `profiles`.
> Provee el código del componente UI (usando Tailwind) y la lógica de estado para condicionar la carga de scripts de terceros."

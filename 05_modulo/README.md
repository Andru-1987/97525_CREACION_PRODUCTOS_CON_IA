# Unidad 5: Escalamiento y límites del vibe coding

**Resumen didáctico del módulo 5 – Escalamiento y límites del Vibe Coding**

| **Punto importante** | **Descripción breve** |
|----------------------|-----------------------|
| **Escalar rompe cosas** | Lo que funciona en un prototipo puede fallar en producción; el crecimiento implica cambios cualitativos. |
| **Riesgos al crecer** | Datos, seguridad, performance y operatividad deben ser reconsiderados. |
| **Performance y observabilidad** | Necesario medir y monitorizar métricas clave (latencia, errores, uso de recursos). |
| **Seguridad de datos sensibles** | Implementar protección desde el diseño (encriptación, control de accesos). |
| **Costos y consumo de IA** | Gestionar tokens y gastos de modelos de IA en producción. |
| **APIs y agentes** | Diferenciar llamadas simples de agentes autónomos; controlar su complejidad. |
| **Vibe Coding vs AI Engineering** | Pasar de exploración a estabilidad cuando el producto se vuelve crítico. |
| **Evolución gradual** | Añadir capas de robustez de forma incremental sin perder agilidad. |
| **Aplicación en entornos corporativos** | Adaptar el enfoque para evitar riesgos organizacionales. |
| **Hacks prácticos** | Consejos rápidos para reducir riesgos manteniendo la velocidad. |

---

### Prompts por etapa del desarrollo de la aplicación de reservas de espacios comunes (amenities)

#### 1. Frontend
- **Manejo de errores amigables**  
  > “Revisa este componente React y sugiere mejoras para manejo de errores, loading states y validación de permisos. ¿Qué podría fallar con alta concurrencia?”
- **Loading & skeleton screens**  
  > “¿Cómo puedo implementar skeletons para la lista de amenities mientras se cargan los datos?”
- **Validación de permisos en UI**  
  > “Propón una estrategia para deshabilitar botones de reserva cuando el usuario no tenga permiso según su rol.”

#### 2. Backend
- **Logs estructurados (JSON)**  
  > “Analiza esta API Node/Express y sugiere dónde agregar logs JSON con contexto de usuario y acción.”
- **Rate limiting**  
  > “Diseña una política de rate‑limiting para el endpoint `POST /bookings` que evite abusos.”
- **Validación de permisos**  
  > “¿Qué middleware debería usar para asegurar que solo usuarios autorizados creen reservas?”
- **Métricas básicas**  
  > “Genera código para exponer métricas de tiempo de respuesta y tasa de errores a Prometheus.”

#### 3. Base de datos
- **Índices y consultas frecuentes**  
  > “Revisa el esquema de `bookings` y sugiere índices para mejorar búsquedas por `amenity_id` y `date`.”
- **Multi‑tenant (organizaciones)**  
  > “Propón una estructura de tablas para soportar organizaciones B2B y relacionar usuarios y reservas.”
- **Backups automáticos**  
  > “Describe un plan de backups diarios y pruebas de restauración para la base Supabase.”
- **Migraciones estructuradas**  
  > “Escribe un script de migración usando Flyway para añadir la tabla `organizations`.”

#### 4. Integraciones externas
- **Analytics (PostHog)**  
  > “Genera un hook `useAnalytics` y los eventos `booking_created`, `booking_cancelled` y `session_start`.”
- **Emails transaccionales (Resend)**  
  > “Crea una función `sendBookingConfirmation` que envíe un email con los datos de la reserva.”
- **Consentimiento de privacidad**  
  > “Diseña un banner de cookie consent que habilite/deshabilite PostHog según la elección del usuario.”

#### 5. Plan incremental
| Semana | Tarea principal | Prompt asociado |
|--------|----------------|-----------------|
| 1 | Añadir logs estructurados en backend y frontend | “Genera logs JSON para cada endpoint y captura errores en UI.” |
| 2 | Implementar rate‑limiting en endpoint crítico | “Diseña middleware de rate‑limiting para `/bookings`.” |
| 3 | Revisar índices y crear backups automáticos | “Propón índices y script de backup diario.” |
| 4 | Añadir validación de permisos en backend | “Implementa middleware de autorización basado en roles.” |
| 5 | Simular escenarios de abuso y añadir analytics | “Crea pruebas de carga y eventos de PostHog para monitorizar abusos.” |


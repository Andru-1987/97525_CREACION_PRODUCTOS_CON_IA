
# Unidad 6: Lanzamiento, distribución y crecimiento

**Resumen didáctico**
- El crecimiento debe estar presente desde el inicio; el MVP sirve para aprender, no solo para lanzar.
- Diferencia entre startups y proyectos tradicionales: intención de escalar rápidamente.
- El MVP es un experimento para validar hipótesis de negocio y de uso.
- Estrategias “Do Things That Don't Scale” para obtener feedback profundo.
- Métricas de tracción: North Star Metric, AARRR (Acquisition, Activation, Retention, Referral, Revenue), DAU/MAU, Churn, CAC, LTV.
- Product‑Market‑Fit (PMF): proceso continuo, señales cualitativas y cuantitativas, importancia del “por qué ahora”.
- Financiamiento: modelos Bootstrapped vs VC‑backed, implicaciones en ritmo y decisiones.

## Tabla de puntos importantes
| Punto clave | Descripción breve |
|---|---|
| **Naturaleza de la startup** | Crecer rápido, intención de escalar, no solo tecnología. |
| **MVP como aprendizaje** | Experimento para validar hipótesis de negocio y uso. |
| **Do Things That Don't Scale** | Acciones manuales para obtener feedback temprano. |
| **Métricas de tracción** | North Star, AARRR, DAU/MAU, Churn, CAC, LTV. |
| **Product‑Market‑Fit** | Proceso progresivo, señales cualitativas y cuantitativas. |
| **Financiamiento** | Bootstrapped vs VC‑backed, decisiones estratégicas. |

## Prompts por etapa del desarrollo de la aplicación de reservas de amenities
- **Fase 1 – Instrumentar aprendizaje**
  - "Agrega un sistema de logging de eventos clave (registro_completado, reserva_creada, flujo_abandonado) en una tabla `eventos_usuario`."
  - "Implementa un banner sencillo que invite a los usuarios a agendar una entrevista corta."
- **Fase 2 – Conseguir early adopters manualmente**
  - "Crea códigos de invitación para registrar usuarios de forma controlada."
  - "Implementa un endpoint `/api/feedback` que almacene comentarios libres."
- **Fase 3 – Loop de feedback sencillo**
  - "Muestra al final del flujo principal un mensaje de feedback rápido (👍/👎) que envíe un evento `feedback_rapido`."
  - "Genera un reporte SQL que cuente usuarios registrados y eventos clave."
- **Fase 4 – Definir y medir la North Star Metric**
  - "Decide cuál es la unidad mínima de valor (ej. reserva creada) y cuenta esa métrica."
  - "Crea un dashboard interno que muestre usuarios totales, North Star semanal y feedbacks."
- **Fase 5 – Escalar un canal de distribución**
  - "Elige un canal (LinkedIn outreach, subreddit, micro‑influencer) y ejecuta una campaña para 50 usuarios."
  - "Añade campo `fuente_registro` a la tabla de usuarios y registra la procedencia."

## Explicación de métricas de tracción
- **North Star Metric**: la acción que mejor representa el valor entregado al cliente (p.ej. reservas completadas). Todas las decisiones deben alinearse a mejorar esta métrica.
- **AARRR**: marco para seguir el funnel completo – adquisición, activación, retención, referencia y revenue.
- **DAU/MAU**: usuarios activos diarios vs mensuales, indica engagement.
- **Churn**: porcentaje de usuarios que dejan de usar el producto en un periodo.
- **CAC** (Cost of Acquiring Customer): gasto total en marketing dividido por número de nuevos clientes.
- **LTV** (Lifetime Value): ingresos esperados de un cliente durante su relación con el producto.

## Explicación de PMF
- No es un estado binario; se alcanza cuando un segmento de usuarios muestra alta retención y recomendación espontánea.
- Señales cualitativas: usuarios que dicen “no puedo vivir sin esto”.
- Señales cuantitativas: retención > 40% después de 3 meses, crecimiento orgánico sostenido.
- El “por qué ahora” (timing) es crucial: mercado, regulación o tendencias que hacen que la solución sea necesaria.

## Explicación del financiamiento
- **Bootstrapped**: autofinanciado, crecimiento controlado, mayor autonomía, foco en rentabilidad temprana.
- **VC‑backed**: inversión externa, mayor velocidad de crecimiento, presión por métricas de tracción y escalabilidad, decisiones estratégicas influenciadas por los inversores.
- Elegir modelo depende de la visión de velocidad, control y riesgo que el equipo esté dispuesto a asumir.

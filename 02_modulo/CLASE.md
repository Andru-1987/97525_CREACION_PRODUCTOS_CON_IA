# Resumen de la Clase: De la Idea al MVP

[Material de clase en vivo](https://docs.google.com/presentation/d/17Jmxi7-38F2aZdfy0ccWQ1ELJj1tTDxY/edit?slide=id.g3b104ef8501_0_360#slide=id.g3b104ef8501_0_360)

## **Tema Central de la Clase**
**¿Qué problema se quiere resolver?**
Nos enfocaremos en cómo crear una aplicación para **reservar espacios comunes en edificios** (como el SUM, la parrilla o el gimnasio). El problema específico es la **desorganización y los conflictos** que surgen cuando los vecinos intentan reservar estos espacios usando métodos actuales como WhatsApp, notas en la pizarra o llamadas al administrador, lo que genera dobles reservas, frustración y malas relaciones entre vecinos.

La **app propuesta** sería una solución digital para centralizar la disponibilidad y permitir reservas sencillas.

---

## **Puntos Principales de la Clase**

### 1. **Cambia tu enfoque: del "producto" al "problema"**
*   **No te enamores de tu idea** (ej: "quiero hacer una app con calendario"). **Enamórate del problema** que existe en el mundo real.
*   El riesgo más grande no es la tecnología, sino **construir algo que nadie necesita**.
*   **Ejemplo claro:** El dolor no es "no tener una app". El dolor es "pelearse con el vecino porque reservaron el mismo salón" o "perder una tarde llamando a todos para saber si el SUM está libre".

### 2. **Investiga como un detective: busca hechos, no halagos**
*   No preguntes "¿te gustaría una app para reservar?". Esa pregunta lleva a respuestas complacientes (como las que te daría tu mamá para no herirte → de ahí el **"Mom Test"**).
*   **Pregunta por comportamientos pasados:** "¿**Cómo** resolviste la reserva del SUM **la última vez**?" o "¿**Qué pasó** la última vez que hubo un malentendido con la reserva?".
*   **La IA es tu aliada** para acelerar esta investigación (ej: pedirle que genere preguntas no sesgadas o liste dolores comunes), pero la validación final debe ser con personas reales.

### 3. **De la información a la solución, paso a paso**
El proceso para no perderse es:
1.  **Identificar Patrones:** ¿Qué se repite en las quejas? (Ej: "Nadie sabe si está libre", "Siempre hay confusiones").
2.  **Dibujar el Viaje del Usuario (User Journey):** Seguir los pasos de un vecino para reservar hoy y ver **dónde sufre más**.
3.  **Formular Oportunidades:** Convertir esos dolores en preguntas de "**¿Cómo podríamos...?**" (Ej: "¿Cómo podríamos mostrar la disponibilidad en un solo lugar confiable?").
4.  **Generar Propuestas Concretas:** Transformar las oportunidades en **ideas claras, no en pantallas** (Ej: "Un dashboard simple que muestre en tiempo real si el SUM está ocupado o libre").

### 4. **Define tu MVP: el experimento mínimo**
*   **MVP (Producto Mínimo Viable) NO es** la versión 1.0 de tu producto soñado. **ES el experimento más pequeño** para probar si tu solución tiene valor.
*   Para definirlo, necesitas:
    *   **Una Hipótesis Clave:** "Si [hago esto], entonces [pasará esto]". (Ej: "Si muestro la disponibilidad en una web, el 70% de las consultas dejarán de hacerse por WhatsApp").
    *   **Una Lista de Funcionalidades MÍNIMAS (Must Have):** Solo lo indispensable para probar esa hipótesis. Para la app de reservas: **Ver disponibilidad, Reservar en 2 clics y Guardar los datos**. **NO incluye:** pagos, login con redes sociales, fotos, etc., en esta primera versión.
    *   **Un Plan para Medir:** Decidir qué vas a medir (ej: cuántas veces se ve la pantalla de disponibilidad) y qué resultado consideras éxito.

### 5. **Construye por capas, no todo de una vez**
El orden inteligente para construir es:
1.  **Etapa 1 - El Esqueleto:** Haz las pantallas y el flujo con datos de mentira (Mock Data). ¿Se entiende cómo se usa? (Herramientas: v0, Lovable).
2.  **Etapa 2 - Los Datos Reales:** Conecta ese esqueleto a una base de datos real (como Supabase). Ahora las reservas **sí se guardan** y persisten. Tu prototipo se convierte en un producto funcional.
3.  **Etapas Posteriores:** Luego añades login, notificaciones, etc.

### 6. **El momento de la verdad: de tu computadora al mundo**
*   **Entorno Local:** Es la app corriendo solo en tu compu (`localhost`). Es tu **laboratorio** para probar y equivocarte sin consecuencias.
*   **Entorno de Producción:** Es la app publicada en internet con una URL (usando Vercel). Es el **campo de pruebas real** con usuarios.
*   **Tu MVP solo existe de verdad cuando está en Producción**, porque ahí es donde la gente real lo usa y tú aprendes lo que realmente funciona.

---

## **Conclusión: Lo Más Importante para Llevar**

1.  **Empieza con el dolor de la gente, no con tu idea brillante.** La investigación rigurosa es lo que separa un producto útil de uno que nadie usará.
2.  **Tu MVP es una pregunta, no una respuesta.** Es una herramienta para aprender. Define **QUÉ** quieres aprender (tu hipótesis) y construye **LO MÍNIMO** necesario para ello.
3.  **Usa la IA como motor, no como piloto.** Es excelente para generar ideas, estructurar información y acelerar pasos, pero **nunca reemplaza hablar con usuarios**.
4.  **Construye en etapas.** Primero haz que *se entienda*, luego haz que *funcione de verdad* (con una base de datos), después hazlo *personal* y *potente*. Este orden te ahorra tiempo y dolor de cabeza.
5.  **El éxito se mide con un link público.** Cuando tu experimento mínimo (MVP) esté en línea y unos pocos vecinos puedan usarlo para reservar el SUM sin pelearse, habrás dado el paso más importante: **haber creado algo real que resuelve un problema real.**

**Meta final de la clase:** Salir con un **Brief de Producto** claro (una hoja) que defina el problema, la hipótesis y las 3-5 funcionalidades clave de tu MVP, listo para empezar a construir.
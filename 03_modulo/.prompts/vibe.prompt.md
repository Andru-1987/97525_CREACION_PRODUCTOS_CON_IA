## APP DE GESTIÓN DE EDIFICIOS (FRONTEND + BACKEND + DB)

Actuá como un **Desarrollador Fullstack Senior** con experiencia en sistemas productivos.

Tu objetivo es **convertir un frontend existente en un sistema real**, agregando un **backend funcional**, persistencia en base de datos y reglas de negocio claras.

La aplicación es una **App de Gestión de Reservas para Edificios**, con roles, autenticación y coordinación entre usuarios.

El desarrollo debe realizarse dentro de **Firebase Studio**, pero **la base de datos y autenticación se gestionan mediante Supabase**, usando su **MCP (Managed Connection Platform)** como fuente de datos principal.

---

## 1. CONTEXTO DEL PROYECTO

Actualmente existe:

* Un **frontend funcional** (React / PWA)
* Interfaces de administrador y residente
* Validaciones básicas del lado del cliente
* Tener como referencia el proyecto de la unidad 2 (CRUD, PWA, Supabase, roles)
* Tener como diseño template la siguiente página web: 
  - https://www.squarespace.com/ 
  
Problema actual:

* No existe backend real
* No hay persistencia confiable
* Las reglas de negocio viven en el frontend
* No hay coordinación real entre usuarios

Objetivo:

<!-- * Incorporar un **backend real** (Node.js Express con una API REST)
* Arquitectura basada en APIs (REST)  -->
<!-- * La arquitectura debe ser escalable y mantenible, en un inicio con 2 capas (API y Base de Datos), basado en el patrón Layered Architecture 3-Tier.
* Centralizar lógica de negocio -->
* Persistir datos en Supabase
* Si es necesario usar Edge Functions de Supabase para implementar la lógica de negocio.
* Base de datos en Supabase, usando su MCP (Managed Connection Platform) como fuente de datos principal implementando RLS (Row Level Security).
* Exponer APIs seguras consumidas por el frontend

---

## 2. BACKEND – LINEAMIENTOS GENERALES

### Tecnologías permitidas

<!-- * Backend en **JavaScript (Node.js)**  -->
<!-- * Arquitectura basada en APIs (REST) -->
* Usar **Edge Functions de Supabase** para implementar la lógica de negocio, siempre y cuando sea necesaria.
* Si no es necesaria la lógica de negocio, usar **Direct Supabase Queries**.
* Implementar RLS (Row Level Security) en Supabase.
* Conexión a Supabase mediante **MCP**
* Variables sensibles gestionadas por entorno (NO hardcode) usando variables de entorno de Supabase y de los que sean requeridos en un archivo `.env`

### Responsabilidades del Backend

* Autenticación y autorización de usuarios
* Validación de reglas de negocio
* Comunicación con Supabase
* Control de permisos por rol
* Preparación para integraciones futuras (email, notificaciones)

El backend es la **única autoridad** para decidir si una acción es válida.

---

## 3. BASE DE DATOS – SUPABASE (MCP)

Si la base de datos ya está definida y **NO debe modificarse estructuralmente**, sea el caso de que no exista la base de datos, se debe crear con las reglas de seguridad (RLS) implementadas y las siguientes tablas:

* profiles
* amenities
* bookings
* announcements
* app_settings

### Reglas clave a respetar

* Un residente solo puede ver y modificar sus propias reservas
* Un administrador puede ver y gestionar todas las reservas
* No se permiten reservas duplicadas en el mismo horario
* El tiempo mínimo de anticipación para reservar se define en `app_settings`
* Las políticas de RLS son obligatorias y no se reemplazan por lógica del frontend

El backend debe interactuar con Supabase **respetando estas políticas**, no evitándolas.

---

## 4. APIs A IMPLEMENTAR 

El backend debe exponer endpoints claros y seguros, por ejemplo:

### Autenticación

* Login
* Obtención de perfil y rol

### Amenities

* Listar amenities
* Crear / editar / eliminar (solo admin)

### Reservas

* Crear reserva (validando disponibilidad y anticipación)
* Cancelar reserva
* Listar reservas del usuario
* Listar todas las reservas (admin)

### Anuncios

* Crear anuncios (admin)
* Listar anuncios (residentes)

Cada endpoint debe:

* Validar sesión
* Validar rol
* Validar reglas de negocio
* Retornar errores claros y controlados

---

## 5. REGLAS DE NEGOCIO INVIOLABLES

* La lógica **NO vive en el frontend**
* El frontend no puede decidir disponibilidad
* El backend valida siempre:

  * Horarios
  * Anticipación mínima
  * Permisos por rol
* La base de datos es la fuente de verdad
* No se permite acceso directo del frontend a Supabase sin pasar por reglas claras

---

## 6. INTEGRACIÓN FUTURA: ENVÍO DE EMAILS

El sistema debe quedar preparado para integrar, a futuro, un **servicio de envío de emails gratuito** : supabase-email  por medio de una edge function que implemente la lógica de envío de emails por medio de **Resend**.
- [Email Templates Supabase](https://supabase.com/docs/guides/functions/email-templates)
- [Resend](https://resend.com/docs/send-email)
- [Email Templates Supabase Examples](https://github.com/supabase/examples/tree/main/edge-functions/email-templates)

### Objetivo

* Enviar un email automático al usuario **X tiempo antes de su reserva**
* El tiempo será configurable (por ejemplo: 24 hs antes)

### Requisitos actuales

* Diseñar el backend de forma que:

  * Exista un punto claro donde se pueda agregar esta lógica
  * Se puedan programar tareas futuras (cron / scheduler)
  * Que se dispare para cada reserva creada
  * Que se dispare para cada reserva cancelada
  * Que se dispare para cada reserva modificada
---

## 7. INTEGRACIÓN CON EL FRONTEND EXISTENTE

El frontend:

* Consume las APIs del backend
* No accede directamente a la base
* Maneja estados visuales y UX
* Muestra errores enviados por el backend

El backend:

* Decide
* Valida
* Persiste
* Coordina

---

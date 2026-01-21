

# PROMPT PARA DESARROLLO DE APP DE RESERVAS COMUNES

Actúa como un Desarrollador Fullstack Senior experto en React, Supabase y UX. Genera la siguiente aplicación de gestión de edificios.

## 1. ESQUEMA DE BASE DE DATOS (SUPABASE / POSTGRES)
Ejecuta este SQL en el editor de Supabase:

```sql
-- Habilitar extensiones
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

-- 1. Tabla de Perfiles (Extensión de Auth.users)
CREATE TABLE profiles (
  id UUID PRIMARY KEY REFERENCES auth.users(id) ON DELETE CASCADE,
  full_name TEXT NOT NULL,
  unit_number TEXT NOT NULL,
  email TEXT UNIQUE NOT NULL,
  role TEXT DEFAULT 'RESIDENT' CHECK (role IN ('ADMIN', 'RESIDENT')),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT timezone('utc'::text, now()) NOT NULL
);

-- 2. Tabla de Espacios Comunes (Amenities)
CREATE TABLE amenities (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  name TEXT NOT NULL,
  description TEXT,
  capacity INTEGER DEFAULT 10,
  available_hours TEXT[] DEFAULT ARRAY['09:00', '10:00', '11:00', '12:00', '13:00', '14:00', '15:00', '16:00', '17:00', '18:00', '19:00', '20:00', '21:00'],
  created_at TIMESTAMP WITH TIME ZONE DEFAULT timezone('utc'::text, now())
);

-- 3. Tabla de Reservas
CREATE TABLE reservations (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  amenity_id UUID REFERENCES amenities(id) ON DELETE CASCADE,
  user_id UUID REFERENCES profiles(id) ON DELETE CASCADE,
  date DATE NOT NULL,
  start_time TIME NOT NULL,
  end_time TIME NOT NULL,
  status TEXT DEFAULT 'CONFIRMED' CHECK (status IN ('PENDING', 'CONFIRMED', 'CANCELLED')),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT timezone('utc'::text, now())
);

-- 4. Eventos e Inhabilitaciones
CREATE TABLE community_events (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  title TEXT NOT NULL,
  description TEXT,
  event_date DATE NOT NULL,
  is_blocking BOOLEAN DEFAULT false,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT timezone('utc'::text, now())
);
```

## 2. REQUISITOS FUNCIONALES CLAVE

### Panel Administrador:
- **Gestión de Residentes:** 
  - Listado de residentes.
  - Botón "Importar CSV" para carga masiva.
  - Input de texto para ingresar múltiples residentes separados por comas (formato: "Nombre, Unidad, Email").
  - Al crear el residente, disparar el alta en Supabase Auth y Profiles.
- **Calendario Maestro:**
  - Vista diaria/semanal/mensual con todas las reservas activas.
  - Filtro por espacio común.
- **Eventos:** CRUD de eventos importantes que bloquean fechas.

### Panel Residente:
- **Calendario de Reservas:**
  - Seleccionar Espacio (Parrilla, Piscina, SUM).
  - Seleccionar Día.
  - Ver slots horarios disponibles (excluyendo ya reservados y fechas bloqueadas por admin).
- **Mis Reservas:** Listado de sus reservas futuras con opción a cancelar.

## 3. ESTILO Y UX
- **Colores:** Paleta moderna Slate/Blue (Primarios en azul profesional, fondos en blanco/gris suave).
- **Dark Mode:** Implementar soporte completo con Tailwind `dark:`.
- **PWA:** Asegurar que el `manifest.json` y Service Worker estén configurados para "Instalar en pantalla de inicio".
- **Realtime:** Usar `supabase.channel()` para que el administrador vea las nuevas reservas al instante sin refrescar.

## 4. INSTRUCCIONES DE IMPLEMENTACIÓN
- Utiliza **Lucide React** para iconos.
- Utiliza **date-fns** para la lógica de fechas del calendario.
- Utiliza **Recharts** si es necesario mostrar estadísticas de uso en el dashboard admin.
- La navegación debe ser SPA (Single Page Application) fluida.

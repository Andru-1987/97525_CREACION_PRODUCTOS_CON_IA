# PROMPT DEFINITIVO: APP DE GESTIÓN DE EDIFICIOS (CRUD + PWA + SUPABASE)

Actúa como un Desarrollador Fullstack Senior. Crea una aplicación profesional para la gestión de reservas en edificios.

## 1. BACKEND: ESQUEMA DE DATOS (SUPABASE)
- Generar las tablas necesarias para el modelo de negocio
- Ingestar algunos registros de prueba
- Implementar RLS (Row Level Security) en Supabase.
- Conexión a Supabase mediante **MCP**


```sql
-- 1. CREACIÓN DE TABLAS

-- Tabla de Perfiles (Extensión de Auth.Users)
CREATE TABLE profiles (
  id UUID REFERENCES auth.users ON DELETE CASCADE PRIMARY KEY,
  email TEXT UNIQUE NOT NULL,
  name TEXT NOT NULL,
  unit TEXT NOT NULL,
  role TEXT NOT NULL CHECK (role IN ('ADMIN', 'RESIDENT')),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Tabla de Amenities
CREATE TABLE amenities (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  name TEXT NOT NULL,
  icon TEXT DEFAULT '🏢',
  capacity INTEGER DEFAULT 10,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Tabla de Reservas
CREATE TABLE bookings (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  amenity_id UUID REFERENCES amenities(id) ON DELETE CASCADE NOT NULL,
  user_id UUID REFERENCES profiles(id) ON DELETE CASCADE NOT NULL,
  booking_date DATE NOT NULL,
  time_slot TEXT NOT NULL,
  status TEXT DEFAULT 'confirmed' CHECK (status IN ('confirmed', 'cancelled')),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Tabla de Anuncios
CREATE TABLE announcements (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  title TEXT NOT NULL,
  content TEXT NOT NULL,
  author_id UUID REFERENCES profiles(id),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Tabla de Configuración Global
CREATE TABLE app_settings (
  id INTEGER PRIMARY KEY DEFAULT 1,
  booking_lead_time_days INTEGER DEFAULT 1,
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  CONSTRAINT one_row CHECK (id = 1)
);

-- 2. SEGURIDAD (Row Level Security - RLS)

ALTER TABLE profiles ENABLE ROW LEVEL SECURITY;
ALTER TABLE amenities ENABLE ROW LEVEL SECURITY;
ALTER TABLE bookings ENABLE ROW LEVEL SECURITY;
ALTER TABLE announcements ENABLE ROW LEVEL SECURITY;
ALTER TABLE app_settings ENABLE ROW LEVEL SECURITY;

-- Políticas para Profiles
CREATE POLICY "Public profiles are viewable by everyone" ON profiles FOR SELECT USING (true);
CREATE POLICY "Users can update own profile" ON profiles FOR UPDATE USING (auth.uid() = id);

-- Políticas para Amenities
CREATE POLICY "Amenities are viewable by everyone" ON amenities FOR SELECT USING (true);
CREATE POLICY "Only admins can modify amenities" ON amenities FOR ALL USING (
  EXISTS (SELECT 1 FROM profiles WHERE id = auth.uid() AND role = 'ADMIN')
);

-- Políticas para Bookings
CREATE POLICY "Users can view own bookings" ON bookings FOR SELECT USING (auth.uid() = user_id OR EXISTS (SELECT 1 FROM profiles WHERE id = auth.uid() AND role = 'ADMIN'));
CREATE POLICY "Users can create own bookings" ON bookings FOR INSERT WITH CHECK (auth.uid() = user_id);
CREATE POLICY "Users can cancel own bookings" ON bookings FOR UPDATE USING (auth.uid() = user_id);

-- 3. INSERCIÓN DE DATOS INICIALES
INSERT INTO app_settings (id, booking_lead_time_days) VALUES (1, 1);
INSERT INTO amenities (name, icon, capacity) VALUES 
('Gimnasio', '🏋️', 10),
('Piscina', '🏊', 20),
('Salón Social', '🎉', 50),
('Parrilla', '🍖', 8);
```

## 2. REGLAS TÉCNICAS INVIOLABLES
- **Imports:** Usar rutas relativas estándar (ej. `../types`, `./Header`). NO usar alias `@/`.
- **Datos:** No usar `.json` externos. Usar `mockData.ts` para constantes tipadas.
- **PWA:** Debe incluir un `manifest.json` y service worker básico para ser instalable.
- **Notificaciones:** Implementar un sistema de "Toasts" reactivos para simular notificaciones push en tiempo real.


## 3. FUNCIONALIDADES CLAVE
- **Dashboard Admin:**
  - **CRUD de Amenities:** Crear (nombre, icono, capacidad), editar y eliminar espacios.
  - **Gestión de Residentes:** Carga masiva mediante CSV o lista pegada (Nombre, Unidad, Email).
  - **Anuncios:** Enviar mensajes que aparecen como notificaciones a todos los residentes.
  - **Reservas:**  Puede crear, actualizar, cancelar y borrar cualquier reserva hecha por los residentes. Podra ver todos las reservas hechas en un calendario con el estilo Google Calendar. 

  - **Modificacion de tiempo de anticipacion de reserva de espacios:** Podra modificar el tiempo que los residente pueden reservar los espacios, siendo por defecto 1 dia, pero va a tener la opcion de hacerlo con opciones de n dias o n semanas o n meses.
  
  
- **Dashboard Residente:**
  - **Reservas:** Interfaz de calendario/slots filtrada por disponibilidad horaria, ademas de permitir seleccionar el dia mostrandolo en un calendario del estilo de Google Calendar, que por defecto deba estar seleccionado 1 dia antes, por que no spuede reservar un espacio en el mismo dia(esta regla puede ser modificada por el rol de administrador).
  - **Mis Reservas:** Historial y cancelación.
  - **Centro de Notificaciones:** Campanita con avisos del administrador.

## 4. UI/UX (Vibe)
- **Estilo template** : Pagina de referencia:  https://www.squarespace.com/ 
- **Paleta:** Slate-900 para fondos oscuros, Primary-500 (#0ea5e9) para acciones principales.
- **Interacción:** Animaciones con Framer Motion o Tailwind Animate. Toasts de éxito/error.
- **Responsividad:** Mobile-first total. Navegación inferior en móviles, sidebar en desktop.

## 5. ACCESO DEMO
- Admin: admin@edificio.com / admin123
- Residente: vecino@edificio.com / vecino123

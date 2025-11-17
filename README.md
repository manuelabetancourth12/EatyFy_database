# EatyFy Database

Esta carpeta contiene la configuración de la base de datos en la nube para el proyecto EatyFy.

## Base de Datos Utilizada
- **Railway PostgreSQL**: Base de datos PostgreSQL alojada en Railway (plataforma en la nube).

## Configuración Actual

### Base de Datos en Producción
La aplicación ahora usa una base de datos PostgreSQL alojada en **Railway** con las siguientes características:

- **Proveedor**: Railway
- **Tipo**: PostgreSQL
- **Host**: shuttle.proxy.rlwy.net
- **Puerto**: 55900
- **Base de datos**: railway
- **Usuario**: postgres

### Tablas Creadas Automáticamente
El backend Spring Boot crea automáticamente las siguientes tablas usando Hibernate:

- `app_users`: Usuarios de la aplicación (id, name, email, password, role, food_preferences)
- `restaurant`: Restaurantes registrados (id, name, address, cuisine_type, average_price_per_person, phone, website, opening_hours, latitude, longitude, owner_id)
- `menu_item`: Ítems del menú de cada restaurante (id, name, description, price, category, restaurant_id)
- `review`: Reseñas de usuarios a restaurantes (id, user_id, restaurant_id, rating, comment, created_at)
- `notification`: Notificaciones para usuarios (id, user_id, title, description, date, read)
- `promotion`: Promociones de restaurantes (id, title, description, city, image, restaurant_id)

## Ventajas de Railway
- ✅ **Compartida**: Múltiples usuarios pueden acceder a la misma base de datos
- ✅ **Persistente**: Datos guardados en la nube, no se pierden
- ✅ **Escalable**: Railway maneja el escalado automáticamente
- ✅ **Segura**: Conexiones encriptadas y backup automático

## Conexión desde el Backend

El backend está configurado para conectarse automáticamente a Railway. Las credenciales están en `application.properties`.
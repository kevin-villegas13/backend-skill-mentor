# Backend - Plataforma de Mentores y Aprendices

## Descripción del Proyecto

Esta aplicación conecta a mentores y aprendices para sesiones de aprendizaje personalizadas. El backend de la plataforma está construido con **NestJS**, **Prisma** y **Socket.IO** para manejar la autenticación, gestión de usuarios, sesiones, mensajes en tiempo real, y notificaciones.

## Requerimientos Funcionales

### 1. **Gestión de Usuarios**
- **Registro de Usuarios**: Los usuarios pueden registrarse como **mentores** o **aprendices** mediante email y contraseña.
- **Inicio de sesión**: Los usuarios pueden iniciar sesión utilizando su email y contraseña.
- **Recuperación de Contraseña**: Los usuarios pueden recuperar o restablecer su contraseña mediante un correo electrónico.

### 2. **Emparejamiento de Mentores y Aprendices**
- **Buscar Mentores**: Los aprendices pueden buscar mentores según habilidades, especialidades, o áreas de interés.
- **Solicitar Mentoría**: Los aprendices pueden solicitar mentorías con mentores disponibles.
- **Aceptar/Rechazar Solicitudes**: Los mentores pueden aceptar o rechazar las solicitudes de mentoría.

### 3. **Gestión de Sesiones**
- **Crear Sesiones**: Los mentores pueden crear sesiones de aprendizaje con una fecha y hora específica.
- **Visualizar Sesiones**: Los aprendices y mentores pueden ver sus sesiones programadas.
- **Historial de Sesiones**: Los mentores y aprendices pueden revisar las sesiones pasadas.

### 4. **Chat en Tiempo Real**
- **Mensajes en Tiempo Real**: Los usuarios pueden enviarse mensajes entre ellos durante las sesiones de mentoría utilizando **Socket.IO**.
- **Verificación de Autorización**: El sistema verifica que los usuarios estén autorizados a chatear según la relación de mentoría.
- **Mensajes Perdidos**: Los mensajes enviados mientras el destinatario está desconectado deben ser almacenados y entregados cuando el destinatario se conecte.

### 5. **Notificaciones**
- **Notificaciones por Email**: Los usuarios reciben notificaciones por email para eventos importantes como nuevos mensajes, solicitudes de mentoría, y sesiones programadas.
- **Notificaciones en la Aplicación**: El sistema envía notificaciones en la aplicación sobre eventos relacionados con la mentoría, como nuevas sesiones o mensajes.

## Requerimientos No Funcionales

### 1. **Escalabilidad**
- La aplicación debe ser capaz de manejar un aumento en el número de usuarios y sesiones sin degradar el rendimiento.

### 2. **Seguridad**
- **Autenticación Segura**: Utilizar JWT (JSON Web Tokens) para autenticar y autorizar las solicitudes de los usuarios.
- **Encriptación de Contraseñas**: Las contraseñas deben ser encriptadas utilizando un algoritmo de hashing seguro (como bcrypt).
- **Protección contra Vulnerabilidades**: Implementación de medidas de seguridad para proteger la aplicación contra ataques como SQL Injection, XSS y CSRF.

### 3. **Disponibilidad**
- El backend debe estar disponible al menos el 99.9% del tiempo, garantizando una alta disponibilidad de las API y los servicios de chat.

### 4. **Rendimiento**
- Las API deben responder en menos de 200 ms bajo condiciones normales.
- Las operaciones relacionadas con la gestión de sesiones y mensajes deben ser eficientes y no afectar la experiencia del usuario.

### 5. **Usabilidad**
- La API debe ser fácil de entender y utilizar para los desarrolladores, con una documentación clara de todos los endpoints y parámetros.

### 6. **Mantenimiento y Actualización**
- El código debe ser modular y bien documentado para facilitar futuras mejoras y mantenimiento.

## Relaciones de Tablas

1. User (Usuarios):
La tabla User almacena la información de cada usuario (mentor o aprendiz).
Relacionado con Mentorías, sesiones, mensajes y notificaciones.

2. Mentorship (Relación Mentor-Aprendiz):
Gestiona la relación entre un mentor y un aprendiz.
Un mentor puede tener múltiples aprendices, y un aprendiz puede tener múltiples mentores.

3. Session (Sesión de Aprendizaje):
Representa una sesión de aprendizaje entre un mentor y un aprendiz.
Cada sesión está asociada a un mentor y un aprendiz, y puede tener múltiples mensajes.

4. Message (Mensajes):
Los mensajes se envían dentro de los chats entre mentor y aprendiz.
Cada mensaje pertenece a un chat y tiene un emisor (usuario).

5. Chat (Conversaciones):
Almacena las conversaciones entre mentor y aprendiz.
Un chat puede contener múltiples mensajes.

6. Notification (Notificaciones):
Gestiona las notificaciones enviadas a los usuarios.
Cada notificación está asociada a un usuario.

![image](https://github.com/user-attachments/assets/8498b900-51e8-4541-b5ec-10c080ac09ec)




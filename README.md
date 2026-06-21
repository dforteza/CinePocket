# CinePocket

*Tu gestor personal de películas en Android.*

## Equipo de desarrollo

- Javier
- Rodrigo
- Diego

## Descripción

CinePocket es una aplicación Android desarrollada para consolidar conocimientos en desarrollo móvil moderno: integra una API externa de películas, navegación entre pantallas con Jetpack Compose y funcionalidades nativas del sistema (compartir, llamadas, navegador).

**Funcionalidades:**
- **Autenticación:** inicio de sesión simulado (email/contraseña), preparado para integrar autenticación real.
- **Explorar películas:** listado ordenado por calificación, importado desde una API externa, con opción de marcar como favoritas.
- **Detalle de película:** información ampliada, compartir por WhatsApp/Google, llamadas, enlace al navegador.
- **Favoritos:** acceso rápido a las películas marcadas.

## Arquitectura

Sigue el patrón **MVVM (Model-View-ViewModel)**:

```
UI Layer (Compose)        → Screens + ViewModels + Navigation
Data Layer                → Repository + DataSources + Models
   ├── Remote (Retrofit)  → Comunicación con la API de películas
   └── Local (Room)       → Persistencia local
```

Estructura de paquetes (`app/src/main/java/com/example/cinepocket/`):

```
data/
├── di/            # Inyección de dependencias (Hilt/Dagger)
├── local/         # Room: DAO, entidades y base de datos
├── remote/        # Retrofit: API, modelos de respuesta
└── repository/    # MovieRepository, abstrae las fuentes de datos

navigation/         # AppNavHost y definición de rutas

ui/
├── screens/       # Login, Home, Detail, Favorites
├── theme/         # Tema y estilos de la app
├── utils/         # Conectividad, intents, compartir
└── viewmodel/     # Lógica de presentación (MVVM)
```

**Tecnologías:** Kotlin, Jetpack Compose, Navigation Compose, Hilt/Dagger, Room, Retrofit + OkHttp, arquitectura MVVM.

## Instrucciones

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/dforteza/CinePocket.git
   ```
2. Abrir el proyecto con Android Studio (Arctic Fox o superior) y esperar a que Gradle sincronice.
3. Ejecutar en un dispositivo físico o emulador (botón Run ▶️).
4. (Opcional) Generar la documentación del código con Dokka:
   ```bash
   ./gradlew dokkaHtml
   ```
   Se genera en `build/dokka/html/index.html`.

## Recursos

- [Jetpack Compose](https://developer.android.com/jetpack/compose)
- [Room](https://developer.android.com/training/data-storage/room)
- [Retrofit](https://square.github.io/retrofit/)
- [Guía de arquitectura Android (MVVM)](https://developer.android.com/topic/architecture)
- [TMDB API](https://developer.themoviedb.org/docs)

## Licencia

Proyecto desarrollado con fines educativos.

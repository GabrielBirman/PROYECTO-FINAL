# App de Finanzas Personales — Android 📱

Aplicación Android nativa para registrar y organizar gastos e ingresos, desarrollada en equipo para la materia **Taller de Programación 3** (ORT, 2025).

## Funcionalidades

- **Onboarding y autenticación**: registro, login y recuperación de contraseña con PIN de seguridad (Firebase Auth).
- **Inicio con resumen financiero**: balance y movimientos recientes.
- **Transacciones**: listado de ingresos y gastos, consumido desde una API REST con Retrofit. Si la API no responde, usa datos locales.
- **Gastos por categoría**: alta de gastos nuevos y vista agrupada por categoría.
- **Notificaciones** dentro de la app.
- **Navegación inferior** entre las secciones principales.

## Tecnologías

- **Kotlin** + **Jetpack Compose** (Material 3)
- **Arquitectura MVVM** con separación en capas `data` / `domain` / `ui`
- **Hilt** para inyección de dependencias
- **Retrofit** + Gson para consumir APIs REST
- **Firebase** Authentication y Firestore
- **Coroutines y Flow** para programación asíncrona
- **Navigation Compose**

## Estructura

```
app/src/main/java/com/ort/parcial/c2/tp3/grupo10/
├── data/          # Repositorios (remoto, fake y con fallback) y API de Retrofit
├── di/            # Módulos de Hilt (Auth, Firebase, Network, Transactions)
├── domain/        # Modelos e interfaces de repositorio
├── shared/        # Servicio de autenticación
└── ui/
    ├── components/   # Componentes reutilizables (botones, inputs, navbar...)
    ├── screens/      # Pantallas: auth, home, transactions, expenses, categories...
    ├── nav/          # Rutas de navegación
    └── theme/        # Colores, tipografías y tema
```

## Cómo correrlo

1. Clonar el repositorio y abrirlo en Android Studio.
2. Copiar tu `google-services.json` de Firebase en `app/` (hay un ejemplo en `app/google-services.sample.json`).
3. Sincronizar Gradle y ejecutar en un emulador o dispositivo (API 27+).

```bash
./gradlew assembleDebug        # Compilar
./gradlew testDebugUnitTest    # Tests unitarios
```

## Equipo

- Gabriel Birman
- Iván Schutt
- Jonathan Vitangeli
- Martín Palma
- Iván Zárate
- Marai Nicolás

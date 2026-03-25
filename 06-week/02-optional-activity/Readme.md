# 🍦 IceCream App

Aplicación móvil desarrollada en Android Studio utilizando Kotlin y Jetpack Compose.

---

## Requisitos

Antes de ejecutar el proyecto, asegúrate de tener:

- Android Studio instalado
- Android SDK configurado
- Conexión a internet (para descargar dependencias)
- Instalar el Proyecto

### Repositorio

Accede al código fuente aquí:  
👉 [](https://github.com/tuusuario/icecream-app)

---

## Abrir el proyecto

1. Abrir Android Studio
2. Seleccionar **"Open"**
3. Buscar la carpeta del proyecto descargado
4. Esperar a que cargue completamente

---

## Configuración inicial

Al abrir el proyecto por primera vez:

- Android Studio sincronizará automáticamente las dependencias (Gradle)
- Espera a que termine este proceso
- Si no inicia automáticamente, haz clic en:
  **"Sync Project with Gradle Files"**

---

## Crear un emulador (AVD)

El emulador es necesario para ejecutar la aplicación.

Pasos:

1. Ir a **Tools → Device Manager**
2. Click en **Create Device**
3. Seleccionar un dispositivo (ejemplo: Pixel 6)
4. Click en **Next**
5. Descargar una versión de Android (API 33 o superior)
6. Click en **Finish**

---

## ▶ Ejecutar la aplicación

1. Seleccionar el emulador creado en la parte superior
2. Presionar el botón **Run ▶️**
3. Esperar a que la aplicación se instale y se abra

---

## Estructura básica del proyecto

El archivo principal que controla la interfaz es:

**MainActivity.kt**

#### Ubicación:

app/src/main/java/com/example/icecream_app/MainActivity.kt

---

## 🎨 Modificar la pantalla principal

Dentro de `MainActivity.kt` se encuentra el diseño de la app.

Ejemplo del código utilizado:

```kotlin
setContent {
    IceCreamAppTheme {
        Box(
            modifier = Modifier
                .fillMaxSize()
                .background(
                    Brush.verticalGradient(
                        colors = listOf(
                            Color(0xFFFFC0CB),
                            Color(0xFF87CEFA),
                            Color(0xFF40E0D0)
                        )
                    )
                ),
            contentAlignment = Alignment.Center
        ) {
            Text(
                text = "Ice Cream 🍦",
                fontSize = 32.sp,
                fontWeight = FontWeight.Bold,
                color = Color.White
            )
        }
    }
}
```

### Resultado esperado

Al ejecutar la aplicación se mostrará:

Pantalla con fondo degradado
Texto centrado: Ice Cream 🍦

### Debugging

Para revisar errores o ejecución:

Ir a la pestaña Logcat (parte inferior de Android Studio)
Ver mensajes del sistema y errores en tiempo real

**_👨‍💻 Autores_**

- Brandow Claros
- Jeronimo Artunduaga
- Victor Brand
- Brandon Sanchez

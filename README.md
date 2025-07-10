# 📸 **Lab13 - Aplicación de Cámara con Visualización de Galería** 🖼️

Este proyecto es una **aplicación Android** desarrollada con **Kotlin** que permite capturar fotos usando la cámara y visualizar una galería con las imágenes tomadas. La aplicación consta de dos actividades principales:

1. **📷 MainActivity**: Permite capturar fotos utilizando la cámara.
2. **🖼️ GalleryActivity**: Muestra una galería con las fotos capturadas.

## 🚀 **Requisitos**

* **Android Studio** (última versión recomendada)
* **Kotlin** 1.5 o superior
* **Android SDK** 33 o superior
* **Java 11** (opcionalmente Java 8 si encuentras problemas con Java 11)

## 🎯 **Funcionalidades**

1. **Captura de fotos** 📸: Utiliza la API **CameraX** para acceder a la cámara y capturar imágenes en formato `.jpg`.
2. **Visualización de imágenes** 🖼️: Almacena las imágenes capturadas en una carpeta específica del almacenamiento interno y las muestra en una galería utilizando un `ViewPager`.
3. **Cambio de cámara** 🔄: La aplicación permite cambiar entre la cámara frontal y trasera.
4. **Galería** 📑: Muestra las imágenes capturadas en un `ViewPager`, permitiendo al usuario navegar entre las imágenes.

## 📂 **Estructura del Proyecto**

### 1. **MainActivity.kt** 📷

La actividad principal (`MainActivity`) permite al usuario tomar fotos usando la cámara. Utiliza **CameraX** para la captura de imágenes. Los permisos necesarios (cámara y almacenamiento) se solicitan en tiempo de ejecución.

#### Funciones principales:

* **Captura de foto** 📸: Usando el botón de captura, la foto se guarda en un directorio específico.
* **Cambio de cámara** 🔄: Permite cambiar entre la cámara frontal y trasera.

### 2. **GalleryActivity.kt** 🖼️

La actividad secundaria (`GalleryActivity`) muestra las imágenes que han sido tomadas y almacenadas en el dispositivo. Utiliza un `ViewPager` para mostrar las imágenes y un adaptador personalizado (`GalleryAdapter`) para cargar las imágenes de forma eficiente.

#### Funciones principales:

* **Cargar imágenes desde el almacenamiento** 🗂️: Recupera las imágenes almacenadas en la carpeta `Lab13_Images`.
* **Mostrar imágenes** 🖼️: Usa un `GalleryAdapter` con un `ViewPager` para permitir la visualización de las imágenes en una galería.

### 3. **GalleryAdapter.kt** 🧩

Este adaptador se encarga de mostrar las imágenes en un `ViewPager`. Utiliza **Glide** para cargar las imágenes de manera eficiente.

### 4. **AndroidManifest.xml** 📜

El archivo de manifiesto de la aplicación configura los permisos necesarios para el acceso a la cámara y al almacenamiento externo.

## 📝 **Instrucciones para ejecutar el proyecto**

### 1. **Clonar el repositorio**

```bash
git clone https://github.com/tu-usuario/Lab13.git
```

### 2. **Abrir el proyecto en Android Studio**

* Abre **Android Studio** y selecciona **"Open an existing project"**.
* Navega hasta la carpeta donde clonaste el repositorio y abre el proyecto.

### 3. **Configurar las dependencias**

Asegúrate de que todas las dependencias estén configuradas en el archivo `build.gradle`. Las principales dependencias son:

```gradle
implementation "androidx.camera:camera-camera2:1.0.1"
implementation "androidx.camera:camera-lifecycle:1.0.1"
implementation "androidx.camera:camera-view:1.0.0-alpha27"
implementation 'com.github.bumptech.glide:glide:4.12.0'
```

### 4. **Habilitar `viewBinding`**

En tu archivo `build.gradle`, asegúrate de habilitar `viewBinding`:

```gradle
android {
    viewBinding {
        enabled = true
    }
}
```

### 5. **Configurar permisos**

En el archivo `AndroidManifest.xml`, asegúrate de tener los permisos de cámara y almacenamiento:

```xml
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-feature android:name="android.hardware.camera.any" />
```

### 6. **Ejecutar la aplicación**

Conecta un dispositivo físico o usa un emulador de Android con soporte para cámara. Luego, ejecuta el proyecto desde Android Studio.

## 🌱 **Mejoras futuras**

* **Soporte para otros formatos de imagen**: Actualmente solo se guardan imágenes en formato `.jpg`, pero se podrían agregar otros formatos como `.png`.
* **Funcionalidad de edición de imágenes** ✍️: Permitir que el usuario edite las fotos antes de guardarlas o compartirlas.
* **Mejorar la galería**: Se podría agregar la opción de eliminar o compartir imágenes desde la galería.
* **Optimización de recursos**: Usar un `RecyclerView` en lugar de `ViewPager` para mejorar la eficiencia al mostrar imágenes.


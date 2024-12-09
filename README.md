# Coffee Shop App

## Descripción
Aplicación para gestionar un coffee shop utilizando Jetpack Compose, Firebase, Retrofit, MVVM, Clean Architecture y otras herramientas modernas de desarrollo en Android. Este proyecto sigue buenas prácticas para asegurar un código modular, escalable y fácil de mantener.

## Tecnologías
- **Jetpack Compose**: Para la interfaz de usuario declarativa.
- **Firebase**: Usado como backend normal para manejar la base de datos (Realtime Database) y almacenamiento de imágenes, sin utilizar la librería oficial de Firebase.
- **Retrofit**: Interactúa con **Realtime Database** de Firebase (usando la URL con `.json`).
- **MVVM + Clean Architecture**: Estructura del proyecto para desacoplar responsabilidades.
- **Kotlin DSL**: Configuración del proyecto en Gradle.
- **Version Catalog**: Gestión centralizada de dependencias.

## Estado actual del proyecto
- Proyecto inicial configurado con **Kotlin DSL** y **Version Catalog**.
- Jetpack Compose.
- Control de versiones con Git inicializado.

## Uso de Firebase como Backend
En este proyecto, **Firebase** se utiliza como un backend tradicional para almacenar datos en **Realtime Database** y gestionar archivos (como imágenes) a través de **Firebase Storage**. No se está utilizando la librería oficial de Firebase, sino que estamos accediendo a los servicios de Firebase usando **Retrofit**.

### Almacenamiento de imágenes
Las imágenes asociadas a los productos (cafés) serán almacenadas en **Firebase Storage**. **Realtime Database** de Firebase no almacena imágenes directamente, sino que guardará las **URL** de las imágenes almacenadas en Firebase Storage. Así, las imágenes pueden ser accesibles mediante las URLs correspondientes.

### Interacción con Firebase como una API RESTful
Al agregar el sufijo `.json` a la URL de una base de datos en **Realtime Database** funciona como una API RESTful. De esta forma, los datos pueden ser accesibles y manipulables mediante solicitudes HTTP. 

## Uso de Version Catalog
En este proyecto, utilizamos **Version Catalog** para gestionar las dependencias y sus versiones de forma centralizada en el archivo `libs.versions.toml`.  
Esto facilita:
1. Mantener las versiones sincronizadas.
2. Simplificar las actualizaciones de dependencias.
3. Garantizar consistencia en todo el proyecto.

**Nota**: A diferencia de proyectos anteriores que utilizaban Groovy o directamente Kotlin DSL, esta implementación mejora la organización y escalabilidad, especialmente para proyectos colaborativos o con múltiples módulos.

## Próximos pasos
1. Integrar Firebase al proyecto:
   Configurar Realtime Database en el proyecto Firebase.
   Configuración adecuada en google-services.json.
2. Implementar la estructura de Clean Architecture:
   Separar el proyecto en capas: Dominio, Datos, y Presentación.
   Configurar la inyección de dependencias utilizando Dagger/Hilt.
3. Configurar Retrofit para la comunicación con Firebase.
4. Crear pantallas iniciales.

## Buenas prácticas
### 1. Testing
- **JUnit**: Pruebas unitarias.
- **Espresso**: Pruebas de interfaz de usuario.
- **MockK/Mockito**: Simulación de dependencias para pruebas.

### 2. Control de versiones
- Flujo de trabajo con **Git Flow**

### 3. Gestión de estado
- Uso de LiveData o Flow para manejo reactivo de datos.

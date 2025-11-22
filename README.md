# README - Pruebas Automatizadas para https://automationexercise.com/

## 1. Descripción del proyecto

Este proyecto contiene un conjunto de **pruebas automatizadas API** para el sitio [AutomationExercise](https://automationexercise.com/).  
Se implementan pruebas de:

1. **Login API**
2. **Lista de productos (`/productsList`)**
3. **Creación de usuario (`/createAccount`)**
4. **Casos negativos**

El objetivo es validar tanto el funcionamiento de la API.

---

## 2. Estructura de la colección Postman

- **Login API**
  - Login exitoso
  - Login con contraseña inválida
  - Login con email inexistente
  - Validación de estructura JSON

- **ProductsList API**
  - Validar código de respuesta 200
  - Validar existencia de productos
  - Validar estructura de un producto (id, name, price)
  - Validar que IDs no sean duplicados

- **CreateAccount API**
  - Creación exitosa con email dinámico
  - Creación fallida con email duplicado
  - Validación de estructura de JSON

- **Casos negativos**
  - Parámetros incompletos
  - Validación de tiempos de respuesta (<500ms)

---

## 3. Variables de entorno usadas

N/A
---

## 4. Cómo usar la colección en Postman

### Paso 1: Descargar la colección
- El proyecto incluye un archivo `.json` (Postman Collection).  

### Paso 2: Importar la colección en Postman
1. Abrir Postman → clic en **Import** (arriba a la izquierda)  
2. Seleccionar **Upload Files**  
3. Subir el archivo `automationexercise-api-tests.postman_collection`
4. Clic en el botón **Import**

### Paso 3: Ejecutar las pruebas
- Puedes ejecutar requests individuales haciendo clic en el botón **Send**.    
- O ejecutar toda la colección:
  1. Seleccionar la colección `automationexercise-api-tests.postman_collection`  
  2. Clic en **Run** (arriba a la derecha)→ se abrirá la ventana del **Collection Runner**  
  3. Seleccionar número de iteraciones  
  4. Clic en **Run**  

---

## 4. Detalles importantes

- Los emails dinámicos se generan automáticamente antes de cada request de creación exitosa.  
- La prueba de **correo duplicado** usa un email fijo (`test@flare.com`) para ser independiente de la creación exitosa.  

---

## 5. Buenas prácticas

- Verificar que la API esté disponible antes de ejecutar la colección.  
- Revisar los códigos de respuesta y mensajes devueltos por la API para validar consistencia.

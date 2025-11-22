# README - Pruebas Automatizadas para https://automationexercise.com/

## 1. Descripción del proyecto

Este proyecto contiene un conjunto de **pruebas automatizadas API** para el sitio [AutomationExercise](https://automationexercise.com/).  
Se implementan pruebas de:

1. **Login API**
2. **Lista de productos (`/productsList`)**
3. **Creación de usuario (`/createAccount`)**
4. **Casos negativos / de borde**

El objetivo es validar tanto el **funcionamiento normal** como la **robustez del backend** frente a datos incorrectos o incompletos.

---

## 2. Estructura de la colección Postman

- **Login API**
  - Login exitoso
  - Login con contraseña inválida
  - Login con email inexistente
  - Validación de estructura JSON (responseCode, message)

- **ProductsList API**
  - Validar código de respuesta 200
  - Validar existencia de productos
  - Validar estructura de un producto (id, name, price)
  - Validar que IDs no sean duplicados

- **CreateAccount API**
  - Creación exitosa con email dinámico
  - Creación fallida con email duplicado (independiente)
  - Validación de estructura de JSON

- **Casos negativos / de borde**
  - Parámetros vacíos
  - Request sin headers (si aplica)
  - Validación de estructura de error
  - Validación de tiempos de respuesta (<500ms)

---

## 3. Variables de entorno usadas

| Variable      | Descripción |
|---------------|------------|
| `newEmail`    | Email dinámico generado para creación exitosa |
| `usedEmail`   | Email ya usado para prueba de duplicado |

---

## 4. Cómo usar la colección en Postman

### Paso 1: Descargar la colección
- El proyecto incluye un archivo `.json` (Postman Collection) y un archivo `.env` (entorno).  

### Paso 2: Importar la colección en Postman
1. Abrir Postman → clic en **Import** (arriba a la izquierda)  
2. Seleccionar **Upload Files**  
3. Subir el archivo `AutomationExercise.postman_collection.json`  
4. Hacer lo mismo con el archivo de entorno `AutomationExercise.postman_environment.json` (opcional)

### Paso 3: Seleccionar el entorno
- En la esquina superior derecha de Postman, seleccionar el entorno **AutomationExercise** para que las variables funcionen.

### Paso 4: Ejecutar las pruebas
- Puedes ejecutar requests individuales haciendo clic en **Send**.  
- O ejecutar toda la colección:
  1. Seleccionar la colección `AutomationExercise`  
  2. Clic en **Run** → se abrirá la ventana del **Collection Runner**  
  3. Seleccionar entorno y número de iteraciones  
  4. Clic en **Start Run**  

---

## 5. Detalles importantes

- Los emails dinámicos se generan automáticamente antes de cada request de creación exitosa.  
- La prueba de **correo duplicado** usa un email fijo (`test@flare.com`) para ser independiente de la creación exitosa.  
- Los tests de casos negativos validan robustez del backend ante datos incompletos o incorrectos.

---

## 6. Buenas prácticas

- Siempre ejecutar los tests con **entorno seleccionado** para que las variables funcionen.  
- Verificar que la API esté disponible antes de ejecutar la colección.  
- Revisar los códigos de respuesta y mensajes devueltos por la API para validar consistencia.
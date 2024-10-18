# Arquitectura MVC

### Pregunta 1: ¿Qué camino sigue el código cuando el usuario accede por primera vez a `index.php`?
**Descripción**: Explica qué ocurre desde que el usuario carga `index.php` hasta que se muestra algo en pantalla. Incluye cómo intervienen el controlador, las vistas y el modelo, si es necesario.

RESPUESTA

Cuando el usuario accede por primera vez a "index.php" se define la variable "BASE_PATH" donde se almacenara la ruta completa del directorio.

Despues se incluira el archivo "/controllers/UserControllers.php" que esta en la ruta especificada en "BASE_PATH".

Por ultimo crea una instancia de "UserController" y llama al método "showForm()" para mostrar un formulario.


### Pregunta 2: ¿Qué camino sigue el código cuando el usuario introduce datos en el formulario?
**Descripción**: Detalla el proceso desde que el usuario envía el formulario hasta que se guarda la información y se muestra una respuesta en pantalla.

> **Nota:** Al crear nuevas vistas, añade alguna forma de navegar entre ellas de modo que el usuario pueda acceder a todas las vistas sin tener que modificar la URL directamente.

RESPUESTA

Cuando el usuario completa el formulario en "userForm.php" y presiona "Create User", los datos se envían a "saveUser.php". El archivo carga el controlador "UserController" y llama al método "saveUser()", donde  obtiene el nombre del usuario del formulario y se crea un objeto "User". Despues, se llama al método "save()" del objeto, que inserta el nombre en la base de datos. Si se inserta correctamente, se carga "userSuccess.php" y se mostrara un mensaje de confirmacion.

### Ejercicio 1: Mostrar Todos los Usuarios
**Descripción**: Extiende la funcionalidad de la aplicación para que se muestre una lista de todos los usuarios que están en la base de datos.
- Añadir un nuevo método en el controlador `UserController` llamado `getAllUsers()`.
- Crear una nueva vista `showUsers.php` para mostrar una tabla con los nombres de los usuarios.

### Ejercicio 2: Eliminar Usuario
**Descripción**: Implementa la funcionalidad para eliminar un usuario de la base de datos.
- Crear un método `deleteUser()` en `UserController`.
- Crear una acción en `showUsers.php` que permita eliminar usuarios, mostrando un botón "Eliminar" al lado de cada nombre en la lista de usuarios.

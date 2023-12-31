﻿# Patrón de diseño MVC

El patrón escogido para el sprint 1 ha sido el MVC.
En este caso me ayudará a mantener el código organizado y facilitará su implementación y el mantenimiento de la aplicación.

### 1. Modelo (Model)   
Es a parte que representa los datos y la lógica de la aplicación. En este caso, las tareas que quiere realizar el usuario.

Para representar las tareas he utilizado un array de objetos con el registro de las tareas y las operaciones que estén relacionadas con ellas. En este caso, el nombre de la tarea y si esta ha sido realizada o no.
```
interface Task {
  task: string;
  isChecked: boolean;
}

const taskList: Task[] = [];
```
### 2. Vista (View)   
Esta parte es la encargada de la interfaz del usuario.

La Vista es la responsable de reflejar los cambios en el Modelo en la interfaz de usuario. Esto se logra mediante la actualización dinámica de elementos HTML para mostrar la información actualizada de las tareas.

### 3. Controlador (Controller):
Es el intermediario entre el Modelo y la Vista.
    
Su función principal es recibir eventos del usuario, como agregar una nueva tarea, marcar una tarea como completada o eliminar una tarea, y luego coordinar la actualización tanto del Modelo como de la Vista en respuesta a estos eventos.    
```
const addInput = (newTask: string): void => { 
  const taskExists = taskList.some((task) => task.task === newTask);

  taskList.push({
    task: newTask,
    isChecked: false,
  });
};
```

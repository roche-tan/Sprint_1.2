# Patrón de diseño MVC

El patrón escogido para el sprint 1 ha sido el MVC.
En este caso me ayudará a mantener el código organizado y facilitará su implementación y el mantenimiento de la aplicación.

### 1. Modelo (Model)   
Es a parte que representa los datos y la lógica de la aplicación. En este caso, las tareas.

Para representar las tareas he utilizado un array de objetos con el registro de las tareas y las operaciones que estén relacionadas con ellas.
```
interface Task {
  task: string;
  isChecked: boolean;
}

const taskList: Task[] = [];
```
### 2. Vista (View)   
Esta parte es la encargada de la interfaz del usuario. En este caso, la lista de tareas pendientes.

Esto se haría con una función que modificara el DOM según las necesidades del usuario.

### 3. Controlador (Controller):
Es el intermediario entre el Modelo y la Vista. Es el que recibe los eventos del usuario y actualiza tanto el modelo como la vista.
```
const addInput = (newTask: string): void => { 
  const taskExists = taskList.some((task) => task.task === newTask);

  taskList.push({
    task: newTask,
    isChecked: false,
  });
};
```

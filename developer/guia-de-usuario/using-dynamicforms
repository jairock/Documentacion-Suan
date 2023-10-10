---
description: >-
  Los formularios dinamicos son una herramienta útil que te permitiran crear formularios facilmente a partir de archivos basados en el estandar XLSForm
---

## Implementación
1. Importar componente **Dynamic Form**
```jsx
  import DynamicForm from "path/to/DynamicForm";
```

2. Configuración de propiedades (atributos que serán enviados al componente DynamicForm):

- **XLSFormURL**: La URL del archivo XLSForm que deseas cargar.
- **submitBtnLabel**: La etiqueta que se mostrará en el botón de envío.
- **formData**: El estado de los datos del formulario.
- **formDataErrors**: El estado de los errores del formulario.
- **setFormData**: La función para actualizar el estado de los datos del formulario.
- **setFormDataErrors**: La función para actualizar el estado de los errores del formulario.

```jsx
  const XLSFormURL = "https://ruta-hacia-tu-xlsform.com/archivo.xls";
  const submitBtnLabel = "Enviar Formulario";
  const [formData, setFormData] = useState({});
  const [formDataErrors, setFormDataErrors] = useState({});
```

3. Definición de la función de manejo de envío
Antes de usar el componente DynamicForm, define una función de manejo de envío **handleSubmit()** que se ejecutará cuando el usuario envíe el formulario. Esta función deberá implementar la logica para procesar los datos almacenados por el formulario en la variable de estado **formData**.

```jsx
  const handleSubmit = async () => {
    // Lógica de envío de datos o procesamiento aquí
  };
```
Ejemplo:
```jsx
  const handleSubmit = async () => {
    // Para obtener el valor de un input del formulario se debe hacer uso de
    // el nombre asignado en la columna name de XLSForm como llave del objeto formData

    const name = formData["todo_name"] 
    const description = formData["todo_description"]

    const newToDo = {
      name: name,
      description: description,
    };
    await API.graphql(graphqlOperation(createTodo, { input: newToDo }));
  };
```
4. Renderización del componente

```jsx
  <DynamicForm
    XLSFormURL={XLSFormURL}
    handleSubmit={handleSubmit}
    submitBtnLabel={submitBtnLabel}
    formData={formData}
    setFormData={setFormData}
    formDataErrors={formDataErrors}
    setFormDataErrors={setFormDataErrors}
  />
```
## Personalización
El componente **DynamicForm** es altamente personalizable a través de la configuración de tu archivo **XLSForm**. Puedes crear campos de diferentes tipos, como texto, números, opciones múltiples, archivos adjuntos y más. Asegúrate de configurar correctamente las siguientes propiedades para cada campo personalizado: 
- **type**: Tipo de campo **(note | text | integer | select_one | select_multiple | file | image | geopoint | begin group | end group)**.
- **name**: Específico para cada campo y debe ser único.
- **label**: La etiqueta o título que se mostrará junto al campo en el formulario.
- **hint**: Opcional, recomendación o pista que se mostrará junto a la etiqueta o titulo del campo.
- **required**: Opcional, en caso de requerir la obligatoriedad un campo a la hora de enviar el formulario **(yes | false)**.
- **appearance**: Opcional, utilizado para personalizar la apariencia del campo, por ejemplo, para campos de texto **(multiline)**
- **relevant**: Opcional, define una condición que debe cumplirse para que el campo sea visible. Por ejemplo, puedes ocultar un campo hasta que se seleccione una opción específica en otro campo.
- **constraint**: Opcional, utilizado para validar un campo. **(No implementado aún)**
- **required_message**: Opcional, utilizado para personalizar mensaje de requerimiento de un campo despues de haber intentado enviar el formulario sin llenar alguno de los campos obligatorios.

##### Agrupación de campos
El componente tambien permite la agrupación visual de elementos mediante el uso de los tipos:
- **begin group**: Indica el comienzo de un grupo
- **end group**: Indica el fin de un grupo

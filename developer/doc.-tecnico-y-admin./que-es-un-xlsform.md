# 💻 Que es un XLSForm?

XLSForm es un estándar de formularios creado para simplificar la creación de formularios en Excel. La autoría se realiza en un formato legible por humanos utilizando una herramienta familiar que casi todos conocen: Excel. Los XLSForms proporcionan un estándar práctico para compartir y colaborar en la autoría de formularios. Son fáciles de comenzar, pero permiten la creación de formularios complejos por parte de alguien familiarizado con la sintaxis descrita a continuación. El XLSForm se convierte luego en un ODK XForm, un estándar de formulario abierto y popular, que te permite crear un formulario con funcionalidades complejas, como lógica de salto, de manera consistente en una variedad de plataformas de recopilación de datos web y móviles.

### Formato Básico

Cada libro de Excel generalmente tiene dos hojas de trabajo: survey (encuesta) y choices (opciones). Una tercera hoja de trabajo opcional, llamada settings (configuraciones), puede agregar especificaciones adicionales a tu formulario.

### La hoja de trabajo de encuesta (survey)

Esta hoja de trabajo le da a tu formulario su estructura general y contiene la mayor parte del contenido del formulario. Contiene la lista completa de preguntas e información sobre cómo deben aparecer en el formulario. Cada fila generalmente representa una pregunta; sin embargo, hay ciertas características adicionales descritas a continuación que puedes agregar al formulario para mejorar la experiencia del usuario.

### La hoja de trabajo de opciones (choices)

Esta hoja de trabajo se utiliza para especificar las opciones de respuesta para preguntas de opción múltiple. Cada fila representa una opción de respuesta. Las opciones de respuesta con el mismo nombre de lista se consideran parte de un conjunto relacionado de opciones y aparecerán juntas para una pregunta. Esto también permite que un conjunto de opciones se reutilice para varias preguntas (por ejemplo, preguntas de sí/no).

Ambas hojas de trabajo tienen un conjunto de columnas obligatorias que deben estar presentes para que el formulario funcione. Además, cada hoja de trabajo tiene un conjunto de columnas opcionales que permiten un mayor control sobre el comportamiento de cada entrada en el formulario, pero no son esenciales. Cada entrada debe tener valores para cada una de las columnas obligatorias, pero las columnas opcionales pueden dejarse en blanco.

### Configurando la hoja de trabajo de encuesta (survey worksheet)

La hoja de trabajo de encuesta tiene 3 columnas obligatorias:

* **type** (tipo): especifica el tipo de entrada que esperas para la pregunta.
* **name** (nombre): especifica el nombre único de variable para esa entrada. No puede haber dos entradas con el mismo nombre. Los nombres deben comenzar con una letra o un guion bajo. Los nombres solo pueden contener letras, dígitos, guiones, guiones bajos y puntos. Los nombres son sensibles a mayúsculas y minúsculas.
* **label** (etiqueta): contiene el texto real que se muestra para la pregunta en el formulario. Alternativamente, se pueden utilizar columnas de traducción de etiquetas. Recuerda que estas columnas son esenciales para que el formulario funcione correctamente. Cada pregunta debe tener valores definidos en estas columnas.

Las columnas opcionales en la hoja de trabajo de encuesta permiten un control adicional sobre el comportamiento de las entradas en el formulario, pero no son obligatorias.

### Configurando la hoja de trabajo de opciones (choices worksheet)

La hoja de trabajo de opciones también tiene 3 columnas obligatorias:

* **list\_name** (nombre de lista): te permite agrupar un conjunto de opciones de respuesta relacionadas, es decir, opciones de respuesta que deben aparecer juntas en una pregunta.
* **name** (nombre): especifica el nombre único de variable para esa opción de respuesta. Al igual que en la hoja de trabajo de encuesta, no puede haber dos opciones de respuesta con el mismo nombre en esta hoja de trabajo. Los nombres deben comenzar con una letra o un guion bajo. Los nombres solo pueden contener letras, dígitos, guiones, guiones bajos y puntos. Los nombres son sensibles a mayúsculas y minúsculas.
* **label** (etiqueta): muestra la opción de respuesta exactamente como deseas que aparezca en el formulario. Alternativamente, se pueden utilizar columnas de traducción de etiquetas. La columna nombre de lista te permite agrupar conjuntos de opciones de respuesta que están relacionadas entre sí y que deben aparecer juntas bajo una pregunta específica en el formulario.

Recuerda que estas columnas también son esenciales para que el formulario funcione correctamente. Cada opción de respuesta debe tener valores definidos en estas columnas.

Al igual que en la hoja de trabajo de encuesta, las columnas opcionales en la hoja de trabajo de opciones permiten un control adicional sobre el comportamiento de las opciones de respuesta, pero no son obligatorias.

### Factores a tener en cuenta

Las columnas que agregues a tu libro de Excel, ya sean obligatorias o opcionales, pueden aparecer en cualquier orden. Las columnas opcionales pueden ser omitidas por completo. También puedes dejar filas o columnas en blanco para mejorar la legibilidad, pero ten en cuenta que no se procesarán datos después de que haya 20 columnas o filas en blanco adyacentes en una hoja. Además, ten en cuenta que todo el formato de archivo .xlsx se ignora, por lo que puedes usar líneas divisorias, sombreado y otras formatos de fuente para que el formulario sea más legible.

Un aspecto importante a tener en cuenta al crear formularios en Excel es que la sintaxis que utilices debe ser precisa. Por ejemplo, si escribes "Choices" o "choice" en lugar de "choices," el formulario no funcionará.

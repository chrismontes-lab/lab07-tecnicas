# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot


| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5/5 | Tabla con clasificación, resumen y conclusión | Si |
| One-shot | 5/5 | Lista numerada con etiquetas | Si |
| Few-shot | 5/5 | Texto -> etiqueta | Si |


**Observación:**

Los tres métodos obtuvieron 5 de 5 aciertos en la clasificación de los comentarios. Sin embargo, se observaron diferencias en el formato de las respuestas. Zero-shot respondió mediante una tabla, one-shot utilizó una lista numerada y few-shot siguió exactamente el formato indicado en los ejemplos. Esto demuestra que proporcionar ejemplos ayuda a mantener una respuesta más uniforme y organizada.


## Ejercicio 3: Chain of Thought


| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | S/ 318.60 | No | Si |
| Paso a paso | S/ 318.60 | Si | Si |


**Observación:**

Ver los pasos permite comprobar cómo se obtuvo el resultado y detectar posibles errores en los cálculos. Aunque la respuesta directa fue correcta, el procedimiento paso a paso ofrece mayor seguridad al momento de verificar la operación.


## Ejercicio 4: Role prompting


| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol | Tecnico e intermedio | Si, ejemplos y codigo Java | Personas que buscan una explicacion general. |
| B. Rol docente | Sencillo | Si, ejemplos cotidianos y codigo | Estudiantes que nunca han programado. |
| C. Rol senior | Tecnico | Si, codigo Java y buenas practicas | Desarrolladores con conocimientos de Java. |


**Observacion:**

Al utilizar diferentes roles, la IA modifico la forma de explicar el mismo concepto. El rol docente utilizo palabras sencillas y ejemplos cotidianos, mientras que el rol senior empleo terminos tecnicos y recomendaciones de desarrollo. Esto demuestra que el rol permite adaptar la respuesta al tipo de usuario.


## Ejercicio 5: Descomposicion


### Pedido de una sola vez
La IA propuso TiendaTec con Java Swing, incluyendo gestión de productos, control de stock, búsqueda, modificación y eliminación. También presentó una estructura inicial de tres clases.

### Pedido por pasos

**Paso 1. Requisitos:** La IA identificó cinco requisitos: gestión de productos, control de inventario, gestión de categorías, alertas de stock bajo y generación de reportes.

**Paso 2. Diseño de clases:** Se propusieron siete clases: Producto, Categoria, MovimientoInventario, Proveedor, AlertaStock, ReporteInventario y DetalleReporte, con sus respectivos atributos y tipos de datos.

**Paso 3. Código:** Se generó la clase Producto.java con siete atributos privados, un constructor y sus métodos getters y setters.

**Paso 4. Mejoras:** La IA propuso incorporar validaciones de datos, un constructor sin parámetros y el método toString().

**Comparación:** El pedido de una sola vez generó una propuesta general del sistema. En cambio, al dividir la tarea en cuatro pasos, fue posible definir los requisitos, diseñar las clases, generar el código y revisar posibles mejoras de manera ordenada.


## Ejercicio 6: Prompt estructurado y autocritica


## Ejercicio 6: Prompt estructurado y autocrítica

### Paso 1. Prompt básico
Se solicitó a ChatGPT generar casos de prueba para un sistema de login. La IA presentó 15 casos con diferentes escenarios positivos, negativos y de validación.

### Paso 2. Prompt estructurado
Se utilizaron las etiquetas rol, contexto, tarea y formato para definir mejor la solicitud. La IA generó exactamente 6 casos de prueba, incluyendo el bloqueo de cuenta después de tres intentos fallidos.

### Paso 3. Autocrítica
Se solicitó revisar la tabla e identificar casos límite faltantes. La IA agregó 7 casos relacionados con campos vacíos, formatos incorrectos de correo y contraseñas con espacios.

### Paso 4. Evaluación

| Criterio | Cumple |
|---|---|
| Tiene las 4 columnas pedidas | Sí |
| Incluye el bloqueo después de 3 intentos | Sí |
| Incluye casos con campos vacíos | Sí |
| Indica qué casos agregó | Sí |
| Hay casos repetidos o incorrectos | No |

**Observaciones:** Se identificó que CP-06 y CP-07 son repetidos. Además, CP-13 presenta una inconsistencia entre el escenario y los datos de entrada, porque no incluye los espacios indicados.

### Paso 5. Prompts utilizados

```text
<rol>Actua como analista de pruebas de software.</rol>

<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>
```

**Mensaje de autocrítica:**

```text
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

### Conclusión
El prompt estructurado permitió obtener una respuesta más específica y organizada que el prompt básico. La autocrítica permitió identificar casos adicionales, aunque fue necesario revisar manualmente la respuesta para detectar duplicaciones e inconsistencias.

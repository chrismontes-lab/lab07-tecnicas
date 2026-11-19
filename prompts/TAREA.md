# Tarea: Mi prompt avanzado

## Tarea elegida

**Desarrollo de un sistema de inventario para una tienda pequeña utilizando Java.**

El proyecto elegido es TiendaTec, un sistema que permite registrar, consultar, listar, modificar y eliminar productos. El objetivo es mejorar progresivamente las instrucciones proporcionadas a la inteligencia artificial para obtener una solución organizada, funcional y comprensible para un estudiante de Java.

## Versión 1: Prompt básico

**Técnica utilizada:** Zero-shot prompting.

**¿Por qué la utilicé?**

Para obtener una primera respuesta sin proporcionar ejemplos ni instrucciones demasiado específicas. De esta manera, pude identificar cómo interpreta la IA una solicitud general.

**Prompt utilizado:**

```text
Crea un sistema de inventario para una tienda pequeña utilizando Java.

El sistema debe permitir registrar, consultar, modificar y eliminar productos.

Cada producto debe tener código, nombre, descripción, precio y cantidad en stock.

Explica cómo funcionaría el sistema y presenta un ejemplo de código Java.
```

**Resultado obtenido:**

La IA propuso un sistema con tres clases: Producto, SistemaInventario y Main. Incluyó las operaciones CRUD, almacenamiento mediante ArrayList y un menú de opciones.

**¿Qué mejoró y qué faltaba?**

Se obtuvo una estructura inicial para el proyecto. Sin embargo, las validaciones y el control de errores necesitaban mayor precisión.

## Versión 2: Role Prompting

**Técnica agregada:** Role Prompting.

**¿Por qué la agregué?**

Para asignar a la IA un rol específico de desarrollador Java y orientar la respuesta hacia una solución más profesional, pero adecuada para un estudiante principiante.

**Prompt utilizado:**

```text
Actúa como un desarrollador Java especializado en sistemas de inventario para pequeños comercios y en programación orientada a objetos.

Revisa la propuesta anterior y desarrolla una versión mejorada del sistema de inventario TiendaTec.

El programa debe utilizar Java, programación orientada a objetos y ArrayList.

Debe incluir las siguientes funcionalidades:
1. Registrar productos.
2. Consultar y listar productos.
3. Modificar productos.
4. Eliminar productos.
5. Validar datos ingresados y evitar códigos duplicados.

Organiza el código en tres archivos: Producto.java, SistemaInventario.java y Main.java.

El código debe ser comprensible para un estudiante que está aprendiendo Java. Evita utilizar herramientas o conceptos innecesariamente avanzados.

Presenta primero la estructura del proyecto, después el código completo de cada clase y finalmente un ejemplo de ejecución.
```

**Resultado obtenido:**

La IA desarrolló una solución más organizada, incorporando validaciones de datos, control de códigos duplicados, manejo de errores numéricos y separación de responsabilidades entre las clases.

**¿Qué mejoró?**

La respuesta fue más específica y presentó una estructura de código más completa. Sin embargo, todavía era posible mejorar la planificación, los ejemplos y la revisión de calidad.

## Versión 3: Prompt final

**Técnicas agregadas:** Role Prompting, Prompt estructurado, Few-Shot Prompting, Descomposición y Autocrítica.

**¿Por qué las agregué?**

Para proporcionar instrucciones más precisas, ejemplos de comportamiento, dividir el desarrollo en etapas y solicitar una revisión final de la solución.

**Prompt utilizado:**

```text
Actúa como un desarrollador Java senior y docente especializado en programación orientada a objetos y aseguramiento de calidad de software.

CONTEXTO:

Estamos desarrollando TiendaTec, un sistema de inventario para una tienda pequeña. El proyecto está dirigido a un estudiante que está aprendiendo Java y necesita comprender cada parte del código.

OBJETIVO:

Mejorar la versión anterior del sistema, manteniendo una estructura sencilla y funcional.

REQUISITOS:

1. Registrar productos.
2. Consultar productos por código.
3. Listar todos los productos.
4. Modificar productos.
5. Eliminar productos.
6. Evitar códigos duplicados.
7. Validar campos vacíos, precios negativos y stocks inválidos.
8. Controlar errores cuando se ingresen letras en campos numéricos.

RESTRICCIONES:

- Utilizar Java y programación orientada a objetos.
- Utilizar ArrayList para almacenar productos.
- Mantener únicamente tres clases: Producto, SistemaInventario y Main.
- No utilizar bases de datos ni bibliotecas externas.
- No utilizar técnicas avanzadas innecesarias para un estudiante principiante.
- Mantener el código organizado y fácil de comprender.

EJEMPLOS DE COMPORTAMIENTO ESPERADO:

- Si se registra el código P001 y después se intenta registrar p001, el sistema debe detectar que es un código duplicado.
- Si se ingresa un precio con letras, debe mostrar un mensaje de error y solicitar nuevamente el dato.
- Si se ingresa un stock negativo, debe rechazarlo.

DESARROLLO:

Divide el trabajo en las siguientes etapas:

1. Revisa las versiones anteriores e identifica qué aspectos necesitan mejorar.
2. Presenta la estructura definitiva de las tres clases.
3. Desarrolla el código completo de cada archivo.
4. Explica brevemente la responsabilidad de cada clase y sus métodos.
5. Presenta casos de prueba positivos y negativos con sus resultados esperados.
6. Explica cómo compilar y ejecutar el programa.

REVISIÓN FINAL:

Antes de presentar la respuesta, comprueba la coherencia entre las tres clases, los nombres de los métodos, los atributos y las llamadas entre ellas. Evita código incompleto y asegúrate de que los ejemplos correspondan con la implementación presentada.
```

**Resultado obtenido:**

La IA produjo una propuesta más completa, organizada en etapas, con tres clases, validaciones, 18 casos de prueba y una lista de comprobación final.

**¿Qué mejoró?**

Se obtuvo una respuesta más precisa y estructurada. Además, se incorporaron ejemplos de comportamiento esperado y una revisión crítica antes de presentar la solución.

## Técnicas usadas en el prompt final

| Técnica | Parte del prompt | Utilidad |
|---|---|---|
| Role Prompting | Rol de desarrollador Java y docente | Define el perfil de la IA. |
| Prompt estructurado | Contexto, objetivo, requisitos y restricciones | Organiza las instrucciones. |
| Few-Shot Prompting | Ejemplos de comportamiento esperado | Orienta las respuestas mediante ejemplos. |
| Descomposición | Desarrollo dividido en seis etapas | Facilita el desarrollo ordenado. |
| Autocrítica | Revisión final de calidad | Solicita identificar posibles inconsistencias. |

## Evaluación del resultado

| Criterio | Resultado |
|---|---|
| Presenta un rol específico | Sí |
| Define claramente las funcionalidades | Sí |
| Utiliza al menos tres técnicas | Sí |
| Incluye ejemplos de comportamiento | Sí |
| Presenta las tres clases completas | Sí |
| Incluye casos de prueba | Sí |
| Comprueba la ejecución real del programa | No |

**Observación:** La revisión realizada por la IA no sustituye la compilación y ejecución del programa. También es necesario comprobar las validaciones directamente en el código.

## Por qué elegí estas técnicas

Elegí estas técnicas porque permiten mejorar progresivamente la calidad de las respuestas de la inteligencia artificial. El Role Prompting ayuda a definir el perfil que debe adoptar la IA; el Prompt estructurado organiza los requisitos y las restricciones; el Few-Shot Prompting proporciona ejemplos concretos; la Descomposición divide el trabajo en etapas más fáciles de desarrollar; y la Autocrítica permite revisar posibles errores antes de utilizar el resultado. La combinación de estas técnicas permitió obtener una propuesta más organizada, específica y adecuada para el desarrollo del sistema TiendaTec.
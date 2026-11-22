# 1.1.1. Una mirada al interior del chatbot (A Look Inside the Chatbot)

## Objetivo de aprendizaje

Comprender la arquitectura general de una aplicación de chatbot basada en un modelo de lenguaje de gran tamaño (*Large Language Model*, LLM), identificar los componentes que participan en una interacción y reconocer cómo se relacionan la interfaz, las instrucciones, los mensajes, el contexto y la generación de respuestas.

## 1. ¿Qué es un chatbot basado en un LLM?

Un chatbot es una aplicación que permite mantener una interacción conversacional mediante mensajes. Cuando utiliza un LLM, incorpora un modelo entrenado para procesar y generar lenguaje. El usuario envía una entrada y la aplicación coordina su procesamiento para producir una respuesta.

Es importante distinguir entre el **chatbot** y el **modelo**:

- **Chatbot o aplicación:** conjunto de componentes que gestionan la interfaz, la conversación, el contexto, las instrucciones y, según el producto, herramientas adicionales.
- **LLM:** componente que procesa secuencias de tokens y genera una continuación de acuerdo con el contexto recibido y los parámetros de ejecución.
- **Interfaz de usuario (User Interface, UI):** espacio donde la persona escribe, envía y consulta mensajes.
- **Backend o servidor de aplicación:** componente que recibe las solicitudes, administra la sesión y coordina la comunicación con el modelo y otros servicios.

Por tanto, el modelo no necesariamente es toda la aplicación. La experiencia del chatbot depende de la integración entre diferentes componentes.

## 2. Arquitectura general de un chatbot

Una interacción simplificada puede representarse mediante el siguiente flujo:

```text
┌──────────────────────────────┐
│       Usuario / Persona      │
└──────────────┬───────────────┘
               │ Escribe un mensaje
               ▼
┌──────────────────────────────┐
│ Interfaz del chatbot (UI)    │
│ Entrada y visualización      │
└──────────────┬───────────────┘
               │ Solicitud
               ▼
┌──────────────────────────────┐
│ Backend / Orquestación       │
│ Sesión, instrucciones,       │
│ historial y herramientas    │
└──────────────┬───────────────┘
               │ Contexto preparado
               ▼
┌──────────────────────────────┐
│ Modelo de lenguaje (LLM)     │
│ Procesamiento y generación   │
└──────────────┬───────────────┘
               │ Respuesta generada
               ▼
┌──────────────────────────────┐
│ Backend y aplicación         │
│ Procesamiento de respuesta   │
└──────────────┬───────────────┘
               │ Resultado
               ▼
┌──────────────────────────────┐
│ Interfaz del chatbot (UI)    │
│ Presenta la respuesta        │
└──────────────┬───────────────┘
               │
               ▼
             Usuario
```

Este esquema es conceptual. La arquitectura real depende del proveedor y del producto. Algunas aplicaciones incluyen recuperación de documentos, filtros de seguridad, ejecución de código, búsqueda, conectores o llamadas a servicios externos.

## 3. Componentes de la interfaz

La interfaz permite que el usuario interactúe con el sistema. Puede incluir:

- **Área de entrada:** campo donde se redacta el prompt.
- **Botón de envío:** inicia el procesamiento de la solicitud.
- **Historial de conversación:** muestra los mensajes anteriores disponibles en la sesión.
- **Área de respuesta:** presenta el contenido generado por el modelo.
- **Carga de archivos:** permite adjuntar documentos, imágenes u otros datos cuando la aplicación lo admite.
- **Controles adicionales:** selección de modelos, configuración, herramientas, voz o generación de contenido, según el producto.

La interfaz facilita la comunicación, pero no determina por sí sola la calidad factual de una respuesta. Una presentación correcta no significa que el contenido sea correcto.

## 4. Instrucciones, mensajes y contexto

El modelo recibe información organizada en una secuencia de mensajes. Cada mensaje puede incluir un rol o procedencia y un contenido.

En una estructura conversacional típica se encuentran:

- **System message (mensaje de sistema):** establece instrucciones generales y límites de comportamiento para el modelo, cuando la plataforma utiliza este mecanismo.
- **Developer message (mensaje de desarrollador):** define instrucciones de la aplicación o del flujo que utiliza el modelo.
- **User message (mensaje del usuario):** contiene la solicitud, pregunta o información aportada por la persona.
- **Assistant message (mensaje del asistente):** contiene las respuestas generadas por el modelo.
- **Tool message (mensaje de herramienta):** puede representar el resultado devuelto por una herramienta integrada, cuando existe ese mecanismo.

Los nombres, niveles de prioridad y formatos exactos dependen de la arquitectura de cada plataforma. No todas las interfaces muestran al usuario todos los mensajes internos.

### Diferencia entre instrucción y contexto

Una **instrucción** indica qué debe hacer el modelo. El **contexto** proporciona información necesaria para realizar la tarea correctamente.

Ejemplo:

- Instrucción: «Resume el documento en cinco puntos».
- Contexto: el documento que debe resumirse, el público al que se dirige y cualquier condición relevante.

Una solicitud puede contener ambos elementos en un mismo mensaje. Separarlos conceptualmente ayuda a detectar qué información falta.

## 5. ¿Cómo procesa el modelo una solicitud?

De forma simplificada, el procesamiento puede entenderse en las siguientes etapas:

1. **Recepción:** la aplicación recibe el mensaje y los datos adjuntos admitidos.
2. **Preparación del contexto:** el sistema organiza las instrucciones y el contenido de la conversación que enviará al modelo.
3. **Tokenización:** el texto se representa mediante unidades llamadas *tokens*. Un token puede corresponder a una palabra, parte de una palabra, un signo o una unidad de otro tipo.
4. **Procesamiento:** el LLM analiza la secuencia de tokens utilizando los parámetros aprendidos durante su entrenamiento.
5. **Generación:** el modelo produce tokens de salida de manera sucesiva, condicionados por el contexto y por la configuración de generación.
6. **Presentación:** la aplicación recibe la salida y la muestra al usuario; puede aplicar procesamiento adicional antes de presentarla.

La tokenización no equivale necesariamente a separar el texto por palabras. Por eso, la cantidad de tokens de un mensaje no coincide siempre con su número de palabras o caracteres.

## 6. ¿Cómo se genera una respuesta?

Los LLM modernos suelen utilizar arquitecturas basadas en *Transformers*. Estas arquitecturas emplean mecanismos de atención para procesar relaciones entre los elementos de una secuencia.

En términos generales, un modelo generativo estima qué token puede continuar la secuencia según el contexto disponible. Selecciona o calcula el siguiente token conforme a su método de generación y repite el proceso hasta producir una respuesta o alcanzar un límite.

La salida puede variar por diferentes factores:

- El contenido y orden de los mensajes.
- Las instrucciones y el contexto proporcionados.
- Los parámetros del modelo.
- La configuración de generación, como temperatura o límites de salida, cuando están disponibles.
- La versión del modelo y las capacidades habilitadas en la aplicación.

Por ello, una misma pregunta puede producir respuestas diferentes en distintas ejecuciones. La fluidez del texto no constituye una prueba de exactitud.

## 7. Historial y ventana de contexto

La **ventana de contexto (Context Window)** es la cantidad máxima de tokens que un modelo puede procesar como contexto en una ejecución, considerando los mensajes y otros elementos que se incluyan en ella. El límite exacto depende del modelo y de la plataforma.

Aunque una interfaz muestre una conversación extensa, no debe suponerse que todo el historial se envía íntegramente al modelo en cada solicitud. La aplicación puede seleccionar, resumir o excluir partes del historial para administrar el contexto.

Cuando se supera la capacidad disponible, puede ser necesario resumir información, dividir una tarea en etapas o volver a proporcionar datos relevantes.

## 8. Herramientas y servicios adicionales

Algunos chatbots amplían las capacidades del modelo mediante herramientas externas. Por ejemplo:

- Búsqueda de información en fuentes disponibles.
- Recuperación de fragmentos de documentos.
- Ejecución de código o cálculos.
- Consulta de bases de datos.
- Acceso a servicios mediante API.
- Procesamiento de archivos e imágenes.

En estos casos, la aplicación puede decidir que una solicitud requiere una herramienta, enviarle una operación y devolver el resultado al modelo para continuar la respuesta. La disponibilidad y los permisos de estas funciones dependen del producto.

Un LLM no debe considerarse automáticamente conectado a Internet, a una base de datos o a los archivos del usuario. Solo dispone de esas capacidades cuando la aplicación se las proporciona y autoriza.

## 9. Ejemplo de interacción

**Usuario:**

«Explica qué es una dirección IP a un estudiante que comienza a estudiar redes. Utiliza un ejemplo sencillo y termina con tres conceptos clave».

**Proceso conceptual:**

1. La interfaz recibe el mensaje.
2. El backend incorpora las instrucciones aplicables y el contexto de la conversación.
3. El modelo procesa los mensajes y genera una explicación.
4. La aplicación recibe y presenta la respuesta.
5. El usuario comprueba si el nivel, el ejemplo y los tres conceptos solicitados están presentes.

Si la respuesta utiliza terminología demasiado avanzada, el usuario puede ajustar el prompt:

«Reescribe la explicación para una persona sin experiencia en redes. Define cada término técnico antes de utilizarlo y conserva los tres conceptos clave al final».

Este proceso muestra que la conversación puede mejorarse mediante instrucciones sucesivas.

## 10. Consideraciones de seguridad y privacidad

La interacción con un chatbot también implica consideraciones de seguridad:

- No introducir credenciales, claves privadas ni información sensible sin autorización y controles adecuados.
- Revisar las condiciones de privacidad, retención y tratamiento de datos del proveedor.
- Tener presente que los archivos adjuntos pueden contener información confidencial o metadatos.
- No asumir que el historial visible equivale a almacenamiento permanente o que se conserva de la misma manera en todos los productos.
- Verificar los resultados antes de utilizarlos en decisiones técnicas, financieras, legales o de seguridad.
- Considerar que las herramientas conectadas pueden ampliar la superficie de riesgo y deben configurarse con permisos mínimos.

## 11. Glosario técnico

| Término | Significado |
|---|---|
| Chatbot | Aplicación que permite interactuar mediante una conversación. |
| LLM (Large Language Model) | Modelo de lenguaje de gran tamaño. |
| UI (User Interface) | Interfaz de usuario. |
| Backend | Componente del servidor que procesa y coordina solicitudes. |
| Prompt | Instrucción o entrada enviada al modelo. |
| Context | Información disponible para orientar la generación. |
| Token | Unidad utilizada para representar el texto procesado por el modelo. |
| Tokenization | Proceso de convertir una entrada en tokens. |
| Context Window | Límite de tokens que el modelo puede considerar en una ejecución. |
| Transformer | Arquitectura de red neuronal utilizada por muchos LLM modernos. |
| API (Application Programming Interface) | Interfaz que permite la comunicación entre aplicaciones o servicios. |

## Ideas clave

- Un chatbot es una aplicación; un LLM es uno de los componentes que puede utilizar.
- La interfaz, el backend y el modelo cumplen funciones diferentes.
- Las instrucciones orientan la tarea y el contexto aporta información para resolverla.
- El modelo procesa tokens y genera la respuesta de manera sucesiva.
- El historial disponible y la ventana de contexto tienen límites.
- Las herramientas externas solo están disponibles cuando la aplicación las integra y autoriza.
- Toda respuesta debe evaluarse antes de utilizarse como información fiable.

> **Nota didáctica:** este documento desarrolla en español los temas del temario compartido. Es material explicativo y no una transcripción literal ni una publicación oficial de Cisco.

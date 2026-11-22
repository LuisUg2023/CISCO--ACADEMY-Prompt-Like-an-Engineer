# 1.2.2. Cómo integrar la IA en tu flujo de trabajo (How AI Can Fit in Your Workflow)

## Objetivo de aprendizaje

Comprender cómo incorporar herramientas de inteligencia artificial en tareas personales y profesionales, seleccionando el tipo de recurso adecuado para cada actividad y manteniendo la supervisión humana durante todo el proceso.

> **Nota de alcance:** Este documento organiza en español los conceptos de la lección y añade explicaciones didácticas para facilitar su estudio. No es una transcripción literal ni debe interpretarse como una publicación oficial de Cisco.

## 1. La IA como parte de un equipo de trabajo

Una forma práctica de entender la integración de la inteligencia artificial consiste en imaginar que dirigimos un equipo formado por diferentes trabajadores y herramientas. Cada integrante tiene capacidades, limitaciones y responsabilidades distintas.

El usuario actúa como director del equipo: define el objetivo, distribuye las tareas, proporciona el contexto, revisa los resultados y toma las decisiones finales. La IA puede acelerar determinadas actividades, pero no sustituye automáticamente el criterio humano ni asume la responsabilidad por el resultado.

La pregunta importante no es simplemente «¿puedo utilizar IA?», sino:

- ¿Qué tarea necesito resolver?
- ¿Qué herramienta está mejor preparada para realizarla?
- ¿Qué información necesita recibir?
- ¿Qué riesgos implica compartir esa información?
- ¿Cómo comprobaré que el resultado es correcto y útil?

## 2. El papel de las personas

Las personas aportan capacidades que siguen siendo esenciales en un flujo de trabajo asistido por IA:

- **Juicio profesional:** interpretar los resultados considerando el contexto real.
- **Conocimiento del dominio:** reconocer requisitos, excepciones y restricciones propias de una actividad.
- **Retroalimentación crítica:** indicar qué está mal, qué falta y qué debe cambiar.
- **Sanity checks:** realizar comprobaciones razonables para detectar errores evidentes o resultados incoherentes.
- **Pushback:** plantear contrapuntos, cuestionar supuestos y expresar desacuerdo constructivo cuando una propuesta no es adecuada.
- **Responsabilidad:** aprobar las decisiones y asumir la responsabilidad por las acciones realizadas.

La supervisión humana no debe limitarse a aceptar o rechazar la respuesta final. También puede intervenir al definir el problema, dividir el trabajo, revisar los pasos intermedios y validar el resultado.

## 3. Software tradicional: operaciones deterministas

El software tradicional es apropiado cuando una tarea tiene reglas definidas y se espera un comportamiento predecible.

Una operación determinista produce el mismo resultado cuando recibe las mismas entradas y se ejecuta bajo las mismas condiciones. Por ejemplo, una fórmula de cálculo, una validación de campos o una consulta estructurada de una base de datos.

**Ventajas:**

- Resultados consistentes y reproducibles.
- Mayor control sobre las reglas que se ejecutan.
- Adecuado para cálculos, validaciones y procesos repetitivos.
- Generalmente requiere menos recursos computacionales que ejecutar un modelo de lenguaje grande.

**Limitaciones:**

- Necesita reglas explícitas y mantenimiento cuando cambian los requisitos.
- Puede ser rígido frente a entradas ambiguas o situaciones no contempladas.
- Las tareas que requieren interpretar lenguaje natural o generar alternativas pueden exigir trabajo adicional.

**Ejemplo:** para calcular el total de una factura, aplicar impuestos según reglas configuradas o verificar que un identificador cumpla un formato, normalmente conviene utilizar código tradicional y no pedir a un LLM que realice el cálculo sin controles.

## 4. LLM alojado en la nube (Cloud-hosted LLM)

Un LLM alojado en la nube se ejecuta en la infraestructura de un proveedor y se utiliza mediante una aplicación, una interfaz web o una API.

Puede resultar útil para:

- Generar ideas y alternativas (*brainstorming*).
- Elaborar borradores y resumir documentos.
- Explicar conceptos y transformar información.
- Crear prototipos (*prototyping*).
- Interpretar instrucciones en lenguaje natural.
- Ayudar a organizar tareas que todavía no tienen un procedimiento completamente definido.

**Ventajas:**

- Acceso a modelos que pueden requerir una infraestructura considerable.
- No es necesario instalar ni mantener localmente todo el entorno de ejecución.
- Puede facilitar el trabajo desde diferentes dispositivos y ubicaciones.
- Es útil para tareas de lenguaje, análisis y generación de contenido.

**Aspectos que deben evaluarse:**

- Privacidad y confidencialidad de la información.
- Políticas de tratamiento, conservación y uso de datos del proveedor.
- Condiciones del plan, límites de uso y disponibilidad del servicio.
- Requisitos legales, contractuales y organizacionales.

No debe suponerse que todos los proveedores utilizan los datos de la misma manera. La retención de conversaciones y su posible utilización para mejorar modelos dependen del proveedor, del producto, del plan y de la configuración aplicable. Antes de compartir información sensible, hay que revisar las condiciones vigentes y las políticas de la organización.

## 5. LLM local (Local LLM)

Un LLM local se ejecuta en un computador o servidor bajo el control del usuario o de su organización, en lugar de enviar necesariamente las solicitudes a un servicio externo.

Puede ser conveniente cuando:

- Se necesita trabajar con información confidencial.
- Se requiere mantener los datos dentro de una infraestructura controlada.
- Se desea reducir la dependencia de un proveedor externo.
- Se necesita operar sin conexión a Internet, siempre que el modelo y sus dependencias ya estén instalados.
- Se quiere experimentar con modelos y configuraciones propias.

**Ventajas:**

- Mayor control sobre dónde se procesan los datos.
- Posibilidad de trabajar sin enviar cada solicitud a un servicio en la nube.
- Control sobre el modelo, su configuración y el entorno de ejecución.
- No depende de los límites diarios de una plataforma externa, aunque sí de los recursos locales y de las licencias aplicables.

**Limitaciones:**

- El equipo debe disponer de memoria RAM, almacenamiento y capacidad de procesamiento suficientes.
- Los modelos comprimidos o cuantizados pueden reducir los requisitos de hardware, pero también pueden afectar la calidad en determinadas tareas.
- En un computador convencional, algunos modelos pueden responder más lentamente.
- La instalación, actualización, seguridad y mantenimiento quedan bajo responsabilidad del usuario o administrador.

Ejecutar un modelo local no garantiza por sí solo la confidencialidad. También deben protegerse el equipo, los archivos, los registros, las copias de seguridad y las conexiones utilizadas.

## 6. Elegir la herramienta según la tarea

No existe una única herramienta que sea la mejor para todas las actividades. La selección depende de la naturaleza de la tarea, la sensibilidad de los datos, los recursos disponibles y el nivel de precisión requerido.

| Tipo de recurso | Conviene utilizarlo cuando | Consideración principal |
|---|---|---|
| Persona | Se necesita criterio, contexto, aprobación o responsabilidad | Requiere tiempo y conocimiento |
| Software tradicional | Hay reglas claras, cálculos o validaciones repetibles | Debe definirse y mantenerse la lógica |
| LLM en la nube | Se requiere generación, análisis de lenguaje o ideación con modelos remotos | Revisar privacidad, políticas y límites |
| LLM local | Se necesita procesar información en infraestructura propia | Revisar hardware, rendimiento y mantenimiento |

En muchos casos, la solución más eficaz es híbrida: combinar personas, software tradicional, modelos locales y modelos en la nube.

## 7. Dividir el trabajo en subtareas

Una tarea compleja suele ser más fácil de resolver cuando se divide en actividades pequeñas y verificables. Esta práctica permite asignar cada subtarea al recurso que mejor puede ejecutarla.

Un flujo de trabajo recomendado es:

1. **Definir el resultado esperado.** Describir qué se necesita producir y cuáles son los criterios de aceptación.
2. **Descomponer la actividad.** Separar el trabajo en subtareas concretas.
3. **Clasificar cada subtarea.** Determinar si requiere juicio humano, reglas deterministas, generación con IA o una combinación.
4. **Seleccionar la herramienta.** Considerar precisión, privacidad, costo, velocidad y recursos.
5. **Preparar los datos.** Entregar únicamente la información necesaria y retirar datos sensibles cuando corresponda.
6. **Ejecutar y revisar.** Comprobar los resultados de cada etapa antes de utilizarlos en la siguiente.
7. **Integrar los resultados.** Unir las partes y verificar que sean coherentes con el objetivo inicial.
8. **Aprobar el resultado.** La persona responsable toma la decisión final.

La división en subtareas también reduce el riesgo de entregar a un modelo una instrucción demasiado amplia, ambigua o difícil de verificar.

## 8. Ejemplo práctico: búsqueda de empleo y adaptación del CV

Supongamos que una persona quiere buscar empleo y adaptar su currículum a una vacante. El proceso puede involucrar información personal, experiencia profesional, requisitos del puesto y documentos que deben revisarse cuidadosamente.

Un flujo híbrido podría ser el siguiente:

**Etapa 1. Organizar información privada**

La persona reúne notas sobre su experiencia, logros, aspiraciones y circunstancias personales. Si esa información es confidencial, puede utilizar un LLM local para organizarla, siempre que el equipo y el entorno estén adecuadamente protegidos.

**Etapa 2. Preparar información para el análisis**

Se seleccionan los datos estrictamente necesarios para adaptar el CV. Antes de utilizar un servicio en la nube, se eliminan o sustituyen datos personales que no sean necesarios, como números de identificación, dirección particular o información privada.

**Etapa 3. Adaptar el currículum**

Un LLM en la nube puede ayudar a comparar los requisitos de la vacante con la experiencia profesional y proponer mejoras en la redacción, el orden de las competencias y la presentación de logros.

La herramienta debe trabajar con información real. No se deben inventar cargos, certificaciones, fechas, resultados ni habilidades para hacer que el perfil parezca más atractivo.

**Etapa 4. Revisión humana**

La persona revisa cada modificación y puede pedir a un compañero que realice una segunda lectura. Esa revisión permite detectar errores, afirmaciones exageradas, omisiones o información que no representa correctamente la experiencia.

**Etapa 5. Decisión final**

La persona decide qué cambios acepta y envía el documento únicamente cuando está conforme con su contenido.

Este ejemplo muestra que diferentes recursos pueden participar en un mismo proceso sin que uno tenga que reemplazar a los demás.

## 9. Buenas prácticas para integrar IA

- Empezar por el problema y no por la herramienta.
- Utilizar software tradicional para operaciones que necesitan reglas exactas y resultados reproducibles.
- Reservar los LLM para tareas en las que aporten valor, especialmente lenguaje, generación y exploración de alternativas.
- No compartir información confidencial sin comprobar las políticas y autorizaciones correspondientes.
- Dividir los procesos complejos en subtareas.
- Dar instrucciones claras y proporcionar contexto suficiente.
- Comprobar datos, cálculos, referencias y afirmaciones importantes.
- Mantener trazabilidad de las modificaciones cuando el proceso lo requiera.
- Conservar la supervisión humana en decisiones relevantes.
- Medir si la incorporación de IA mejora realmente la calidad, el tiempo o el costo del proceso.

## 10. Glosario de términos

| Término en inglés | Equivalente en español | Significado en este contexto |
|---|---|---|
| Workflow | Flujo de trabajo | Secuencia organizada de actividades para alcanzar un resultado |
| Pushback | Contrapunto o desacuerdo constructivo | Cuestionamiento razonado de una propuesta o supuesto |
| Deterministic behavior | Comportamiento determinista | Mismas entradas y condiciones producen el mismo resultado |
| Cloud-hosted LLM | LLM alojado en la nube | Modelo ejecutado en infraestructura de un proveedor |
| Local LLM | LLM local | Modelo ejecutado en un equipo o servidor controlado localmente |
| Brainstorming | Lluvia de ideas | Generación y exploración de alternativas |
| Prototyping | Creación de prototipos | Elaboración de una versión inicial para probar una idea |
| Data privacy | Privacidad de los datos | Protección y control sobre el tratamiento de la información |
| Computing power | Capacidad de cómputo | Recursos disponibles para procesar operaciones |
| Sanity check | Comprobación de coherencia | Revisión rápida para detectar errores evidentes |
| Brittle | Frágil o poco flexible | Sistema que falla fácilmente ante cambios o casos no previstos |

## 11. Ideas clave

1. La IA debe integrarse como un recurso dentro de un flujo de trabajo, no como sustituto automático de las personas.
2. Las personas aportan contexto, juicio, revisión crítica y responsabilidad.
3. El software tradicional es adecuado para operaciones deterministas y reglas explícitas.
4. Los LLM en la nube ofrecen capacidades de generación y análisis, pero requieren evaluar privacidad y condiciones del proveedor.
5. Los LLM locales ofrecen control sobre el entorno de ejecución, a cambio de requerir hardware y mantenimiento.
6. Dividir una tarea compleja en subtareas permite asignar cada actividad a la herramienta más apropiada.
7. La decisión y aprobación final deben permanecer en manos de la persona responsable.

---

**Fin de la lección 1.2.2.**

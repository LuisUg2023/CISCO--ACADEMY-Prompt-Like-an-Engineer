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


# 12. Laboratorio práctico: trabajar con múltiples LLM en la nube

<badge>Práctica guiada</badge>

## 12.1. Objetivo del laboratorio

Utilizar tres modelos de lenguaje alojados en la nube (*Cloud LLM*) para resolver una misma tarea, comparar sus resultados, identificar diferencias y limitaciones, aplicar evaluación cruzada y elaborar una respuesta final supervisada por una persona.

Al finalizar, el estudiante podrá:

- Ejecutar el mismo prompt en diferentes plataformas de IA.
- Mantener constantes las instrucciones para que la comparación sea más justa.
- Evaluar precisión, cobertura, claridad, razonamiento verificable y cumplimiento del formato.
- Identificar afirmaciones no sustentadas y posibles alucinaciones.
- Utilizar un modelo para revisar la respuesta de otro sin delegar la decisión final.
- Combinar los resultados útiles en una entrega final.

## 12.2. Escenario

Una organización desea realizar una primera revisión de un conjunto pequeño de registros de autenticación y actividad de archivos. El objetivo es preparar un resumen preliminar para el equipo de soporte y seguridad.

Los registros siguientes son **datos sintéticos creados exclusivamente para esta práctica**. No representan un incidente real.

| Hora | Evento | Usuario | Dirección IP de origen | Detalle |
|---|---|---|---|---|
| 09:02 | Inicio de sesión fallido (5 intentos) | analista1 | 203.0.113.24 | Credenciales rechazadas |
| 09:05 | Inicio de sesión exitoso | analista1 | 203.0.113.24 | Autenticación aceptada |
| 09:07 | Acceso a archivo | analista1 | 203.0.113.24 | inventario.csv |
| 09:08 | Acceso a archivo | analista1 | 203.0.113.24 | usuarios.csv |
| 09:10 | Cierre de sesión | analista1 | 203.0.113.24 | Sesión finalizada |

**Limitación importante:** estos registros no indican si la dirección IP pertenece a una persona autorizada, si el dispositivo es conocido, si los archivos fueron descargados, si el acceso estaba permitido o si hubo exposición de información. Los modelos deben reconocer estas incertidumbres y no inventar conclusiones.

## 12.3. Herramientas necesarias

Utiliza tres servicios de LLM Cloud a los que tengas acceso mediante navegador. Como ejemplos puedes seleccionar:

- ChatGPT.
- Google Gemini.
- Anthropic Claude.
- Microsoft Copilot, como alternativa si alguno de los anteriores no está disponible.

No es obligatorio utilizar exactamente esas tres plataformas. Registra el nombre del servicio y, si la interfaz lo muestra, el modelo seleccionado. Los nombres y versiones disponibles pueden cambiar.

**Requisitos:**

- Navegador web y conexión a Internet.
- Acceso a tres servicios de IA en la nube.
- Un documento o una hoja de cálculo para registrar los resultados.
- Los datos sintéticos incluidos en esta práctica.

No se requiere instalar software, escribir código ni configurar claves API. Si una plataforma no está disponible, utiliza otra y anota el cambio.

## 12.4. Reglas de ejecución

Para que la comparación sea razonable:

1. Utiliza el mismo texto de prompt y los mismos registros en los tres servicios.
2. Inicia una conversación nueva en cada plataforma para evitar que el historial anterior altere el contexto.
3. No añadas instrucciones adicionales a un solo modelo durante la primera ronda.
4. Conserva las respuestas completas.
5. Registra el nombre del servicio y el modelo visible.
6. No introduzcas información personal, credenciales, registros reales ni datos confidenciales.
7. No interpretes la respuesta de un LLM como evidencia de que ocurrió un incidente.

## 12.5. Fase 1: ejecutar el mismo prompt en tres modelos

Abre el primer servicio de IA, inicia una conversación nueva y pega el siguiente prompt. Repite exactamente el mismo procedimiento en los otros dos servicios.

### Prompt principal

```text
Actúa como analista de seguridad informática de nivel inicial.
Debes realizar una revisión preliminar de los siguientes registros
sintéticos de autenticación y acceso a archivos.

REGISTROS:
09:02 - 5 intentos fallidos de inicio de sesión.
Usuario: analista1.
IP de origen: 203.0.113.24.

09:05 - Inicio de sesión exitoso.
Usuario: analista1.
IP de origen: 203.0.113.24.

09:07 - Acceso al archivo inventario.csv.
Usuario: analista1.
IP de origen: 203.0.113.24.

09:08 - Acceso al archivo usuarios.csv.
Usuario: analista1.
IP de origen: 203.0.113.24.

09:10 - Cierre de sesión.
Usuario: analista1.
IP de origen: 203.0.113.24.

TAREA:
Prepara un análisis preliminar para un equipo de soporte y seguridad.

FORMATO OBLIGATORIO:
1. Resumen ejecutivo de máximo 100 palabras.
2. Línea de tiempo de los eventos.
3. Indicadores que merecen revisión.
4. Hechos observados directamente en los registros.
5. Hipótesis posibles, claramente identificadas como hipótesis.
6. Información adicional necesaria para confirmar o descartar las hipótesis.
7. Cinco acciones recomendadas, ordenadas por prioridad.

RESTRICCIONES:
- No inventes eventos, usuarios, ubicaciones ni evidencias.
- No afirmes que hubo una intrusión o una filtración de datos sin pruebas.
- No supongas que acceder a un archivo significa descargarlo.
- Diferencia los hechos de las hipótesis.
- Si la información no permite llegar a una conclusión, indícalo.
- Utiliza lenguaje técnico claro y comprensible.
- Respeta exactamente los apartados solicitados.
```

Guarda las tres respuestas como **Respuesta A**, **Respuesta B** y **Respuesta C**. No selecciones todavía una ganadora.

## 12.6. Fase 2: comparación de resultados

Compara las respuestas utilizando esta matriz. Asigna una puntuación de 1 a 5 en cada criterio:

| Criterio | 1 punto | 3 puntos | 5 puntos |
|---|---|---|---|
| Fidelidad a los registros | Inventa o altera datos | Presenta alguna imprecisión | Respeta todos los registros |
| Separación entre hechos e hipótesis | Los mezcla | Los separa parcialmente | Los distingue claramente |
| Reconocimiento de incertidumbre | Afirma conclusiones sin evidencia | Reconoce algunas limitaciones | Expone claramente lo que no se sabe |
| Recomendaciones | Son vagas o desproporcionadas | Son parcialmente útiles | Son concretas, proporcionadas y priorizadas |
| Cumplimiento del formato | Omite varios apartados | Cumple parcialmente | Incluye todos los apartados |
| Claridad técnica | Es confusa | Es comprensible con ajustes | Es clara y precisa |

**Puntuación máxima:** 30 puntos por respuesta.

La puntuación no debe asignarse por el estilo más convincente o por la longitud de la respuesta. Debe basarse en el cumplimiento de los criterios y en la evidencia disponible.

## 12.7. Fase 3: evaluación cruzada entre modelos

Ahora utiliza los modelos para revisar respuestas producidas por otros servicios.

En el segundo modelo, pega la Respuesta A junto con este prompt:

```text
Actúa como revisor independiente de un análisis de seguridad.
Evalúa la respuesta que aparece a continuación utilizando
exclusivamente los registros originales de esta práctica.

Comprueba:
1. Si se inventaron datos o eventos.
2. Si se confundieron hechos con hipótesis.
3. Si se afirmaron intrusiones, descargas o filtraciones sin evidencia.
4. Si se identificaron las limitaciones de los registros.
5. Si las acciones recomendadas son proporcionadas.

Devuelve una tabla con las columnas:
- Observación.
- Fragmento o afirmación revisada.
- Problema detectado.
- Justificación.
- Corrección recomendada.

No reescribas todo el análisis.
No inventes evidencia.
Si no encuentras un error, indícalo expresamente.

RESPUESTA QUE DEBES REVISAR:
[PEGAR AQUÍ LA RESPUESTA A]
```

Repite el procedimiento con las otras respuestas, procurando que cada una sea revisada por un servicio diferente del que la generó. Por ejemplo:

| Respuesta original | Modelo que la generó | Modelo revisor |
|---|---|---|
| A | ChatGPT | Gemini |
| B | Gemini | Claude |
| C | Claude | ChatGPT |

Si utilizas otros servicios, conserva la regla: el revisor no debe ser el mismo modelo que produjo la respuesta evaluada, siempre que sea posible.

La evaluación cruzada sirve para encontrar errores y diferencias, pero tampoco garantiza que el revisor tenga razón. Comprueba cada observación contra los registros originales.

## 12.8. Fase 4: mejorar una respuesta mediante retroalimentación

Selecciona la respuesta que haya obtenido la mejor puntuación inicial. Incorpora únicamente las correcciones que puedas justificar con los datos.

Envía al modelo que produjo esa respuesta el siguiente prompt:

```text
Debes revisar tu análisis anterior utilizando la siguiente
retroalimentación de un revisor independiente.

RETROALIMENTACIÓN:
[PEGAR AQUÍ LAS OBSERVACIONES QUE HAYAS VERIFICADO]

INSTRUCCIONES:
- Corrige los errores confirmados.
- Conserva las afirmaciones que sí estén sustentadas.
- No incorpores observaciones que contradigan los registros.
- Mantén separados los hechos, las hipótesis y los datos faltantes.
- No afirmes que hubo intrusión, descarga o filtración sin evidencia.
- Conserva los siete apartados del formato original.

Entrega una versión revisada y una lista breve de los cambios realizados.
```

Compara la versión inicial y la revisada. Comprueba si las modificaciones realmente mejoraron la calidad o si introdujeron nuevos errores.

## 12.9. Fase 5: construir una respuesta final

Como responsable del ejercicio, integra los elementos más sólidos de las respuestas y de las revisiones. Puedes utilizar un cuarto modelo o cualquiera de los tres servicios para preparar un borrador de síntesis.

Prompt de síntesis:

```text
Actúa como asistente de redacción técnica.
A continuación recibirás tres análisis y sus observaciones de revisión.

Tu tarea es preparar un único informe preliminar que:
- Utilice solamente hechos presentes en los registros.
- Distinga hechos, hipótesis y aspectos pendientes de verificar.
- Elimine afirmaciones no sustentadas.
- Incluya recomendaciones proporcionales.
- Mantenga una estructura clara para el equipo de soporte y seguridad.

No decidas cuál modelo tiene razón por su reputación o estilo.
No inventes datos para completar vacíos.
Si existen diferencias no resueltas, señálalas.

ANÁLISIS A:
[PEGAR RESPUESTA A]

ANÁLISIS B:
[PEGAR RESPUESTA B]

ANÁLISIS C:
[PEGAR RESPUESTA C]

OBSERVACIONES VERIFICADAS:
[PEGAR LAS OBSERVACIONES CONFIRMADAS]
```

La síntesis generada es un borrador. La persona que realiza el laboratorio debe revisar el informe final y decidir qué afirmaciones acepta.

## 12.10. Registro de resultados

Completa la siguiente tabla durante la práctica:

| Campo | Modelo A | Modelo B | Modelo C |
|---|---|---|---|
| Plataforma utilizada | | | |
| Nombre del modelo visible | | | |
| ¿Cumplió el formato? | | | |
| ¿Inventó algún dato? | | | |
| ¿Separó hechos e hipótesis? | | | |
| ¿Reconoció limitaciones? | | | |
| Puntuación sobre 30 | | | |
| Principal fortaleza | | | |
| Principal debilidad | | | |

Registra también:

- ¿Qué respuesta fue más fiel a los registros?
- ¿Qué modelo identificó mejor la información faltante?
- ¿Qué errores detectó la evaluación cruzada?
- ¿Qué correcciones mejoraron el resultado?
- ¿Hubo alguna recomendación que parecía convincente, pero no estaba sustentada?
- ¿Qué partes del informe final tuviste que corregir manualmente?

## 12.11. Criterios de evaluación del laboratorio

| Actividad | Puntaje |
|---|---:|
| Ejecución del mismo prompt en tres LLM Cloud | 15 |
| Conservación y registro de las respuestas | 10 |
| Comparación con la matriz de evaluación | 20 |
| Evaluación cruzada entre modelos | 20 |
| Revisión y mejora mediante retroalimentación | 15 |
| Informe final y reflexión personal | 20 |
| **Total** | **100** |

## 12.12. Resultado esperado

Al terminar, el estudiante tendrá:

1. Tres respuestas obtenidas de distintos LLM Cloud.
2. Una matriz comparativa con puntuaciones justificadas.
3. Observaciones de evaluación cruzada.
4. Una versión revisada de uno de los análisis.
5. Un informe final integrado y revisado por una persona.
6. Una conclusión sobre las fortalezas y limitaciones observadas en cada servicio.

## 12.13. Conclusión del laboratorio

Utilizar múltiples LLM Cloud no significa enviar una pregunta a varios modelos y elegir automáticamente la respuesta más extensa o popular. El valor está en comparar resultados bajo condiciones similares, detectar errores, solicitar revisiones independientes y combinar las contribuciones que puedan justificarse.

Cada modelo puede aportar una perspectiva diferente, pero también puede equivocarse. La evaluación cruzada reduce algunos riesgos, no los elimina. La verificación contra los datos originales y la aprobación humana siguen siendo indispensables.

**Principio fundamental:** los modelos generan y revisan propuestas; la persona verifica la evidencia y toma la decisión final.

---

**Fin del laboratorio práctico de múltiples LLM Cloud.**

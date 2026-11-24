# U3 · Especificación de requisitos — Riego Sin Regarla

**Equipo:** Los umisumi
**Proyecto:** Riego Sin Regarla
**Versión:** 0.1  
**Fecha:** 17/11/2026  
**Estado del documento:** En elaboración  
**Unidad:** 3 · Ingeniería de Requisitos  
**Materia:** Fundamentos de Ingeniería de Software (SCC-1007)

**Integrantes:**

- Lozano Andrade Cristian Emmanuel --- Calidad y Documentación
- Lopez Medina Genesis Marisol -------- Desarrollo y coordinación
- Bermejo Rodriguez Ana Cristina -------- Analisis

---

## A. Identificación y alcance

### A.1 Identificación del proyecto

### A.2 Proceso TO-BE seleccionado

**Proceso:** Supervisar condiciones de agua en zona nogalera

Para determinar si recibió el riego necesario, considerando el nivel del agua, el tiempo y las características del terreno. Cuando se identifiquen las condiciones para considerar un cambio de flujo, el sistema notificará al productor para que revise la situación y autorice el cambio hacia otra zona.

### A.3 Objetivo de esta especificación

Definir los requisitos de un sistema que apoye el control del riego por inundación en una nogalera mediante la supervisión de las condiciones del agua y la notificación al productor cuando se identifique que una zona recibió el riego necesario.

Se contempla el uso de sensores para obtener información sobre el nivel del agua. También se considera que el tiempo de riego y las condiciones del terreno pueden influir en la cantidad de agua necesaria para cada zona.

De acuerdo con lo expresado por el productor en la segunda entrevista, el sistema deberá informarle cuando se considere necesario cambiar el flujo, pero no deberá realizar ese cambio sin su autorización.

### A.4 Alcance

**Dentro del alcance:**

- Obtener información del nivel del agua mediante sensores.
- Considerar el tiempo de riego y las condiciones del terreno para evaluar si una zona recibió suficiente agua.
- Supervisar el avance del agua mientras no se hayan alcanzado las condiciones necesarias
- Identificar cuándo existen condiciones para considerar un cambio de flujo
- Notificar al productor cuando se identifiquen esas condiciones
- Esperar la autorización del productor antes de realizar un cambio de flujo
- Contemplar una respuesta ante lecturas incorrectas de los sensores. El procedimiento técnico deberá definirse durante el diseño del sistema

**Fuera del alcance:**

- Administrar la distribución del agua del distrito de riego
- Elaborar un calendario completo de riego para la nogalera
- Automatizar todas las actividades agrícolas
- Controlar procesos que no estén relacionados con la supervisión de nivel y el cambio de flujo entre las zonas seleccionadas
- Sustituir por completo la supervisión y las decisiones del encargado
- Realizar cambios de flujo sin que el productor los autorice

### A.5 Indicador de mejora

La mejora se evaluará mediante la diferencia entre el tiempo de espera estimado que muestra XALTIL y el tiempo real que espera el paciente en el centro de salud.

**Estado del alcance:** Definido inicialmente con base en el documento U2-E01. Pendiente de validación con los stakeholders.

---

## B. Fuentes y necesidades

Las necesidades documentadas se obtuvieron inicialmente del análisis del negocio realizado en la Unidad 2. Todavía es necesario contrastarlas con usuarios y representantes de los centros de salud.

### B.1 Registro de fuentes

| ID | Técnica o documento | Fecha | Hallazgo o necesidad | Estado | Enlace o referencia |
| --- | --- | --- | --- | --- | --- |
| F-01 | Entrevista al productor César Ramírez Grimaldo | 03/09/2026 | El productor explicó el proceso de riego por inundación, la observación del avance del agua y la operación de compuertas para dirigir el flujo hacia diferentes zonas. | Entrevista realizada. Los criterios para determinar que una zona recibió suficiente agua se aclararon posteriormente en F-02 | Por registrar |
| F-02 | Segunda entrevista de seguimiento al productor César Ramírez Grimaldo | 15/11/2026 | Se aclaró que para determinar si una zona recibió suficiente agua se consideran el nivel alcanzado y el tiempo de riego; que la cantidad necesaria puede variar por las condiciones del terreno; que el orden de las zonas puede cambiar; que existen interrupciones por daños en acequias o bordos; y que el productor desea recibir una notificación y autorizar los cambios de flujo. También solicitó contar con un historial de las zonas regadas y los cambios realizados. | Entrevista realizada. Algunos aspectos técnicos siguen pendientes de análisis. | Por registrar |
| F-03 | Análisis del proceso y propuesta TO-BE del equipo en U2 | 27/10/2026 | El equipo propuso utilizar sensores para supervisar el nivel del agua y mecanismos físicos para apoyar la operación de las compuertas. También propuso contemplar una respuesta cuando no se pueda confirmar una lectura valida | Propuesta del equipo que debe revisarse a partir de las respuestas del productor y del análisis técnico. | Por registrar |

### B.2 Necesidades identificadas

| ID | Necesidad identificada | Fuente relacionada | Estado |
|---|---|---|---|---|
| N-01 | Conocer el nivel del agua en la zona que está recibiendo el riego. | F-01, F-02 | Identificada. |
| N-02 | Determinar si una zona recibió suficiente agua considerando el nivel alcanzado y el tiempo de riego. | F-02 | Confirmada por el productor. Los valores específicos están pendientes. |
| N-03 | Considerar las diferencias y desniveles del terreno al determinar la cantidad de agua necesaria. | F-02 | Confirmada por el productor |
| N-04 | Permitir flexibilidad en el orden de atención de las zonas de riego. | F-02 | Confirmada por el productor. |
| N-05 | Considerar las interrupciones ocasionadas por derrumbes o daños en acequias y bordos. | F-02 | Confirmada. Su tratamiento en el sistema está pendiente de análisis. |
| N-06 | Notificar al productor cuando existan condiciones para considerar un cambio de flujo y permitirle autorizarlo. | F-02 | Confirmada como preferencia del productor. |
| N-07 | Contemplar una respuesta cuando el sensor no pueda determinar correctamente el nivel del agua. | F-02 | El productor indicó que debería reiniciarse. El procedimiento técnico está pendiente. |
| N-08 | Contar con un historial de las zonas regadas y los cambios de flujo realizados, incluyendo fecha y hora. | F-02 | Necesidad expresada por el productor. |
| N-09 | Mejorar el control del agua para evitar desperdicios durante el riego. | F-02 | Confirmada como mejora esperada por el productor. |

### B.3 Preguntas pendientes de aclarar

- ¿Qué valores o referencias se utilizarán para determinar el nivel de agua necesario en cada zona?
- ¿En qué lugar de cada zona sería conveniente colocar los sensores para obtener una lectura representativa?
- ¿Qué condiciones técnicas pueden provocar que una lectura del sensor sea incorrecta o no confiable?
- ¿Cómo se comprobará que el sensor volvió a proporcionar lecturas correctas después del procedimiento de reinicio?
- ¿Qué compuertas intervienen exactamente en cada cambio de flujo y cómo se relacionan las zonas que reciben el agua?
- ¿Qué mecanismos físicos serían adecuados para operar las compuertas, considerando que el productor desea autorizar los cambios?

### B.4 Información pendiente de validar

| ID | Información pendiente | Acción para atenderla | Estado |
| ---- | ---- | ---- | ---- |
| P-01 | Definir los valores o referencias que permitirán determinar cuándo una zona recibió suficiente agua. | Analizar cómo se establecerán los valores de referencia para cada zona. | Pendiente |
| P-02 | Determinar cómo se considerarán las diferencias del terreno al evaluar las condiciones de riego. | Revisar cómo se representarán las características de cada zona dentro del sistema. | Pendiente |
| P-03 | Definir la ubicación adecuada de los sensores para obtener lecturas representativas del nivel del agua. | Investigar las condiciones de instalación y ubicación de los sensores. | Pendiente |
| P-04 | Establecer cómo se identificarán las lecturas incorrectas o no confiables. | Investigar las posibles causas de error y los criterios técnicos para detectar lecturas no válidas. | Pendiente |
| P-05 | Definir el procedimiento técnico de reinicio del sensor y cómo comprobar que sus lecturas vuelven a ser confiables. | Analizar alternativas de recuperación y validación de lecturas. | Pendiente |
| P-06 | Identificar las compuertas que intervienen en cada cambio de flujo y revisar la viabilidad de operarlas mediante mecanismos físicos. | Revisar el funcionamiento de las compuertas y su relación con las zonas de riego. | Pendiente |
| P-07 | Determinar cómo se contemplarán las interrupciones ocasionadas por daños en acequias o bordos dentro del proceso propuesto. | Analizar cómo se representarán estas situaciones y qué intervención necesitará el encargado. | Pendiente |
| P-08 | Definir cómo se conservarán y consultarán los registros de las zonas regadas y los cambios de flujo. | Investigar alternativas de almacenamiento persistente y revisar cómo se podrá consultar el historial. | Pendiente |
| P-09 | Determinar si el historial necesita información adicional a la zona de origen, zona de destino, fecha y hora. | Revisar qué datos serían útiles para identificar y consultar cada cambio de flujo. | Pendiente |

---

## C. Organización del alcance de los requisitos

## C.1 Ruta seleccionada

**Ruta elegida:** B (sin épica).

## C.2 Justificación de la elección

Se eligió esta ruta porque el proyecto Riego sin regarla ya cuenta con un proceso específico identificado desde la Unidad 2. El trabajo se concentra en supervisar el avance del agua en una zona de la nogalera, determinar si recibió el riego necesario y notificar al productor para que pueda autorizar el cambio de flujo hacia otra zona.
Además, mediante la segunda entrevista se aclararon condiciones importantes del proceso, como considerar el nivel del agua y el tiempo de riego, tomar en cuenta las diferencias del terreno y permitir que el productor conserve la decisión de autorizar los cambios.
Por esta razón, no se considera necesario organizar el alcance mediante una épica y varias capacidades, debido a que el proceso que se busca atender ya está delimitado. La Ruta B permite relacionar directamente el objetivo del proyecto con las necesidades y los requisitos que deberá cumplir el sistema.

## C.3 Proceso delimitado

Proceso acotado: Supervisión de las condiciones del agua en una zona de la nogalera, determinación de si recibió el riego necesario y notificación al productor para que autorice el cambio de flujo hacia otra zona.

El proceso inicia cuando existe disponibilidad de agua y el encargado permite su entrada al área de riego. Continúa con la supervisión del nivel del agua, considerando el tiempo y las condiciones del terreno. Cuando se identifican las condiciones necesarias para considerar que la zona recibió suficiente agua, se notifica al productor para que decida si autoriza el cambio de flujo. El proceso finaliza cuando se atienden las zonas contempladas para el turno y se detiene el suministro.

Objetivo: Proponer un sistema que apoye la supervisión del riego mediante sensores, considerando el nivel del agua, el tiempo y las condiciones del terreno, y que notifique al productor cuando se identifiquen las condiciones para considerar un cambio de flujo, conservando su autorización antes de realizarlo.

Requisitos funcionales vinculados:

- RF-GENESIS-01 — Validación de lecturas del sensor.
- RF-CRISTIAN-01 — Evaluación de las condiciones de riego.
- RF-CRISTIAN-02 — Notificación y autorización del cambio de flujo.
- RF-ANA-01 — Registro de cambios de flujo.
- RF-GENESIS-02 — Registro de zonas regadas.

Requisito no funcional vinculado:

- RNF-ANA-02 — Conservación de registros.

---

## D. Reglas del dominio

Las reglas del dominio representan condiciones propias del proceso de riego que pueden influir en el comportamiento del sistema. Se identifican a partir de la información proporcionada por el productor en las entrevistas y del análisis realizado por el equipo.

| ID | Regla del contexto | Fuente | Quién establece la regla | Evidencia | Estado |
| ---- | ---- | ---- | ---- | ---- | ---- |
| RG-01 | Para determinar si una zona recibió suficiente agua se consideran el nivel alcanzado y el tiempo de riego. | F-02 | Productor/encargado, de acuerdo con su experiencia y práctica de trabajo. | Segunda entrevista del 15/11/2026. | Confirmada. Los valores específicos están pendientes de definir. |
| RG-02 | La cantidad de agua necesaria puede variar dependiendo de las condiciones y desniveles del terreno. | F-02 | Productor/encargado, con base en las características del terreno. | Segunda entrevista del 15/11/2026. | Confirmada. |
| RG-03 | El orden de atención de las zonas puede cambiar; lo importante es que cada una reciba la cantidad de agua necesaria. | F-02 | Productor/encargado. | Segunda entrevista del 15/11/2026. | Confirmada. |
| RG-04 | Pueden presentarse interrupciones en el riego debido a derrumbes o daños en las acequias y bordos, lo que puede requerir modificar temporalmente la dirección del agua para realizar reparaciones. | F-02 | Productor/encargado, de acuerdo con las condiciones que se presentan durante el riego. | Segunda entrevista del 15/11/2026. | Confirmada. Falta analizar cómo se contemplará esta situación en el proceso propuesto. |
| RG-05 | El productor debe recibir una notificación cuando se identifiquen las condiciones para considerar un cambio de flujo y conservar la decisión de autorizarlo. | F-02 | Productor/encargado. | Segunda entrevista del 15/11/2026. | Confirmada como preferencia del productor. |
| RG-06 | Cuando el sensor no pueda determinar correctamente el nivel del agua, debe contemplarse su reinicio antes de continuar utilizando sus lecturas. | F-02 | El productor expresó que el sensor debería reiniciarse; el equipo debe definir el procedimiento técnico. | Segunda entrevista del 15/11/2026. | Necesidad identificada. Procedimiento técnico pendiente de análisis. |

## D.2 Pendientes de validación

- Definir los valores o referencias que permitirán determinar cuándo una zona recibió suficiente agua
- Analizar cómo se considerarán las diferencias del terreno al evaluar las condiciones de riego
- Revisar técnicamente cómo se detectará una lectura incorrecta o no confiable
- Definir el procedimiento de reinicio del sensor y cómo se comprobará que volvió a proporcionar lecturas correctas
- Identificar las compuertas que intervienen en cada cambio de flujo y revisar la viabilidad de operarlas mediante mecanismos físicos
- Definir cómo se contemplarán las interrupciones por daños en acequias o bordos dentro del proceso propuesto

---

## E. Catálogo priorizado de requisitos

| Identificador | Nombre | Tipo | Responsable de la propuesta | Prioridad |
| ---- | ---- | ---- | ---- | ---- |
| RF-ANA-01 | Registro de cambios de flujo | RF | Ana Cristina Bermejo Rodríguez | P2-Media |
| RNF-ANA-02 | Conservación de registros | RNF | Ana Cristina Bermejo Rodríguez | P2-Media |
| RF-GENESIS-01 | Validación de lecturas del sensor | RF | Genesis Marisol Lopez Medina | P1-Alta |
| RF-GENESIS-02 | Registro de zonas regadas | RF | Genesis Marisol Lopez Medina | P2-Media |
| RF-CRISTIAN-01 | Evaluación de las condiciones de riego | RF | Cristian Emmanuel Lozano Andrade | P1-Alta |
| RF-CRISTIAN-02 | Notificación y autorización del cambio de flujo | RF | Cristian Emmanuel Lozano Andrade | P1-Alta |

### E.1 Requisitos funcionales y no funcionales

RF-ANA-01-Registro de cambios de flujo

Requisito verificable:
El sistema debe registrar cada cambio de flujo realizado entre zonas, indicando la zona de origen, la zona de destino y la fecha y hora en que se efectuó el cambio.

- Fuente: F-03, análisis del proceso y propuesta TO-BE del equipo en U2. F-02 confirma posteriormente la necesidad de contar con un historial de cambios.
- Prioridad: P2 – Media.
- Motivo: Permite consultar los cambios realizados y dar seguimiento al proceso de riego. Es útil para el control de las operaciones, aunque no interviene directamente en la evaluación del nivel del agua.
- Responsable: Ana Cristina Bermejo Rodríguez.
- Estado: Propuesto; pendiente de revisión por el equipo.

RNF-ANA-02—Conservación de registros
Requisito verificable:
El sistema debe conservar los registros de cambios de flujo para que permanezcan disponibles después de cerrar y volver a iniciar la aplicación.

- Fuente: Propuesta técnica individual de Ana, derivada de la necesidad de mantener un historial de los cambios de flujo identificada durante el análisis del proyecto.
- Prioridad: P2 – Media.
- Motivo: Permite mantener disponible la información de los cambios realizados para su consulta posterior. Complementa el registro de operaciones y evita que la información dependa únicamente de que la aplicación permanezca abierta.
- Responsable: Ana Cristina Bermejo Rodríguez.
- Estado: Propuesto; pendiente de revisión técnica.

RF-GENESIS-01—Validación de lecturas del sensor
Requisito verificable:
El sistema debe validar las lecturas recibidas del sensor antes de utilizarlas para evaluar las condiciones de riego. Cuando detecte una lectura no confiable, debe descartarla y notificar al encargado para que verifique la situación antes de continuar con la evaluación.

- Fuente: F-02, segunda entrevista al productor, y F-03, propuesta TO-BE del equipo en U2.
- Prioridad: P1 – Alta.
- Motivo: Evita que el sistema utilice información incorrecta para evaluar las condiciones de riego. Una lectura no confiable podría provocar una evaluación equivocada y afectar el control del agua.
- Responsable: Genesis Marisol Lopez Medina.
-Estado: Propuesto; pendiente de revisión por el equipo y definición de criterios técnicos de validación.

RF-GENESIS-02 — Registro de zonas regadas
Requisito verificable:
El sistema debe registrar las zonas de la nogalera que hayan sido confirmadas como regadas, incluyendo la identificación de la zona y la fecha y hora de su confirmación.

- Fuente: F-02, segunda entrevista al productor, en la que expresó la necesidad de contar con un historial de las zonas regadas.
- Prioridad: P2 – Media.
- Motivo: Permite llevar un seguimiento de las zonas que ya recibieron riego y consultar posteriormente cuándo fueron atendidas. Complementa el registro de cambios de flujo, porque registra la atención de cada zona y no solamente el movimiento del agua entre ellas.
- Responsable: Genesis Marisol Lopez Medina.
- Estado: Propuesto; pendiente de revisión por el equipo y validación con el productor.

RF-CRISTIAN-01 — Evaluación de las condiciones de riego
Requisito verificable:
El sistema debe evaluar las condiciones de riego de cada zona utilizando las lecturas válidas del nivel del agua, el tiempo de riego y los parámetros establecidos para considerar las características del terreno.

- Fuente: F-02, segunda entrevista al productor, y F-03, análisis del proceso y propuesta TO-BE del equipo en U2.
- Prioridad: P1 – Alta.
- Motivo: Es una función central del proyecto, porque permite apoyar la determinación de si una zona recibió suficiente agua. Considerar las condiciones del terreno evita utilizar un único criterio para todas las zonas.
- Responsable: Cristian Emmanuel Lozano Andrade.
- Estado: Propuesto; pendiente de revisión por el equipo y definición de los parámetros 
de evaluación.

RF-CRISTIAN-02 — Notificación y autorización del cambio de flujo
Requisito verificable:
Cuando el sistema identifique que una zona cumple las condiciones establecidas para considerar suficiente el riego, debe notificar al productor y esperar su autorización antes de iniciar el cambio de flujo hacia otra zona.

- Fuente: F-02, segunda entrevista al productor, y F-03, propuesta TO-BE del equipo en U2.
- Prioridad: P1 – Alta.
- Motivo: Permite mantener informado al productor y respetar su decisión sobre los cambios de flujo. El productor expresó que desea recibir notificaciones y conservar la autorización de las operaciones.
- Responsable: Cristian Emmanuel Lozano Andrade.
- Estado: Propuesto; pendiente de revisión por el equipo y validación de la forma de autorización.

### E.2 Justificación de prioridades

P1–Alta

- RF-GENESIS-01: Es necesario comprobar que los datos recibidos sean confiables antes de utilizarlos. Una lectura incorrecta podría provocar una evaluación equivocada.

- RF-CRISTIAN-01: Representa una función central del proyecto: determinar si una zona ha recibido suficiente agua tomando en cuenta el nivel, el tiempo y las características del terreno.

- RF-CRISTIAN-02: Permite mantener al productor informado y conservar su participación en las decisiones. También evita que el sistema realice un cambio de flujo sin autorización.

P2-Media

- RF-ANA-01: Permite consultar los movimientos realizados entre zonas y conocer cuándo ocurrieron. Es importante para dar seguimiento al proceso, aunque no determina por sí mismo si una zona recibió suficiente agua.

- RNF-ANA-02: Permite mantener disponible la información histórica después de cerrar o reiniciar la aplicación. Complementa las funciones de registro y consulta.

- RF-GENESIS-02: Permite llevar un historial de las zonas que completaron el riego. Aporta información útil para el seguimiento, pero depende de que primero se pueda evaluar y confirmar la condición de riego.

No se asignaron requisitos P3 porque, dentro de las seis propuestas integradas, no se identificó alguno que corresponda únicamente a una mejora opcional o futura

---

## F. Criterios de aceptación

Los siguientes criterios permiten comprobar los resultados esperados de cada requisito sin agregar funciones distintas a las descritas en el catálogo.

RF-ANA-01—Registro de cambios de flujo

- Dado: que el productor autoriza un cambio de flujo entre dos zonas.
- Cuando: el sistema registra el cambio realizado.
- Entonces: deberá guardar la zona de origen, la zona de destino y la fecha y hora del evento.
Comprobación: Realizar un cambio de flujo autorizado y consultar el historial para verificar que aparezcan los datos correspondientes.

RNF-ANA-02—Conservación de registros

- Dado: que el sistema ya cuenta con registros de cambios de flujo almacenados.
- Cuando: la aplicación se cierre y posteriormente vuelva a iniciarse.
- Entonces: los registros anteriores deberán permanecer disponibles para su consulta.
Comprobación: Guardar un registro, cerrar y volver a abrir la aplicación, y comprobar que el registro siga disponible.

RF-GENESIS-01—Validación de lecturas del sensor

- Dado: que el sensor proporciona una lectura que no cumple con los criterios de confiabilidad definidos.
- Cuando: el sistema recibe y valida esa lectura.
- Entonces: deberá descartarla, notificar al encargado y evitar que se utilice para evaluar las condiciones de riego.
Comprobación: Proporcionar una lectura identificada como no confiable y verificar que el sistema no la utilice en la evaluación y genere la notificación correspondiente.
Pendiente: Definir los criterios técnicos que permitirán clasificar una lectura como no confiable.

RF-GENESIS-02—Registro de zonas regadas

- Dado: que una zona ha alcanzado las condiciones de riego establecidas y su finalización ha sido confirmada.
- Cuando: el sistema registra la zona como regada.
- Entonces: deberá guardar la identificación de la zona y la fecha y hora de confirmación.
Comprobación: Confirmar la finalización del riego de una zona y consultar el historial para verificar que aparezca con su información correspondiente.

RF-CRISTIAN-01—Evaluación de las condiciones de riego

- Dado: que el sistema cuenta con una lectura válida del sensor y con los parámetros necesarios de la zona.
- Cuando: evalúa las condiciones de riego considerando el nivel del agua, el tiempo y las características del terreno.
- Entonces: deberá determinar si se alcanzaron las condiciones establecidas o si debe continuar la supervisión.
Comprobación: Realizar pruebas con datos que representen condiciones suficientes e insuficientes de riego y verificar que el resultado de la evaluación corresponda con los parámetros definidos.
Pendiente: Establecer los valores y parámetros que se utilizarán en cada zona.

RF-CRISTIAN-02—Notificación y autorización del cambio de flujo

- Dado: que el sistema determinó que una zona alcanzó las condiciones de riego establecidas.
- Cuando: se genera la notificación correspondiente.
- Entonces: deberá informar al productor y esperar su autorización antes de realizar o indicar la ejecución del cambio de flujo.
Comprobación: Generar una condición de riego cumplida y verificar que se envíe la notificación. Después, comprobar que el cambio no se ejecute sin autorización del productor.

---

## G. Backlog y boceto

### G.1 Backlog inicial

El backlog organiza los requisitos del proyecto de acuerdo con su prioridad y las dependencias identificadas. Su propósito es establecer un orden de trabajo que permita atender primero las funciones principales del sistema y posteriormente incorporar las funciones complementarias.

| Orden | Identificador | Requisito | Prioridad | Responsable de la propuesta |
| ---- | ---- | ---- | ---- | ---- |
| 1 | RF-GENESIS-01 | Validación de lecturas de sensor | P1-Alta | Genesis Marisol |
| 2 | RF-CRISTIAN-01 | Evaluación de las condiciones de riego | P1-Alta | Cristian Emmanuel |
| 3 | RF-CRISTIAN-02 | Notificación y autorización del cambio de flujo | P1-Alta | Cristian Emmanuel |
| 4 | RF-ANA-01 | Registro de cambios de flujo | P2-Media | Ana Cristina |
| 5 | RF-GENESIS-02 | Registro de zonas regadas | P2-Media | Genesis Marisol |
| 6 | RNF-ANA-02 | Conservación de registros | P2-Media | Ana Cristina |

### G.2 Dependencias entre requisitos

| Requisito | Depende de | Justificación |
| ---- | ---- | ---- |
| RF-GENESIS-01 | Ninguno dentro del catálogo | Es necesario validar las lecturas antes de utilizarlas en las evaluaciones |
| RF-CRISTIAN-01 | RF-GENESIS-01 | Necesita recibir lecturas válidas para evaluar las condiciones de riego. |
| RF-CRISTIAN-02 | RF-CRISTIAN-01 | La notificación se genera después de determinar que se alcanzaron las condiciones de riego. |
| RF-ANA-01 | RF-CRISTIAN-02 | El registro del cambio requiere que exista una autorización y que el cambio de flujo se haya realizado. |
| RF-GENESIS-02 | RF-CRISTIAN-01 | Para registrar una zona como regada, primero debe determinarse que alcanzó las condiciones establecidas y confirmarse su finalización. |
| RNF-ANA-02 | RF-ANA-01 y RF-GENESIS-02 | La conservación de registros complementa la información generada por las funciones de registro. |

### G.3 Orden propuesto de trabajo

- Validación de lecturas del sensor: establecer que los datos recibidos sean confiables antes de utilizarlos

- Evaluación de las condiciones de riego: utilizar las lecturas válidas, el tiempo y las características del terreno para determinar si una zona recibió suficiente agua 

- Notificación y autorización: informar al productor cuando se cumplan las condiciones y esperar su autorización para cambiar el flujo

- Registro de cambios de flujo: almacenar la información de los cambios realizados entre zonas

- Registro de zonas regadas: conservar el historial de las zonas que hayan completado el riego

- Convsercacion de registros: asegurar que la información almacenada permanezca disponible después de cerrar o reiniciar la aplicación

Este orden considera las dependencias funcionales entre los requisitos. Los elementos de prioridad media complementan las funciones principales y pueden organizarse posteriormente, respetando las dependencias que existen entre ellos.

### G.4 Relación con Trello

| Actividad de Trello | Relación con el Backlog |
| ---- | ---- |
| ACT-64 | Elaboración de los requisitos individuales de Ana |
| ACT-65 | Elaboración de los requisitos individuales de Marisol |
| ACT-66 | Elaboración de los requisitos individuales de Cristian |
| ACT-67 | Integración y revisión de los requisitos | 
| ACT-68 | Revisión y definición de criterios de aceptación |
| ACT-69 | Asignación y justificación de prioridades |
| ACT-70 | Organización del backlog y sus dependencias |

### G.5 Boceto del recorrido prioritario

El siguiente recorrido representa la secuencia principal que debe atenderse primero, considerando los requisitos de prioridad alta:

RF-GENESIS-01: Validación de lecturas del sensor.
↓
RF-CRISTIAN-01: Evaluación de las condiciones de riego
↓
¿Se alcanzaron las condiciones establecidas?

- NO: continuar supervisando la zona
- SI: generar una notificación al productor
↓
¿El productor autoriza el cambio?

- NO: mantener el flujo actual y esperar una nueva decisión 
- SI: realizar el cambio de flujo autorizado

Los registros de cambios y zonas regadas, así como su conservación, complementan el recorrido mediante los requisitos de prioridad media.

### G.6 Resultado de la actividad

Se organizó el backlog con los seis requisitos del catálogo, respetando sus identificadores y prioridades. También se identificaron las dependencias entre ellos y se estableció un orden propuesto de trabajo que inicia con la validación de lecturas, continúa con la evaluación de las condiciones de riego y finaliza la secuencia principal con la autorización del productor.

El backlog queda relacionado con las actividades de Trello y con el catálogo de requisitos del proyecto, sin agregar funciones que estén fuera del alcance establecido

---

## H. Trazabilidad y cambios

### H.1 Matriz de trazabilidad

La matriz permite relacionar las fuentes de información con las necesidades identificadas, los requisitos propuestos, sus criterios de aceptación y el boceto elaborado en ACT-72. También permite identificar las relaciones que se encuentran incompletas y los aspectos que requieren revisión.

| ID req | Fuente | Necesidad asociada | Criterio de aceptación | Relación con el boceto | Estado |
| ---- | ---- | ---- | ---- | ---- | ---- |
| RF-ANA-01 | F-02, F-03 | N-08: Contar con un historial de cambios de flujo. | Registrar zona origen, zona destino, fecha y hora del cambio realizado. | Parcial. El boceto contempla controles de compuerta, pero no muestra una consulta al historial de cambios. | Requiere complementar el boceto. |
| RF-ANA-02 | F-04 | Conservar los registros de cambios de flujo después de cerrar y volver a iniciar la aplicación. | Los registros deben permanecer disponibles después de reiniciar la aplicación. | Indirecta. La conservación de información no se representa visualmente en el boceto. | Relación documentada. Pendiente de revisión técnica. |
| RF-GENESIS-01 | F-02, F-03 | N-07: Contemplar una respuesta ante lecturas incorrectas del sensor. | Descartar la lectura no confiable, notificar al encargado y evitar utilizarla en la evaluación | Parcial. El boceto incluye notificaciones, pero no representa claramente el procedimiento de validación de lecturas | Requiere complementar el recorrido. |
| RF-GENESIS-02 | F-02 | N-08: Contar con un historial de las zonas regadas | Registrar la identificación de la zona y la fecha y hora de confirmación. | No visible. No se muestra una pantalla de consulta de zonas regadas. | Requiere complementar el boceto. |
| RF-CRISTIAN-01 | F-02, F-03 | N-02 y N-03: Determinar si una zona recibió suficiente agua considerando el nivel, tiempo y terreno. | Evaluar las condiciones con una lectura válida y los parámetros establecidos para la zona. | Parcial. El boceto muestra el control de compuertas, pero no presenta el nivel del agua ni el resultado de la evaluación. | Requiere complementar el boceto. |
| RF-CRISTIAN-02 | F-02, F-03 | N-06: Notificar al productor y permitirle autorizar el cambio de flujo. | Notificar cuando se cumplan las condiciones y esperar la autorización antes de realizar el cambio. | Parcial. Se muestra una bandeja de notificaciones y controles de compuerta, pero no el proceso de autorización del cambio de zona. | Requiere complementar el boceto. |

### H.2 Cambios y pendientes

| Aspecto | Decisión o siguiente paso | Estado |
| ---- | ---- | ---- |
|Identificadores de requisitos | Mantener los identificadores del catálogo y corregir errores de escritura. | Corregido |
| Criterios de aceptación | Mantener los criterios documentados en F y revisar que correspondan con cada requisito. | Integrados |
| Boceto | Revisar las pantallas para relacionarlas con el recorrido prioritario y los requisitos. | Completado | 
| Parámetros de riego | Definir valores y referencias para evaluar las condiciones de cada zona | Pendiente |
| Validación de sensores | Definir criterios técnicos para identificar lecturas no confiables | Pendiente |
Conservación de registros | Revisar la solución técnica para mantener la información después de cerrar la aplicación. | Pendiente |

---

## I. Referencias y herramientas

### I.1 Fuentes del proyecto

- F-01. Entrevista inicial al productor, realizada el 03/09/2026
- F-02. Segunda entrevista de seguimiento al productor, realizada el 15/11/2026.
- F-03. Análisis del proceso y propuesta TO-BE del equipo, Unidad 2, 27/10/2026.
- F-04. Propuesta técnica individual de Ana Cristina sobre conservación de registros.

### I.2 Herramientas utilizadas

| Herramienta | Proveedor | Uso dentro del proyecto | Enlace |
| ---- | ---- | ---- | ---- |
| Figma | Figma, Inc. | Elaboración del boceto y representación visual del recorrido principal del sistema | https://www.figma.com/make/WiKXpLWr7vupJOECNt3MyL/Interfaz-de-Riego-Natural?t=DipdOTpHiuYdy7GB-20&fullscreen=1 |
| Trello | Atlassian | Organización de actividades, responsables y seguimiento del trabajo de equipo | https://trello.com/b/9fPSPRCr/riego-sin-regarla1 |

### I.3 Documentos de apoyo 

- ACT-71. Investigación y selección de herramienta para elaborar el boceto.
- ACT-72. Elaboración del boceto del recorrido principal.
- ACT-73. Elaboración de la matriz de trazabilidad.
- ACT-67. Integración y revisión del catálogo de requisitos.
- ACT-68. Revisión y definición de criterios de aceptación.
- ACT-69. Asignación y justificación de prioridades.
- ACT-70. Organización del backlog y sus dependencias.

Las herramientas y documentos anteriores se utilizaron como apoyo para la elaboración y organización de la especificación de requisitos del proyecto.

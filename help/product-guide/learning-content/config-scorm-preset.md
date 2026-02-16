---
title: Configuración de ajustes preestablecidos de SCORM
description: Obtenga información acerca de las distintas configuraciones de ajustes preestablecidos de SCORM en Formación y aprendizaje del producto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
source-git-commit: 3fdedee6e07908632bcf1b804805fcac7925c4e0
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Configurar ajuste preestablecido de salida SCORM

Una vez creado el ajuste preestablecido, configure las opciones de SCORM. Las opciones de configuración preestablecidas están organizadas en las pestañas General, Contenido y Publicar.

- **General:** Se usa para especificar la configuración básica de salida, como la versión admitida, la ruta de acceso de salida, el nombre del archivo ZIP, la plantilla de salida y otras opciones relacionadas con la experiencia del alumno.

  ![](assets/scorm-general-tab-v3.png){width="650" align="left"}

  **Experiencia del alumno**

   - **Los alumnos deben avanzar por el contenido en un orden secuencial**: garantiza que los alumnos se mueven por el quiz en una secuencia fija y no pueden saltar preguntas ni saltar entre preguntas.
   - **Los alumnos deben intentar responder todas las preguntas para continuar**: Requiere que los alumnos intenten responder todas las preguntas antes de poder enviar la prueba, lo que evita envíos incompletos.
   - **Orden aleatorio de preguntas para cada intento**: muestra las preguntas de prueba en un orden diferente para cada intento, lo que ayuda a reducir la previsibilidad.
   - **Aleatoriza las opciones de respuesta para cada intento**: Cambia las opciones de respuesta para cada pregunta en cada intento, lo que reduce la posibilidad de adivinar en función de la posición.
   - **Usar ID de pregunta en los informes de pruebas**: incluye el ID de pregunta único en los informes de pruebas, lo que facilita el seguimiento, el análisis y la asignación de resultados a preguntas específicas.
   - **Flujo de trabajo de generación posterior**: al elegir esta opción, se muestra una nueva lista desplegable de flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados.

- **Contenido:** Úselo para especificar el filtrado condicional disponible (usando DITAVAL o usando algún ajuste preestablecido de condición) y el conjunto de variables.

  ![](assets/scorm-content-tab.png){width="650" align="left"}

- **Publicar:** Use esta configuración solo si desea publicar la salida en SCORM Cloud para acceso directo.

  ![](assets/scorm-publish-tab.png){width="650" align="left"}

Una vez configurados todos los cambios, guárdelos para el ajuste preestablecido de SCORM con **Guardar** en la esquina derecha de la barra de herramientas de la página de ajustes preestablecidos de SCORM.

---
title: Configuración de ajustes preestablecidos de SCORM
description: Obtenga información acerca de las distintas configuraciones de ajustes preestablecidos de SCORM en Formación y aprendizaje del producto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: dbb138a7804d102d1b9aa9cfbc3564e827ef199e
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 0%

---

# Configurar ajuste preestablecido de salida SCORM

Una vez creado el ajuste preestablecido, configure las opciones de SCORM. Las opciones de configuración preestablecidas están organizadas en las pestañas General, Contenido, Experiencia del alumno y Publicación.

- **General:** Se usa para especificar la configuración básica de salida, como la versión admitida, la ruta de acceso de salida, el nombre de archivo SCORM (zip), la plantilla de salida y el flujo de trabajo de generación posterior para una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados.

  ![](assets/scorm-general-tab-v3.png){width="650"}


- **Contenido:** Úselo para especificar el filtrado condicional disponible (usando DITAVAL o usando algún ajuste preestablecido de condición) y el conjunto de variables.

  ![](assets/scorm-content-tab.png){width="650"}

- **Experiencia del alumno:** La ficha **Experiencia del alumno** le permite configurar cómo los alumnos interactúan con la salida de SCORM y navegan por ella. La configuración está organizada en **General**, **Navegación** y **Prueba**, lo que le permite controlar la accesibilidad del contenido, el flujo de navegación y el comportamiento de las pruebas para disfrutar de una experiencia de aprendizaje a medida.

  ![](assets/learner-experience.png){width="650"}

  - **General:** Configure opciones de nivel de salida como habilitar las descargas de PDF para los alumnos.

    - **Permitir que los alumnos descarguen el curso PDF**: cuando está habilitada, esta opción agrega un icono de PDF a la salida de SCORM. Al hacer clic en este icono, el alumno puede descargar una versión de PDF del contenido del curso directamente desde la salida publicada.

      **Requisitos previos:** Antes de habilitar esta opción, asegúrese de lo siguiente:

      - La **plantilla de salida** debe configurarse con el icono **Incrustar PDF** en la ubicación deseada y debe seleccionarse la misma plantilla en la opción **Plantilla de salida** de la pestaña **General** al configurar un ajuste preestablecido de SCORM.

        ![](assets/embed-pdf.png){width="650"}

      - El **ajuste preestablecido nativo de PDF** asociado debe haberse generado al menos una vez. Si se selecciona un ajuste preestablecido de PDF no generado, se producirá un error que solicitará al usuario que publique el ajuste preestablecido.

    Una vez que la salida SCORM se genera con la configuración anterior, la salida resultante incluye un icono de PDF, como se muestra a continuación, que permite a los alumnos descargar el curso PDF.

    ![](assets/pdf-icon.png){width="650"}

  - **Navegación:** Defina cómo se mueven los alumnos a través del curso, incluida la progresión secuencial, las condiciones de finalización obligatorias y las reglas para desbloquear el botón **Siguiente**.

    - **Los alumnos deben avanzar por el contenido en un orden secuencial**: garantiza que los alumnos se mueven por el curso en una secuencia fija y no pueden saltar ni saltar entre los componentes del curso.
    - **Deshabilitar el botón siguiente si el alumno no supera el examen**: impide que el alumno pase a la siguiente sección/página hasta que apruebe el examen.
    - **Los alumnos deben intentar responder todas las preguntas para continuar**: Requiere que los alumnos intenten responder todas las preguntas antes de poder enviar la prueba, lo que evita envíos incompletos.
    - **Bloquear progreso hasta completar**: impide la navegación a través del curso hasta que se cumplan todas las subcondiciones configuradas por debajo de él al deshabilitar el botón **Siguiente** en el curso.
      - **Todos los elementos interactivos abiertos**: Requiere que el alumno abra todos los elementos interactivos de la página.
      - **Todos los medios vistos**: Requiere que el alumno vea todos los medios de vídeo/audio de la página.
      - **Se han intentado todas las comprobaciones de conocimientos**: Requiere que el alumno intente cada pregunta de comprobación de conocimientos de la página.
      - **Tiempo mínimo empleado en la página**: Requiere que el alumno permanezca en la página durante al menos la duración especificada antes de que se active el botón Siguiente. Una vez activado, debe introducir el tiempo necesario como se menciona a continuación.
        - **Tiempo requerido (segundos)**: El número mínimo de segundos (por ejemplo, `30`) que un alumno debe permanecer en la página para que se cumpla esta condición.

  - **Prueba:** configure el comportamiento relacionado con las pruebas, como la asignación aleatoria del orden de las preguntas y las opciones de respuesta, para reducir la previsibilidad entre los intentos.

    - **Orden aleatorio de preguntas para cada intento**: muestra las preguntas de prueba en un orden diferente para cada intento, lo que ayuda a reducir la previsibilidad.
    - **Aleatoriza las opciones de respuesta para cada intento**: Cambia las opciones de respuesta para cada pregunta en cada intento, lo que reduce la posibilidad de adivinar.

- **Publicar en LMS:** Use esta configuración para publicar el contenido directamente en Adobe Learning Manager (ALM). En el menú desplegable **Servidor de publicación**, seleccione **Adobe Learning Manager** y, a continuación, elija el **perfil de publicación** necesario que se configuró anteriormente en la configuración de Workspace. El perfil seleccionado se utiliza para establecer la conexión y cargar el contenido generado en ALM.

  >[!NOTE]
  >
  > Antes de publicar contenido en ALM, debe configurar un perfil de publicación de Adobe Learning Manager. Para obtener más información, vea [Publicar perfiles](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Una vez configurados todos los cambios, guárdelos para el ajuste preestablecido de SCORM con **Guardar** en la esquina derecha de la barra de herramientas de la página de ajustes preestablecidos de SCORM.

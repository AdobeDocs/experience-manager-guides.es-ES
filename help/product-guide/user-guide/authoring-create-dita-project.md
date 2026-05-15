---
title: Creación de un proyecto DITA
description: Cree un proyecto DITA con una plantilla en AEM Guides. Aprenda a utilizar un proyecto DITA para iniciar las revisiones.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
feature: Reviewing
role: User
TQID: https://experienceleague.adobe.com/mOwLR3UFEcVKiEYLzLxo5lzK3rIeNJtB7q-qEyraY30
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 0%

---

# Creación de un proyecto DITA {#id1645HA00NM6}

Adobe Experience Manager Guides proporciona una plantilla de proyecto DITA que puede utilizar para crear y administrar las tareas de revisión.

Puede crear un proyecto DITA y, a continuación, utilizarlo para iniciar las revisiones. Un proyecto permite definir una fecha límite y controlar las tareas y el tiempo necesarios para completar la tarea de revisión para la que se ha creado el proyecto.

Puede agregar integrantes del equipo a un proyecto a los que luego se les podrían asignar diversas funciones: autores, revisores y editores.

Una vez creado el proyecto DITA, puede iniciar la revisión desde el Editor o desde la interfaz de usuario de Assets. Para obtener más información, vea [Enviar temas para revisión](review-send-topics-for-review.md#).

Del mismo modo, cada vez que un autor inicia un flujo de trabajo de revisión, los miembros seleccionados del proyecto reciben una notificación por correo electrónico. Para configurar las notificaciones por correo electrónico, vea *Personalizar plantillas de correo electrónico* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

Siga estos pasos para crear un proyecto DITA:

1. Abra la consola Proyectos.

   También puede acceder a la consola Proyectos mediante la siguiente URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Seleccione **Crear** \> **Proyecto** para iniciar el asistente Crear proyecto.

   ![](images/project-console-63.png){width="650"}

1. En la página Crear proyecto, seleccione la plantilla **Proyecto DITA** y seleccione **Siguiente**.

1. En la página Propiedades del proyecto, escriba los siguientes detalles:

   Información en la ficha **Básico**:

   ![](images/create-project.png){width="650"}

   - Escriba el **Título**, la **Descripción** y la **Fecha de vencimiento** de su proyecto.

   - Si lo desea, puede elegir una miniatura para el proyecto.

   - De forma predeterminada, pasa a ser el propietario del proyecto. Para agregar más usuarios a este proyecto:

   1. Escriba o elija un usuario de la lista desplegable **Usuario**.

   1. Elija un tipo de usuario: autores, revisores o editores.

      >[!NOTE]
      >
      >En esta lista desplegable verá otros tipos de usuarios, pero para un proyecto DITA sólo debe elegir entre los tipos de usuario Autores, Revisores o Editores. Incluso si añade un usuario de un tipo diferente, dicho usuario no podrá acceder a ninguna función específica de DITA disponible en Experience Manager Guides.

   1. Seleccione **Añadir**.

      >[!NOTE]
      >
      >Si utiliza la versión 3.5 o anterior de Experience Manager Guides, se muestra una opción para seleccionar un fichero de mapa DITA con el fin de resolver referencias clave para los flujos de trabajo de edición, previsualización y revisión de temas. En las versiones 3.6 y posteriores, puede establecer el mapa raíz mediante el Editor. Para obtener más información, vea las [Preferencias de usuario](web-editor-features.md#id2087G0P40SB) en el editor. Otra forma de configurar el mapa raíz es configurándolo en los perfiles globales o de nivel de carpeta. Para obtener más información, consulte *Configurar perfiles globales o de nivel de carpeta* en la Guía de instalación y configuración.

   Información en la ficha **Avanzado**:

   - Escriba un nombre para el proyecto. Este nombre se utiliza para crear la dirección URL de este proyecto.

1. Seleccione **Crear**.

   Aparecerá el cuadro de diálogo Proyecto creado.

1. Seleccione **Abrir** para abrir la página de su proyecto.


**Tema principal:**&#x200B;[&#x200B; Introducción a la revisión](review.md)

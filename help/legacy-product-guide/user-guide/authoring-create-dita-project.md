---
title: Creación de un proyecto DITA
description: Cree un proyecto DITA con una plantilla en AEM Guides. Aprenda a utilizar un proyecto DITA para iniciar las revisiones.
feature: Reviewing
role: User
hide: true
exl-id: 1b29c50a-04d0-4052-b893-44fb8bcc3c97
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Creación de un proyecto DITA {#id1645HA00NM6}

AEM Guides proporciona una plantilla de proyecto DITA que puede utilizar para crear y administrar las tareas de revisión.

Puede crear un proyecto DITA y, a continuación, utilizarlo para iniciar las revisiones. Un proyecto permite definir una fecha límite y controlar las tareas y el tiempo necesarios para completar la tarea de revisión para la que se ha creado el proyecto.

Puede agregar integrantes del equipo a un proyecto a los que luego se les podrían asignar diversas funciones: autores, revisores y editores.

Una vez creado el proyecto DITA, puede iniciar la revisión desde el Editor web o desde la interfaz de usuario de Assets. Para obtener más información, vea [Enviar temas para revisión](review-send-topics-for-review.md#).

Del mismo modo, cada vez que un autor inicia un flujo de trabajo de revisión, los miembros seleccionados del proyecto reciben una notificación por correo electrónico. Para configurar las notificaciones por correo electrónico, consulte *Personalizar plantillas de correo electrónico* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

Siga estos pasos para crear un proyecto DITA:

1. Abra la consola Proyectos.

   También puede acceder a la consola Proyectos mediante la siguiente URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Haga clic en **Crear** \> **Proyecto** para iniciar el asistente Crear proyecto.

   ![](images/project-console-63.png){width="650" align="left"}

1. En la página Crear proyecto, seleccione la plantilla **Proyecto DITA** y haga clic en **Siguiente**.

1. En la página Propiedades del proyecto, escriba los siguientes detalles:

   Información en la ficha **Básico**:

   ![](images/create-project.png){width="650" align="left"}

   - Escriba el **Título**, la **Descripción** y la **Fecha de vencimiento** de su proyecto.

   - Si lo desea, puede elegir una miniatura para el proyecto.

   - De forma predeterminada, pasa a ser el propietario del proyecto. Para agregar más usuarios a este proyecto:

   1. Escriba o elija un usuario de la lista desplegable **Usuario**.

   1. Elija un tipo de usuario: autores, revisores o editores.

      >[!NOTE]
      >
      >En esta lista desplegable verá otros tipos de usuarios, pero para un proyecto DITA sólo debe elegir entre los tipos de usuario Autores, Revisores o Editores. Incluso si añade un usuario de un tipo diferente, dicho usuario no podrá acceder a ninguna función específica de DITA disponible en AEM Guides.

   1. Haga clic en **Agregar**.

      >[!NOTE]
      >
      >Si utiliza la versión 3.5 o anterior de AEM Guides, se muestra una opción para seleccionar un fichero de mapa DITA con el fin de resolver referencias clave para los flujos de trabajo de edición, previsualización y revisión de temas. En las versiones 3.6 y posteriores, puede establecer el mapa raíz mediante el Editor Web. Para obtener más información, consulte [Preferencias de usuario](web-editor-features.md#id2087G0P40SB) en el Editor web. Otra forma de configurar el mapa raíz es configurándolo en los perfiles globales o de nivel de carpeta. Para obtener más información, consulte *Configurar perfiles globales o de nivel de carpeta* en la Guía de instalación y configuración.

   Información en la ficha **Avanzado**:

   - Escriba un nombre para el proyecto. Este nombre se utiliza para crear la dirección URL de este proyecto.

1. Haga clic en **Crear**.

   Aparecerá el cuadro de diálogo Proyecto creado.

1. Haz clic en **Abrir** para abrir la página del proyecto.


**Tema principal:**[ Revisar temas o asignaciones](review.md)

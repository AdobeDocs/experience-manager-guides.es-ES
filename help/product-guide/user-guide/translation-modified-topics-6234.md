---
title: Traducir temas modificados
description: Obtenga información sobre cómo volver a traducir un tema modificado en AEM Guides.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: ae36a7fdff6ae147619340aa3a3d2bb6c7774fe0
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---

# Traducir temas modificados {#id16A5A0B6072}

Si realiza cambios en algunos de los temas, esos temas requerirán una nueva traducción. Puede realizar un seguimiento de los temas modificados desde el mapa DITA. En la carpeta de copia de idioma de origen, seleccione el fichero de mapa DITA en la consola Mapa y seleccione la ficha Traducción. Puede ver el estado de cada tema tanto si requiere una nueva traducción como si no.

Realice los siguientes pasos para enviar un tema modificado para su retraducción:

1. Seleccione el archivo de asignación DITA de la carpeta de copia de idioma de origen de **Map Console** en el Editor.

1. Seleccione la ficha **Traducción**.

1. En el panel **Traducción** de la izquierda, seleccione los **Idiomas disponibles** para los que desea comprobar el estado y seleccione **Aplicar**.

   Puede ver el estado de traducción de cada tema. Los temas que tienen otra revisión del tema disponible aparte de lo que se envió para su traducción, muestran un estado **Fuera de sincronización**.

   >[!NOTE]
   >
   > El flujo de trabajo de traducción compara la última revisión guardada del archivo de tema en la carpeta del idioma de origen con la versión traducida.

   Si selecciona la flecha para ver más detalles, puede ver la copia de idioma en particular que no está sincronizada.

   ![](images/out-of-sync-uuid-new.png){width="800" align="left"}

1. Seleccione la casilla de verificación para seleccionar los temas que desea enviar para su retraducción.

   Cuando selecciona un tema que no está sincronizado, aparece el botón **Marcar en sincronización** encima de la barra de título.

   Puede usar el botón **Marcar en sincronización** para anular el estado Fuera de sincronización de los temas del mapa DITA.  Por ejemplo, si ha realizado algunos cambios muy menores que realmente no necesitan traducción, puede marcar su estado como Sincronizado.

   >[!NOTE]
   >
   > Si selecciona el botón **Marcar en sincronización**, se establece el estado del tema en Sincronizado para los temas seleccionados sin sincronización.

1. Puede seleccionar el **botón Enviar para traducción**.

1. Puede elegir crear un nuevo proyecto de traducción o agregar temas a un proyecto de traducción existente. Proporcione los detalles necesarios para configurar el proyecto de traducción.

1. Seleccione **Enviar**.

   Se muestra un mensaje de confirmación que indica que el tema se ha enviado para su traducción.

1. Vaya al proyecto de traducción en la consola Proyecto. Se crea una nueva tarjeta de trabajo de traducción en la carpeta. Seleccione los puntos suspensivos para ver los recursos de la carpeta.

   ![](images/incremental-job-new.png){width="300" align="left"}

1. Para iniciar la traducción, seleccione la flecha de la tarjeta del trabajo de traducción y seleccione **Start** en la lista. Un mensaje notifica que el trabajo se ha iniciado.

   También puede ver el estado del tema que se traduce al seleccionar los puntos suspensivos en la parte inferior de la tarjeta de trabajo de traducción.

   >[!NOTE]
   >
   > Si utiliza el servicio de traducción humana, debe exportar el contenido para su traducción. Una vez que tenga el contenido traducido, debe importarlo de nuevo en el proyecto de traducción.

1. Una vez finalizada la traducción, el estado cambia a **Listo para revisión**. Seleccione los puntos suspensivos para ver los detalles del tema y realice una de las siguientes acciones en la barra de herramientas:

   - Seleccione **Mostrar en Assets** para ver y comprobar la traducción.

   - Seleccione **Aceptar traducción** si cree que los cambios se han traducido correctamente. Se muestra un mensaje de confirmación.

   - Seleccione **Rechazar traducción** si cree que es necesario volver a realizar el trabajo. Se muestra un mensaje de rechazo.

   >[!NOTE]
   >
   > Es importante aceptar o rechazar el recurso traducido; de lo contrario, el archivo permanece en la ubicación temporal y no se copia en DAM.

1. Vuelva al archivo de mapa DITA en la carpeta de idioma de origen en la interfaz de usuario de Assets. Los temas retraducidos ahora están sincronizados.


**Tema principal:**[ Resumen de traducción de contenido](translation.md)

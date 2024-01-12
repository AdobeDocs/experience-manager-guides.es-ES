---
title: Traducir temas modificados
description: AEM Obtenga información sobre cómo volver a traducir un tema modificado en Guías de.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traducir temas modificados {#id16A5A0B6072}

Si realiza cambios en algunos de los temas, esos temas requerirán una nueva traducción. Puede realizar un seguimiento de los temas modificados desde el mapa DITA. En la carpeta de copia de idioma de origen, pulse en el fichero de mapa DITA y en la ficha Traducción. Puede ver el estado de cada tema tanto si requiere una nueva traducción como si no.

Realice los siguientes pasos para enviar un tema modificado para su retraducción:

1. Pulse en el fichero de mapa DITA de la carpeta de copia de idioma de origen.

1. Haga clic en **Traducción** pestaña.

1. En el **Filtrar** panel de la izquierda, seleccione **Traducir idiomas** que desea comprobar el estado de y haga clic en **Listo**.

   Puede ver el estado de traducción de cada tema. Los temas que tienen otra revisión del tema disponible que la que se envió para su traducción muestran un **Obsoleto** estado.

   >[!NOTE]
   >
   > El flujo de trabajo de traducción compara la última revisión guardada del archivo de tema en la carpeta del idioma de origen con la versión traducida.

   Si hace clic en la flecha para ver más detalles. puede ver la copia de idioma en particular que no está actualizada.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Haga clic en la casilla de verificación para seleccionar los temas que desea enviar para su retraducción.

   Cuando selecciona una fecha sin sincronizar, la variable **Crear/actualizar copias de idioma** aparece en el panel Referencias y la opción **Descartar estado de falta de sincronización** botón situado encima de **Filtrar** icono.

   Puede usar el complemento **Descartar fuera de sincronización** para anular el estado Obsoleto de los temas del mapa DITA. Por ejemplo, si ha realizado algunos cambios en la versión en inglés del tema que no necesitan traducción, puede utilizar este botón y cambiar el estado Obsoleto del tema seleccionado.

   >[!NOTE]
   >
   > Si hace clic en **Descartar estado de falta de sincronización** establece el estado del tema en Actualizado para los temas obsoletos seleccionados.

1. Clic **Actualizar copias de idioma** y configure el trabajo de traducción.

1. Puede elegir crear un nuevo proyecto de traducción o agregar temas a un proyecto de traducción existente. Proporcione los detalles necesarios para configurar el proyecto de traducción.

1. Clic **Inicio**.

   Se muestra un mensaje de confirmación que indica que el tema se ha enviado para su traducción.

1. Vaya al proyecto de traducción en la consola Proyecto. Se crea una nueva tarjeta de trabajo de traducción en la carpeta. Haga clic en los puntos suspensivos para ver los recursos de la carpeta.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Para iniciar la traducción, haga clic en la flecha de la tarjeta del trabajo de traducción y seleccione **Inicio** de la lista. Un mensaje notifica que el trabajo se ha iniciado.

   También puede ver el estado del tema que se está traduciendo al hacer clic en los puntos suspensivos en la parte inferior de la tarjeta de trabajo de traducción.

   >[!NOTE]
   >
   > Si utiliza el servicio de traducción humana, debe exportar el contenido para su traducción. Una vez que tenga el contenido traducido, debe importarlo de nuevo en el proyecto de traducción.

1. Una vez finalizada la traducción, el estado cambia a **Listo para revisión**. Haga clic en los puntos suspensivos para ver los detalles del tema y realice una de las siguientes acciones en la barra de herramientas:

   - Clic **Mostrar en Assets** para ver y verificar la traducción.

   - Clic **Aceptar traducción** si cree que los cambios se han traducido correctamente. Se muestra un mensaje de confirmación.

   - Clic **Rechazar traducción** si cree que hay que volver a hacer el trabajo. Se muestra un mensaje de rechazo.

   >[!NOTE]
   >
   > Es importante aceptar o rechazar el recurso traducido; de lo contrario, el archivo permanece en la ubicación temporal y no se copia en DAM.

1. Vuelva al archivo de mapa DITA en la carpeta de idioma de origen en la interfaz de usuario de Assets. Los temas retraducidos ahora están sincronizados.


**Tema principal:**[ Traducir contenido](translation.md)

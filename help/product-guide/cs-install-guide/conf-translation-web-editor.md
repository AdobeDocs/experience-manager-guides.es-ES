---
title: Configuración de la función de traducción en el editor web
description: Obtenga información sobre cómo configurar la función de traducción en el editor web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Configuración de la función de traducción en el editor web {#id21BONI0J0YR}

El editor web proporciona una potente función de traducción para traducir el contenido a varios idiomas.

Puede usar el complemento **Administrar** en el Editor Web para traducir el contenido. Esta pestaña está disponible de forma predeterminada.

Para ocultar la variable **Administrar** en el Editor Web, realice los siguientes pasos:

1. Iniciar sesión en **Adobe Experience Manager** como administrador.
1. Haga clic en **Adobe Experience Manager** en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Haga clic en **Configuración del editor XML**.
1. Haga clic en **Editar** en la parte superior.
1. Descargue la `ui\_config.json` file.Remove el siguiente fragmento de código del archivo descargado:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Cargue el archivo ui\_config.json actualizado.

Tenga en cuenta que la variable **Administrar** el filtro ya no está disponible.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)

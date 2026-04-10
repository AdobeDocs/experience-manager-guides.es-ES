---
title: Personalizar editor web
description: Aprenda a personalizar la visualización de tablas pegadas en el Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Configurar la visualización de las tablas pegadas

Mediante la barra de herramientas secundaria del Editor, puede insertar una tabla simple en la ubicación válida actual o siguiente de un tema. También puede copiar una tabla desde Microsoft Word o Excel y pegarla directamente en un archivo de tema.

Los administradores pueden configurar cómo se muestran las tablas copiadas. De forma predeterminada, estas tablas copiadas se muestran como `simpletable` en el editor. Sin embargo, puede cambiar esta configuración para mostrar las tablas copiadas como `tgroup` actualizando la configuración del Editor XML.

>[!NOTE]
>
> Si copia una tabla con filas o columnas combinadas, la tabla se pegará como tabla normal `trgoup` y no como `simpletable`, independientemente de la configuración de tabla configurada en la configuración del Editor XML.

Para actualizar el formato de tabla predeterminado, realice los siguientes pasos:

1. Abra la página Navegaciones de Adobe Experience Manager y seleccione **Herramientas** a la izquierda.
2. En el panel Herramientas, seleccione **Guías** de la lista de herramientas.
3. Seleccione **Perfiles de carpeta** y, a continuación, seleccione el perfil en el que desea actualizar la configuración de la tabla.
4. Vaya a la ficha **Configuración del editor XML**.
5. Seleccione el icono **Editar** de la parte superior.
6. Seleccione el icono **Descargar** para descargar el archivo `ui_config.json` en su sistema local.
7. En el archivo `ui_config.json`, actualice la configuración `simpletable` como se muestra a continuación:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Una vez actualizado, guarde el archivo y cárguelo.

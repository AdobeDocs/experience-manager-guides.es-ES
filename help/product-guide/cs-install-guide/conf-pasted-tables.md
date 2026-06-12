---
title: Personalizar editor web
description: Aprenda a personalizar la visualización de tablas pegadas en el Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
TQID: https://experienceleague.adobe.com/0g3LyLfKxZEbtl968wJK6r1xPHRjagayeBF4xSvJF6c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
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

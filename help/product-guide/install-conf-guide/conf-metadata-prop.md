---
title: Configuración de la lista de omisión de propiedades de metadatos
description: Obtenga información sobre cómo configurar la lista de omisión para las propiedades de metadatos en AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Configuración de la lista de omisión de propiedades de metadatos

Cuando se edita un archivo, cualquier cambio en los campos de metadatos disponibles en **Propiedades del archivo** o aplicado en el déclencheur back-end contiene el asterisco (*) en la versión del documento. Para evitar que las actualizaciones de metadatos generadas por el sistema afecten a este indicador, los administradores pueden configurar una lista de omisión para las propiedades de los metadatos.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción **Omitir propiedad de metadatos para versión sucia**.


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, vaya a la opción **Omitir propiedad de metadatos para versión sucia**.

   Revise la lista de propiedades de metadatos predeterminadas configuradas actualmente para que se ignoren.

1. Añada o elimine propiedades de metadatos según los requisitos.
1. Seleccione **Guardar** para guardar la configuración actualizada.


>[!ENDTABS]

## Propiedades de metadatos predeterminadas en la lista de omisión

AEM Guides incluye un conjunto predeterminado de propiedades de metadatos en la lista de omisión. Puede modificar esta lista para agregar o quitar propiedades de metadatos según sea necesario.

* &quot;jcr:mixinTypes&quot;,
* &quot;jcr:primaryType&quot;,
* &quot;jcr:frozenMixinTypes&quot;,
* &quot;jcr:frozenPrimaryType&quot;,
* &quot;jcr:frozenUuid&quot;,
* &quot;jcr:uuid&quot;,
* &quot;dam:extracted&quot;,
* &quot;jcr:lastModified&quot;,
* &quot;jcr:lastModifiedBy&quot;,
* &quot;dc:modified&quot;,
* &quot;dam:sha1&quot;,
* &quot;dam:size&quot;,
* &quot;guías:wordCount&quot;,
* &quot;dam:scene7UploadTimeStamp&quot;,
* &quot;dam:scene7LastModified&quot;

Sólo se tienen en cuenta las propiedades de metadatos que no están incluidas en la lista de omisión para marcar la versión de un documento como sucia.

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)

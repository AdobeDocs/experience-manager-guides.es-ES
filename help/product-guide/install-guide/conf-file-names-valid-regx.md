---
title: Configure Regx para caracteres de nombre de archivo válidos
description: Obtenga información sobre cómo configurar Regx para caracteres de nombre de archivo válidos
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Configure Regx para caracteres de nombre de archivo válidos {#id214BD0550E8}

A partir de la versión 3.8 de AEM Guides, como administrador, puede definir una lista de caracteres especiales válidos permitidos en los nombres de archivo. En versiones anteriores, se permitía a los usuarios definir nombres de archivo que contenían caracteres especiales como `@`, `$`, `>`, etc. Estos caracteres especiales provocaban problemas al abrir temas desde el panel de mapas DITA o al hacer clic en el vínculo del tema en el índice, lo que a menudo provocaba que la página no se abriera debido a los caracteres especiales de la dirección URL.

Si utiliza la configuración que le permite definir una regx para los caracteres de nombre de archivo válidos, tendrá control total sobre cómo se asignan los nombres de archivo internamente en el sistema. Puede definir una lista de caracteres especiales permitidos en los nombres de archivo. De manera predeterminada, la configuración de nombre de archivo válida contiene &quot;`a-z A-Z 0-9 - _`&quot;. Al crear un nuevo archivo, puede tener cualquier carácter especial en el título del archivo, pero internamente se reemplazará con &quot;`-`&quot; en el nombre del archivo. Por ejemplo, puede tener el título del archivo como &quot;Introducción 1&quot; o &quot;Introduction@1&quot;, el nombre de archivo correspondiente generado para ambos casos sería &quot;Introducción-1&quot;.

Cuando defina una lista de caracteres válidos, recuerde que estos caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; siempre se reemplazarán por &quot;`-`&quot;.

Si no configura la lista de caracteres especiales válidos, el proceso de creación de archivos podría dar algunos resultados inesperados. Para evitar estos errores, se recomienda encarecidamente realizar este cambio de configuración inmediatamente después de actualizar la compilación a la versión 3.8.

Para configurar la regx para caracteres \(o permitidos\) válidos en los nombres de archivo, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete *com.adobe.fmdita.config.ConfigManager*.

1. En la propiedad **Regex for Valid Characters**, asegúrese de que la propiedad está establecida en \[-a-zA-Z0-9\_\]. Puede añadir más caracteres a esta lista, pero debe tener estos caracteres básicos y la lista debe comenzar con un guión &quot;-&quot;.

   >[!NOTE]
   >
   > Esta propiedad sólo se aplica a los nombres de archivo y no a los nombres de carpeta.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> AEM De forma similar a la lista de caracteres de nombre de archivo válidos, también puede especificar una lista de caracteres de nombre de archivo válidos para la salida de sitio de la lista de nombres de archivo de salida de la página de datos de sitio de. AEM Para obtener más información, consulte [Configurar nombres de archivo válidos para la salida de sitio de la red de distribución de datos](conf-file-names-valid-regx-aem-site-output.md#).

**Tema principal:**&#x200B;[&#x200B; Configurar nombres de archivo](conf-file-names.md)

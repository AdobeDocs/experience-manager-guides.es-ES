---
title: Configure Regx para caracteres de nombre de archivo válidos
description: Obtenga información sobre cómo configurar Regx para caracteres de nombre de archivo válidos
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Configure Regx para caracteres de nombre de archivo válidos {#id214BD0550E8}

A partir de la versión 3.8 de AEM Guides, como administrador, puede definir una lista de caracteres especiales válidos permitidos en los nombres de archivo. En versiones anteriores, se permitía a los usuarios definir nombres de archivo que contenían caracteres especiales como `@`, `$`, `>`, etc. Estos caracteres especiales provocaban problemas al abrir temas desde el panel de mapas DITA o al hacer clic en el vínculo del tema en el índice, lo que a menudo provocaba que la página no se abriera debido a caracteres especiales en la dirección URL.

Si utiliza la configuración que le permite definir una regx para los caracteres de nombre de archivo válidos, tendrá control total sobre cómo se asignan los nombres de archivo internamente en el sistema. Puede definir una lista de caracteres especiales permitidos en los nombres de archivo. De manera predeterminada, la configuración de nombre de archivo válida contiene &quot;`a-z A-Z 0-9 - _`&quot;. Al crear un nuevo archivo, puede tener cualquier carácter especial en el título del archivo, pero internamente se reemplazará con &quot;`-`&quot; en el nombre del archivo. Por ejemplo, puede tener el título del archivo como &quot;Introducción 1&quot; o &quot;Introduction@1&quot;, el nombre de archivo correspondiente generado para ambos casos sería &quot;Introducción-1&quot;.

Cuando defina una lista de caracteres válidos, recuerde que estos caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; siempre se reemplazarán por &quot;`-`&quot;.

Si no configura la lista de caracteres especiales válidos, el proceso de creación de archivos podría dar algunos resultados inesperados. Para evitar estos errores, se recomienda encarecidamente realizar este cambio de configuración.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la regex para los caracteres de nombre de archivo válidos:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | El valor es un patrón regex. Debe tener tres caracteres básicos y la lista debe comenzar con un guión \(-\).<br> **Valor predeterminado**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> AEM De forma similar a la lista de caracteres de nombre de archivo válidos, también puede especificar una lista de caracteres de nombre de archivo válidos para la salida de sitio de la lista de nombres de archivo de salida de la página de datos de sitio de. AEM Para obtener más información, consulte [Configurar nombres de archivo válidos para la salida de sitio de la red de distribución de datos](conf-file-names-valid-regx-aem-site-output.md#).

**Tema principal:**&#x200B;[ Configurar nombres de archivo](conf-file-names.md)

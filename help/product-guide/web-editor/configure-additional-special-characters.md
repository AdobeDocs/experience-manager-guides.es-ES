---
title: Configurar caracteres especiales adicionales en la barra de herramientas del Editor Web
description: Aprenda a configurar caracteres especiales adicionales en el editor web de AEM Guides.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Cómo configurar caracteres especiales adicionales en la barra de herramientas del Editor Web

Hay una opción de acceso directo en la barra de herramientas del editor web para permitir que el autor inserte ya los caracteres especiales.
Lo mismo se puede ver en la siguiente captura de pantalla:

![Caracteres especiales](assets/special-chars.png)


Esta lista de caracteres se puede configurar aquí. Si necesita agregar más caracteres a esto, siga los siguientes pasos:

+ AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

+ Cree el archivo symbol.json en la siguiente ubicación: &#39;/apps/fmdita/xmleditor/&#39; (puede copiar el archivo predeterminado desde la ubicación &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39;)

+ Agregue la definición de carácter especial en el archivo symbol.json como:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

La estructura del archivo symbol.json se explica a continuación:

+ &quot;label&quot;: &quot;Símbolos lógicos&quot;: especifica la categoría de los caracteres especiales. En el fragmento, se define una categoría con el nombre &quot;Símbolo lógico&quot;.

+ &quot;items&quot;: define la colección de caracteres especiales de la categoría.

+ &quot;name&quot;: &quot;≥&quot;, &quot;title&quot;: &quot;Greater-Than or Equal To&quot;: Esta es la definición del carácter especial. Comienza con la etiqueta &quot;nombre&quot;, que no debe cambiarse. El nombre va seguido del carácter especial. El &quot;título&quot; es el nombre o título del carácter especial que aparece como información de objeto para ese carácter especial.

Puede definir varias definiciones de caracteres especiales dentro de una categoría.

Esto añadirá otra categoría en el cuadro de diálogo de caracteres especiales:

![Categoría de símbolo especial](assets/special-char-category.png)

![Insertar carácter especial](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Guía de instalación y configuración](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)

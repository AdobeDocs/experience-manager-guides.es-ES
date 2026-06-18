---
title: Configurar caracteres especiales adicionales en la barra de herramientas del Editor
description: Aprenda a configurar caracteres especiales adicionales en el Editor de AEM Guides.
feature: Web Editor
role: User
exl-id: 4007eb03-c100-4892-b293-f22b3f0082e2
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Cómo configurar caracteres especiales adicionales en la barra de herramientas del editor para aplicaciones locales

Hay una opción de acceso directo en la barra de herramientas del editor web para permitir que el autor inserte ya los caracteres especiales.
Lo mismo se puede ver en la siguiente captura de pantalla:

![Caracteres especiales](assets/special-chars.png)


Esta lista de caracteres se puede configurar aquí. Si necesita agregar más caracteres a esto, siga los siguientes pasos:

+ Inicie sesión en AEM y abra el modo CRXDE Lite.

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

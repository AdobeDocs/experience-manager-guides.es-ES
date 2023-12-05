---
title: Configurar los caracteres especiales permitidos
description: Aprenda a configurar los caracteres especiales permitidos
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Configurar los caracteres especiales permitidos {#id20CIL600035}

El editor web permite insertar algunos caracteres especiales de forma predeterminada. Sin embargo, puede personalizar la lista de caracteres especiales que los autores pueden insertar en sus documentos. Si personaliza la lista de caracteres especiales, sobrescribirá el conjunto predeterminado de caracteres especiales. Solo los caracteres especiales que agregue en la configuración estarán disponibles para los autores.

Siga estos pasos para sobrescribir la lista predeterminada de caracteres especiales:

1. Crear `symbols.json` en la siguiente ubicación del repositorio de Git de Cloud Manager:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Añada la definición de carácter especial en la variable `symbols.json` archivo como:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La estructura del `symbols.json` se explica a continuación:

- `"label": "Arrows"`: Esto especifica la categoría de los caracteres especiales. En el fragmento, seleccione una categoría con el nombre `"Arrows"` está definida.
- `"items"`: define la colección de caracteres especiales de la categoría.
- `"name": "←", "title": "Left Arrow"`: Esta es la definición del carácter especial. Comienza con el `"name"` etiqueta, que no debe cambiarse. El nombre va seguido del carácter especial. El `"title"` es el nombre o título del carácter especial que aparece como información de objeto para ese carácter especial.

  Puede definir varias definiciones de caracteres especiales dentro de una categoría.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)

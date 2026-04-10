---
title: Configurar los caracteres especiales permitidos
description: Aprenda a configurar los caracteres especiales permitidos
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Configurar los caracteres especiales permitidos {#id20CIL600035}

El editor web permite insertar algunos caracteres especiales de forma predeterminada. Sin embargo, puede personalizar la lista de caracteres especiales que los autores pueden insertar en sus documentos. Si personaliza la lista de caracteres especiales, sobrescribirá el conjunto predeterminado de caracteres especiales. Solo los caracteres especiales que agregue en la configuración estarán disponibles para los autores.

Las siguientes pestañas proporcionan instrucciones para sobrescribir la lista predeterminada de caracteres especiales según la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Cree el archivo `symbols.json` en la siguiente ubicación del repositorio Git de Cloud Manager:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Agregar la definición de carácter especial en el archivo `symbols.json` como:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La estructura del archivo `symbols.json` se explica a continuación:

- `"label": "Arrows"`: esto especifica la categoría de los caracteres especiales. En el fragmento, se define una categoría con el nombre `"Arrows"`.
- `"items"`: define la colección de caracteres especiales de la categoría.
- `"name": "←", "title": "Left Arrow"`: esta es la definición del carácter especial. Comienza con la etiqueta `"name"`, que no se debe cambiar. El nombre va seguido del carácter especial. `"title"` es el nombre o título del carácter especial que aparece como información de objeto para ese carácter especial.

  Puede definir varias definiciones de caracteres especiales dentro de una categoría.

>[!TAB Local]

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. crear `symbols.json` archivo en la siguiente ubicación:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Agregar la definición de carácter especial en el archivo `symbols.json` como:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La estructura del archivo `symbols.json` se explica a continuación:

- `"label": "Arrows"`: esto especifica la categoría de los caracteres especiales. En el fragmento, se define una categoría con el nombre `"Arrows"`.
- `"items"`: define la colección de caracteres especiales de la categoría.
- `"name": "←", "title": "Left Arrow"`: esta es la definición del carácter especial. Comienza con la etiqueta `"name"`, que no se debe cambiar. El nombre va seguido del carácter especial. `"title"` es el nombre o título del carácter especial que aparece como información de objeto para ese carácter especial.

Puede definir varias definiciones de caracteres especiales dentro de una categoría.

>[!ENDTABS]

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](customize-overview.md)

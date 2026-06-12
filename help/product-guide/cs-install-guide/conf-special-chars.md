---
title: Configurar los caracteres especiales permitidos
description: Aprenda a configurar los caracteres especiales permitidos
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/4E8kj37-4mj6StL4NBMzoebW6XgyfNV5e5emGg3EX8c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 208
ht-degree: 0%

---

# Configurar los caracteres especiales permitidos {#id20CIL600035}

El editor web permite insertar algunos caracteres especiales de forma predeterminada. Sin embargo, puede personalizar la lista de caracteres especiales que los autores pueden insertar en sus documentos. Si personaliza la lista de caracteres especiales, sobrescribirá el conjunto predeterminado de caracteres especiales. Solo los caracteres especiales que agregue en la configuración estarán disponibles para los autores.

Siga estos pasos para sobrescribir la lista predeterminada de caracteres especiales:

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


**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)

---
title: Configurar los caracteres especiales permitidos
description: Aprenda a configurar los caracteres especiales permitidos
exl-id: 3dd7752e-0836-480a-b1e1-6fa2099d404f
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/vKiBbH1skwiRRU-VETpOk3YCCAm-Lr-Cbh335E-Q7Z8'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%
---
# Configurar los caracteres especiales permitidos {#id20CIL600035}

El editor web permite insertar algunos caracteres especiales de forma predeterminada. Sin embargo, puede personalizar la lista de caracteres especiales que los autores pueden insertar en sus documentos. Si personaliza la lista de caracteres especiales, sobrescribirá el conjunto predeterminado de caracteres especiales. Solo los caracteres especiales que agregue en la configuración estarán disponibles para los autores.

Siga estos pasos para sobrescribir la lista predeterminada de caracteres especiales:

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


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)

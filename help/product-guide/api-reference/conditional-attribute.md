---
title: La API de REST funciona con atributos condicionales
description: Obtenga información acerca de la API de REST para trabajar con atributos condicionales
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2:
  - id: d27d524e-c4e5-4b77-b86b-3db049db0b25
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 5%

---

# La API de REST funciona con atributos condicionales {#id175UB30E05Z}

La siguiente API de REST permite agregar atributos condicionales en un perfil de carpeta.

## Añadir un atributo condicional en un perfil de nivel de carpeta

Método POST que agrega atributos condicionales a un perfil de nivel de carpeta determinado.

**URL de solicitud**:\
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/folderprofiles

**Parámetros**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `:operation` | Cadena | Sí | Nombre de la operación a la que se llama. El valor de este parámetro es ``ADDATTRIBUTEPROFILES``. <br> **Nota:** El valor no distingue entre mayúsculas y minúsculas. |
| `profilename` | Cadena | Sí | Nombre para mostrar del perfil de nivel de carpeta en el que se deben agregar los atributos condicionales. |
| `conditionalprofiles` | Matriz JSON | Sí | Matriz JSON que consta del nombre del atributo condicional y sus valores. El siguiente fragmento de código de ejemplo muestra la matriz JSON con dos atributos: `platform` y `product` con varios valores asignados a ellos. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Valores de respuesta**:\
Devuelve una respuesta HTTP 200 \(Correcto\).

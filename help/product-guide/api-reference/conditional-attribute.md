---
title: La API de REST funciona con atributos condicionales
description: Obtenga información acerca de la API de REST para trabajar con atributos condicionales
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# La API de REST funciona con atributos condicionales {#id175UB30E05Z}

La siguiente API de REST permite agregar atributos condicionales en un perfil de carpeta.

## Añadir un atributo condicional en un perfil de nivel de carpeta

Método de POST que agrega atributos condicionales a un perfil determinado de nivel de carpeta.

**URL de solicitud**:\
http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/folderprofiles

**Parámetros**:\
|Nombre|Tipo|Descripción|Requerida| ----|----|--------|----------- |`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es ``ADDATTRIBUTEPROFILES``. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas.| |`profilename`|Cadena|Sí|Nombre para mostrar del perfil de nivel de carpeta en el que se deben agregar los atributos condicionales.| |`conditionalprofiles`|Matriz JSON|Sí|Matriz JSON que consta del nombre y los valores del atributo condicional. El siguiente fragmento de código de ejemplo muestra la matriz JSON con dos atributos: `platform` y `product` con varios valores asignados a ellos.|

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

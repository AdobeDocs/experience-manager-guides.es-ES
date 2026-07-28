---
title: La exportación de metadatos falla con la excepción "La cadena es demasiado larga" en Experience Manager Guides
description: Comprenda por qué la exportación de metadatos puede fallar para el contenido de las guías en la IU de Assets.
feature: Authoring, Publishing
role: User
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 1c61df4820e559417410d25c81800637481b040c
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 0%

---

# ¿Por qué la exportación de metadatos para una carpeta falla con la excepción &quot;La cadena es demasiado larga&quot;?

Cuando [exporta metadatos](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/using/metadata#export-metadata) para una carpeta desde la interfaz de usuario de Assets, el trabajo de exportación puede fallar con la excepción `String is too long`. Esto suele ocurrir cuando la carpeta contiene propiedades específicas de Experience Manager Guides que almacenan valores que no son de cadena, como `baselineObj`.

**¿Por qué ocurre esto?**

Experience Manager Guides utiliza internamente algunas propiedades almacenadas en el nodo de metadatos de un recurso y contienen datos, como objetos JSON, en lugar de valores de cadena sin formato. Al exportar metadatos para una carpeta, si **Properties to be export** está establecido en **All**, el trabajo de exportación intenta convertir cada propiedad en una cadena y produce un error en las propiedades que contienen este tipo de datos.

**¿Cómo se evita?**

Para evitar este error, las siguientes propiedades se excluyen de la exportación de metadatos de forma predeterminada en la **configuración del exportador de metadatos de recursos**:

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**¿Todavía puedo exportar estas propiedades?**

Sí. Si necesita una o más de estas propiedades en la exportación, puede editar la **configuración del exportador de metadatos de recursos** y quitarlas de la lista de exclusión.

La eliminación de una propiedad de la lista de exclusión no garantiza que la exportación se realice correctamente. Según el tamaño y el contenido de los datos subyacentes, el trabajo puede fallar con la misma excepción. Si se encuentra con esto después de volver a habilitar una propiedad, agréguela de nuevo a la lista de exclusión para restaurar el comportamiento de exportación predeterminado y confiable.

---
title: Eliminar la opción "Eliminar" del menú contextual del archivo en el editor web para usuarios específicos
description: Aprenda a personalizar el editor web eliminando la opción "Eliminar" del menú contextual del archivo para usuarios/grupos específicos
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 0%

---

# Quitar la opción &quot;Eliminar&quot; del menú contextual del archivo en el editor web

En este artículo aprenderemos a ocultar la opción &quot;Eliminar&quot; del menú contextual de archivos en AEM Guides Web Editor para usuarios o grupos específicos. Para otras personalizaciones en las opciones del menú contextual de archivo, consulte Extensión de las guías. Se pueden encontrar más detalles [aquí](https://github.com/adobe/guides-extension/tree/main).

Como puede ver en el siguiente fragmento, el menú contextual del archivo tiene la opción &#39;Eliminar&#39; disponible para este usuario específico.

![Menú contextual de archivo con Eliminar](../../../assets/authoring/file-contextmenu-Delete.png)

Ahora veamos cómo podemos ocultar la opción &quot;Eliminar&quot; para este usuario.

## Pasos de implementación:

- Vaya a Herramientas > Seguridad > Permisos de la página de inicio de AEM.
- Elija el grupo o usuario en el cuadro de búsqueda.
- Haga clic en &quot;Añadir ACE&quot; en la esquina superior derecha.
- Elija la ruta de la carpeta.
- Incluir privilegios &quot;jcr:removeChildNodes&quot; y &quot;jcr:removeNode&quot;.
- Elija &quot;Tipo de permiso&quot; como &quot;denegado&quot; y haga clic en &quot;Agregar&quot; como se muestra a continuación.

![Permiso de usuario denegado ACE](../../../assets/authoring/permission-ACE-Delete.png)

![Lista de control de acceso en permisos](../../../assets/authoring/delete-acl.png)

### Pruebas

- Inicie sesión en AEM como el usuario para el que se han agregado los ACE.
- Abra el editor web.
- Vaya a la vista del repositorio y elija la carpeta para la que se han agregado las ACE.
- Abra el menú contextual del archivo.
- La opción &quot;Eliminar&quot; no aparecerá en el menú contextual.

El menú contextual del archivo ahora tendrá este aspecto:

![Menú contextual de archivo sin eliminar](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Web Editor as they are also tied to delete process at the backend.
```

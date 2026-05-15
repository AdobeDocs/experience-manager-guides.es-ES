---
title: Aumente el rendimiento de traducción de los archivos DITA en las guías de AEM
description: Prácticas recomendadas, sugerencias y trucos para aumentar el rendimiento del proyecto de traducción DITA en AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
TQID: https://experienceleague.adobe.com/n6-b3-ZsOIueVYWgcm1NkDLKRAOwQhWxctbgj7Q6P1U
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 0%

---

# Prácticas recomendadas a seguir para la traducción en AEM Guides

El rendimiento del proyecto de traducción puede disminuir a medida que la actividad de traducción en el sistema aumenta con el tiempo.

Cada proyecto de traducción genera varios grupos de usuarios para el acceso, lo que provoca un aumento en el número de grupos de usuarios dentro del sistema. A medida que se amplía el número de grupos de usuarios, puede ralentizar gradualmente las operaciones de CRUD relacionadas con los permisos de usuario, lo que podría afectar al rendimiento general de AEM. Además, si los proyectos de traducción permanecen activos después de completarse, puede afectar negativamente al rendimiento de la sincronización de traducción entre AEM y el proveedor de traducción.

**Seguir las prácticas recomendadas descritas a continuación ayudará a mantener un entorno eficiente.**

## Si su versión de es anterior a la 4.6 (local) o a la 2404 (en la nube):

- Marcar todos los proyectos como &quot;Inactivos&quot; una vez completada y aprobada la traducción.El proyecto permanece disponible para su revisión y se marca simplemente como inactivo.
   - Seguir estos pasos ayudará a mantener el rendimiento general de la traducción en buen estado de salud.
     ![Proyecto De Traducción Inactivo &#x200B;](../assets/translation/translation-project-image1.png)

- La carpeta de proyectos más antiguos, que está marcada como inactiva, aprobada y revisada, debe eliminarse
   - Seguir estos pasos ayudará a mantener el rendimiento general de la traducción en buen estado al limpiar los archivos de traducción temporales y los grupos de usuarios asociados a esta carpeta de proyecto.
     ![Eliminar proyecto de traducción y carpeta &#x200B;](../assets/translation/translation-project-image2.png)


## Si está en, versión 4.6 o 2404 o posterior:

Puede seguir siguiendo los mismos pasos que se mencionaron anteriormente. A partir de la versión 4.6/2404, AEM Guides introduce una configuración de editor para que los administradores desactiven la eliminación automática de proyectos de traducción.

Consulte: [Eliminar o deshabilitar automáticamente un proyecto de traducción completado](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Configuración automatizada para eliminar y deshabilitar el proyecto de traducción en AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)

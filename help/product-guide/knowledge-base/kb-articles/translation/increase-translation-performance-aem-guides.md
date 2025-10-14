---
title: AEM Aumente el rendimiento de traducción de los archivos DITA en las guías de la
description: Prácticas recomendadas, sugerencias y trucos para aumentar el rendimiento del proyecto de traducción DITA en AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
source-git-commit: 18fe3cbb1439d489d243d98a546ef1095104a863
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Prácticas recomendadas a seguir para la traducción en AEM Guides

El rendimiento del proyecto de traducción puede disminuir a medida que la actividad de traducción en el sistema aumenta con el tiempo.

Cada proyecto de traducción genera varios grupos de usuarios para el acceso, lo que provoca un aumento en el número de grupos de usuarios dentro del sistema. AEM A medida que se expande el número de grupos de usuarios, puede ralentizar gradualmente las operaciones de CRUD relacionadas con los permisos de usuario, lo que podría afectar al rendimiento general. AEM Además, si los proyectos de traducción permanecen activos después de completarse, puede afectar negativamente al rendimiento de la sincronización de traducción entre los proveedores de traducción y los de la aplicación de la traducción de la traducción de los proyectos de traducción de los que se dispone en el sitio web.

**Seguir las prácticas recomendadas descritas a continuación ayudará a mantener un entorno eficiente.**

## Si su versión de es anterior a la 4.6 (local) o a la 2404 (en la nube):

- Marcar todos los proyectos como &quot;Inactivos&quot; una vez completada y aprobada la traducción. El proyecto permanece disponible para su revisión y se marca simplemente como inactivo.
   - Seguir estos pasos ayudará a mantener el rendimiento general de la traducción en buen estado de salud.

     ![Proyecto De Traducción Inactivo &#x200B;](../assets/translation/translation-project-image1.png)

- La carpeta de proyectos más antiguos, que está marcada como inactiva, aprobada y revisada, debe eliminarse
   - Seguir estos pasos ayudará a mantener el rendimiento general de la traducción en buen estado al limpiar los archivos de traducción temporales y los grupos de usuarios asociados a esta carpeta de proyecto.

     ![Eliminar proyecto de traducción y carpeta &#x200B;](../assets/translation/translation-project-image2.png)


## Si está en, versión 4.6 o 2404 o posterior:

Puede seguir siguiendo los mismos pasos que se mencionaron anteriormente. A partir de la versión 4.6/2404, AEM Guides introduce una configuración de editor para que los administradores desactiven la eliminación automática de proyectos de traducción.

Consulte: [Eliminar o deshabilitar automáticamente un proyecto de traducción completado](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Configuración automatizada para eliminar y deshabilitar el proyecto de traducción en AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)

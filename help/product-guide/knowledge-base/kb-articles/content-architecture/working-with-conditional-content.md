---
title: Trabajo con contenido condicional
description: Aprenda a crear condiciones y, a continuación, configure la generación de contenido condicional en  [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
TQID: https://experienceleague.adobe.com/3Gz6-sJn7dvzJSlnKgRoRqpFTqtj5fiVlAjOv0lbD1o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 0%

---

# Trabajo con contenido condicional

**Caso de uso**

* Los autores pueden establecer condiciones en un fragmento de contenido para poder controlar si se muestra en la salida.

* Los autores pueden elegir al publicar la publicación mostrar u ocultar diferentes condiciones.

* Por ejemplo, los autores pueden agregar atributos como versión 1.0 y versión 2.0 en el contenido y utilizar condiciones para incluir la versión 1.0 para la versión 1.0 y excluir la versión 2.0.

**Paso 1**

Defina las condiciones relevantes para la documentación en [!UICONTROL Perfiles de carpeta]:
Consulte la sección **Configurar atributos condicionales para perfiles globales o de nivel de carpeta** en [Página 69 de la Guía de instalación y configuración](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Configurar condiciones en perfiles de carpeta](assets/conditions-in-profiles.png)

**Paso 2**

Seleccione el **[!UICONTROL Perfil de carpeta]** definido en el paso 1 de **Preferencias de usuario** en el Editor XML:
Consulte la sección **Preferencias de usuario** en [Página 41 de la Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Paso 3**

Utilice las condiciones para condicionalizar secciones de contenido:
Consulte la sección **Condiciones** en [Página 90 de la Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Usar condiciones en el editor web](assets/conditions-in-web-editor.png)

**Paso 4**

Defina los ajustes preestablecidos de condición en el nivel de mapa para elegir qué condiciones habilitar en la salida
Consulte la sección **Usar ajustes preestablecidos de condición** en [Página 249 de la Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

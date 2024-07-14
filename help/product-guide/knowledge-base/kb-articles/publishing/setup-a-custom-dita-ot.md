---
title: Configurar DITA-OT personalizado en  [!DNL AEM Guides]
description: Aprenda a configurar DITA-OT personalizado en  [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# AEM Configurar DITA-OT personalizado en [!DNL AEM Guides] para su uso en el espacio de trabajo de la

Los pasos para agregar un DITA-OT personalizado se documentan en la sección _Usar complementos DITA-OT personalizados_ de la _Guía de instalación y configuración_.

En un nivel superior, los pasos son:

+ Obtenga la DITA-OT básica
   + Si desea obtener una copia de DITA-OT predeterminada de [!DNL AEM Guides], descárguela de la ruta de acceso `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Si desea obtener una versión diferente, puede descargar desde [dita-ot repo](https://www.dita-ot.org/download)
+ Realice cambios en DITA-OT como [agregar nuevo complemento](https://www.dita-ot.org/dev/topics/plugins-installing.html) o personalizar complementos existentes (consulte el ejemplo en la sección Vínculos relacionados a continuación)
+ Cargar `DITA-OT.zip` recibido en `/apps/<project-folder>/dita_resources` (se recomienda crear una carpeta de proyecto personalizada)
+ Agregar un perfil DITA mediante **[!UICONTROL Herramientas]** > **[!UICONTROL Guías]** > **[!UICONTROL Perfiles DITA]** (use la ruta DITA-OT donde se cargó el DITA-OT personalizado, consulte la captura de pantalla siguiente)
  ![Perfiles DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalizar ejemplos de complementos DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)

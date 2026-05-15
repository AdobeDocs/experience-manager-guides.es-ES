---
title: Configurar DITA-OT personalizado en  [!DNL AEM Guides]
description: Aprenda a configurar DITA-OT personalizado en  [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# Configurar DITA-OT personalizado en [!DNL AEM Guides] para AEM

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

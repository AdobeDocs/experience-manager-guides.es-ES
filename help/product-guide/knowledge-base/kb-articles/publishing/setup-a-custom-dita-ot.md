---
title: Configuración de DITA-OT personalizado en [!DNL AEM Guides]
description: Obtenga información sobre cómo configurar DITA-OT personalizado en [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Configuración de DITA-OT personalizado en [!DNL AEM Guides] AEM para la

Los pasos para agregar una DITA-OT personalizada se documentan en la sección _Uso de complementos DITA-OT personalizados_ de la _Guía de instalación y configuración_.

En un nivel superior, los pasos son:

+ Obtenga la DITA-OT básica
   + Si desea obtener una copia de DITA-OT de forma predeterminada de [!DNL AEM Guides], descargarlo desde la ruta `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Si desea obtener una versión diferente, puede descargar desde [repositorio dita-ot](https://www.dita-ot.org/download)
+ Realice cambios en DITA-OT como [agregar nuevo complemento](https://www.dita-ot.org/dev/topics/plugins-installing.html)o personalizar complementos existentes (consulte el ejemplo en la sección vínculos relacionados a continuación).
+ Cargar `DITA-OT.zip` recibido a `/apps/<project-folder>/dita_resources` (se recomienda crear una carpeta de proyecto personalizada)
+ Añadir perfil DITA mediante **[!UICONTROL Herramientas]** > **[!UICONTROL Guías]** > **[!UICONTROL Perfiles DITA]** (utilice la ruta DITA-OT donde se carga el DITA-OT personalizado; consulte la siguiente captura de pantalla)
  ![Perfiles DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalizar ejemplos de complementos DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)

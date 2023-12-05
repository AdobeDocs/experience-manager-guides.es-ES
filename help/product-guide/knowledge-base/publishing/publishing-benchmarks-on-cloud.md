---
title: Guías que publican puntos de referencia en AEMaaCS
description: AEM Comprender los límites del sistema en la publicación en Cloud de.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 8%

---

# AEM Análisis de publicación de guías de AEM en AEMaaCS

AEM Actualmente, el servicio en la nube de Guides tiene algunos límites en la publicación de tamaños de mapa que el equipo de Guides está trabajando activamente para resolver.

El equipo de Guides ha introducido un microservicio de publicación escalable para admitir mapas grandes y varias publicaciones simultáneas. Para obtener más información sobre el nuevo microservicio de publicación, consulte [publicación de arquitectura de microservicios](publish-microservice-architecture-and-performance.md)

AEM Para configurar el nuevo servicio de publicación para cualquier entorno en la nube de, consulte [configurar nueva publicación basada en microservicios](configure-microservices.md)


## Entorno de ejecución

    AEM Versión de la versión: 2023.5.11983.20230511T173830Z
    Versión del complemento de la guía: 2023.6.0
    AEM AEM Plantilla de sitio de la página: Guías de la páginaPlantilla de OOTB
    Versión de DITA-OT: 3.5.4
    Tipo de flujo de trabajo de publicación: dividir flujo de trabajo de publicación
    Salida admitida por el microservicio: PDF nativo, PDF (Dita-OT)

## Números de generación de salida

| Tipo de salida | Tamaño del mapa (referencias del tema) | Tiempo de ejecución (en segundos) | Microservicio de publicación |
|---------------|------------------------------|----------------------------|-----------------------|
| AEM Sitio web de | 3500 | 5220 | No |
| PDF nativo | 3500 | 780 | Sí |
| PDF (DITA-OT) | 11000 | 960 | Sí |
| HTML5 | 3500 | 240 | No |
| Personalizado | 300 | 300 | No |

## Puntos clave que recordar

- AEM El sitio crea muchos nodos y acoplamientos cq:Page procesándolos individualmente durante el tiempo de generación. AEM Por este motivo, es aconsejable evitar la ejecución de grandes publicaciones de sitios de varios grupos de informes simultáneos, ya que puede sobrecargar al sistema.
- AEM El tiempo de generación del sitio depende de la plantilla utilizada. El tiempo de ejecución puede aumentar si se utiliza una plantilla compleja.
- El tiempo de ejecución de la publicación personalizada es para una salida personalizada de ejemplo. El tiempo de publicación personalizado solo depende de la propia lógica de transformación del cliente.

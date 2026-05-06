---
title: Guías que publican puntos de referencia en AEMaaCS
description: Comprenda los límites del sistema para la publicación en AEM Cloud.
feature: Publishing
role: User, Admin
source-git-commit: b6e4fd5051018ce6c60aadf66e6bf7375322aaa1
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 20%

---

# Parámetros de publicación de AEM Guides en AEMaaCS

Este análisis de rendimiento evalúa el rendimiento de las nuevas API de publicación en diferentes ajustes preestablecidos de salida y el aumento del tamaño de los mapas en AEM Guides as a Cloud Service. El objetivo es comprender el comportamiento de la escalabilidad e identificar los cuellos de botella del rendimiento.

El servicio de publicación usa una [arquitectura basada en microservicios](https://experienceleague.adobe.com/es/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) con escalado automático, lo que permite administrar cargas de trabajo más grandes mediante pods adicionales.

## Entorno de ejecución

- **Versión de AEM**:2026.4.25322.20260407T085152Z
- **Versión del complemento de guías**: 2026.5.0
- **Recuento inicial de pod**: 2 pods
- **Comportamiento de escalado automático**: se escaló hasta 4 pods en 4 nodos a medida que aumentó la carga
- **CPUv**: 10
- **RAM por pod**: 8 GB
- **Usuarios simultáneos**: 1 usuario

>[!NOTE]
>
> Este ejercicio se centró en cómo se comporta la publicación a medida que aumenta el tamaño del mapa, destacando el impacto de los mapas más grandes en el rendimiento, la latencia y la finalización de la publicación general bajo carga.


## Números de generación de salida

**Sitio nativo de AEM**

| MapSize | Tiempo(s) de ejecución | Microservicio |
| ------- | ------------------ | ------------ |
| 10 | 62.378 | Sí |
| 100 | 64.27 | Sí |
| 1000 | 93.091 | Sí |
| 5000 | 496.319 | Sí |
| 10000 | 922.602 | Sí |

**PDF nativo**

| MapSize | Tiempo(s) de ejecución | Microservicio |
| ------- | ------------------ | ------------ |
| 10 | 62.302 | Sí |
| 100 | 62.431 | Sí |
| 1000 | 108.666 | Sí |
| 5000 | 201.379 | Sí |
| 10000 | 1170.689 | Sí |

**PDF**

| MapSize | Tiempo(s) de ejecución | Microservicio |
| ------- | ------------------ | ------------ |
| 10 | 30.926 | Sí |
| 100 | 30.987 | Sí |
| 1000 | 77.007 | Sí |
| 5000 | 247.505 | Sí |
| 10000 | 686.61 | Sí |

**HTML5**

| MapSize | Tiempo(s) de ejecución | Microservicio |
| ------- | ------------------ | ------------ |
| 10 | 30.844 | Sí |
| 100 | 30.834 | Sí |
| 1000 | 77.384 | Sí |
| 5000 | 170.237 | Sí |
| 10000 | 419.166 | Sí |


## Observaciones clave

- El tiempo de generación del sitio de AEM depende de la plantilla que se utilice. El tiempo de ejecución puede aumentar si se utiliza una plantilla compleja.
- El tiempo de ejecución de la publicación personalizada se basa en una salida personalizada de ejemplo. El tiempo de publicación personalizado solo depende de la propia lógica de transformación del cliente.
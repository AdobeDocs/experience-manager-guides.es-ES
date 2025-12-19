---
title: Migración de contenido de no UUID a UUID
description: Obtenga información sobre cómo migrar contenido que no es UUID a UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Migración de contenido de no UUID a UUID {#id226TI0U20XA}


Puede migrar el contenido que no sea UUID a UUID en función de la versión actual de Experience Manager Guides que esté utilizando.

>[!IMPORTANT]
>
> Antes de migrar contenido al servidor UUID, asegúrese de que tiene instalado un servidor que no sea UUID con una versión compatible de AEM Guides.

## Matriz de compatibilidad

Utilice la siguiente matriz para determinar la ruta de migración correcta en función de su versión actual que no sea UUID. Esto garantiza una transición sin problemas después de la migración.

| Versión no UUID necesaria para la migración | Versión de UUID después de la migración | Ruta de actualización admitida después de la migración |
|---|---|---|
| 4.3.1 no UUID | 4.3.2 UUID | Después de migrar a la versión 4.3.2 UUID, debe instalar directamente la 4.6.0 (UUID). Una vez que esté en 4.6.0, actualice a la versión 5.1.0 y luego instale el paquete de servicio 3 5.1.0. |
| Paquete de servicio 4 4.6.0 no UUID | UUID 4.6.1 | Después de migrar a la versión 4.6.1 UUID, debe actualizar directamente a la 5.1.0 (UUID). Una vez completada la actualización, instale la versión 5.1.0 del paquete de servicio 3. |

## Estimación del tiempo de migración

La utilidad de migración procesa los recursos a una velocidad media de ~50 ms por recurso. La siguiente tabla proporciona estimaciones del tiempo de migración para un sistema configurado con 64 vCPU, 128 GB de RAM y almacenamiento respaldado por SSD. Los requisitos de memoria pueden aumentar para repositorios más grandes o recursos con muchas representaciones o binarios de alta resolución.

>[!NOTE]
>
> El tiempo real de migración puede variar según el rendimiento del hardware, el rendimiento del almacenamiento, las actividades simultáneas de AEM y la carga general del sistema.


| **Recuento de recursos** | **Aprox. Hora** |
|-----------------|-------------------------|
| 10K | ~8-9 minutos |
| 50K | ~42 minutos |
| 100K | ~1,4 horas |
| 250K | ~3,5 horas |
| 500K | ~7 horas |
| 750K | ~10,5 horas |
| 1 M | ~14 horas |
| 2 M | ~28 horas (~1,2 días) |
| 3M | ~42 horas (~1,75 días) |
| 5M | ~69 horas (~2,9 días) |
| 10M | ~139 horas (~5,8 días) |


Para ver los pasos detallados sobre la migración del contenido, consulte los siguientes artículos:

- [**4.3.1 sin UUID a 4.3.2 Migración de contenido UUID**](./migrate-non-uuid-4-3.md)
- [Migración de contenido de UUID del paquete de servicio 4 **4.6.0 sin UUID a 4.6.1**](./migrate-non-uuid-uuid-4-6.md)




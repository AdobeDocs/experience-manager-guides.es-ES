---
title: Migración de contenido de no UUID a UUID
description: Obtenga información sobre cómo migrar contenido que no es UUID a UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: e38cd858201ea657ce276eb4b358b0d4eff502b2
workflow-type: tm+mt
source-wordcount: '205'
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
| 4.3.1 no UUID | 4.3.2 UUID | Después de migrar al UUID versión 4.3.2, puede instalar directamente la versión 4.6.0 (UUID). Una vez que esté en 4.6.0, actualice a la versión 5.1.0 y luego instale el paquete de servicio 1 5.1.0. |
| Paquete de servicio 4 4.6.0 no UUID | UUID 4.6.1 | Después de migrar al UUID versión 4.6.1, puede actualizar directamente a la versión 5.1.0 (UUID). Una vez completada la actualización, instale la versión 5.1.0 del paquete de servicio 1. |

Para ver los pasos detallados sobre la migración del contenido, consulte los siguientes artículos:

- [**4.3.1 sin UUID a 4.3.2 Migración de contenido UUID**](./migrate-non-uuid-4-3.md)
- [Migración de contenido de UUID del paquete de servicio 4 **4.6.0 sin UUID a 4.6.1**](./migrate-non-uuid-uuid-4-6.md)




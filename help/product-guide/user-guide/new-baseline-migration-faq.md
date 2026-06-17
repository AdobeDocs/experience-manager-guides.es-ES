---
title: Preguntas frecuentes sobre la nueva migración de línea de base en Adobe Experience Manager Guides
description: Obtenga información acerca de las preguntas más frecuentes sobre la nueva migración de línea de base en Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: 919
ht-degree: 0%

---

# Nuevas preguntas frecuentes sobre migración de línea base

Estas preguntas frecuentes tratan sobre preguntas comunes relacionadas con la migración a la nueva línea de base, los cambios de comportamiento, las consideraciones de migración y los resultados esperados al actualizar al nuevo modelo de línea de base.

## ¿Cuáles son las principales ventajas de migrar a la nueva línea de base?

El nuevo modelo de línea base ofrece varias mejoras, entre las que se incluyen:

- Rendimiento y escalabilidad mejorados
- Mejor coherencia de la IU y del servidor
- Comportamiento determinístico de edición y guardado
- Funciones de filtrado y navegación mejoradas
- Previsualizaciones de impacto de dependencias
- Fiabilidad mejorada durante la creación y las actualizaciones de línea de base
- Mejor compatibilidad con API y automatización

## ¿La migración de línea base crea nuevas líneas base para todas las versiones de un mapa?

No, el proceso de migración crea nuevas líneas de base solo para la **copia de trabajo actual** del mapa. Las líneas bases asociadas con otras copias de trabajo no se incluyen en la migración.

## ¿Qué sucede cuando un usuario vuelve a una versión anterior de un mapa?

Cuando se restaura o se accede a una versión anterior de un mapa, las líneas base asociadas con esa versión se migran automáticamente al nuevo modelo de línea base mediante un proceso de migración asincrónica.

## ¿Se migran las referencias no válidas a la nueva línea base?

No, las referencias no válidas se omiten durante la migración para mantener la coherencia de la línea de base y garantizar la fiabilidad de la línea de base migrada.

## ¿Cambia la migración de línea de base la línea de base?

La migración prevista conserva todo el contenido y las referencias de línea de base válidas exactamente como son. Sin embargo, las referencias no válidas no se incluyen en la línea base migrada. Aparte de la eliminación de referencias no válidas, la migración no introduce ningún cambio en las referencias o en el comportamiento de resolución de dependencias.

Cualquier cambio adicional en las referencias o en la resolución de dependencias sólo puede producirse después de modificar, volver a generar o crear la línea base migrada con el nuevo modelo de línea base.

Hasta que se realice una de estas acciones, la línea base migrada seguirá reflejando la definición de línea base original.

## ¿Se incluyen las referencias `reltable` en el nuevo modelo de línea base?

No, las referencias que se originan en `reltable` elementos se excluyen de la resolución de línea de base, coherente con el comportamiento del modelo de línea de base heredado.

## ¿Cómo se gestionan las referencias DIRECTAS en la nueva línea base?

En el modelo Nueva línea de base, las referencias de mapa directo se clasifican explícitamente como referencias **DIRECT**. Durante la migración y la resolución de la línea de base, estas referencias tienen la prioridad más alta y se resuelven antes que todos los demás tipos de referencia.

## ¿Se incluyen las referencias `scope="peer"` en la línea de base?

No, las referencias con `scope="peer"` no se incluyen en el modelo de línea de base. Excluir estas referencias mejora el rendimiento de publicación y evita una resolución de dependencias innecesaria.

## ¿Se pueden seguir administrando las líneas de base desde el panel de mapas?

No, la administración de la línea de base solo se admite desde la **consola de mapas** en la nueva línea de base. No se admite la creación y administración de líneas de base desde el **panel de mapa**.

## ¿Se requiere alguna precaución durante la migración?

Sí, las modificaciones de línea de base deben evitarse mientras se produce una migración, especialmente en las copias de trabajo. Realizar cambios en las líneas de base durante la migración puede provocar errores de migración y dejar las líneas de base en un estado incoherente.

## ¿Qué sucede si faltan versiones después de la migración?

Es posible que algunas líneas base deban reconstruirse después de la migración si las versiones a las que hacen referencia ya no están disponibles o no son accesibles.


## ¿Cuál es el tiempo aproximado necesario para migrar líneas base para una configuración On-Premise?

El tiempo de migración depende de varios factores, entre ellos:

- Número de líneas de base que se migran
- Número total de referencias entre esas líneas de base
- Tamaño y complejidad del repositorio
- Configuración de hardware
- Recursos del sistema disponibles

Según las pruebas internas y las observaciones de repositorios que contienen aproximadamente 18 000 referencias, la duración de la migración puede variar significativamente según la estructura del repositorio y el entorno operativo.

| Ámbito de migración | Duración típica |
|-----------------|------------------|
| Línea base única | Unos segundos |
| 10 a 15 líneas de base | Unas pocas decenas de segundos |
| 25 a 50 líneas de base | Aproximadamente 1-2 minutos |

>[!NOTE]
>
> Estas cifras se proporcionan solo como referencia y se basan en un entorno On-Premise. Los valores reales pueden variar según la complejidad del repositorio, la capacidad de la infraestructura, la configuración del hardware y las condiciones generales de funcionamiento.

## ¿Podemos volver a las líneas de base antiguas?

Sí. Sin embargo, cuando se realiza una reversión, las líneas de base antiguas se restauran al estado en el que se encontraban en el momento de la migración. Los cambios realizados mientras la configuración de línea base antigua está desactivada y la nueva configuración de línea base está activa no se reflejan en las líneas base restauradas.

Los objetos de línea de base originales permanecen disponibles en su ubicación original. Cuando se desactiva la nueva configuración de instantánea, el sistema vuelve automáticamente a utilizar los objetos originales.

## ¿Cómo podemos migrar a nuevas líneas de base?

Para migrar a una línea de base nueva, siga los pasos de [Migrar a una línea de base nueva](./web-editor-baseline-v2.md#migrate-to-new-baseline).

## ¿Podemos migrar a la nueva línea de base en cualquier momento? ¿Hay algún requisito previo?

Sí. Puede habilitar la nueva línea de base en cualquier momento, siempre que su entorno cumpla los requisitos mínimos de versión.

**Requisitos previos:**

- AEM Guides (local): versión 5.2 o posterior
- AEM Guides (Cloud Service): Versión 2026.05.0 o posterior

Una vez cumplidos estos requisitos, puede migrar las antiguas líneas de base existentes al nuevo modelo de línea de base y empezar a utilizar sus capacidades.

## ¿Es necesario realizar una copia de seguridad del estado del servidor actual antes de migrar a la nueva línea de base?

No se requiere una copia de seguridad adicional específicamente para la migración a la nueva línea de base.

Sin embargo, las líneas base asociadas con la copia de trabajo se pueden perder si un usuario realiza posteriormente una operación de reversión de la versión. Este comportamiento no es exclusivo del nuevo modelo de línea base; si se revierte a una versión anterior también se pueden eliminar los nodos de copia de trabajo de la línea base anterior correspondientes.

Si es importante conservar las líneas de base de copia de trabajo, se recomienda realizar una copia de seguridad de ellas antes de la migración. Después de la migración, los usuarios trabajarán principalmente con nuevas líneas de base, pero una versión posterior revertida puede causar la pérdida de las líneas de base de la copia de trabajo.



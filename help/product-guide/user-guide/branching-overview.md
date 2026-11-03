---
title: Bifurcación en AEM Guides | Adobe Experience Manager Guides`
description: Aprenda a crear y administrar ramas de un mapa DITA en AEM Guides para admitir la creación paralela, la publicación independiente y la combinación de cambios de documentación.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 3f0d8e31537ade58a4eab5ddf73eb6d263d3dd96
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%
---
# Información general

>[!NOTE]
>
> La función de ramificación y combinación se introdujo en la versión 2026.11.0 de Experience Manager Guides as a Cloud Service y está desactivada de forma predeterminada. Para habilitar la función para su entorno, póngase en contacto con el equipo de éxito del cliente.

La bifurcación en Adobe Experience Manager Guides le permite crear y administrar varias ramas desde la rama **main** para que un mapa DITA funcione en diferentes versiones de documentación en paralelo. Cada rama permite a los autores administrar los cambios de contenido de forma independiente, sin afectar al contenido correspondiente en otras ramas.

Con la bifurcación, varios equipos pueden trabajar simultáneamente en distintas versiones, funciones o correcciones asociadas al mismo mapa DITA. Puede combinar los cambios de una rama en la rama predeterminada (`main`) cuando las actualizaciones estén listas.

## Funcionamiento de la bifurcación

Puede crear una rama a partir de **main** o cualquier rama existente de un mapa DITA. Después de crear una rama, puede cambiar a ella y comenzar a editar el mapa y su contenido. También puede publicar contenido de la rama seleccionada o combinar cambios en `main` cuando esté listo.

Por ejemplo, considere un mapa DITA denominado `install-the-lift.ditamap` que contenga instrucciones de instalación para un producto. Su equipo de documentación puede crear dos ramas de este mapa a partir de `main`:

- **Versión 1:** El equipo A mantiene las instrucciones de instalación existentes y corrige las direcciones.
- **Versión 2:** Equipo B desarrolla instrucciones de instalación para nuevas características.

Ambos equipos pueden trabajar de forma independiente en sus respectivas ramas de mapas sin afectar a los cambios de los demás.

>[!NOTE]
>
>Se crea una rama basada en un mapa DITA. También puede agregar y editar temas a los que no haga referencia el mapa dentro de la rama seleccionada. Para obtener más información, vea [Abrir o editar temas fuera del mapa actual](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

Cuando se crea una rama de un mapa DITA, Experience Manager Guides no copia automáticamente los temas a los que se hace referencia en el mapa en la nueva rama. Los temas que no han cambiado se leen desde la rama de origen o la rama predeterminada (principal). Un tema se copia en la nueva rama solo cuando lo edita y lo guarda en esa rama.

Por ejemplo, un mapa DITA hace referencia a 100 temas y el repositorio contiene 50 temas adicionales a los que el mapa no hace referencia. Al crear una rama nueva (versión 1.0), los 100 temas a los que se hace referencia pasan a formar parte automáticamente de la versión 1.0, aunque no se edite ninguno de ellos. Los 50 temas a los que no se hace referencia no pasan a formar parte automáticamente de la nueva rama. Si edita 10 de ellos, solo esos 10 pasan a formar parte de la versión 1.0. Los 40 temas restantes sin cambios se siguen utilizando desde la rama predeterminada (principal).

>[!NOTE]
>
> Las versiones de temas siguen funcionando con la bifurcación. Puede crear y administrar versiones de temas dentro de una rama seleccionada de un mapa DITA. Cada rama mantiene su propio historial de versiones, independiente de otras ramas.

## Ventajas principales

Trabajar con una rama en Experience Manager Guides ofrece las siguientes ventajas:

- **Edición aislada:** Realice cambios dentro de una rama de mapa seleccionada sin afectar al contenido correspondiente en otras ramas.
- **Creación paralela:** permite que varios equipos trabajen simultáneamente en diferentes versiones, características o correcciones dentro de sus respectivas ramas de mapas.
- **Publicación independiente:** Publique la documentación de ramas de mapas individuales sin esperar a que se completen los cambios en otras ramas.
- **Combinación controlada:** Combine los cambios de una rama de asignación en la rama predeterminada (`main`), con la capacidad de revisar y resolver conflictos.

## Bifurcación frente a líneas base

>[!NOTE]
>
> Las líneas base y las ramas son características mutuamente exclusivas. Cuando la bifurcación está habilitada, la funcionalidad de línea base deja de estar disponible. Sin embargo, las líneas de base existentes permanecen intactas y no se eliminan. Si la bifurcación se desactiva posteriormente, las líneas base existentes volverán a estar disponibles para su uso.

Una **línea de base** identifica una combinación específica de versiones de temas para un mapa DITA, lo que le permite generar resultados utilizando esas versiones seleccionadas.

Una **rama** proporciona un entorno de edición independiente para un mapa DITA y su contenido, lo que permite a los autores realizar cambios sin afectar a otras ramas del mismo mapa.

| Líneas bases | Ramificación |
|---|---|
| Seleccionar versiones específicas de temas en un mapa DITA. | Cree ramas independientes de un mapa DITA para administrar los cambios de forma independiente. |
| Se utiliza para publicar combinaciones específicas de versiones de temas. | Se utiliza para desarrollar y publicar diferentes versiones en paralelo. |
| No proporcione contextos de edición aislados. | Compatibilidad con la edición y combinación aisladas. |

## Próximas funcionalidades

Actualmente, las siguientes funcionalidades solo son compatibles con la rama predeterminada (`main`) y se prevé que sean compatibles con otras ramas de un mapa DITA en futuras versiones de Experience Manager Guides:

- Buscar
- Buscar y reemplazar
- Revisar flujos de trabajo


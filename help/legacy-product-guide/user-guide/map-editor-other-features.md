---
title: Otras funciones de los editores de mapas
description: Descubra algunas funciones comunes en los editores de mapas básicos y avanzados. Aprenda a resolver referencias clave en el editor de mapas.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
TQID: https://experienceleague.adobe.com/tAzYI5Pxc6SkzgksjL3mFAQHY01YtejwTrU6vHW5vMc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 467
ht-degree: 0%

---

# Otras funciones de los editores de mapas {#id1942D0T0HUI}

Algunas funciones comunes de los editores de mapas básicos y avanzados son:

## Resolver referencias clave {#id176GD01H05Z}

Una referencia de clave de contenido DITA o `conkeyref` es un mecanismo para insertar una parte del contenido de un tema en otro. Este mecanismo utiliza claves para localizar el contenido que se va a reutilizar, en lugar del mecanismo de referencia de contenido directo. Para obtener más información acerca de las referencias directas e indirectas en DITA, consulte *Direccionamiento DITA* en Especificación del lenguaje DITA OASIS.

Si el tema DITA tiene referencias clave asociadas, deben resolverse antes de obtener una vista previa, editar o revisar un tema.

Las referencias clave se resuelven en función del mapa raíz establecido en el siguiente orden de prioridad:

1. Preferencias de usuario
1. Panel Vista de mapa
1. Perfil de carpeta

El mapa raíz seleccionado en Preferencias de usuario tiene la prioridad más alta para resolver las referencias clave seguidas del panel Vista de mapa y el mapa raíz Perfil de carpeta. Por lo tanto, si no se define ningún mapa en las Preferencias del usuario, se utilizará el mapa abierto en el panel Vista de mapa. Si no se abre ninguna asignación en el panel Vista de mapa, se utiliza el conjunto de asignaciones de los Perfiles de carpeta para resolver las referencias clave.

Las referencias clave se pueden almacenar en un fichero de mapa DITA o en un fichero DITA independiente. En AEM Guides, puede especificar referencias clave en el nivel de proyecto o de sesión. Si ya se ha definido un mapa raíz para la sesión del usuario, se utilizará para resolver las claves. De lo contrario, se utiliza el mapa raíz predeterminado para esa carpeta. Si no se configura un mapa raíz predeterminado, las referencias clave que faltan se resaltan al usuario.

Existen varias formas de resolver referencias clave en un tema DITA mediante la definición del mapa DITA que se utilizará en las siguientes ubicaciones:

**Propiedades del proyecto**: puede definir un mapa raíz para resolver referencias clave al crear un proyecto en la sección Propiedades del proyecto.

Esta asignación raíz se aplicará a todos los recursos \(carpetas y subcarpetas\) asociados a ese proyecto. Para el contenido al que se hace referencia en varios proyectos, se mantiene una lista alfabética de proyectos y se utiliza el mapa raíz predeterminado asociado al primer proyecto. También se puede elegir el mapa DITA que se utilizará de la lista para resolver referencias clave.

**Vista previa del tema**: en el modo de vista previa del tema, haga clic en el icono Resolución de clave de la barra de herramientas y seleccione el archivo DITA que se utilizará para las referencias de clave.

**Vista de edición de tema**: haga clic en el icono Resolución de clave mientras edita un tema DITA y seleccione el archivo DITA que se utilizará para resolver las referencias de clave.

**Tema principal:**[ Trabajar con el editor de mapas](map-editor.md)

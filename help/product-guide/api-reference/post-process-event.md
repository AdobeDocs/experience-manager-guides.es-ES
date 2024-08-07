---
title: Controlador de eventos de posprocesamiento
description: Obtenga información acerca del controlador de eventos posteriores al procesamiento
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 5%

---

# Controlador de eventos de posprocesamiento {#id175UB30E05Z}

AEM Guides expone el evento com/adobe/fmdita/postprocess/complete que se utiliza para realizar cualquier operación de posprocesamiento. Este evento se activa cada vez que se realiza una operación en un archivo DITA. Las siguientes operaciones en un fichero DITA déclencheur este evento:

>[!NOTE]
>
> AEM Este evento no se activa para la operación de eliminación en la versión 6.1 de.

- Cargar
- Creación
- Modificación
- Eliminación

AEM Es necesario crear un controlador de eventos de tipo para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `path` | Cadena | Ruta del archivo que activó este evento. Normalmente, es el archivo en el que se ha realizado una operación. |
| `status` | Cadena | Estado de devolución de la operación realizada. Las opciones posibles son: - <br>- SUCCESS: La operación de posprocesamiento se completó correctamente. <br>- COMPLETADA CON ERRORES: la operación de posprocesamiento se completó, pero con algunos errores. <br> - ERROR: error en la operación posterior al procesamiento debido a un error grave. |
| `message` | Cadena | Si el estado es COMPLETADO CON ERRORES o FALLIDO, este parámetro contiene los detalles sobre el error o el motivo del error. |
| `operation` | Cadena | La operación de posprocesamiento realizada en el archivo. Las opciones posibles son: <br>- Adición <br>- Actualización <br>- Eliminación |

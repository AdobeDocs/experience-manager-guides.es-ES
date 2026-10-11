---
title: Controlador de eventos de posprocesamiento
description: Obtenga información acerca del controlador de eventos posteriores al procesamiento
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/ixD-jFpXxkdmPbOWtCDxPgjtxu-FfJkzGCdUHNeA1CY'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: e0bef973-8c57-4760-9b12-ec950a3c7247
    internal-label: Post processing event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 4%
---
# Controlador de eventos de posprocesamiento {#id175UB30E05Z}

## UUID y CLOUD SERVICE

Adobe Experience Manager Guides expone el evento `com/adobe/guides/postprocess/complete` que se usa para realizar operaciones posteriores al procesamiento. Este evento se activa cada vez que se realiza una operación en un archivo DITA. Las siguientes operaciones en un fichero DITA déclencheur este evento:

- Cargar
- Crear
- Modificar

>[!NOTE]
>
> El evento posterior al procesamiento se activa habilitando el indicador `fire.processing.events`, que es un parámetro de configuración en `fmdita config manager`. Cuando se establece en true, almacena en déclencheur los eventos (com/adobe/guides/postprocess/complete) para rastrear la finalización posterior al procesamiento. De forma predeterminada, se establece en false (deshabilitado).

Debe crear un controlador de eventos Adobe Experience Manager para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```
com/adobe/guides/postprocess/complete 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `path` | Cadena | Ruta del archivo que activó este evento. Normalmente, es el archivo en el que se ha realizado una operación. |
| `eventType` | Cadena | El tipo de evento, es decir, CREATE o MODIFY. |
| `status` | Cadena | Estado de devolución de la operación realizada. Las opciones posibles son: <br>- SUCCESS: La operación de posprocesamiento se completó correctamente. <br>- ERROR: error en la operación posterior al procesamiento debido a algún error. |
| `errorMsg` | Cadena | El mensaje de error en caso de que falle la operación posterior al procesamiento. |
| `uuid` | Cadena | El UUID del archivo que activó este evento. Normalmente, es el archivo en el que se ha realizado una operación. |

**Analizador de eventos de muestra**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## No UUID


Adobe Experience Manager Guides expone el evento com/adobe/fmdita/postprocess/complete que se utiliza para realizar cualquier operación de posprocesamiento. Este evento se activa cada vez que se realiza una operación en un archivo DITA. Las siguientes operaciones en un fichero DITA déclencheur este evento:

>[!NOTE]
>
> Este evento no se activa para la operación de eliminación en AEM 6.1.

- Cargar
- Creación
- Modificación
- Eliminación

Debe crear un controlador de eventos Adobe Experience Manager para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `path` | Cadena | Ruta del archivo que activó este evento. Normalmente, es el archivo en el que se ha realizado una operación. |
| `status` | Cadena | Estado de devolución de la operación realizada. Las opciones posibles son: <br>- SUCCESS: La operación de posprocesamiento se completó correctamente. <br>- COMPLETADA CON ERRORES: la operación de posprocesamiento se completó, pero con algunos errores. <br>- ERROR: error en la operación posterior al procesamiento debido a algún error. |
| `message` | Cadena | Si el estado es COMPLETADO CON ERRORES o FALLIDO, este parámetro contiene los detalles sobre el error o el motivo del error. |
| `operation` | Cadena | La operación de posprocesamiento realizada en el archivo. Las opciones posibles son: <br>- Adición <br>- Actualización <br>- Eliminación |

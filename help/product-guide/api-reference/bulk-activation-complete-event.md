---
title: Controlador de eventos de activación masiva completa
description: Obtenga información acerca del controlador de eventos de activación masiva completa
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: 9b8971bf7065a94a2e42669094249c822c555718
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 6%

---

# Controlador de eventos de activación masiva completa

Experience Manager Guides expone el evento `com/adobe/fmdita/replication/complete` que se usa para realizar cualquier operación después de la finalización de un proceso de activación en masa. Este evento se activa cada vez que se completa un proceso de activación masiva. AEM Por ejemplo, si ejecuta la activación masiva de un ajuste preestablecido de sitio de un mapa de, se llama a este evento una vez que finaliza el proceso de activación.

AEM Es necesario crear un controlador de eventos de tipo para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```
com/adobe/fmdita/replication/complete 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `path` | Cadena | Ruta del archivo que activó este evento. <br> Por ejemplo, `/content/output/sites/ditamap1-ditamap`. <br> Es una lista de rutas serializadas como una matriz JSON. |
| `messageType` | Cadena | El tipo de mensaje. <br>Opción posible: `REPLICATION` |
| `action` | Cadena | Esta es la acción realizada. <br>Opción posible: `BulkReplicate` |
| `user` | Cadena | El usuario que inició la operación. |
| `result` | Cadena | El resultado de la activación masiva. Es un objeto JSON serializado: <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Cadena | AgentId utilizado en la replicación. Por ejemplo, `"publish"`. |
| `importMode` | Cadena | Modo de importación utilizado en la activación. Las opciones posibles son: <br>`REPLACE, MERGE, UPDATE`. |


**Listener de eventos de muestra**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```

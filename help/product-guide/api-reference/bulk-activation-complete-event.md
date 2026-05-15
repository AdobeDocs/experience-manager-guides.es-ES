---
title: Controlador de eventos de activación masiva completa
description: Obtenga información acerca del controlador de eventos de activación masiva completa
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
TQID: https://experienceleague.adobe.com/M8Q8A8auCkKjmoilHsUfU2ztNSCxOWstwPC1bMLmvD0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 6%

---

# Controlador de eventos de activación masiva completa

Experience Manager Guides expone el evento `com/adobe/fmdita/replication/complete` que se usa para realizar cualquier operación después de la finalización de un proceso de activación en masa. Este evento se activa cada vez que se completa un proceso de activación masiva. Por ejemplo, si ejecuta la activación masiva de un ajuste preestablecido de sitio AEM de un mapa, se llama a este evento una vez finalizado el proceso de activación.

Debe crear un controlador de eventos AEM para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

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

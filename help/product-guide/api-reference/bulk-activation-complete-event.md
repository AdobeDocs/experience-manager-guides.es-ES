---
title: Controlador de eventos de activación masiva completa
description: Obtenga información acerca del controlador de eventos de activación masiva completa
source-git-commit: 8f1bb12a92ab9a63aef1765e51159644242683a0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# Controlador de eventos de activación masiva completa

Las guías del Experience Manager exponen `com/adobe/fmdita/replication/complete` evento que se utiliza para realizar cualquier operación después de la finalización de un proceso de activación masiva. Este evento se activa cada vez que se completa un proceso de activación masiva. AEM Por ejemplo, si ejecuta la activación masiva de un ajuste preestablecido de sitio de un mapa de, se llama a este evento una vez que finaliza el proceso de activación.

AEM Es necesario crear un controlador de eventos de tipo para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```
com/adobe/fmdita/replication/complete 
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`path`|Cadena|Ruta del archivo que activó este evento. <br> Por ejemplo, `/content/output/sites/ditamap1-ditamap`. <br> Es una lista de rutas serializadas como una matriz JSON.| |`messageType`|Cadena|Tipo de mensaje. <br>Opción posible: `REPLICATION`| |`action`|Cadena|Esta es la acción realizada. <br>Opción posible: `BulkReplicate`| |`user`|Cadena|El usuario que inició la operación.| |`result`|Cadena|Resultado de la activación masiva. Es un objeto JSON serializado: <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|Cadena|Id. de agente utilizado en la replicación. Por ejemplo, `"publish"`.| |`importMode`|Cadena|Modo de importación utilizado en la activación. Las opciones posibles son: <br>`REPLACE, MERGE, UPDATE`.|


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

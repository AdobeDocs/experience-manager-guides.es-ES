---
title: Recomendaciones para la optimización del rendimiento
description: Conozca las Recomendaciones para la optimización del rendimiento
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/6q077Ib1EIQ4AA51ktmZ966RZrSt08xJQh5t4llzgbQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 917
ht-degree: 0%

---

# Recomendaciones para la optimización del rendimiento {#id213BD0JG0XA}

## Configurar el almacén de datos \(Obligatorio\)

**¿Cuál es el cambio?**
Establezca la propiedad `minRecordLength` en un valor de `100` en la configuración `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.`. Para obtener más información sobre el almacén de datos de archivos y el almacén de datos S3, consulte el artículo [Configuración de almacenes de nodos y almacenes de datos en AEM 6](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/data-store-config.html).

>[!NOTE]
>
> Para el almacén de datos S3, el coste de mantenimiento del contenido en el almacén de datos también depende del número de solicitudes. Por lo tanto, al realizar esta configuración con S3: también se debe tener en cuenta el coste de configuración por solicitud y el tamaño de la caché.

**¿Cuándo se debe configurar?**
Después de la configuración inicial, pero antes de migrar cualquier contenido. Debe realizar este cambio incluso en un sistema existente, lo que garantiza que todo el contenido nuevo se almacene en el almacén de datos en lugar de en el almacén de segmentos.

**Resultado de este cambio**
Los ficheros DITA se guardan en el almacén de datos en lugar de en el almacén de segmentos. Esto mantiene el tamaño del almacén de segmentos por debajo de los límites recomendados, lo que mejora la capacidad de respuesta del sistema.

## Actualizar índice de Lucene \(Obligatorio\)

**¿Cuál es el cambio?**
Excluir /var/dxml de oak:index/lucene.

>[!NOTE]
>
> AEM Guides nunca utiliza índices Lucene para buscar contenido en el nodo /var/xml.

**¿Cuándo se debe configurar?**
Si está realizando este cambio en un sistema nuevo antes de migrar contenido, solo se requiere actualizar oak:index/lucene. De lo contrario, en un sistema existente en el que el contenido ya se ha migrado y después de realizar el cambio en oak:index/lucene, vuelva a generar los índices de Lucene \(*que podría tardar unas horas en completarse*\).

**Resultado de este cambio**
Este cambio evita que el nodo /var/xml se indexa y almacene en el almacén de segmentos.

## Optimización de memoria Java \(Obligatorio\)

**¿Cuál es el cambio?**
Los parámetros de inicio de JVM deben ajustarse cuidadosamente en función de la infraestructura y el tamaño del disco. Se recomienda consultar con el Soporte de Adobe para obtener ayuda y poder acceder a la configuración ideal. Sin embargo, puede probar las siguientes configuraciones usted mismo:

- Establezca el tamaño de la pila de JVM en un mínimo de 1/4 de la memoria total disponible. Utilice el parámetro `-Xmx<size>` para establecer el tamaño de memoria de la pila. Establezca el valor de -`Xms` es igual a `-Xmx`.

- Habilitar `-XX:+HeapDumpOnOutOfMemoryError` y establecer la ruta de acceso de `-XX:HeapDumpPath=</path/to/folder` `>`.

- Activar el registro de Java GC como:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- En general, para Java 11, use G1GC \(`-XX:+UseG1GC`\) y para Java 8 use CMS \(-`XX:+UseConcMarkSweepGC`\).

- Utilice `-XX:NewRatio` para controlar el tamaño de la memoria de generación joven. El valor predeterminado es 2, lo que significa que 1/3 de la memoria se utiliza para la generación joven. Dado que hay muchos objetos que se crean y destruyen rápidamente, el uso de un valor de 1 asignará 1/2 de la memoria a la generación joven.

- Controle el número de objetos que se promocionan a la generación anterior mediante `-XX:MaxTenuringThreshold`. Utilice el valor de 15 \(predeterminado\) para retrasar el momento en que los objetos se promocionan a la generación antigua.

**¿Cuándo se debe configurar?**
Si está realizando este cambio en un sistema existente, debe reiniciar el sistema. En caso de una instalación nueva, este cambio debe realizarse en el archivo de secuencia de comandos de inicio \(.bat o .sh\) antes de iniciar el sistema.

**Resultado de este cambio**
Esto da como resultado un tamaño de pila óptimo y una ejecución regulada del CG.

## Minificación de la biblioteca de cliente en la instancia de autor \(Opcional\)

**¿Cuál es el cambio?**
Las bibliotecas de cliente deben configurarse para que se minifiquen en las instancias de creación. Esto garantiza que haya menos bytes para descargar cuando un usuario navega por el sistema desde diferentes ubicaciones. Para realizar este cambio, establezca la configuración en **HTML Library Manager** desde la consola Felix.

**¿Cuándo se debe configurar?**
Esto se puede hacer en tiempo de ejecución a través de la consola Felix o mediante la implementación de código.

**Resultado de este cambio**
Este cambio mejora el tiempo de carga de las páginas en la instancia de autor, ya que se transfieren menos bytes para cargar las bibliotecas de cliente.

## Configurar subprocesos de publicación simultáneos \(Obligatorio, según el caso de uso\)

**¿Cuál es el cambio?**
Este cambio es necesario si utiliza DITA-OT para publicar la salida y también se han definido varios subprocesos de publicación simultáneos.

De forma predeterminada, AEM Guides establece los subprocesos de publicación en el número de CPU+1. Sin embargo, se recomienda establecer este valor en la mitad \(1/2\) o un tercio \(1/3\) del número total de CPU. Para ello, establezca la propiedad **Generation Pool Size** en la configuración `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` según las recomendaciones.

**¿Cuándo se debe configurar?**
Esto se puede hacer en tiempo de ejecución a través de la consola Felix o mediante la implementación de código.

**Resultado de este cambio**
Este cambio garantiza que, en una instancia de autor en ejecución, todos los recursos no se asignen a las operaciones de publicación. Esto mantiene los recursos del sistema disponibles para los autores, lo que mejora la experiencia del usuario.

## Configure el tamaño de lote de nodos para la generación de resultados del sitio de AEM \(Obligatorio, según el caso de uso\)

**¿cuál es el cambio?**
Este cambio es necesario si está generando una salida de AEM Sites.

Establezca la propiedad **Limitar páginas del sitio AEM en el montón** en `com.adobe.fmdita.config.ConfigManager` a un número basado en la configuración de su sistema. Esta propiedad define el tamaño de lote de nodos que se confirmarán cuando se generen las páginas del sitio. Por ejemplo, en un sistema con un mayor número de CPU y tamaño de pila, puede aumentar el valor predeterminado de `500` a un número mayor. Debe probar la ejecución con el valor modificado para obtener un valor óptimo para esta propiedad.

**¿Cuándo se debe configurar?**
Esto se puede hacer en tiempo de ejecución a través de la consola Felix o mediante la implementación de código.

**Resultado de este cambio**
Un número mayor de **Limitar páginas del sitio AEM en el montón** optimiza el proceso de generación de resultados del sitio AEM.


**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)

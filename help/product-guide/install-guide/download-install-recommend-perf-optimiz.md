---
title: Recommendations para la optimización del rendimiento
description: Conozca Recommendations para la optimización del rendimiento
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: b28b7d96cce69f677b0bcf891b94d7ac84eb1eb0
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Recommendations para la optimización del rendimiento {#id213BD0JG0XA}

## Configurar el almacén de datos \(Obligatorio\)

**¿Cuál es el cambio?**
AEM Establezca la propiedad `minRecordLength` en un valor de `100` en la configuración `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.`. Para obtener más información sobre el almacén de datos de archivos y el almacén de datos S3, consulte el artículo [Configuración de almacenes de nodos y almacenes de datos en el artículo de 6](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/data-store-config.html) de la sección.

>[!NOTE]
>
> Para el almacén de datos S3, el coste de mantenimiento del contenido en el almacén de datos también depende del número de solicitudes. Por lo tanto, al realizar esta configuración con S3: también se debe tener en cuenta el coste de configuración por solicitud y el tamaño de la caché.

**¿Cuándo se debe configurar?**
Después de la configuración inicial, pero antes de migrar cualquier contenido. Debe realizar este cambio incluso en un sistema existente, lo que garantiza que todo el contenido nuevo se almacene en el almacén de datos en lugar de en el almacén de segmentos.

**Resultado de este cambio**
Los ficheros DITA se guardan en el almacén de datos en lugar de en el almacén de segmentos. Esto mantiene el tamaño del almacén de segmentos por debajo de los límites recomendados, lo que mejora la capacidad de respuesta del sistema.

## Actualizar índice de Lucene \(Obligatorio\)

**¿Cuál es el cambio?**
Excluya /var/dxml de oak:index/lucene.

>[!NOTE]
>
> AEM Guides nunca utiliza índices Lucene para buscar contenido en el nodo /var/xml.

**¿Cuándo se debe configurar?**
Si realiza este cambio en un sistema nuevo antes de migrar contenido, solo es necesario actualizar oak:index/lucene. De lo contrario, en un sistema existente en el que el contenido ya se ha migrado y después de realizar el cambio en oak:index/lucene, vuelva a generar los índices de Lucene \(*que puede tardar unas horas en completarse*\).

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
Las bibliotecas de cliente deben configurarse para que se minifiquen en las instancias de creación. Esto garantiza que haya menos bytes para descargar cuando un usuario navega por el sistema desde diferentes ubicaciones. Para realizar este cambio, establezca la configuración en **Administrador de bibliotecas de HTML** desde la consola Felix.

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

## AEM Configure el tamaño de lote de nodos para la generación de salida del sitio de la página de destino de la página \(Obligatorio, según el caso de uso\)

**¿cuál es el cambio?**
Este cambio es necesario si está generando una salida de AEM Sites.

AEM Establezca la propiedad **Limitar páginas del sitio en el montón** en `com.adobe.fmdita.config.ConfigManager` a un número basado en la configuración de su sistema. Esta propiedad define el tamaño de lote de nodos que se confirmarán cuando se generen las páginas del sitio. Por ejemplo, en un sistema con un mayor número de CPU y tamaño de pila, puede aumentar el valor predeterminado de `500` a un número mayor. Debe probar la ejecución con el valor modificado para obtener un valor óptimo para esta propiedad.

**¿Cuándo se debe configurar?**
Esto se puede hacer en tiempo de ejecución a través de la consola Felix o mediante la implementación de código.

**Resultado de este cambio**
AEM AEM Un número mayor de **Límite de páginas del sitio en el montón** de la propiedad optimiza el proceso de generación de resultados del sitio en el sitio en el sitio en el que se ha puesto en marcha la.


**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)

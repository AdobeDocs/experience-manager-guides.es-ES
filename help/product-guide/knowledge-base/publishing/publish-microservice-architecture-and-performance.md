---
title: Arquitectura y rendimiento de microservicios de publicación en la nube
description: Comprenda cómo el nuevo microservicio permite la publicación escalable en AEMaaCS.
exl-id: 948fce3f-b989-48f0-9a85-e921717e2986
feature: Microservice in AEM Guides
role: User, Admin
TQID: https://experienceleague.adobe.com/dXRfQ3DBW-1l-4hy5H0yowfXntJ3jcLU5bHvkquJBOY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b455a250-64c4-4598-b015-7b6b6dc528b1
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 753
ht-degree: 0%

---

# Arquitectura de microservicios y análisis de rendimiento de Cloud Publishing

Este artículo comparte la información sobre la arquitectura y los números de rendimiento del nuevo microservicio de publicación en la nube.

>[!NOTE]
>
> La publicación basada en microservicios en AEM Guides admite tipos de ajustes preestablecidos de salida de PDF (tanto nativos como basados en DITA-OT), AEM Site (mediante asignación de componentes compuestos), HTML5, JSON y CUSTOM.

## Problemas con los flujos de trabajo de publicación existentes en la nube

La publicación DITA es un proceso que consume muchos recursos y que depende principalmente de la memoria del sistema y de CPU disponibles. La necesidad de estos recursos aumenta aún más si los editores publican asignaciones grandes con muchos temas o si se activan varias solicitudes de publicación paralelas.

Si no utiliza el nuevo servicio, todas las publicaciones se realizan en el mismo pod Kubernetes(k8) que también ejecuta el servidor en la nube de AEM. Un pod k8 típico tiene un límite en la cantidad de memoria y CPU que puede usar. Si los usuarios de AEM Guides publican cargas de trabajo grandes o paralelas, este límite puede incumplirse rápidamente. K8 reinicia los pods que intentan usar más recursos que el límite configurado, lo que puede tener un impacto grave en la propia instancia de nube de AEM.

Esta restricción de recursos fue la principal motivación para crear un servicio dedicado que nos pueda permitir ejecutar varias cargas de trabajo de publicación simultáneas y grandes en la nube.

Para obtener más información sobre la publicación de flujos de trabajo en la nube, consulte las [preguntas frecuentes sobre el flujo de trabajo de publicación y la escalabilidad](/help/product-guide/user-guide/publishing-scalability-faq.md).

## Introducción a la nueva arquitectura

El servicio utiliza las soluciones de nube más avanzadas de Adobe, como App Builder, IO Eventing e IMS, para crear una oferta sin servidor. Estos servicios se basan en los estándares de la industria ampliamente aceptados como Kubernetes y docker.

Cada solicitud al nuevo microservicio de publicación se ejecuta en un contenedor de docker aislado que ejecuta solo una solicitud de publicación a la vez. Se crean varios contenedores nuevos automáticamente en caso de que se reciban nuevas solicitudes de publicación. Este contenedor único por configuración de solicitud permite al microservicio ofrecer el mejor rendimiento a los clientes sin introducir riesgos de seguridad. Estos contenedores se descartan una vez finalizada la publicación, lo que libera los recursos no utilizados.

Todas estas comunicaciones están protegidas por Adobe IMS mediante autenticación y autorización basadas en JWT y se ejecutan a través de HTTPS.

<img src="assets/architecture.png" alt="pestaña proyectos" width="600">

>[!NOTE]
>
> El proceso de publicación ejecuta algunas partes dependientes del contenido de la solicitud en el propio servidor de AEM, como la generación de listas de dependencias. Sin embargo, las partes más exhaustivas del proceso de publicación, como ejecutar DITA-OT o el motor nativo, se han descargado al nuevo servicio.


## Análisis de rendimiento

Esta sección muestra las cifras de rendimiento del microservicio. Compara el rendimiento del microservicio con la oferta local de AEM Guides, ya que la arquitectura de la nube antigua tenía problemas en la publicación simultánea o en la publicación de mapas muy grandes.

Si publica un mapa grande en modo local, es posible que tenga que modificar los parámetros de la pila Java o que se produzcan errores de memoria insuficiente. En la nube, el microservicio ya está diseñado y tiene una pila Java y otras configuraciones óptimas listas para usar.

### Ejecución de una publicación en la nube o local

* Nube

  Si está ejecutando una sola publicación en la nube mediante el nuevo servicio, la publicación puede tardar un poco más en comparación con la publicación única local. Este tiempo ligeramente elevado se debe a la naturaleza distribuida de la nueva arquitectura de la nube.

  <img src="assets/cloud_single_publish.png" alt="pestaña proyectos" width="600">

* On-Prem

  Los resultados de la publicación única son mejores en la arquitectura de la nube antigua o en las instalaciones, ya que la publicación completa se produce en el mismo pod/equipo en el que se ejecuta AEM.

  <img src="assets/onprem_single_publish.png" alt="pestaña proyectos" width="600">

### Ejecución de varias publicaciones en la nube o locales

* Nube

  El nuevo microservicio de publicación destaca en este escenario. Como puede ver en la imagen siguiente, con el aumento de los múltiples trabajos de publicación simultáneos, la nube puede publicarlos sin ningún aumento significativo en el tiempo de publicación.

  <img src="assets/cloud_bulk_publish.png" alt="pestaña proyectos" width="600">

* On-Prem

  La ejecución de la publicación simultánea en un servidor local provoca una degradación grave del rendimiento. Esta caída de rendimiento es más grave si los editores publican aún más mapas simultáneamente.

  <img src="assets/onprem_bulk_publish.png" alt="pestaña proyectos" width="600">

## Ventajas adicionales

Alguna parte de cada solicitud de publicación debe ejecutarse en la instancia de AEM para recuperar el contenido de publicación correcto y enviarlo al microservicio. La nueva arquitectura de la nube utiliza trabajos de AEM en lugar de flujos de trabajo de AEM, como ocurría en la arquitectura antigua. Este cambio permite a los administradores de AEM Guides configurar individualmente las colas de publicación en la nube sin afectar a otros trabajos de AEM ni a las configuraciones de flujo de trabajo.

Encontrará detalles sobre cómo configurar el nuevo microservicio de publicación aquí: [Configurar microservicio](configure-microservices.md)

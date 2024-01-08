---
title: Flujo de trabajo de generación posterior
description: Resumen del flujo de trabajo de generación posterior con un ejemplo
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 2%

---

# AEM Publicación de guías de usuario - Flujo de trabajo de generación posterior

AEM Guías le proporciona la flexibilidad para especificar un flujo de trabajo de generación posterior a la salida. AEM Puede realizar algunas tareas de posprocesamiento en la salida que se genera mediante las guías de.
Por ejemplo, es posible que desee establecer ciertas propiedades en la salida del PDF o que desee enviar un correo electrónico a un conjunto de usuarios una vez generada la salida.


## ¿Cuáles son los pasos necesarios para utilizar los flujos de trabajo de generación posterior?

### Creación de un proceso de flujo de trabajo

Cree un proceso de flujo de trabajo basado en Java o ECMA que realice la operación en la salida generada. Por ejemplo, copiar algunos metadatos del origen al contenido generado o manipular los metadatos de la salida generada.
- Tomaremos un ejemplo de creación de un proceso de este tipo mediante el script ECMA (puede consultar el paquete adjunto)
- Para el proceso de flujo de trabajo basado en Java, consulte la sección &quot;*Personalizar flujo de trabajo de generación posterior a la salida*&quot; de [Guía de instalación y configuración](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Crear un modelo del flujo de trabajo

Con el proceso de flujo de trabajo personalizado que creó en el paso anterior, cree un modelo de flujo de trabajo y agréguele ese paso de proceso.
- También debe añadir un paso de proceso obligatorio &quot;*Finalizar generación posterior*&quot; como último paso del flujo de trabajo.

Consulte el modelo de flujo de trabajo de muestra siguiente:

![Modelo de flujo de trabajo de generación posterior](../assets/workflows/pgwf-workflow-model.png)


### Usar este flujo de trabajo de generación posterior en un mapa

AEM El flujo de trabajo de generación de publicaciones es una propiedad que se puede configurar en cualquier ajuste preestablecido de salida dentro del mecanismo de publicación de las guías de. Ejemplo:

![Flujo de trabajo de generación de publicaciones en ajustes preestablecidos de salida](../assets/workflows/pgwf-preset-settings.png)


Suponiendo que el modelo seleccionado ya se ha creado.


### Pruebas

Ahora puede ejecutar la publicación con este ajuste preestablecido y validar el resultado del paso de proceso


## Muestra

Para su referencia, puede utilizar el siguiente paquete e instalarlo a través del administrador de paquetes para probar el flujo de trabajo de generación posterior de muestra (*como se indica en las capturas de pantalla anteriores*)

[Modelo de flujo de trabajo de generación posterior basado en ECMA de muestra](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)

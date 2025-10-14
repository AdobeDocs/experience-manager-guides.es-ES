---
title: Generar salida
description: Genere la salida para un mapa DITA desde la consola de mapas y el tablero de mapas de AEM Guides.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: 358d38ca761661eaee7aeac2cc7d46c53105c543
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Generar salida

Existen dos formas de generar resultados para un mapa DITA:

- [Generar salida para un mapa DITA desde la consola Mapa](#generate-output-for-a-dita-map-from-the-map-console)
- [Generar salida para un mapa DITA desde el panel Mapa](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Generar salida para un mapa DITA desde la consola Mapa

Realice los siguientes pasos para generar la salida de un mapa DITA mediante la consola Mapa:

1. [Abra un archivo de asignación en la consola de mapas](./open-files-map-console.md).
2. La consola de mapas DITA se muestra con la lista de **Ajustes preestablecidos de salida** disponibles para generar resultados.

3. Abra el ajuste preestablecido que desee utilizar para generar la salida y seleccione **Generar salida** para iniciar el proceso de generación.

   <img src="images/generate-output-pdf.png" alt="ficha de metadatos" width="600">

   O bien, pase el ratón sobre el ajuste preestablecido y seleccione **Generar** en el menú contextual del ajuste preestablecido.


   <img src="images/generate-preset-map-console.png" alt="ficha de metadatos" width="600">

Una vez que finalice la generación de resultados, seleccione **Ver resultados** para ver el resultado.

Un cuadro de diálogo **Correcto** está visible en la esquina inferior derecha de la pantalla.

Si una salida no se realiza correctamente, se muestra el siguiente mensaje de error.

<img src="images/error-log.png" alt="registro de errores" width="250">

Para ver el registro de errores, seleccione **Descartar**, pase el ratón sobre la pestaña del ajuste preestablecido seleccionado y seleccione **Ver registro** en el menú contextual del ajuste preestablecido.

## Generar salida para un mapa DITA desde el panel Mapa

Realice los siguientes pasos para generar la salida de un mapa DITA mediante el tablero de mandos Mapa:

1. En la interfaz de usuario de Assets, desplácese hasta el fichero de mapa DITA que desee publicar y selecciónelo.

   Aparecerá la consola de mapas DITA con la lista de Ajustes preestablecidos de salida disponibles para generar la salida.

1. Seleccione uno o varios ajustes preestablecidos de salida que desee utilizar para generar la salida.

   ![](images/generate-multiple-outputs-uuid.png){align="left"}

1. Seleccione el icono **Generate** para iniciar el proceso de generación de resultados.


Puede ver el estado actual de la solicitud de generación de resultados en la ficha **Salidas**. Para obtener más información, vea [Ver el estado de la tarea de generación de resultados](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> Si un proceso de generación de resultados de un ajuste preestablecido está en cola o en curso, no se puede iniciar otra tarea de generación de resultados para el mismo ajuste preestablecido.

También se puede generar la salida de AEM Sites para uno o más temas o todo el mapa DITA desde la consola Mapa. Para obtener más información, vea [Generar salida de la base de conocimiento](web-editor-article-publishing.md#id218CK0U019I).

## Combinando diferentes temas dentro de un mapa DITA utilizando el atributo `chunk`

Un mapa DITA puede incluir distintos tipos de temas, como referencias, conceptos y tareas. El atributo `chunk=to-content` le permite combinar estos temas para generar un solo resultado de página en AEM Sites. Sin embargo, para publicar correctamente el tema combinado, asegúrese de que el administrador ha configurado el catálogo XML correcto en los perfiles DITA.

El sistema requiere un identificador público con la palabra clave `composite` en el catálogo XML para identificar y aplicar correctamente la regla DTD adecuada.
Esta configuración se incluye de forma predeterminada en el catálogo XML estándar. Sin embargo, si utiliza un catálogo XML personalizado, asegúrese de que el administrador haya añadido este ID público a la configuración. Sin ella, es posible que el tema combinado no se publique correctamente.

Para obtener más información sobre cómo usar Public ID y System ID en los DTD/XSD personalizados, consulte [Integración de la especialización DITA](../cs-install-guide/dita-ot-specialization.md#integrate-dita-specialization-id211mb0e00xa).



**Tema principal:**&#x200B;[&#x200B; Generación de resultados](generate-output.md)

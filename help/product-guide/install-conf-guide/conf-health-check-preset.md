---
title: Configurar ajustes preestablecidos de comprobación de estado
description: Obtenga información sobre cómo configurar ajustes preestablecidos de comprobación de estado en el perfil global o de nivel de carpeta para que los autores y editores puedan ejecutar comprobaciones de estado en un mapa DITA.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: fd5e1e85933eb2785b0a74b0fa49fec1da4ca0c2
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Crear y administrar ajustes preestablecidos de comprobación de estado

>[!NOTE]
>
> Esta función está habilitada de forma predeterminada. Si prefiere no utilizar esta función en su entorno, póngase en contacto con el equipo de éxito del cliente.

Como administrador, puede configurar la función de comprobación de estado en el nivel de perfil de carpeta en Experience Manager, lo que permite a autores y editores ejecutar comprobaciones de estado en un mapa DITA. Esto incluye la detección temprana de problemas como vínculos rotos, ID duplicados y errores de validación de Schematron en un mapa antes de la publicación, en lugar de comprobar cada archivo individualmente. Las comprobaciones que se ejecutan se definen mediante un ajuste preestablecido de comprobación de estado, un conjunto de reglas que los autores y los editores pueden seleccionar y ejecutar.

Este artículo proporciona información sobre la creación y administración de ajustes preestablecidos de comprobación de estado.

## Crear un ajuste preestablecido de comprobación de estado

Realice los siguientes pasos para crear un ajuste preestablecido de comprobación de estado en el nivel de perfil de carpeta:

1. Vaya a [Configuración de Workspace](./workspace-settings.md) y seleccione **Comprobación de estado** en la lista.
1. En el panel **Ajustes preestablecidos de comprobación de estado**, seleccione **Nuevo**.

   ![](./assets/health-check-preset-create.png)
1. Se muestra el cuadro de diálogo **Nuevo ajuste preestablecido de comprobación de estado**. Añada un nombre de ajuste preestablecido y seleccione las reglas o comprobaciones que desee incluir; las opciones disponibles son Vínculos rotos, ID duplicados y Validaciones de Schematron.

   ![](./assets/health-check-preset-dialog.png)
1. Seleccione **Crear**.
1. Seleccione **Guardar** para guardar la configuración.

Este ajuste preestablecido ya está disponible para autores y editores. Para los autores, la función está disponible en el menú Opciones de un mapa en la vista Mapa y en el panel Informe de comprobación de estado junto al panel Buscar, lo que les permite ejecutar una comprobación de estado en el mapa seleccionado utilizando uno de los ajustes preestablecidos de comprobación de estado configurados para su perfil. Para obtener más información, vea [Funciones adicionales en el editor de mapas](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).

Para los editores, la opción **Ejecutar comprobación de estado antes de generar resultados** se muestra en el panel preestablecido, que pueden habilitar o deshabilitar según sea necesario. Cuando se habilita, el informe de comprobación de estado se anexa a los registros al principio del proceso de publicación, pero no bloquea la generación de resultados.

## Administrar ajustes preestablecidos de comprobación de estado

Una vez creado, el ajuste preestablecido se añade al panel Ajustes preestablecidos de comprobación de estado desde el que puede realizar las operaciones de edición, duplicado o eliminación en el ajuste preestablecido.

![](./assets/health-check-preset-manage.png)

- **Editar**: Permite editar los campos preestablecidos, como el nombre del ajuste preestablecido, las comprobaciones (seleccionar o anular la selección de comprobaciones) y agregar o quitar archivos de Schematron adjuntos al ajuste preestablecido.
- **Duplicate**: crea un duplicado del ajuste preestablecido en la misma lista.
- **Quitar**: quita el ajuste preestablecido del panel.

Seleccione **Guardar** para guardar los cambios.

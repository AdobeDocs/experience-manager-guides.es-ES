---
title: Anulaciones de configuración
description: Obtenga información sobre cómo configurar las anulaciones de configuración
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: e4b213b5f0efda18fb24f100f3ee8237947890bf
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Anulaciones de configuración {#id216IFC003XA}

Para realizar cualquier actualización de la configuración, se debe utilizar el siguiente método genérico:

1. Acceda al repositorio de Git de Cloud Manager.

1. Cree un nuevo archivo JSON en la siguiente ubicación:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Asigne un nombre al archivo en el siguiente formato:

   $\{PID\}.cfg.json

   En este caso, el PID es el ID de proceso de la configuración.

1. Agregue propiedades en el archivo JSON con el siguiente formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Confirme los cambios y ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

## Configuración de la IU de Experience Manager Guides

La versión 2025.02.0 de Adobe Experience Manager Guides incorpora una interfaz de usuario mejorada y funciones mejoradas para ayudarle a trabajar de forma más rápida y eficaz que nunca. Esto incluye una página de inicio completamente nueva, una barra de herramientas del editor más limpia y organizada, una consola de mapas dedicada y funciones mejoradas.

Para garantizar una transición sin problemas y minimizar las interrupciones, Experience Manager Guides proporciona una opción de configuración que le permite volver a la IU antigua (y viceversa) según sea necesario.

>[!IMPORTANT]
>
> Esta opción de configuración para cambiar entre la IU nueva y la antigua era compatible hasta la versión 2025.4.0. Con la versión 2025.6.0, esta configuración está obsoleta y ya no se puede utilizar para volver a la IU antigua.

Siga estos pasos para configurar la interfaz de usuario de Experience Manager Guides:

1. Abra Adobe Experience Manager y, a continuación, seleccione el programa que contiene el entorno que desea configurar.
2. Cambie a la ficha **Entornos**.
3. Seleccione el nombre del entorno que desea configurar. Esto lo llevará a la página **Información del entorno**.
4. Cambie a la ficha **Configuración**.
5. Seleccione **Agregar/Actualizar**.
6. Añada los detalles de configuración de la IU. Asegúrese de utilizar el mismo nombre y configuración que se indican en la siguiente captura de pantalla.

   ![](assets/enable-penultimate-ui.png){width="800" align="left"}

   Si establece el valor en **true**, se conserva la interfaz de usuario antigua, mientras que **false** activa la nueva interfaz de usuario.



**Tema principal:**&#x200B;[ Descargar e instalar](download-install.md)

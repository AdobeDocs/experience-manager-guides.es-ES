---
title: Iniciar el editor web
description: Obtenga información sobre cómo iniciar el editor web desde la página de navegación de AEM, la interfaz de usuario de AEM Assets y la consola de mapas DITA en AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
TQID: https://experienceleague.adobe.com/O-rew8ysArVVeDpj3T7oEi-hEg-phDWzb85gD2l-9gQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 592
ht-degree: 0%

---

# Iniciar el editor web {#id2056B0140HS}

Puede iniciar el Editor Web desde las ubicaciones siguientes:

- [Página de navegación de AEM](#id2056BG00RZJ)
- [IU de AEM Assets](#id2056BG0307U)
- [Consola de mapa DITA](#id2056BG090BF)

En las secciones siguientes se describen los detalles de cómo puede tener acceso al Editor Web y cómo puede iniciarlo desde varias ubicaciones.

## Página de navegación de AEM {#id2056BG00RZJ}

Al iniciar sesión en AEM, se le muestra la página Navegación:

![](images/web-editor-from-navigation-page.png){width="800"}

Al hacer clic en el vínculo **Guías**, accederá directamente al Editor web.

![](images/web-editor-launch-page.png){width="800"}

Cuando haya iniciado el Editor Web sin seleccionar ningún archivo, aparecerá una pantalla en blanco. Puede abrir un archivo para editarlo desde el repositorio de AEM o desde su colección de Favoritos.

- Haga clic en el icono **Guías** (![](images/aem-guides-icon.png) ) para volver a la página Navegación de AEM.

- El botón **Cerrar** le lleva a un destino de acuerdo con su configuración:



  <details>

  <summary> Cloud Services </summary>

  Si utiliza Cloud Services, haga clic en el botón **Cerrar** para volver a la página Navegación de AEM.
  </details>

  <details>

  <summary> Software On-Premise</summary>

  Si utiliza el software On-premise de AEM Guides (4.2.1 y versiones posteriores), haga clic en el botón **Cerrar** de la derecha para volver a la ruta de acceso del archivo actual en la interfaz de usuario de Assets.

  </details>

## IU de AEM Assets {#id2056BG0307U}

Otra ubicación desde la que puede iniciar el Editor web es desde la interfaz de usuario de AEM Assets. Puede seleccionar uno o varios temas y abrirlos directamente en el Editor web. Para abrir un tema en el Editor Web, siga estos pasos:

1. En la interfaz de usuario de Assets, vaya al tema que desee editar.

   >[!NOTE]
   >
   > También puede ver el UUID del tema.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800"}

   >[!IMPORTANT]
   >
   > Asegúrese de tener los permisos de lectura y escritura en la carpeta que contiene el tema que desea editar.

1. Para obtener un bloqueo exclusivo sobre el tema, selecciónelo y haga clic en **Desproteger**.

   >[!IMPORTANT]
   >
   > Si el administrador ha configurado la opción **Deshabilitar edición sin desprotección**, debe desproteger el archivo antes de editarlo. Si no desprotege el archivo, no podrá ver la opción de edición.

1. Cierre el modo de selección de recursos y haga clic en el tema que desee editar.

   Se muestra la vista previa del tema.

   Puede abrir el editor web desde la vista de lista, la vista de tarjeta y el modo de vista previa.

   >[!IMPORTANT]
   >
   > Si desea abrir varios temas para editarlos, seleccione los temas que desee en la interfaz de usuario de recursos y haga clic en Editar. Asegúrese de que el explorador no tenga habilitado el bloqueador de ventanas emergentes; de lo contrario, solo se abrirá el primer tema de la lista seleccionada para editarlo.

   ![](images/edit-from-preview_cs.png){width="800"}

   Si no desea obtener una vista previa de un tema y desea abrirlo directamente en el Editor Web, haga clic en el icono Editar del menú de acción rápida desde la vista de tarjeta:

   ![](images/edit-topic-from-quick-action_cs.png){width="800"}

1. Haga clic en **Editar** para abrir el tema en el editor web.

   ![](images/edit-mode.png){width="800"}


## Consola de mapa DITA {#id2056BG090BF}

Para abrir el Editor Web desde la consola de mapas DITA, siga estos pasos:

1. En la interfaz de usuario de Assets, desplácese hasta el fichero de mapa DITA que contiene el tema que desea editar y haga clic en él.

   Se muestra la consola de mapas DITA.

1. Haga clic en **Temas**.

   Se muestra una lista de temas en el fichero de asignación. El UUID de los temas se muestra debajo del título del tema.

1. Seleccione el archivo de tema que desee editar.

1. Haga clic en **Editar tema**.

   ![](images/edit-topics-map-console_cs.png){width="800"}

1. El tema se abre en el Editor Web.

   >[!IMPORTANT]
   >
   > Si el administrador ha configurado la opción **Deshabilitar edición sin desprotección**, debe desproteger el archivo antes de editarlo. Si no desprotege el archivo, el documento se abrirá en el editor en modo de solo lectura.


**Tema principal:**&#x200B;[&#x200B; Trabajar con el editor web](web-editor.md)

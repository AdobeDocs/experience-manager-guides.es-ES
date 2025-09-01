---
title: Descargar e instalar plantillas de AEM Sites para servicios locales
description: Obtenga información sobre cómo descargar e instalar plantillas de AEM Sites para en Prem Services
feature: Installation
role: Admin
level: Experienced
source-git-commit: 20ba7f4582f1d155e555c9ff3ac58e1e3c400765
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Descargar e instalar plantillas de AEM Sites (servicios locales)

Esta guía proporciona instrucciones paso a paso para configurar la última plantilla de AEM Guides para generar AEM Sites. Siga estos pasos para instalar los paquetes necesarios, crear y configurar ajustes preestablecidos y generar AEM Sites.

## Requisitos previos

Antes de continuar con la configuración, asegúrese de que se cumplen los siguientes requisitos previos:

- **Adobe Experience Manager (AEM):** Una instancia en ejecución de **AEM 6.5** con **Service Pack** 21, 20 y 19 y **AEM Guides 4.6.0**, o versiones posteriores instaladas.

- **Permisos requeridos**: asegúrese de tener los siguientes permisos:

   - Acceso al **Portal de distribución de software** para descargar los paquetes necesarios
   - Acceso al **Administrador de paquetes de CRX** para instalar paquetes en AEM.
   - Permisos para crear y modificar ajustes preestablecidos en AEM Guides.

- **Descargar paquetes**: Descargue los siguientes paquetes del **Portal de distribución de software**:

   - Paquete de componentes: on-prem-guides-components.all-1.x.0.zip
   - Paquete de sitios: aemg-docs.all-1.x.0.zip

## Instalación de paquetes mediante el Administrador de paquetes de CRX

1. **Instalar el paquete de componentes:**
   1. Vaya a [**Administrador de paquetes CRX**](http://&lt;your-aem-instance>/crx/packmgr).
   2. Cargue e instale el paquete on-premise-guides-components.all-1.x.0.zip.

2. **Instale el paquete de Sites:** Cargue e instale el paquete aemg-docs.all-1.x.0.zip mediante el Administrador de paquetes de CRX.


## Crear y configurar ajustes preestablecidos del sitio de AEM

1. **Crear un nuevo ajuste preestablecido:**
   1. Abra un mapa DITA en AEM Guides y vaya al panel **Salida**.
   2. Seleccione **Crear ajuste preestablecido**.
   3. Seleccione el tipo como **AEM Sites**.
   4. Introduzca un nombre para el ajuste preestablecido.
   5. Desmarque la opción **Usar asignación de componentes heredados**.
   6. Seleccione **Agregar** para crear el ajuste preestablecido.

      ![Nuevo cuadro de diálogo de ajustes preestablecidos de salida](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Configurar ajuste preestablecido del sitio de AEM:** Hay dos opciones para configurar el sitio predeterminado (OOTB):

   **Opción 1: usar el menú desplegable del sitio**

   1. Seleccione **Sitio** como **Documentos de AEMG**.
   2. Compruebe que **Publish path** y **Topic page template** se hayan establecido automáticamente en:
      - Ruta de publicación: aemg-docs/en/docs/product1
      - Plantilla de página de tema: Página de tema.

      ![Usar menú desplegable del sitio](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Opción 2: usar la ruta del sitio**

   1. Establezca la **ruta del sitio** manualmente como /content/aemg-docs/en/docs/product1.
   2. Compruebe que **Plantilla de página de tema** se establece automáticamente como Página de tema.

      ![Usar ruta de acceso al sitio](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Guardar el ajuste preestablecido:** Guarde los cambios realizados en el ajuste preestablecido.

## Generar AEM Sites

1. **Generar sitio:**
   1. Con el ajuste preestablecido configurado, ahora se puede generar el sitio de AEM para el mapa DITA correspondiente.
   2. El sitio generado estará disponible en la ruta: /content/aemg-docs/en/docs/product1.
2. **Cambiar la ruta de acceso de generación predeterminada (opcional):** Si desea cambiar la ruta de acceso predeterminada para la generación de sitios, realice los siguientes pasos:

   1. Vaya a **AEM Sites**.
   2. Cree una nueva página de producto en la estructura del sitio OOTB.
   3. Vaya a **Documentos de AEMG** > **Inglés** > **Documentos**.

      ![Crear página en la estructura del sitio de AEM ](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Seleccione el mosaico **Página de inicio** y, a continuación, seleccione **Siguiente**.

      ![Seleccionar mosaico de página principal](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Escriba **Title** y **Name** para la página.
   6. Seleccione **Crear**.


---
title: Descargar e instalar plantillas de AEM Sites para Cloud Services
description: Obtenga información sobre cómo descargar e instalar plantillas de AEM Sites para Cloud Services
feature: Installation
role: Admin
level: Experienced
exl-id: 67f7ff26-fbc7-426c-aa7d-9bf4debf05d8
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# Descargar e instalar plantillas de AEM Sites (Cloud Services)

Esta guía proporciona instrucciones paso a paso para configurar la última plantilla de AEM Guides para generar páginas de AEM Sites en un entorno de nube. Siga estos pasos para instalar los paquetes necesarios, crear y configurar ajustes preestablecidos y generar AEM Sites.

## Requisitos previos

Antes de continuar con la configuración, asegúrese de que se cumplen los siguientes requisitos previos:

- **Adobe Experience Manager (AEM) Cloud**: Una instancia en ejecución de **AEM as a Cloud Service** con **AEM Guides 2502 o versiones posteriores**.

- **Permisos requeridos**: debe tener los siguientes permisos:

   - Acceso a **Cloud Manager** para implementar paquetes.
   - Acceso al **repositorio Git** asociado con su entorno.
   - Permisos para crear y modificar ajustes preestablecidos en AEM Guides.

- **Descargar paquetes**: Descargue los siguientes paquetes del Portal de distribución de software:

   - Paquete de componentes: guides-components.all-1.x.0.zip
   - Plantilla de sitios: aemg-docs-1.x.0.zip

## Instalación de paquetes mediante la implementación en la nube

Instale el paquete de **componentes (guides-components.all-1.x.x.zip)** y realice los siguientes pasos

1. **Clonar repositorio Git:**
   1. Vaya a **Repositorios** en el panel izquierdo de Cloud Manager.
   2. Seleccione **Acceder a la info del repositorio** y copie el comando clonar de Git.

      ![Seleccionar información de repositorio de acceso](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

   3. Clone el repositorio en el sistema local utilizando el nombre de usuario y la contraseña proporcionados (genere la contraseña si es necesario).
2. **Agregar paquete al paquete Maven:**
   1. En el repositorio clonado localmente, cree un nuevo paquete Maven o añádalo a uno existente.
   2. Asegúrese de que la estructura `/jcr_root/apps/fmdita/` instalada exista en el proyecto Maven.

      ![Estructura en el proyecto Maven](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


   3. Coloque el archivo guides-components.all-1.x.x.zip descargado en la carpeta de instalación.

3. **Actualizar filtros.xml:**

   1. Abra el archivo filters.xml ubicado en la carpeta META-INF del directorio de contenido principal.
   2. Agregue el siguiente filtro: filter root=`/apps/fmdita` mode=`merge`/


      ![Agregar filtro](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Configurar pom.xml:** Actualice el archivo pom.xml según los requisitos del entorno.
5. **Insertar cambios y ejecutar canalización:**
   1. Inserte los cambios en el repositorio principal de Git.
   2. Vaya a **Canalizaciones** en Cloud Manager y ejecute la canalización para el entorno deseado.
6. **Verificar instalación:** Una vez completada la implementación, el paquete de componentes se instalará en el entorno de nube de AEM.

## Crear sitio con plantillas instaladas

1. **Importar plantilla de sitios:**
   1. Vaya a la página de AEM Sites (servername/sites.html).
   2. Seleccione **Crear** > **Sitio** de la plantilla.
   3. Importe la plantilla de sitios aemg-docs-1.x.x.zip con la opción **Importar**.
2. **Seleccionar plantilla:** Seleccione **AEMG Docs 1.x.x** y luego seleccione **Siguiente**.
3. **Escriba los detalles del sitio:** Escriba el **Título del sitio** y **Nombre del sitio**.

   ![Crear sitio](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Seleccione **Crear**.

## Crear ajuste preestablecido del sitio AEM

1. **Crear un nuevo ajuste preestablecido:**
   1. Abra un mapa DITA en AEM Guides y vaya al panel **Salida**.
   2. Seleccione **Crear ajuste preestablecido**.
   3. Seleccione el tipo como **AEM Sites**.
   4. Introduzca un nombre para el ajuste preestablecido.
   5. Desmarque la opción **Usar asignación de componentes heredados**.

      ![Crear nuevo ajuste preestablecido del sitio AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350" align="left"}

   6. Seleccione **Agregar** para crear el ajuste preestablecido.
2. **Configurar ajuste preestablecido del sitio de AEM:** Hay dos opciones para configurar el sitio predeterminado (OOTB):

   **Opción 1: usar el menú desplegable del sitio**

   1. Seleccione **Sitio** como el creado anteriormente (por ejemplo, el sitio de documentos de AEMG).
   2. Compruebe que la plantilla **Publish path** y **Topic page** esté establecida automáticamente en:
      - Ruta de publicación: `/content/AEMG-Docs-Site/en/docs/product`
      - Plantilla de página de tema: Página de tema

      ![Use el menú desplegable del sitio para configurar el sitio de AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Opción 2: usar la ruta del sitio**

   1. Establecer la **ruta del sitio** manualmente como `/content/AEMG-Docs-Site/en/docs/product`.
   2. Compruebe que la plantilla **Página de tema** se establezca automáticamente en Página de tema.

      ![Use la ruta de acceso del sitio para configurar el sitio de AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

3. **Guardar el ajuste preestablecido:** Guarde los cambios realizados en el ajuste preestablecido.

## Generar AEM Sites

1. **Generar sitio:**
   1. Con el ajuste preestablecido configurado, genere el sitio de AEM para el mapa DITA correspondiente.
   2. El sitio generado estará disponible en la ruta: `/content/AEMG-Docs-Site/en/docs/product`.
2. **Cambiar la ruta de acceso de generación predeterminada (opcional):** Si desea cambiar la ruta de acceso predeterminada para la generación de sitios, realice los siguientes pasos:
   1. Vaya a **AEM Sites**.
   2. Cree una nueva página de producto en la estructura del sitio OOTB.
   3. Vaya a **Documentos de AEMG** > **Inglés** > **Documentos**.

      ![Creación de página](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}

   4. Seleccione el mosaico **Página de inicio** y, a continuación, seleccione **Siguiente**.

      ![Seleccionar mosaico de inicio](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

   5. Escriba **Title** y **Name** para la página.
   6. Seleccione **Crear**.

>[!NOTE]
>
> Asegúrese de que todas las configuraciones se prueben en un entorno que no sea de producción antes de su implementación en producción. <br><br> Consulte la [Implementación en la documentación de AEM as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview) para obtener más información.

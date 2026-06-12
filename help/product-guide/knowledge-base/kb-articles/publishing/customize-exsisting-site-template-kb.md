---
title: Personalizar las plantillas de sitio de AEM existentes para AEM Guides
description: Aprenda a personalizar las plantillas de sitio de AEM existentes para AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: d48709b8-f5b2-4545-ac65-838c5d8b1bae
TQID: https://experienceleague.adobe.com/mzWOXyP0Zr-tScAYAc4R1BBm9LaFKVhOIRbbb9DrVRQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 9555f90917819727b77daea4520b6bba2350129f
workflow-type: tm+mt
source-wordcount: 951
ht-degree: 2%

---

# Personalizar las plantillas de sitio de AEM existentes para AEM Guides

Esta guía proporciona instrucciones paso a paso para personalizar las plantillas de sitio de AEM existentes y utilizarlas con AEM Guides para generar AEM Sites a partir de temas y mapas DITA.

Si está utilizando la plantilla predeterminada AEM Guides (AEMG Docs), las configuraciones y los componentes ya están establecidos y se pueden utilizar tal cual para publicar el contenido de AEM Guides. Sin embargo, si desea utilizar las plantillas de AEM Sites existentes con personalización de marca para publicar contenido de AEM Guides, siga los pasos a continuación para alinear las plantillas de sitios con los requisitos de renderización de AEM Guides.


## Requisitos previos

- Tiene los permisos y el acceso adecuados a las plantillas de AEM.
- Comprenderá las plantillas editables de AEM y la estructura del sitio de AEM.
- Tiene una jerarquía de sitio existente creada con plantillas editables.
- Tiene al menos dos plantillas del proyecto existente:

   - **Plantilla de página de contenedor de documentación** utilizada para procesar el mapa DITA como raíz de documentación.
   - **Plantilla de página de tema** utilizada para procesar páginas de tema DITA individuales.

## Consideraciones de nomenclatura de plantillas

Los nombres de las plantillas variarán según la configuración del proyecto. Por ejemplo, en la configuración de documentos de AEMG de OOTB:

- Página de contenedor de documentación: `/conf/AEMG-Docs-Site/settings/wcm/templates/kb-content`

- Página de tema: `/conf/AEMG-Docs-Site/settings/wcm/templates/topic-content`

**Personalización:** El proceso de personalización implica dos pasos principales:

1. Configuración de plantilla: identifique y configure las dos plantillas (contenedor y tema).
2. Componentes de las guías de procesamiento: incruste los componentes de AEM Guides necesarios para habilitar funciones como tabla de contenido, navegación y visualización de metadatos.

## Configuración de plantilla

Elija y configure dos plantillas editables del sitio de AEM.

### Plantilla de página del contenedor de documentación

La plantilla Página de contenedor de documentación se utiliza para crear la página de contenedor de documentación del producto que procesa el contenido de un mapa DITA.

- Sirve como punto de entrada o página principal para un conjunto específico de documentación (por ejemplo, un manual o una guía del producto).
- Agregue la propiedad id=&quot;category-page&quot; al jcr:content del nodo inicial de la plantilla. Esto garantiza que AEM Guides trate automáticamente todas las páginas creadas a partir de esta plantilla como contenedores de documentación.

  ![Agregando id=&quot;category-page&quot;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650"}

- Agregue un componente Texto con la propiedad obligatoria: text=&quot;$category.html$&quot;.

  ![Agregando componente de texto](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650"}

- Normalmente incluye elementos de navegación, como vínculos a secciones o temas dentro de la documentación.
- Se puede personalizar para incluir marcas, encabezados, pies de página y otros elementos de diseño.

**Ejemplo de caso de uso:**
Si dispone de un mapa DITA para un manual de producto, la plantilla de página contenedora de documentación generará la página principal de dicho manual, mostrando una descripción general y vínculos a temas individuales.

### Plantilla de página de tema

- La **plantilla de página de tema** se usa para crear páginas para **temas DITA** individuales.
- Cada tema de un mapa DITA se representa como una página independiente utilizando esta plantilla.
- Contiene un **componente Texto** con la propiedad obligatoria: text=&quot;$topic.content$&quot;.

  ![Agregando componente de texto con propiedad obligatoria](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650"}

- Este marcador de posición se sustituye por el contenido real del tema DITA durante la generación del sitio.
   - El componente de texto se suele colocar dentro de un **componente Container** para garantizar un diseño y un estilo adecuados.
   - Se puede personalizar para incluir encabezados, pies de página y elementos de navegación coherentes en todas las páginas de temas.

**Ejemplo de caso de uso:**
Si tiene un tema DITA sobre &quot;Instrucciones de instalación&quot;, la plantilla de página del tema generará una página que mostrará el contenido de ese tema.

**Componente de contenedor:**

![Agregando componente de contenedor](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650"}

>[!NOTE]
>
> Asegúrese de que los componentes que usan sling:resourceType en `wcm/foundation/components` se migren al `core/wcm/components` correspondiente.

Añada el mismo componente de contenedor en la estructura de la misma plantilla:

![Agregando contenedor y componente de texto](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650"}

## Componentes de guías de procesamiento en plantillas personalizadas

Para habilitar las funciones de los componentes principales de AEM Guides, como la tabla de contenido, la redirección de páginas, la navegación y la visualización de metadatos, debe incluir componentes específicos de AEM Guides en las plantillas personalizadas. Estos componentes deben agregarse explícitamente a las plantillas editables correspondientes (Página de contenedor de documentación o Página de tema) para garantizar que la funcionalidad deseada esté disponible durante la generación del sitio y el tiempo de ejecución.

Consulte la tabla siguiente para obtener la lista de componentes y su uso:

| Característica | Nombre del componente | Descripción | Plantilla recomendada |
|---|---|---|---|
| Tabla de contenidos | guidessidenavigation | Procesa la tabla de contenido completa desde el mapa DITA | Página de tema |
| Redireccionamiento de página | child direct | Redirige a la primera página de tema del mapa | Contenedor de documentación |
| Mini TDC | minitoc | Muestra la tabla de contenido del tema actual | Página de tema |
| Última actualización | pageproperty | Muestra la última fecha de modificación | Página de tema |
| Localizador | buscapersonas | Permite la navegación entre las páginas de temas anterior y siguiente | Página de tema |
| Navegación por idiomas | language navigation | Permite cambiar entre distintas versiones de idioma | Cualquier plantilla |


## Casos de uso de componentes

- **Componente de redireccionamiento (child-direct):** Añádalo a la plantilla de página contenedora de documentación para que la página de inicio del producto generada a partir del mapa DITA se redirija automáticamente a la primera página de tema. Si la página contenedora de documentación está diseñada para actuar como una página de inicio independiente con componentes y diseño personalizados, este componente no es obligatorio.

- **Tabla de contenido (guidessidenavigation):** Agregue esto a la plantilla de la página del tema para procesar una tabla de contenido navegable junto con el contenido del tema. El índice se deriva del mapa DITA y ayuda a los usuarios a navegar por temas relacionados.


## Habilitar las bibliotecas de cliente de Guides

De forma predeterminada, las bibliotecas de cliente (clientlibs) proporcionadas en el paquete de componentes de AEM Guides no se aplican a las plantillas personalizadas. Para habilitarlos:

1. **Editar la plantilla:**

   1. Abra **Plantilla de página de contenedor** y **Plantilla de página de tema** en modo de editor.
   2. Seleccione **Editar plantilla** (se abrirá una dirección URL como conf/settings/wcm/templates/structure.html).

      ![Editar plantilla](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650"}

2. **Actualizar directiva de página:**

   1. Vaya al botón **Información de página** y seleccione **Política de página**.
   2. Añada las siguientes bibliotecas de cliente:
      - **Bibliotecas de cliente**
      - **Encabezado de página JavaScript de bibliotecas de cliente**

3. **Guardar cambios:** Guarde la plantilla después de agregar las bibliotecas de cliente necesarias.

   ![Agregar bibliotecas de cliente](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650"}


>[!NOTE]
>
> Asegúrese de que las plantillas se prueben en un entorno que no sea de producción antes de su implementación en producción.<br><br>Consulte la documentación oficial de [AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview) y [AEM Sites](https://experienceleague.adobe.com/es/docs/experience-manager-core-components/using/get-started/authoring) para obtener más detalles.

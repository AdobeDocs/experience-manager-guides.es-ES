---
title: Reutilización de contenido DITA en AEM Guides
description: Este breve artículo explica cómo AEM Guides y DITA le ayudan a ahorrar tiempo y esfuerzo al utilizar la reutilización de contenido
role: User, Admin
author: Pulkit Nagpal(punagpal)
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
TQID: https://experienceleague.adobe.com/zCktDt9h2K-lCluedb39M5cc40j34GATjIvm04kU-nc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 557
ht-degree: 0%

---

# Reutilización de contenido en AEM Guides

Adobe AEM Guides aprovecha los puntos fuertes de DITA para proporcionar una interfaz fácil de usar para la reutilización de contenido.

Este artículo analizará:

1. [Reutilización mediante referencia de tema (`topicrefs`)](#reusability-using-topic-referencestopicref)
2. [Reutilización mediante referencia de contenido (`conref` y `conkeyref`)](#reusability-using-content-reference-conref--conkeyref)
3. [Sugerencia de bonificación para reutilizar contenido con arrastrar y soltar en AEM Guides](#reuse-content-with-a-single-click-in-aem-guides)

## Reutilización mediante referencias de temas (topicref)



Supongamos que es una empresa de fabricación y que tiene temas genéricos para precauciones de seguridad o técnicas de resolución de problemas.

Se pueden consultar y adaptar en manuales de usuario específicos para cada modelo de máquina, reduciendo la redundancia y asegurando que la información de seguridad central siga siendo coherente.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>
```


Del mismo modo para el modelo 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>
```

## Reutilización mediante referencia de contenido (conref y conkeyref)

El atributo content reference (conref) permite vincular otras partes del contenido. Esto promueve la reutilización y reduce la redundancia.

Por ejemplo:

Supongamos que es una empresa financiera y tiene un tema genérico para KYC que contiene procedimientos KYC para individuos, empresas, etc.

Desea reutilizar el fragmento KYC individual para los temas &quot;Cuenta de almacenamiento&quot; y &quot;Cuenta de demostración&quot;.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

Aquí `conref=kyc_procedures.dita#indvidual_kyc` key_processes.dita es el identificador de archivo y #individual_kyc es el identificador de fragmento.

Kyc_procedure.dita sigue siendo la única fuente de información. Si los cambios regulatorios requieren actualizaciones en el proceso KYC, actualice la ruta del tema con la nueva. Los cambios se reflejarán automáticamente en todos los temas que hagan referencia a él.

Con AEM Guides, son dos clics

Paso 1: Haga clic en Insertar contenido reutilizable
![barra de herramientas](../../assets/publishing/content-reusability_image1.png)

<br>

Paso 2: Seleccione el archivo y el fragmento que debe reutilizarse.
![conref](../../assets/publishing/content-reusability_image2.png)

Al igual que &quot;conref&quot;, puede utilizar &quot;conkeyref&quot; donde, en lugar de proporcionar una ruta de contenido, se hace referencia al contenido mediante una clave

Ejemplo de código:

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

La definición de la clave tiene este aspecto:

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Clave: &quot;Key_procedure&quot; sigue siendo la única fuente de información. Si hay cambios en el proceso KYC según lo requerido por las regulaciones, simplemente necesita actualizar una ruta de tema con una nueva ruta de tema, y esos cambios se reflejan automáticamente en todos los temas que se refieren a ella.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

En este caso, la ruta del tema cambia de &quot;kyc_procedure_2020.dita&quot; a &quot;kyc_procedure_2024.dita&quot; debido a los cambios recientes en la regulación.

Con AEM Guides, son dos clics

Paso 1: Haga clic en Insertar contenido reutilizable
![barra de herramientas](../../assets/publishing/content-reusability_image1.png)

Paso 2: Seleccione el mapa raíz (opcional), la clave y el fragmento que debe reutilizarse.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

Aquí el mapa raíz se seleccionó automáticamente porque ya estaba abierto en la vista del mapa.


## Reutilización del contenido con un solo clic en AEM Guides

AEM Guides ofrece la capacidad &quot;Contenido reutilizable&quot; para agregar referencias de contenido con un solo clic.

Paso 1: Agregar un tema genérico a contenido reutilizable

![Agregar contenido reutilizable](../../assets/publishing/content-reusability_image4.png)

Paso 2: Una vez agregado, arrastre y suelte el fragmento que desee reutilizar en cualquiera de los temas de destino.

![Agregar gif de contenido reutilizable](../../assets/publishing/content-reusability_image5.gif)



## Preguntas frecuentes

### No se muestra todo el contenido después de seleccionar el archivo o la clave en el cuadro de diálogo Reutilizar contenido

Asignar ID a fragmentos (elementos Dita) que desee reutilizar en otros temas

## Las claves no se muestran en el cuadro de diálogo Reutilizar contenido

Asegúrese de haber abierto el mapa raíz/mapa principal en la vista de mapa, que tiene una definición de clave, o agregue la ruta del mapa raíz manualmente en el mismo cuadro de diálogo.


<br>
<br>
<br>


Publica en la comunidad de AEM Guides [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) para cualquier consulta.

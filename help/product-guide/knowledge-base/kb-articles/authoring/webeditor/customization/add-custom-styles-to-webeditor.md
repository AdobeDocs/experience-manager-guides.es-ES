---
title: Agregar estilos personalizados al Editor web de guías
description: Aprenda a añadir estilos personalizados para cambiar la apariencia del editor web de Guías.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Agregar estilos personalizados al Editor web de guías

En este artículo aprenderemos a añadir estilos personalizados para cambiar el aspecto y la presentación predeterminados del editor web.

Esto implica los siguientes pasos:
- Añadir los estilos personalizados mediante la configuración del editor XML de perfil de carpeta
- Selección del perfil de carpeta respectivo en el editor web y prueba de los cambios


## Implementación de mediante un ejemplo

Comprendamos esto con un ejemplo en el que queremos mostrar la descripción breve y el título como bloque independiente con algunos aspectos de estilo en el editor.

![Vista previa del editor web con estilos personalizados](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementación de esto


### Añadir el CSS personalizado al perfil de carpeta

Utilice los perfiles de carpeta para comprobar la *css_layout.css* en la pestaña &quot;Configuración del editor XML&quot; y añada el archivo CSS con estilos personalizados

[utilice este vínculo para obtener más información sobre el perfil de carpeta y la configuración del diseño de la plantilla CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Utilice lo siguiente para configurar el estilo anterior en el editor web:
- Uso [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) y cárguelo en el perfil de carpeta que elija
- Instalación del paquete adjunto [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) AEM uso del administrador de paquetes de datos para instalar los recursos utilizados en el archivo CSS anterior

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Pruebas

- Abrir editor web
- En las preferencias del usuario, elija el perfil de carpeta en el que ha añadido los estilos personalizados. Si lo ha agregado al Perfil global, probablemente ya esté utilizando.
- Al abrir un tema, verá que el área de edición debe tener una interfaz de usuario personalizada

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Referencias

También le puede interesar la sesión de expertos sobre las configuraciones y personalizaciones de los editores web que se explica en [Sesión de experto en el editor web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)

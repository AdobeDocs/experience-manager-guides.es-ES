---
title: Configuración de Dispatcher
description: Obtenga información sobre cómo configurar Dispatcher
feature: Installation
role: Admin
level: Experienced
exl-id: 4b7b4e9b-0a5c-4b61-87d9-a6bd6494c030
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 6%
---
# Configuración de Dispatcher {#id213BCM0M05U}

Si planea utilizar una instancia de Dispatcher en AEM Author junto con AEM Guides, debe realizar las siguientes configuraciones adicionales para completar la configuración:

>[!NOTE]
>
> Dispatcher es la herramienta de almacenamiento en caché o de equilibrio de carga de Adobe Experience Manager. Para obtener más información acerca del uso de Dispatcher, consulte [Información general de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=es).

## Habilitar AllowEncodedSlashes en las direcciones URL

Las direcciones URL con barras codificadas no están habilitadas de forma predeterminada en la configuración de AEM Dispatcher, pero mientras trabaja en AEM Guides debe habilitarlas. Para ello, debe establecer el parámetro `AllowEncodedSlashes` en **On** en la configuración de Apache como se muestra en el siguiente fragmento de código:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configuración del archivo mime.types para DITA

Al utilizar una Dispatcher con AEM Guides, debe asegurarse de que el mapa DITA y los archivos de tema se representan como HTML para que los autores vean el contenido como esperan \(en lugar del formato de texto sin procesar\).

Siga estos pasos para actualizar el archivo `mime.types`:

1. Conéctese al servidor de Dispatcher mediante SSH y busque el archivo `httpd.conf`.

1. Compruebe la ruta de acceso del archivo `mime.types`.

1. Abra el archivo `mime.types` y busque &quot; text/html&quot;. La asignación predeterminada para &quot; text/html&quot; es:

   `text/html html htm`

1. Actualice la asignación añadiendo extensiones ditamap y dita como:

   `text/html html htm ditamap dita`

1. Guarde y cierre el archivo.


Esta actualización de configuración garantiza que los archivos de tema y mapa DITA representados por Dispatcher se muestren como HTML en la interfaz de usuario de Assets.

## Permitir URL de solicitud de preferencias de usuario

Cuando utilice una Dispatcher con AEM Guides, si la instancia de autor tiene una instancia de Dispatcher delante, realice los dos cambios siguientes:

- Incluya en la lista blanca la URL de petición POST. A continuación se muestra una regla `/filters` de muestra: Agregar esta regla al archivo de configuraciones de Dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Asegúrese de que el patrón de URL `/libs/cq/security/userinfo.json` no se almacene en caché en el Dispatcher de autor; por lo tanto, agregue una regla `\(like below\)` en `author\_dispatcher.any`

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

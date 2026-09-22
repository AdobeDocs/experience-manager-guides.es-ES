---
title: Configuración del asistente de IA en modo automático
description: Aprenda a configurar el asistente de inteligencia artificial aplicada a la agencia en Experience Manager Guides
source-git-commit: 5ed0a5191e1852dd65e0461f02d520b195f7cc39
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 1%
---

# Configuración del asistente de IA en modo automático para Cloud Service

Como administrador, puede configurar el asistente de IA en modo automático para su organización en Experience Manager Guides. Los pasos de configuración varían según si la configuración de Unified Shell está habilitada en su entorno de AEM as a Cloud Service y si los usuarios iniciaron sesión mediante la autenticación SSO o sin SSO. Este artículo describe el proceso de configuración para cada escenario.

## Requisitos previos

Su organización debe incorporarse a **CX Enterprise Coworker** antes de configurar el asistente de IA en modo automático.

## Configurar el asistente de IA en función de su entorno

Utilice la siguiente tabla para identificar qué ruta de configuración se aplica a los usuarios y, a continuación, siga los pasos correspondientes.

| Shell unificado | Tipo de inicio de sesión | Configuración requerida |
|---|---|---|
| Habilitado | SSO | No hay ninguna configuración adicional. Todo funciona de forma predeterminada |
| Habilitado | No SSO | Añadir la configuración de IMS al entorno |
| Deshabilitado | SSO | Añadir la configuración de IMS al entorno |
| Deshabilitado | No SSO | Añadir la configuración de IMS al entorno |

### Usuarios con el shell unificado habilitado

**inicio de sesión SSO**

Si el shell unificado está habilitado y los usuarios inician sesión mediante SSO, no se requiere ninguna configuración adicional. El asistente de IA en modo automático funciona una vez que su organización se ha incorporado a CX Enterprise Coworker.

**Inicio de sesión sin SSO**

Si el shell unificado está habilitado pero los usuarios inician sesión sin SSO, debe [agregar la configuración de IMS al entorno](#add-ims-configuration-to-the-environment) a continuación.

### Usuarios con el shell unificado deshabilitado

Si el shell unificado está deshabilitado, debe [agregar la configuración de IMS al entorno](#add-ims-configuration-to-the-environment) para ambos:

- Inicio de sesión SSO
- Inicio de sesión sin SSO

## Añadir la configuración de IMS al entorno

Siga estos pasos para agregar la configuración de IMS al entorno:

1. Abra Experience Manager y, a continuación, seleccione el programa que contiene el entorno que desea configurar.

2. Cambie a la ficha **Entornos**.

3. Seleccione el nombre del entorno que desea configurar. Esto lo llevará a la página **Información del entorno**.

4. Cambie a la ficha **Configuración**.

5. Pegue los detalles del servicio JSON (descargados cuando creó la configuración de IMS en Adobe Developer Console) en el campo **Value** correspondiente a `SERVICE_ACCOUNT_DETAILS`. Asegúrese de utilizar el mismo nombre y la misma configuración que el entorno espera.

>[!NOTE]
>Si todavía no ha creado las credenciales de OAuth/IMS para su entorno, primero debe hacerlo en Adobe Developer Console antes de completar este paso.

![configuración de cuenta de servicio de ims](assets/ims-service-account-config.png){width="800"}

## Habilitar el modo de agente

Una vez completada la configuración para su entorno, póngase en contacto con el equipo de éxito del cliente para habilitar el modo automático.

Con el modo Agente habilitado para su entorno, vaya a **Configuración de Workspace** y habilite la opción **Agente** en la pestaña **General** de la sección **Asistente de IA**.

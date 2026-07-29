---
title: Actualizaciones de la API en versiones de Experience Manager Guides
description: Obtenga información acerca de las distintas actualizaciones de la API en las versiones de Experience Manager Guides
source-git-commit: 24637376024107ae575620e5491c0150da6cc956
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---


# Actualizaciones de la API en versiones de Experience Manager Guides

Este artículo proporciona detalles de las API recién agregadas en la documentación de Swagger para versiones de Adobe Experience Manager Guides. Para obtener acceso a la documentación de Swagger a través de la interfaz de AEM, vaya a **Herramientas** > **Guías** > **API Swagger**.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Versión 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Característica</td>
        <td>Subfunción</td>
        <td>Método</td>
        <td>API</td>
        <td>Descripción</td>
    </tr>
    <tr>
        <td rowspan="7"><b>Recursos</b></td>
        <td rowspan="7"></td>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/asset/import"</td>
        <td>Importa uno o varios recursos en una carpeta de destino; admite la carga de varias partes y la resolución de conflictos</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>`/bin/guides/v1/asset/list`</td>
        <td>Devuelve la lista paginada de recursos bajo una ruta de carpeta</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>`/bin/guides/v1/asset/validatexml`</td>
        <td>Valida el XML DITA para el formato correcto, la validez de esquema y la integridad de conref</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/asset/version/revert"</td>
        <td>Revierte un recurso a una versión especificada</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/asset/currentversion/detail"</td>
        <td>Devuelve los detalles de la versión actual (nombre de la versión, estado sucio, etiquetas, etc.)</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/assets/status"</td>
        <td>Inicia un trabajo asincrónico para comprobar el estado de las guías de los recursos en una ruta determinada</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/assets/status"</td>
        <td>Recupera el estado/los resultados de un trabajo de estado del activo por ID de trabajo</td>
    </tr>
    <tr>
        <td rowspan="3"><b>Publicación</b></td>
        <td rowspan="3"></td>
        <td>PUBLICAR</td>
        <td>`/bin/guides/v1/output/generate`</td>
        <td>Inicia la ejecución del ajuste preestablecido para generar la salida de un mapa</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status`</td>
        <td>Devuelve el estado de una sola generación de salida por ruta de mapa e ID de generación</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status/list`</td>
        <td>Devuelve el estado de todos los ajustes preestablecidos generados para una ruta de mapa</td>
    </tr>
    <tr>
        <td rowspan="18"><b>Traducción</b></td>
        <td rowspan="6">Idioma</td>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/copies"</td>
        <td>Copias de idioma de un recurso por ruta o UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/groups"</td>
        <td>Grupos de idiomas para un perfil de carpeta</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/list"</td>
        <td>Admite idiomas de traducción (filtrados)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/root"</td>
        <td>Idiomas raíz disponibles para una ruta de recursos</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/variable"</td>
        <td>Variables de idioma por tipo y códigos de idioma</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/language/variable"</td>
        <td>Crea, actualiza o elimina variables de idioma</td>
    </tr>
    <tr>
        <td rowspan="7">Proyecto</td>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/project/create"</td>
        <td>Creación/actualización de un proyecto de traducción para un mapa DITA</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/project/sync"</td>
        <td>Crea/actualiza un proyecto de traducción (flujo de sincronización)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/creationstatus"</td>
        <td>Estado de sincronización de traducción de un proyecto por ruta</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/existing"</td>
        <td>Proyectos de traducción existentes para el usuario actual</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/inprogress"</td>
        <td>Proyectos en curso para un recurso determinado</td>
    </tr>
    <tr>
        <td>ELIMINAR</td>
        <td>"/bin/guides/v1/translation/project/delete"</td>
        <td>Actualización previa a la eliminación de los estados o las propiedades de traducción de recursos</td>
    </tr>
    <tr>
        <td>ELIMINAR</td>
        <td>"/bin/guides/v1/translation/project/job/delete"</td>
        <td>Actualización de la eliminación previa de los estados de los recursos antes de eliminar el trabajo</td>
    </tr>
    <tr>
        <td rowspan="5">Referencia</td>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/reference/accept"</td>
        <td>Aceptar contenido traducido de las páginas secundarias del trabajo</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/reference/reject"</td>
        <td>Rechazar contenido traducido de páginas secundarias del trabajo</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/reference/sync"</td>
        <td>Creación de copias de idioma en carpetas de destino</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/reference/baseline/export"</td>
        <td>Exportar línea base de traducción a los idiomas de destino</td>
    </tr>
    <tr>
        <td>PUBLICAR</td>
        <td>"/bin/guides/v1/translation/reference/status/forcesync"</td>
        <td>Forzar la actualización de recursos no sincronizados a recursos no sincronizados</td>
    </tr>
</table>

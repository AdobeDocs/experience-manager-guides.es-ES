---
title: Métricas clave de SCORM para el progreso del alumno y la finalización del curso
description: Obtenga información acerca de las métricas clave de SCORM para el progreso del alumno y la finalización del curso
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: 'https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 1%
---
# Métricas clave de SCORM para el progreso del alumno y la finalización del curso

El artículo enumera los parámetros clave capturados en un paquete SCORM, junto con sus campos correspondientes y ejemplos. Estos parámetros proporcionan información crítica sobre el progreso del alumno, la finalización del curso, los detalles de interacción y el rendimiento de las pruebas. Los administradores pueden utilizar esta información para validar el seguimiento, configurar los informes y garantizar análisis precisos dentro del entorno de LMS. A continuación se proporcionan valores de muestra para cada parámetro tal como aparece en el paquete SCORM.

| **Nombre del parámetro** | **Descripción** | **Campos** | **Ejemplo** |
|---|---|---|---|
| **Estado de finalización del curso** | Indica si el curso se ha completado o no | cmi.completion_status | incompleto |
| **Recuento de intentos** | Número de intentos del alumno | Contador/contenido de intentos del lado de LMS | Intentos: 1 |
| **Ubicación del paquete SCORM** | Marcador o ubicación actual en el curso | cmi.location | - |
| **Finalización del progreso** | Progreso del alumno | cmi.progress_measure | 0,87 |
| **Tiempo total (intento)** | Tiempo total empleado en el intento actual | cmi.total_time | 0000:01:09.87 |
| **Visibilidad del índice y recuento de temas** | Muestra visibilidad del índice y detalles de finalización del tema | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Estado por tema** | Finalización y estado de aprobación de cada tema | Estado personalizado por lección | - |
| **Por estado de elección de pregunta** | Registra las opciones seleccionadas del alumno por pregunta | value, generated_id, selected | - |
| **Puntuación general de la pregunta** | Puntuación obtenida en el nivel de pregunta y agregada | {&quot;score&quot;:0,&quot;maxScore&quot;:1} y % | &quot;score&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interacciones en cada nivel de pregunta** | Detalles de la interacción del alumno por pregunta | id/type/timestamp/right_response/learner_response/result/latency | - |
| **Estado general del curso** | Indica aprobación/error y progreso general | success_status, completion_status, score, progress_measure | Si se pasó o no |
| **Detalles del alumno** | Identifica al alumno por ID y nombre | cmi.learner_id, cmi.learner_name | Albert |
| **Parámetros de prueba** | Configuraciones para el tiempo de prueba y la puntuación de aprobación | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valores no definidos o configurados |

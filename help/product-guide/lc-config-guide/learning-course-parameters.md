---
title: Métricas clave de SCORM para el progreso del alumno y la finalización del curso
description: Obtenga información acerca de las métricas clave de SCORM para el progreso del alumno y la finalización del curso
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 0dff380131dadc971f257eb464700392328164e5
workflow-type: tm+mt
source-wordcount: '279'
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
| **Tiempo total (intento)** | Tiempo total empleado en el intento actual | cmi.total_time | 0000:01:09,87 |
| **Visibilidad del índice y recuento de temas** | Muestra visibilidad del índice y detalles de finalización del tema | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Estado por tema** | Finalización y estado de aprobación de cada tema | Estado personalizado por lección | - |
| **Por estado de elección de pregunta** | Registra las opciones seleccionadas del alumno por pregunta | value, generated_id, selected | - |
| **Puntuación general de la pregunta** | Puntuación obtenida en el nivel de pregunta y agregada | {&quot;score&quot;:0,&quot;maxScore&quot;:1} y % | &quot;score&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interacciones en cada nivel de pregunta** | Detalles de la interacción del alumno por pregunta | id/type/timestamp/right_response/learner_response/result/latency | - |
| **Estado general del curso** | Indica aprobación/error y progreso general | success_status, completion_status, score, progress_measure | Si se pasó o no |
| **Detalles del alumno** | Identifica al alumno por ID y nombre | cmi.learner_id, cmi.learner_name | Albert |
| **Parámetros de prueba** | Configuraciones para el tiempo de prueba y la puntuación de aprobación | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valores no definidos o configurados |
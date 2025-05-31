# Laboratorio: Refactorización y Evolución de Sistema Heredado RAG FIEE-UNI

## Descripción

Este laboratorio aborda el análisis, refactorización, evolución y administración de un sistema heredado de Recuperación de Información (RAG) para la Facultad de Ingeniería Eléctrica y Electrónica (FIEE) de la UNI. El proyecto incluye extracción de texto, generación de embeddings, integración con modelos de lenguaje y pruebas unitarias.

---

## Contenido del Laboratorio

### 1. Análisis del Sistema Legado

- Revisión del código original para identificar:
  - Módulos críticos y su función.
  - Código duplicado y lógica confusa.
  - Áreas con bajo rendimiento y falta de pruebas.
- Se detectó duplicación en funciones de procesamiento de texto y validación.
- Se identificó que la lógica de interacción y procesamiento estaba mezclada dificultando el mantenimiento.

### 2. Definición de Requerimientos de Evolución

- Introducción de nuevas funcionalidades como generación de reportes mensuales y notificaciones.
- Corrección de bugs detectados en validaciones y modularidad.
- Optimización del rendimiento mediante mejor estructuración del código y uso eficiente de la base de datos vectorial.

### 3. Control de Versiones

- Uso de Git para gestionar los cambios.
- Se definió un flujo básico para crear ramas, hacer commits y fusionar cambios.
- Se resaltó la importancia de realizar commits pequeños y frecuentes para facilitar el control y revisión.

### 4. Pruebas Unitarias

- Creación de tests para funciones críticas utilizando `pytest`.
- Uso de mocks para simular llamadas a APIs externas (OpenAI).
- Ajustes en los tests para adaptarse a la nueva API y a la lógica actualizada.
- Cobertura sobre funciones de procesamiento de texto, OCR, generación de reportes y notificaciones.

### 5. Discusión y Retroalimentación

- Se documentaron los cambios realizados y problemas resueltos.
- Mejoras destacadas en modularidad, cobertura de pruebas y rendimiento en tests.
- Dificultades enfrentadas con importaciones, adaptación a cambios en librerías externas y ajuste de tests.

### 6. Administración de Sistemas Heredados

- **Migración gradual:** Dividir el sistema en módulos para migrar sin interrumpir operaciones.
- **Wrappers:** Usar envoltorios para integrar el sistema con nuevas tecnologías sin modificar el código original.
- **Microservicios:** Encapsular funcionalidades en servicios independientes para mejorar escalabilidad y mantenimiento.
- **Documentación continua:** Mantener actualizada la arquitectura, usar documentación automática y registros de cambios, y capacitar al equipo.

---

## Estructura del Proyecto



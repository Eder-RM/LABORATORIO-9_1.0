# Laboratorio 9: Evolución, Mantenimiento y Administración de Sistemas Heredados

## Descripción General

Este proyecto corresponde al Laboratorio 9 del curso de Evolución, Mantenimiento y Administración de Sistemas Heredados, aplicado al sistema RAG FIEE-UNI. Se enfoca en la modernización y mejora continua de un sistema legado que combina procesamiento OCR, generación y consulta de embeddings mediante FAISS y modelos de lenguaje para asistencia tipo chatbot.

El objetivo principal es refactorizar el código para mejorar modularidad, robustez y rendimiento, corregir errores detectados, implementar pruebas unitarias, y añadir funcionalidades que soporten una gestión sostenible y escalable del sistema.

---

## 1. Análisis del Sistema Legado

### Módulos clave identificados:

- **app.py:** Controla la interfaz con el usuario y la lógica del chatbot, integrando modelos de lenguaje y base vectorial FAISS.
- **json_to_embeddings.py:** Limpia y segmenta documentos JSON, genera embeddings y construye la base FAISS para consultas.
- **ocr_to_json.py:** Utiliza OCR para extraer texto de imágenes y PDFs, almacenando el resultado en JSON.
- **visualization_bd_vectorial.py:** Visualiza la base de embeddings usando reducción dimensional PCA para análisis exploratorio.
- **test_fiee_rag_real.py:** Conjunto de pruebas unitarias e integración para validar funcionalidades con datos reales y simulados.

### Problemas detectados en el código legado:

- Código monolítico con funciones extensas y responsabilidades mezcladas que dificultan la mantenibilidad.
- Repetición de código y prompts similares en múltiples partes, generando redundancia y posibilidad de errores.
- Ausencia de pruebas unitarias robustas, con cobertura limitada y falta de casos críticos.
- Manejo insuficiente y genérico de excepciones, que no facilita una correcta gestión de errores ni recuperación.
- Escasa documentación y comentarios en el código, dificultando la comprensión y extensión del sistema.
- Carga repetitiva y costosa de modelos de lenguaje y embeddings, sin mecanismos de caché o reutilización eficiente.
- Visualización de datos poco modular, sin control adecuado de excepciones ni posibilidad de reutilización en diferentes contextos.

---

## 2. Definición de Requerimientos de Evolución

### Nuevas funcionalidades propuestas:

- Incorporación de reportes mensuales automáticos que resuman estadísticas clave del procesamiento, uso y desempeño del sistema.
- Implementación de un sistema de notificaciones y alertas que avise en puntos críticos del flujo, como fallos en el OCR, errores en la carga o consulta de la base de datos vectorial.
- Configuración flexible para activar o desactivar estas alertas y definir parámetros de monitoreo.

### Mejoras en corrección de errores:

- Implementar un manejo de excepciones específico y robusto para cada módulo, facilitando diagnóstico y corrección.
- Mejorar las validaciones de entrada y salida en los procesos de OCR y generación de embeddings para evitar fallos silenciosos o errores no controlados.
- Ajustar los flujos de procesamiento para garantizar integridad y consistencia en la base de datos vectorial.

### Optimización:

- Refactorización del código para evitar la recreación repetitiva de modelos de lenguaje, prompts y bases de embeddings, mediante caché y reutilización inteligente.
- Modularización clara y separación de responsabilidades en archivos y funciones, para facilitar pruebas, mantenimiento y evolución.
- Optimización en almacenamiento y consultas a la base FAISS, mejorando escalabilidad y tiempos de respuesta.

---

## 3. Plan de Mantenimiento y Evolución

- **Fase 1: Pruebas Unitarias**  
  Ampliar cobertura en `test_fiee_rag_real.py` para funciones clave y módulos visuales, garantizando robustez.

- **Fase 2: Refactorización Modular**  
  Separar responsabilidades, dividir funciones monolíticas, centralizar prompts y configuraciones, y mejorar legibilidad.

- **Fase 3: Optimización y Manejo de Errores**  
  Introducir caché para modelos y bases de datos, optimizar consultas y mejorar mensajes de error para facilitar mantenimiento.

- **Fase 4: Nuevas Funcionalidades**  
  Incorporar reportes automáticos y sistema de alertas configurables para monitoreo y mejora continua.

Se recomienda el uso de control de versiones mediante ramas específicas para cada fase, con revisiones exhaustivas antes de integrar cambios a la rama principal.

---

## 4. Implementación y Refactorización

- División del código en funciones y módulos especializados para mejorar legibilidad, mantenimiento y escalabilidad.
- Corrección de errores de importación y lógica en funciones críticas.
- Integración de nuevas funcionalidades con pruebas automatizadas que aseguren calidad y confiabilidad.
- Optimización del rendimiento mediante reutilización de modelos y estructuras de datos, reduciendo tiempos de carga y respuesta.

---

## 5. Validación y Evaluación

- Ejecución continua de pruebas unitarias y de integración para detectar y corregir errores tempranamente.
- Ajustes en pruebas para reflejar correctamente la funcionalidad real del sistema.
- Mejoras evidentes en modularidad del código y cobertura de pruebas, facilitando futuras evoluciones.
- Resolución de problemas iniciales relacionados con importaciones y lógica de procesamiento, logrando estabilidad.

---

## 6. Administración de Sistemas Heredados (Aplicado al Proyecto RAG FIEE-UNI)

### Estrategias recomendadas:

- **Migración gradual:**  
  Actualización progresiva de módulos críticos sin interrumpir el servicio, manteniendo compatibilidad y operación continua.

- **Uso de wrappers o envoltorios:**  
  Implementación de interfaces limpias que aíslan el código heredado del nuevo, facilitando mantenimiento y futuras integraciones.

- **Microservicios (visión a futuro):**  
  Fragmentación del sistema en servicios independientes y escalables para mejorar mantenimiento, despliegue y resiliencia.

### Documentación Continua

- Mantener documentación clara, actualizada y accesible para cada módulo y proceso del sistema.
- Uso de herramientas automáticas para generación y mantenimiento de documentación y changelogs.
- Capacitación constante del equipo para preservar modularidad, calidad y coherencia en las evoluciones futuras.



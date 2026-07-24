# Dataset: Evaluación de Accesibilidad Digital en Sitios Web de la UNLP

## Descripción General

Este repositorio contiene los datos en formato CSV derivados de una auditoría automatizada de accesibilidad web sobre los portales institucionales de la Universidad Nacional de La Plata (UNLP) y sus 17 facultades.

El dataset forma parte de la investigación **"Digital Accessibility in Higher Education: Assessment of Barriers and the Potential of Artificial Intelligence for Inclusion"**, cuyo objetivo es identificar y caracterizar barreras de accesibilidad desde el enfoque de la Interacción Humano-Computadora (HCI) y el modelo social de la discapacidad.

## Metodología de Recolección de Datos

Los datos fueron recolectados mediante la herramienta de evaluación automatizada **Pa11y (CLI)**, configurada para verificar conformidad con las **Pautas de Accesibilidad para el Contenido Web (WCAG) 2.2 nivel AA**.

* **Alcance:** Se analizaron 113 páginas web correspondientes a las 17 facultades de la UNLP.
* **Selección de páginas:** Se definieron 7 secciones representativas del recorrido típico del estudiante:

  * Inicio (Home)
  * Ingreso
  * Planes de estudio
  * Calendario académico
  * Contacto
  * Noticias
  * Becas
* **Procedimiento:** Para cada URL, Pa11y ejecuta una inspección automatizada sobre el DOM renderizado, identificando incumplimientos de criterios WCAG mediante reglas basadas en estándares W3C.
* **Volumen de datos:** Se registraron un total de **11.484 hallazgos**, clasificados en errores y advertencias.

## Estructura del Dataset (`analisis_accesibilidad.csv`)

El archivo CSV contiene las siguientes variables:

* `Fecha`: Fecha de ejecución de la evaluación.
* `Facultad`: Unidad académica evaluada.
* `Seccion`: Tipo de página analizada (ej. Home, Ingreso, Becas).
* `URL`: Dirección de la página evaluada.
* `Tipo`: Tipo de hallazgo reportado por Pa11y (Error, Warning, Notice).
* `Norma`: Estándar evaluado (WCAG 2.2 AA).
* `PrincipleCode`: Código del principio WCAG (1–4).
* `Principio`: Principio de accesibilidad afectado:
  * 1: Perceptible
  * 2: Operable
  * 3: Comprensible
  * 4: Robusto
* `Guideline`: Guía WCAG asociada al criterio.
* `Criterio`: Criterio de conformidad específico (ej. 1.4.3 Contrast (Minimum), 1.1.1 Non-text Content, 4.1.1 Parsing).
* `Tecnica`: Técnica o fallo documentado por W3C (ej. H37, H30, F77).
* `Code`: Código interno generado por Pa11y/HTML CodeSniffer.
* `Mensaje`: Descripción del problema detectado.
* `Selector`: Selector CSS del elemento HTML afectado.

## Hallazgos Principales

El análisis exploratorio del dataset evidencia:

* Alta concentración de problemas en los principios:

  * **Perceptible (60.55%)**
  * **Robusto (37.96%)**
* El criterio con mayor nivel de incumplimiento es:

  * **1.4.3 – Contraste mínimo (38.81%)**
* Frecuencia significativa de técnicas asociadas a:

  * Falta de texto alternativo en imágenes (H37)
  * Problemas de estructura de enlaces (H30)
  * Errores de parsing y validación HTML (F77, 4.1.1)

Estos resultados sugieren deficiencias sistemáticas en la implementación de buenas prácticas de accesibilidad, particularmente en la percepción visual y la robustez del código.

## Limitaciones

* La evaluación es **automatizada**, por lo que no cubre completamente aspectos que requieren validación manual (ej. comprensión del contenido, semántica contextual).
* Los resultados dependen del estado del DOM al momento del análisis (contenido dinámico puede variar).
* No se incluyeron pruebas con tecnologías asistivas (lectores de pantalla, navegación por teclado real).

## Uso del Dataset

Este dataset puede utilizarse para:

* Análisis exploratorio de accesibilidad web
* Identificación de patrones de incumplimiento WCAG
* Entrenamiento de modelos de clasificación o detección automática
* Visualización en herramientas de BI (Power BI, Tableau, etc.)

## Licencia

Este dataset se distribuye bajo licencia **GNU General Public License v3.0 (GPL-3.0)**, promoviendo su reutilización en el marco de la ciencia abierta.

## Contacto

Paola Amadeo
[pamadeo@linti.unlp.edu.ar](mailto:pamadeo@linti.unlp.edu.ar)

# Dataset: Digital Accessibility Evaluation at UNLP

## Descripción General
Este repositorio contiene los datos crudos (en formato CSV) resultantes de la auditoría automática de accesibilidad web realizada en los portales institucionales de la Universidad Nacional de La Plata (UNLP) y sus 17 facultades. 

El dataset forma parte de la investigación **"Digital Accessibility in Higher Education: Assessment of barriers and the potential of artificial intelligence for inclusion"**, cuyo objetivo es diagnosticar las barreras de accesibilidad desde la Interacción Humano-Computadora (HCI).

## Metodología de Recolección de Datos
Los datos fueron recolectados utilizando la herramienta automatizada **Pa11y-CLI**, evaluando el nivel de conformidad **WCAG 2.2 AA**.
- **Alcance:** Se analizaron 113 páginas web distribuidas en 7 categorías representativas para la vida universitaria (Home, Ingreso, Planes de Estudio, Calendario, Contacto, Noticias y Becas).
- **Volumen de datos:** El análisis arrojó un total de 11.484 hallazgos (errores y advertencias) basados en la inspección sistemática del DOM (Document Object Model) renderizado de cada página.

## Estructura del Dataset (`analisis_accesibilidad.csv`)
El archivo CSV contiene las siguientes columnas principales *(nota: ajusta estos nombres a los que realmente tenga tu archivo)*:

* `Facultad / Unidad Académica`: Nombre de la facultad evaluada.
* `Sección`: Categoría de la página evaluada (ej. *Home, Enrolment, Scholarships*).
* `Principio_WCAG`: Principio de accesibilidad vulnerado (*Perceivable, Robust, Operable, Understandable*).
* `Criterio_WCAG`: Criterio de conformidad específico (ej. *1.4.3 Contrast, 4.1.1 Parsing, 1.1.1 Non-text Content*).
* `Tipo_Hallazgo`: Clasificación del problema detectado por Pa11y (Error, Warning).
* `Cantidad`: Número de ocurrencias del error en esa URL específica.

## Hallazgos Principales
El análisis detallado de este dataset demuestra una fuerte concentración de errores en los principios **Perceptible (60.55%)** y **Robusto (37.96%)**. El criterio con mayor índice de incumplimiento es el **1.4.3 (Contraste mínimo)**, representando el 38.81% del total de los problemas detectados.

## Uso y Licencia
Este dataset se publica con fines de investigación académica en el marco de la Ciencia Abierta. 
[GNU 3.0]

## Contacto
pamadeo@linti.unlp.edu.ar

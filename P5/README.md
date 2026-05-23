# DIU - Práctica 5: Evaluación · A/B Testing y Accesibilidad

**Proyecto:** SushiJAMA  
**Centro:** ETSIIT — Universidad de Granada  
**Curso:** 2025-2026  
**Equipo:** Manuel Jesús Izquierdo, Juan Antonio Jara

---

## Descripción

En esta práctica evaluamos la usabilidad de dos diseños web mediante un estudio A/B. Nuestra propuesta actúa como **Caso A (SushiJAMA)** y evaluamos como **Caso B** el proyecto **DorayakiYa** del equipo DIU1.Zipizape.

La metodología combina cuatro pilares: reclutamiento de usuarios, Eye Tracking con GazeMapping, cuestionario SUS y auditoría de accesibilidad. Los resultados se sintetizan en un Usability Report centrado en el Caso B.

🔗 **Web evaluada (Caso B):** [https://repair-umber-32369566.figma.site](https://repair-umber-32369566.figma.site)

---

## 1. Reclutamiento de Usuarios y Diseño del Experimento

### Tareas de prueba

Se definieron 3 tareas para guiar la sesión de cada usuario. Las tareas cubren los flujos principales de DorayakiYa y están diseñadas para aislar variables concretas:

| Tarea | Descripción | Variable que mide |
|---|---|---|
| **T1** | Encuentra el plato más caro del menú | Distinción entre "Carta" y "Pide Online", navegación por productos |
| **T2** | Reserva una mesa para 2 personas este sábado a las 21:00 | Localización de la reserva, comprensión del selector AM/PM |
| **T3** | Añade un Katsudon al carrito y ve al proceso de pago | Flujo de compra, localización del icono del carrito |

Las sesiones son **supervisadas** (el evaluador observa y anota sin intervenir) con una duración estimada de 5-10 minutos por usuario.

### Tabla de participantes

| ID | Edad | Género | Nivel Digital | Gafas/Lentillas | Exp. previa en tests | Caso evaluado |
|---|---|---|---|---|---|---|
| P01 | | | | | | B |
| P02 | | | | | | B |
| P03 | | | | | | B |
| P04 | | | | | | B |
| P05 | | | | | | B |

> 📋 Los datos demográficos se recogen a través del formulario Tally al finalizar cada sesión.  
> 🔗 **Formulario SUS + datos demográficos:** [https://tally.so/r/2EDJBj](https://tally.so/r/2EDJBj)

---

## 2. Eye Tracking

Se utilizó **GazeMapping** para analizar el comportamiento visual de los usuarios sobre las páginas principales de DorayakiYa. Se rasterizaron 2 páginas con FireShot y se definieron los siguientes POIs (Puntos de Interés):

**Página Inicio:**
- Botón "Pide aquí" (CTA principal)
- Logo (¿redirige al inicio?)
- Menú de navegación con dropdown "Ir a..."

**Página Reserva:**
- Formulario de datos (nombre, email, comensales)
- Botón "Confirmar Reserva"
- Selector de fecha y hora

| Heatmap Inicio | Heatmap Reserva |
|---|---|
| *(captura pendiente de sesiones)* | *(captura pendiente de sesiones)* |

### Conclusiones Eye Tracking

> *(Se completará tras las sesiones con usuarios)*

---

## 3. Cuestionario SUS y Análisis A/B

El cuestionario SUS se administró a cada usuario **inmediatamente después** de completar las 3 tareas, sin pausa, para evitar sesgos de memoria.

Los resultados se analizaron con **sus.mixality.de** para obtener el análisis multivariable.

### Puntuaciones SUS

| Usuario | Caso | Puntuación SUS |
|---|---|---|
| P01 | B | |
| P02 | B | |
| P03 | B | |
| P04 | B | |
| P05 | B | |
| **Media Caso B** | | |
| **Media Caso A (SushiJAMA)** | | |

> *(Se completará tras las sesiones con usuarios)*

### Comparativa A/B

> *(Gráfico y conclusiones pendientes de datos SUS)*

La media de referencia del SUS es **68 puntos**. Puntuaciones por encima indican usabilidad aceptable; por debajo, señalan problemas que requieren atención.

---

## 4. Auditoría de Accesibilidad

Se realizó una auditoría completa de las 5 páginas principales de DorayakiYa usando **Google Lighthouse** y **WAVE**.

### Resultados globales

| Página | WAVE AIM Score | Errores | Errores Contraste |
|---|---|---|---|
| Inicio | 9.3 / 10 ✅ | 2 | 0 |
| Carta | 4.0 / 10 🟠 | 2 | 24 |
| Pedir Online | 5.2 / 10 🟡 | 3 | 16 |
| Carrito | 9.1 / 10 ✅ | 2 | 0 |
| Reseñas | 8.1 / 10 ✅ | 4 | 0 |

**Lighthouse Accessibility Score (Inicio):** 82/100

Los principales hallazgos son errores de contraste en las tarjetas de la página Carta y Pedir Online, ausencia de semántica HTML estructural (headings, landmarks) y dos imágenes enlazadas sin texto alternativo en el header.

📄 [Ver Accessibility Report completo](./Accessibility_Report_Dorayakiya.md)

---

## 5. Usability Report

El informe de usabilidad completo centrado en el **Caso B (DorayakiYa)** incluye resumen ejecutivo, metodología, resultados SUS, análisis de Eye Tracking, auditoría de accesibilidad y tabla de recomendaciones priorizadas.

📄 [Ver Usability Report](./P4_UsabReport_Dorayakiya_doneby_DIU1_SushiJAMA.md)

> *(Se completará tras el análisis de datos)*

---

## Conclusiones

> *(Se completará al finalizar la práctica)*

La evaluación cruzada con DorayakiYa nos ha permitido aplicar de forma práctica las técnicas de UX Research aprendidas durante el curso. El proceso de diseñar las tareas, reclutar usuarios y analizar los resultados con herramientas estandarizadas como SUS nos ha dado una perspectiva objetiva sobre qué aspectos de un diseño impactan realmente en la experiencia del usuario final.

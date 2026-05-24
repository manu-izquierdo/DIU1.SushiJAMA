# Usability Report — DorayakiYa

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRF017nhV-TFmNER2OM8UbXtdN6xwAKBYrv0i6onNfKu6Yn0BV0RK6aiOroeXl73LSY-B0&usqp=CAU" alt="usability" style="height:150px" />

### Evaluación de usabilidad del proyecto DorayakiYa

**Fecha:** 24 de mayo de 2026  
**Proyecto evaluado (Caso B):** DorayakiYa — [https://repair-umber-32369566.figma.site](https://repair-umber-32369566.figma.site)  
**GitHub del proyecto:** [https://github.com/zipizapeteam/UX_CaseStudy](https://github.com/zipizapeteam/UX_CaseStudy)

### Realizado por

**Equipo DIU1_SushiJAMA** — Manuel Jesús Izquierdo y Juan Antonio Jara  
Somos estudiantes de Diseño de Interfaces de Usuario (ETSIIT, Universidad de Granada). Hemos realizado este informe como parte de la evaluación cruzada de la práctica 5, aplicando las técnicas de UX Research aprendidas durante el curso: cuestionario SUS, análisis de accesibilidad con Lighthouse y WAVE, y diseño de pruebas con usuarios.

---

## 1. Resumen Ejecutivo

**Objetivo:** Evaluar la usabilidad y accesibilidad de DorayakiYa, un restaurante japonés temático con camareros robot, desarrollado por el equipo DIU1.Zipizape. La evaluación se centra en los flujos principales: exploración del menú, reserva de mesa y pedido online.

**Metodología:** Se combinaron tres técnicas: pruebas con usuarios con tareas definidas, cuestionario SUS (System Usability Scale) administrado a 5 participantes, y auditoría de accesibilidad automática con Google Lighthouse y WAVE sobre las 5 páginas principales de la web.

**Principales hallazgos:**
1. La puntuación SUS media es de **67 puntos**, 1 punto por debajo del umbral de aceptabilidad de 68, con una varianza alta entre usuarios (rango 37.5 – 90).
2. La página **Carta** presenta **24 errores de contraste** (AIM Score 4/10), siendo la página más problemática en accesibilidad a pesar de ser la más consultada.
3. El botón **"Confirmar Reserva"** está posicionado encima del formulario, generando confusión en el flujo de reserva al romper la secuencia natural de lectura.

**Resultado global:** Con una media SUS de **67/100**, el diseño se sitúa en la franja **Marginal / Poor** según la escala estándar. El proyecto tiene una identidad visual cuidada y funciona correctamente en sus páginas secundarias, pero presenta fricciones en los dos flujos más críticos: reserva y carta.

---

## 2. Metodología y Reclutamiento

### Perfil de los participantes

| ID | Edad | Género | Nivel Digital | Gafas/Lentillas | Exp. previa en tests | Caso |
|---|---|---|---|---|---|---|
| P01 | 21 | Hombre | Alto | Sí | Sí | B |
| P02 | 21 | Mujer | Medio | Sí | No | B |
| P03 | 20 | Hombre | Alto | No | Sí | B |
| P04 | 21 | Hombre | Alto | No | Sí | B |
| P05 | 22 | N/D | Alto | Sí | No | B |

**Edad media:** 21 años. **Perfil predominante:** estudiante universitario con competencia digital alta. La muestra es homogénea en perfil técnico, lo que puede haber favorecido puntuaciones más altas en usuarios con facilidad para la tecnología y explica en parte la alta varianza.

### Escenario de la prueba

Las sesiones fueron **supervisadas** con una duración de 5-10 minutos. Se definieron 3 tareas concretas diseñadas para aislar variables independientes:

| Tarea | Descripción | Variable medida |
|---|---|---|
| T1 | Encuentra el plato más caro del menú | Distinción entre Carta y Pide Online, navegación por productos |
| T2 | Reserva una mesa para 2 personas este sábado a las 21:00 | Localización de la reserva, comprensión del selector AM/PM |
| T3 | Añade un Katsudon al carrito y ve al proceso de pago | Flujo de compra, localización del icono del carrito |

Cada usuario completó las 3 tareas de forma consecutiva sin pausa. Inmediatamente después se administró el cuestionario SUS seguido de las preguntas demográficas, todo a través del formulario Tally.

### Herramientas utilizadas

- **Tally.so** — recogida del cuestionario SUS y datos demográficos
- **sus.mixality.de** — análisis multivariable de resultados SUS
- **Google Lighthouse** — auditoría de accesibilidad automática
- **WAVE (WebAIM)** — análisis de accesibilidad por página

---

## 3. Resultados del Cuestionario SUS

### Puntuaciones individuales

| Usuario | Puntuación SUS | Etiqueta |
|---|---|---|
| P01 | 37.5 | Not Acceptable 🔴 |
| P02 | 70.0 | Good 🟢 |
| P03 | 62.5 | OK / Marginal 🟡 |
| P04 | 75.0 | Good 🟢 |
| P05 | 90.0 | Excellent 🟢 |
| **Media** | **67.0** | **Marginal** |

**Referencia:** La media global del SUS en estudios comparativos es **68 puntos**. DorayakiYa obtiene **67**, situándose 1 punto por debajo del umbral de aceptabilidad.

### Análisis de los gráficos

Los gráficos generados por sus.mixality.de muestran una **alta dispersión** en las puntuaciones, visible en el boxplot: el rango va de 37.5 a 90, con una mediana en torno a 70. Esta varianza indica que la experiencia de uso es muy desigual según el perfil del usuario.

El gráfico de desglose por preguntas revela los puntos más débiles:

- **Pregunta 5** ("Las funciones están bien integradas"): el 80% de los usuarios respondió en la franja negativa — es el ítem con peor valoración de todo el cuestionario y apunta a problemas de coherencia entre las páginas Carta y Pide Online, que muestran productos similares sin diferenciación clara.
- **Pregunta 1** ("Me gustaría usar esta web con frecuencia"): 40% en desacuerdo, lo que sugiere que la propuesta de valor no está siendo percibida con claridad suficiente.
- **Preguntas 3, 7 y 9** (facilidad de uso, aprendizaje y confianza): resultados positivos, confirmando que la web es **fácil de usar una vez que el usuario entiende la estructura**.

El gráfico de conclusividad indica que con 5 participantes el estudio tiene una fiabilidad aproximada del 35-40%, lo que es esperable para una muestra pequeña. Los resultados son orientativos y consistentes con las observaciones cualitativas de las sesiones.

---

## 4. Análisis de Eye Tracking

> *(Sección pendiente de completar con los heatmaps de GazeMapping)*

La prueba de Eye Tracking se diseñó sobre las páginas Inicio y Reserva, que concentran los elementos de navegación más críticos. Se definieron los siguientes POIs:

**Página Inicio:** botón "Pide aquí" (CTA principal), logo, menú dropdown "Ir a..."  
**Página Reserva:** formulario de datos, botón "Confirmar Reserva", selector de fecha y hora

| Heatmap Inicio | Heatmap Reserva |
|---|---|
| *(pendiente)* | *(pendiente)* |

---

## 5. Auditoría de Accesibilidad

### Puntuaciones automáticas

| Herramienta | Página | Resultado |
|---|---|---|
| Lighthouse | Inicio | **82 / 100** |
| WAVE AIM | Inicio | 9.3 / 10 ✅ |
| WAVE AIM | Carta | 4.0 / 10 🔴 |
| WAVE AIM | Pedir Online | 5.2 / 10 🟠 |
| WAVE AIM | Carrito | 9.1 / 10 ✅ |
| WAVE AIM | Reseñas | 8.1 / 10 ✅ |

### Principales barreras detectadas

**Perceptible — Contraste insuficiente en Carta y Pedir Online**
Las tarjetas azules de ambas páginas presentan 24 y 16 errores de contraste respectivamente. Afecta a todos los nombres de platos, precios y botones "Añadir al carrito". Criterio WCAG 1.4.3 (Nivel AA).

**Perceptible — Imágenes enlazadas sin texto alternativo**
Los dos logos del header no tienen `alt` descriptivo en ninguna página. Criterio WCAG 1.1.1 (Nivel A).

**Robusto — Sin estructura semántica HTML**
Todas las páginas carecen de `<main>`, `<nav>`, `<h1>`/`<h2>` y `<footer>`. La jerarquía visual existe pero no está trasladada al código. Criterio WCAG 1.3.1 (Nivel A).

**Comprensible — Selector de hora en AM/PM**
El formulario de reserva usa formato AM/PM en una interfaz en español, lo que genera confusión en la tarea más crítica. Criterio WCAG 3.2.4.

📄 [Ver Accessibility Report completo](./Accessibility_Report_Dorayakiya.md)

---

## 6. Conclusiones y Recomendaciones

DorayakiYa es un proyecto con una propuesta creativa sólida y una identidad visual bien definida. La web funciona correctamente en la mayoría de páginas y tres de las cinco obtienen puntuaciones de accesibilidad superiores a 8/10. Sin embargo, los resultados del SUS y el análisis de usabilidad identifican fricciones concretas que afectan a los flujos más importantes.

### Tabla de recomendaciones priorizadas

| **Prioridad** | **Hallazgo** | **Recomendación de mejora** |
|---|---|---|
| 🔴 **Alta** | Puntuación SUS 67 — P01 con 37.5 indica experiencia muy negativa. La pregunta 5 (integración de funciones) es el ítem peor valorado. | Diferenciar claramente "Carta" (solo consulta) de "Pide Online" (con carrito). Añadir etiquetas o descripciones que expliquen el propósito de cada sección. |
| 🔴 **Alta** | Botón "Confirmar Reserva" posicionado encima del formulario — rompe el flujo natural de lectura. | Mover el botón al final del formulario, después de todos los campos. Es el orden que el usuario espera: rellenar → confirmar. |
| 🔴 **Alta** | 24 errores de contraste en página Carta — AIM Score 4/10. | Cambiar el color del texto sobre tarjetas azules a `#0A3D5C`. Resuelve todos los errores de contraste de una vez. |
| 🟠 **Media** | Selector de hora AM/PM en formulario de reserva en español. | Cambiar a formato 24h para evitar confusión en reservas de tarde/noche. |
| 🟠 **Media** | Sin estructura de headings ni landmarks HTML en ninguna página. | Añadir `<h1>`, `<h2>`, `<main>`, `<nav>` y `<footer>` — mejora la accesibilidad y el SEO simultáneamente. |
| 🟡 **Baja** | Logos del header sin atributo `alt` descriptivo. | Añadir `alt="DorayakiYa - Ir al inicio"` — cambio de una línea, corrección global. |
| 🟡 **Baja** | Botón "Pagar" activo en el carrito vacío. | Deshabilitar el botón cuando el carrito tiene 0 productos para evitar acciones sin efecto. |

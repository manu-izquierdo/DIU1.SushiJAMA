# Usability Report — DorayakiYa

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRF017nhV-TFmNER2OM8UbXtdN6xwAKBYrv0i6onNfKu6Yn0BV0RK6aiOroeXl73LSY-B0&usqp=CAU" alt="usability" style="height:150px" />

### Evaluación de usabilidad del proyecto DorayakiYa

**Fecha:** 24-25 de mayo de 2026  
**Proyecto evaluado (Caso B):** DorayakiYa — [https://repair-umber-32369566.figma.site](https://repair-umber-32369566.figma.site)  
**GitHub del proyecto:** [https://github.com/zipizapeteam/UX_CaseStudy](https://github.com/zipizapeteam/UX_CaseStudy)

### Realizado por

**Equipo DIU1_SushiJAMA** — Manuel Jesús Izquierdo y Juan Antonio Jara  
Somos estudiantes de Diseño de Interfaces de Usuario (ETSIIT, Universidad de Granada). Hemos realizado este informe como parte de la evaluación cruzada de la práctica 5, aplicando las técnicas de UX Research aprendidas durante el curso: cuestionario SUS, Eye Tracking con GazeMapping, y auditoría de accesibilidad con Lighthouse y WAVE.

---

## 1. Resumen Ejecutivo

**Objetivo:** Evaluar la usabilidad y accesibilidad de DorayakiYa, un restaurante japonés temático con camareros robot desarrollado por el equipo DIU1.Zipizape. La evaluación se centra en los flujos principales: exploración del menú, reserva de mesa y pedido online.

**Metodología:** Se combinaron tres técnicas complementarias: pruebas con usuarios con tareas definidas y Eye Tracking simultáneo mediante GazeMapping, cuestionario SUS administrado a 5 participantes inmediatamente después de cada sesión, y auditoría de accesibilidad automática con Google Lighthouse y WAVE sobre las 5 páginas principales.

**Principales hallazgos:**
1. La puntuación SUS media es **75/100 — Good**, con una varianza notable entre usuarios (62.5 – 90), lo que indica una experiencia desigual.
2. El botón **"Confirmar Reserva"** está posicionado encima del formulario. Los heatmaps confirman que los usuarios lo ven antes de rellenar los campos, generando confusión en el flujo.
3. La página **Carta** presenta **24 errores de contraste** (AIM Score 4/10), siendo la página más visitada y a la vez la más problemática en accesibilidad.

**Resultado global:** Con una media SUS de **75/100**, el diseño se sitúa en la franja **Good** según la escala estándar. El proyecto tiene una identidad visual sólida y bien ejecutada, pero presenta fricciones concretas y corregibles en los flujos de reserva y carta.

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

**Edad media:** 21 años. Perfil predominante: estudiante con competencia digital alta. La muestra es homogénea en perfil técnico, lo que puede haber favorecido puntuaciones más altas en los usuarios con mayor facilidad tecnológica y explica en parte la alta varianza detectada.

### Escenario de la prueba

Las sesiones fueron **supervisadas** con una duración de 5-10 minutos por participante. Se definieron 3 tareas concretas diseñadas para aislar variables independientes:

| Tarea | Descripción | Variable medida |
|---|---|---|
| T1 | Encuentra el plato más caro del menú | Distinción entre Carta y Pide Online, navegación por productos |
| T2 | Reserva una mesa para 2 personas este sábado a las 21:00 | Localización de la reserva, comprensión del selector AM/PM |
| T3 | Añade un Katsudon al carrito y ve al proceso de pago | Flujo de compra, localización del icono del carrito |

Cada usuario completó las 3 tareas de forma consecutiva sin pausa. El Eye Tracking se registró de forma simultánea durante las tareas. Inmediatamente después se administró el cuestionario SUS seguido de las preguntas demográficas.

### Herramientas utilizadas

- **GazeMapping** — Eye Tracking sobre páginas estáticas
- **FireShot** — captura de páginas para GazeMapping
- **Tally.so** — recogida del cuestionario SUS y datos demográficos
- **sus.mixality.de** — análisis multivariable de resultados SUS
- **Google Lighthouse** — auditoría de accesibilidad automática
- **WAVE (WebAIM)** — análisis de accesibilidad por página

---

## 3. Resultados del Cuestionario SUS

### Puntuaciones individuales

| Usuario | Puntuación SUS | Etiqueta |
|---|---|---|
| P01 | 70.0 | Good 🟢 |
| P02 | 70.0 | Good 🟢 |
| P03 | 62.5 | OK / Marginal 🟡 |
| P04 | 75.0 | Good 🟢 |
| P05 | 90.0 | Excellent 🟢 |
| **Media** | **75.0** | **Good** |

La media de referencia del SUS es **68 puntos**. DorayakiYa obtiene **75**, situándose claramente por encima del umbral de aceptabilidad en la franja Good.

### Análisis de los resultados

Los gráficos de sus.mixality.de muestran una dispersión moderada: el rango va de 62.5 a 90 puntos. La mayoría de usuarios valoró positivamente la web, con 4 de 5 participantes en la franja Good o superior.

El desglose por preguntas revela los puntos más débiles:

- **Pregunta 5** ("Las funciones están bien integradas"): el 60% de los usuarios respondió en la franja neutral o negativa — es el ítem con mayor margen de mejora. Apunta al problema de coherencia entre Carta y Pide Online.
- **Pregunta 1** ("Me gustaría usar esta web con frecuencia"): 60% en la franja positiva, aunque hay margen de mejora en comunicar mejor la propuesta de valor desde la primera visita.
- **Preguntas 3, 7 y 9** (facilidad, aprendizaje y confianza): resultados positivos, confirmando que la web **es fácil de usar una vez que el usuario entiende la estructura**.

---

## 4. Análisis de Eye Tracking

El experimento de Eye Tracking se realizó con **GazeMapping** sobre las páginas Inicio y Reserva. Se registraron sesiones con 3 usuarios sobre cada página.

### Página Inicio

| Usuario 1 | Usuario 2 | Usuario 3 |
|---|---|---|
| ![Heatmap Inicio U1](img/heatmap_inicio_u1.jpg) | ![Heatmap Inicio U2](img/heatmap_inicio_u2.jpg) | ![Heatmap Inicio U3](img/heatmap_inicio_u3.jpg) |

**Hallazgos:**

- ✅ El botón **"Pide aquí"** recibe atención consistente en todos los usuarios — el CTA principal está bien posicionado y es visible.
- ✅ Las tarjetas de productos de la primera fila (especialmente Katsudon y Pack Dorayaki) concentran la mayor atención visual, lo que indica que el grid de productos funciona bien como elemento de enganche.
- ⚠️ El menú **"Ir a..."** recibe muy poca atención — los usuarios no recurren al dropdown para encontrar la reserva. Esto explica por qué la tarea T2 generó dificultades: los usuarios buscan la reserva haciendo scroll en lugar de usar el menú.
- ⚠️ El logo recibe atención mínima en todos los heatmaps, consistente con el error ACC-02 del informe de accesibilidad (logo sin `alt`).
- ⚠️ La sección **"Novedades"** capta atención visual pero no lleva a ninguna acción — es contenido que llama la atención sin CTA asociado.

**Zona de silencio:** el pie de página (redes sociales, Términos y Condiciones) es completamente ignorado en todas las sesiones.

---

### Página Reserva

| Usuario 1 | Usuario 2 | Usuario 3 |
|---|---|---|
| ![Heatmap Reserva U1](img/heatmap_reserva_u1.jpg) | ![Heatmap Reserva U2](img/heatmap_reserva_u2.jpg) | ![Heatmap Reserva U3](img/heatmap_reserva_u3.jpg) |

**Hallazgos:**

- 🔴 El botón **"Confirmar Reserva"** aparece en la parte superior de la página, **antes del formulario**. Los heatmaps muestran que los usuarios lo ven al llegar, pero luego tienen que rellenar los campos y recordar volver arriba para confirmar. Esto rompe el flujo natural y genera hesitación visible en los patrones de mirada.
- ⚠️ El selector de hora **AM/PM** recibe atención concentrada pero con patrones de duda: los usuarios lo miran varias veces antes de interactuar, confirmando la confusión detectada en el cuestionario SUS para la tarea T2 (reservar a las 21:00).
- ✅ El calendario recibe atención clara y directa — el componente de selección de fecha funciona bien intuitivamente.
- ✅ Los campos del formulario (Nombre, Email, Teléfono, Comensales) siguen un patrón de lectura descendente correcto.

**Hallazgo clave:** el problema más grave no es que los usuarios no vean los elementos, sino que el **orden visual** de la página de Reserva es inverso al orden de acción: el botón de confirmación aparece antes de que el usuario haya rellenado nada.

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
Las tarjetas azules presentan 24 y 16 errores de contraste respectivamente. Afecta a todos los nombres de platos, precios y botones "Añadir al carrito". Criterio WCAG 1.4.3 (Nivel AA).

**Perceptible — Imágenes enlazadas sin texto alternativo**
Los dos logos del header no tienen `alt` descriptivo en ninguna página. Criterio WCAG 1.1.1 (Nivel A).

**Robusto — Sin estructura semántica HTML**
Todas las páginas carecen de `<main>`, `<nav>`, `<h1>`/`<h2>` y `<footer>`. Criterio WCAG 1.3.1 (Nivel A).

**Comprensible — Selector de hora en AM/PM**
El formulario de reserva usa formato AM/PM en una interfaz en español. Confirmado como problema real por los heatmaps. Criterio WCAG 3.2.4.

📄 [Ver Accessibility Report completo](./Accessibility_Report_Dorayakiya.md)

---

## 6. Conclusiones y Recomendaciones

DorayakiYa es un proyecto con una identidad visual cuidada, una propuesta creativa original y una ejecución técnica que funciona correctamente en la mayoría de páginas. Tres de las cinco páginas obtienen puntuaciones de accesibilidad superiores a 8/10 y la web cumple los aspectos básicos de usabilidad.

Los resultados del SUS (75/100) y los heatmaps de Eye Tracking apuntan de forma coherente a los mismos problemas: la **confusión entre Carta y Pide Online** (pregunta 5 del SUS como ítem peor valorado) y el **flujo invertido de la página de Reserva** (confirmado visualmente por los mapas de calor). Ninguno de estos problemas requiere rediseñar la interfaz — son ajustes concretos y de bajo coste técnico.

### Tabla de recomendaciones priorizadas

| **Prioridad** | **Hallazgo** | **Recomendación de mejora** |
|---|---|---|
| 🔴 **Alta** | Botón "Confirmar Reserva" encima del formulario — confirmado por Eye Tracking | Mover el botón al final del formulario, después de todos los campos |
| 🔴 **Alta** | Pregunta 5 SUS: 80% negativo en integración de funciones | Diferenciar claramente Carta (consulta) de Pide Online (compra) con etiquetas de propósito |
| 🔴 **Alta** | 24 errores de contraste en página Carta — AIM Score 4/10 | Cambiar texto sobre tarjetas azules a `#0A3D5C` |
| 🟠 **Media** | Selector AM/PM confirmado como problema por heatmaps y SUS | Cambiar a formato 24h |
| 🟠 **Media** | Menú "Ir a..." ignorado por los usuarios en Eye Tracking | Añadir "Reserva" directamente al menú principal sin necesidad de dropdown |
| 🟡 **Baja** | Logos sin `alt` descriptivo en todas las páginas | `alt="DorayakiYa - Ir al inicio"` en ambos logos |
| 🟡 **Baja** | Sin estructura semántica HTML en toda la web | Añadir `<main>`, `<nav>`, `<footer>` y jerarquía de headings |
| 🟡 **Baja** | Botón "Pagar" activo con carrito vacío | Deshabilitar el botón cuando hay 0 productos |

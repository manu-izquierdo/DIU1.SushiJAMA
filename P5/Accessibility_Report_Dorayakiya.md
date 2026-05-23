# Accessibility Report — DorayakiYa (Caso B)

![WCAG](https://img.uxcel.com/cdn-cgi/image/format=auto/practices/wcag-principles-overview-1742315821212/a-1742315821212-2x.jpg)

---

## 1. Ficha Técnica del Informe

| Campo | Detalle |
|---|---|
| **Nombre del proyecto** | DorayakiYa — Caso B (DIU1.Zipizape) |
| **URL analizada** | https://repair-umber-32369566.figma.site/ |
| **Normativa de referencia** | WCAG 2.1 — Nivel AA / Norma UNE-EN 301549 |
| **Herramientas utilizadas** | Google Lighthouse 12 (modo Desktop, incógnito) · WAVE Web Accessibility Evaluation Tool |
| **Fecha de la auditoría** | 23 de mayo de 2026 |
| **Realizado por** | Equipo DIU1_SushiJAMA |

---

## 2. Puntuaciones Globales (Métricas Automáticas)

### Lighthouse (página de Inicio)

| Métrica | Resultado |
|---|---|
| **Accessibility Score** | **82 / 100** |

Una puntuación de 82/100 en Lighthouse indica que el proyecto tiene una base sólida. La mayoría de aspectos fundamentales están cubiertos correctamente: el atributo `lang` está presente, los botones tienen nombres accesibles, el viewport está bien configurado y las imágenes decorativas usan `alt` vacío correctamente. Los puntos de mejora que se detallan a continuación son perfectamente corregibles y no restan valor al trabajo realizado.

### WAVE — Resumen por página

| Página | AIM Score | Errores | Errores Contraste | Alertas |
|---|---|---|---|---|
| **Inicio** | 9.3 / 10 ✅ | 2 | 0 | 20 |
| **Carta** | 4.0 / 10 🟠 | 2 | 24 | 15 |
| **Pedir Online** | 5.2 / 10 🟡 | 3 | 16 | 15 |
| **Carrito** | 9.1 / 10 ✅ | 2 | 0 | 18 |
| **Reseñas** | 8.1 / 10 ✅ | 4 | 0 | 20 |

Tres de las cinco páginas analizadas obtienen un AIM Score por encima de 8/10, lo que refleja un buen nivel de accesibilidad general. Las páginas Carta y Pedir Online presentan errores de contraste vinculados al uso de las tarjetas azules, que es el principal punto de mejora del proyecto.

---

## 3. Análisis por Principios POUR

![POUR](https://cdn.sanity.io/images/r115idoc/production/e745ae232e5e6760c1392354021aed4eecc4627d-1920x1080.png)

---

### A. Perceptible

**Hallazgo ACC-01 — Contraste en tarjetas de Carta y Pedir Online**

Las páginas Carta y Pedir Online muestran errores de contraste en los textos sobre las tarjetas azules (nombres de platos, precios y botones "Añadir al carrito"). WAVE detectó 24 errores en Carta y 16 en Pedir Online. Cabe destacar que las páginas Inicio, Carrito y Reseñas no presentan ningún error de contraste, lo que indica que la paleta de colores funciona bien en la mayoría de contextos — el problema está localizado en un componente concreto: las tarjetas azules.

- **Criterio WCAG:** 1.4.3 — Contraste mínimo (Nivel AA). Ratio mínimo exigido: 4.5:1.
- **Impacto:** Usuarios con baja visión pueden tener dificultad para leer los precios y nombres en estas dos páginas.
- **Recomendación:** Oscurecer ligeramente el texto de las tarjetas a `#0A3D5C` o aclarar el fondo a `#B8E7FA`. Es un ajuste puntual de color que resolvería todos los errores de contraste del proyecto de una sola vez.

**Hallazgo ACC-02 — Imágenes enlazadas sin texto alternativo**

Los dos logos del header (logo principal y logo secundario) actúan como enlace al inicio pero no tienen atributo `alt` con descripción. Al ser parte del header compartido, este error aparece en todas las páginas.

- **Criterio WCAG:** 1.1.1 — Contenido no textual (Nivel A)
- **Impacto:** Un usuario con lector de pantalla escucha "enlace" sin descripción al llegar al logo.
- **Recomendación:** Añadir `alt="DorayakiYa - Ir al inicio"` a ambas imágenes. Es un cambio de una línea que resuelve el error en toda la web simultáneamente.

**Hallazgo ACC-03 — Etiquetas ausentes en formulario de Reseñas**

Los campos "Tu nombre" y el área de texto de la página Reseñas no tienen etiqueta `<label>` asociada. El resto de formularios de la web (Reserva, Registro) no presentan este problema.

- **Criterio WCAG:** 1.3.1 — Información y relaciones (Nivel A)
- **Impacto:** Un usuario con lector de pantalla no identifica automáticamente el propósito de esos campos.
- **Recomendación:** Añadir `<label for="nombre">Tu nombre</label>` vinculado al input. Corrección rápida y de bajo coste técnico.

---

### B. Operable

**Hallazgo ACC-04 — Estructura de encabezados no implementada**

Los títulos visuales de las páginas (secciones, nombres de bloques de contenido) están diseñados correctamente a nivel visual pero no están marcados con etiquetas `<h1>`-`<h2>` en el HTML. WAVE identificó entre 6 y 12 posibles headings por página. La jerarquía visual existe y es clara — solo falta trasladarla al código.

- **Criterio WCAG:** 2.4.6 — Encabezados y etiquetas (Nivel AA)
- **Impacto:** Un usuario de lector de pantalla no puede navegar por secciones mediante la tecla H.
- **Recomendación:** Marcar el título principal de cada página como `<h1>` y los títulos de sección como `<h2>`. Al tener ya la jerarquía visual definida, este cambio es directo.

**Hallazgo ACC-05 — Enlace vacío en página Pedir Online**

WAVE detectó un elemento `<a>` sin contenido ni descripción en la página Pedir Online.

- **Criterio WCAG:** 2.4.4 — Propósito del enlace (Nivel AA)
- **Impacto:** Un usuario que navega con teclado llegará a ese enlace sin saber qué hace.
- **Recomendación:** Eliminar el enlace vacío o añadir un `aria-label` descriptivo.

---

### C. Comprensible

**Hallazgo ACC-06 — Selector de hora en formato AM/PM**

El componente de selección de hora en la página Reserva usa formato AM/PM, mientras que el resto de la interfaz está en español y sigue convenciones europeas.

- **Criterio WCAG:** 3.2.4 — Identificación consistente (Nivel AA)
- **Impacto:** Puede generar confusión al reservar horarios de tarde/noche.
- **Recomendación:** Cambiar a formato 24h para mantener la coherencia con el idioma y contexto de la interfaz.

**Hallazgo ACC-07 — Textos subrayados que no son enlaces**

En todas las páginas aparecen 3 elementos de texto subrayados que no son enlaces, lo que puede confundir al usuario sobre si son clicables.

- **Criterio WCAG:** 3.2.4 — Identificación consistente
- **Recomendación:** Eliminar el subrayado de esos textos y reservar ese estilo solo para enlaces.

---

### D. Robusto

**Hallazgo ACC-08 — Ausencia de regiones semánticas**

Todas las páginas carecen de elementos semánticos `<main>`, `<nav>` y `<footer>`. La estructura visual está bien resuelta, pero el HTML usa `<div>` genéricos en lugar de landmarks semánticos.

- **Criterio WCAG:** 1.3.1 — Información y relaciones (Nivel A)
- **Impacto:** Los lectores de pantalla no pueden ofrecer navegación por regiones.
- **Recomendación:** Envolver el menú en `<nav>`, el contenido principal en `<main>` y el pie en `<footer>`. Al ser un cambio estructural global, resolvería esta alerta en todas las páginas a la vez.

---

## 4. Tabla de Hallazgos y Prioridades

| **ID** | **Prioridad** | **Páginas afectadas** | **Criterio WCAG** | **Error detectado** | **Recomendación técnica** |
|---|---|---|---|---|---|
| **ACC-01** | 🔴 Alta | Carta, Pedir Online | 1.4.3 Contraste | Texto sobre tarjetas azules sin contraste suficiente | Cambiar texto a `#0A3D5C` o fondo a `#B8E7FA` |
| **ACC-02** | 🔴 Alta | Todas | 1.1.1 Contenido no textual | 2 imágenes enlazadas (logos) sin `alt` descriptivo | `alt="DorayakiYa - Ir al inicio"` en ambos logos |
| **ACC-03** | 🟠 Media | Reseñas | 1.3.1 / 3.3.2 | 2 campos de formulario sin `<label>` | Añadir `<label>` asociado a cada input |
| **ACC-04** | 🟠 Media | Todas | 2.4.6 Encabezados | Títulos visuales no marcados como `<h1>`/`<h2>` | Implementar jerarquía de headings en HTML |
| **ACC-05** | 🟠 Media | Todas | 1.3.1 | Sin regiones semánticas (`<main>`, `<nav>`, `<footer>`) | Añadir landmarks HTML5 a la estructura |
| **ACC-06** | 🟡 Baja | Pedir Online | 2.4.4 | Enlace vacío sin texto ni `aria-label` | Eliminar o añadir `aria-label` descriptivo |
| **ACC-07** | 🟡 Baja | Reserva | 3.2.4 | Selector de hora en AM/PM en interfaz española | Cambiar a formato 24h |
| **ACC-08** | 🟡 Baja | Todas | 3.2.4 | 3 textos subrayados que no son enlaces | Eliminar subrayado de textos no enlazados |

---

## 5. Conclusiones y Declaración de Conformidad

**Valoración general**

DorayakiYa es un proyecto con una identidad visual cuidada y una propuesta creativa sólida. Desde el punto de vista de la accesibilidad, el proyecto demuestra buenas prácticas en varios aspectos importantes: los botones son accesibles, el viewport permite el zoom y las páginas principales (Inicio, Carrito y Reseñas) obtienen puntuaciones WAVE superiores a 8/10.

Los errores detectados son en su mayoría **de naturaleza técnica y fácilmente corregibles**, no de concepto. La mayoría derivan de dos decisiones puntuales: el uso de tarjetas azules sin ajuste de contraste y la ausencia de semántica HTML en la estructura. Ninguno de estos problemas requiere rediseñar la interfaz — son correcciones de código que pueden aplicarse de forma incremental.

**El sitio cumple parcialmente con el Nivel AA de WCAG 2.1.** Con las mejoras propuestas, especialmente el ajuste de contraste en las tarjetas y la adición de landmarks semánticos, el proyecto podría alcanzar fácilmente un nivel de conformidad completo.

**Tres acciones inmediatas de mayor impacto:**
1. Ajustar el color de texto en las tarjetas azules — resuelve ACC-01 y elimina 40 errores de contraste de una vez.
2. Añadir `alt` a los logos del header — una línea de código, corrección global en toda la web.
3. Implementar `<h1>`/`<h2>` y landmarks `<main>`/`<nav>`/`<footer>` — mejora estructural que resuelve ACC-04 y ACC-05 simultáneamente.

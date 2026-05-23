# Accessibility Report — DorayakiYa (Caso B)

![WCAG](https://img.uxcel.com/cdn-cgi/image/format=auto/practices/wcag-principles-overview-1742315821212/a-1742315821212-2x.jpg)

---

## 1. Ficha Técnica del Informe

| Campo | Detalle |
|---|---|
| **Nombre del proyecto** | DorayakiYa — Caso B (evaluado por DIU1_SushiJAMA) |
| **URL analizada** | https://repair-umber-32369566.figma.site/ |
| **Normativa de referencia** | WCAG 2.1 — Nivel AA / Norma UNE-EN 301549 |
| **Herramientas utilizadas** | Google Lighthouse 12 (modo Desktop, incógnito) · WAVE Web Accessibility Evaluation Tool |
| **Fecha de la auditoría** | 23 de mayo de 2026 |
| **Realizado por** | Equipo DIU1_SushiJAMA (Manuel Jesús Izquierdo, Juan Antonio Jara) |

---

## 2. Puntuaciones Globales (Métricas Automáticas)

| Herramienta | Métrica | Resultado |
|---|---|---|
| **Lighthouse** | Accessibility Score | **82 / 100** |
| **WAVE** | AIM Score | **9.3 / 10** |
| **WAVE** | Errores críticos | **2** (imágenes con enlace sin alt) |
| **WAVE** | Errores de contraste | **0** |
| **WAVE** | Alertas | **20** (estructura de headings, regiones, enlaces redundantes) |
| **WAVE** | Elementos ARIA hidden | **9** |

La puntuación de 82/100 en Lighthouse y 9.3/10 en WAVE indica un nivel de accesibilidad **parcialmente aceptable**. La web supera los aspectos más básicos pero presenta barreras reales para usuarios con lector de pantalla y estructura semántica deficiente que impide una navegación eficiente.

---

## 3. Análisis por Principios POUR

![POUR](https://cdn.sanity.io/images/r115idoc/production/e745ae232e5e6760c1392354021aed4eecc4627d-1920x1080.png)

---

### A. Perceptible

**Hallazgo ACC-01 — 2 imágenes enlazadas sin texto alternativo**

WAVE detectó 2 imágenes que actúan como enlace (linked images) sin atributo `alt`. Se trata de los dos logos del header: el logo principal y el logo secundario de la esquina derecha. Ambos son `<a>` con imagen interior sin descripción.

- **Criterio WCAG incumplido:** 1.1.1 — Contenido no textual (Nivel A)
- **Impacto:** Un usuario con lector de pantalla (NVDA, JAWS, VoiceOver) escucha "enlace" sin ninguna descripción. No sabe que es el logo ni que lleva al inicio.
- **Recomendación:** Añadir `alt="DorayakiYa - Ir al inicio"` a ambas imágenes enlazadas del header.

**Hallazgo ACC-02 — Contraste insuficiente en textos sobre tarjetas azules**

Lighthouse detectó múltiples elementos de texto que no alcanzan la ratio mínima de contraste. Los casos más evidentes son los nombres de platos y precios sobre las tarjetas azul turquesa (`#027FB1`).

- **Criterio WCAG incumplido:** 1.4.3 — Contraste mínimo (Nivel AA). Exige ratio ≥ 4.5:1 para texto normal.
- **Impacto:** Usuarios con baja visión o daltonismo no pueden leer correctamente los precios ni los nombres de los platos.
- **Recomendación:** Oscurecer el texto a `#0A3D5C` o cambiar el fondo de tarjeta a un tono más claro como `#B8E7FA`.

---

### B. Operable

**Hallazgo ACC-03 — Sin estructura de headings (No heading structure)**

WAVE alerta de que la página no tiene estructura de encabezados (`<h1>`, `<h2>`...). Los títulos visibles como "Prueba nuestros mejores platos", "Novedades" o "Sobre nosotros" están marcados como posibles headings (`h?`) pero no están implementados como tales en el HTML — son `<div>` o `<p>` con estilos de título.

- **Criterio WCAG incumplido:** 2.4.6 — Encabezados y etiquetas (Nivel AA)
- **Impacto:** Un usuario de lector de pantalla no puede navegar por secciones usando la tecla H (navegación por headings), que es la forma más habitual de moverse en webs largas.
- **Recomendación:** Marcar el título principal como `<h1>` y los títulos de sección como `<h2>`. Hay 12 posibles headings identificados por WAVE que deberían convertirse.

**Hallazgo ACC-04 — Enlace redundante (Redundant link)**

WAVE detectó 1 enlace redundante: el logo y el enlace de texto "Inicio" en el menú apuntan a la misma URL. Esto genera ruido innecesario para usuarios de lector de pantalla que escuchan dos veces el mismo destino.

- **Criterio WCAG relacionado:** 2.4.4 — Propósito del enlace (Nivel AA)
- **Recomendación:** Añadir `aria-hidden="true"` al enlace del logo para que el lector de pantalla lo omita, manteniendo solo el enlace de texto "Inicio" como navegable.

---

### C. Comprensible

**Hallazgo ACC-05 — Reloj de reserva en formato AM/PM en interfaz en español**

La página de Reserva muestra un selector de hora con formato AM/PM. En España el formato estándar es de 24 horas, lo que genera confusión funcional directa.

- **Criterio WCAG relacionado:** 3.2.4 — Identificación consistente (Nivel AA)
- **Impacto:** Un usuario puede reservar a las 8:00 AM creyendo que reserva a las 20:00. Error funcional que afecta a toda la funcionalidad de reserva.
- **Recomendación:** Cambiar el componente de hora a formato 24h o añadir una aclaración textual visible junto al selector.

**Hallazgo ACC-06 — 3 textos subrayados que no son enlaces (Underlined text)**

WAVE detectó 3 textos subrayados que no son enlaces. El subrayado es una convención universal para indicar enlace — usarlo en texto no enlazado confunde al usuario.

- **Criterio WCAG relacionado:** 3.2.4 — Identificación consistente
- **Recomendación:** Eliminar el subrayado de textos que no sean enlaces. Usar negrita o color para énfasis.

---

### D. Robusto

**Hallazgo ACC-07 — Sin regiones de página (No page regions)**

WAVE confirma lo detectado por Lighthouse: la página no tiene regiones semánticas (`<main>`, `<nav>`, `<header>`, `<footer>`). Toda la estructura está en `<div>` genéricos.

- **Criterio WCAG incumplido:** 1.3.1 — Información y relaciones (Nivel A)
- **Impacto:** Los lectores de pantalla no pueden ofrecer navegación por regiones. El usuario no puede "saltar al contenido" ni identificar dónde está la navegación.
- **Recomendación:** Envolver el menú en `<nav>`, el contenido principal en `<main>`, y el pie de página en `<footer>`.

**Hallazgo ACC-08 — 9 elementos con ARIA hidden**

WAVE detectó 9 elementos con `aria-hidden="true"`. Este atributo oculta contenido a los lectores de pantalla. Si se aplica a contenido funcional (botones, textos informativos), genera barreras invisibles.

- **Criterio WCAG relacionado:** 4.1.2 — Nombre, función, valor (Nivel A)
- **Recomendación:** Revisar cada uno de los 9 elementos con `aria-hidden` para verificar que solo se aplica a elementos puramente decorativos.

---

## 4. Tabla de Hallazgos y Prioridades

| **ID** | **Prioridad** | **Herramienta** | **Criterio WCAG** | **Error detectado** | **Recomendación técnica** |
|---|---|---|---|---|---|
| **ACC-01** | 🔴 Crítica | WAVE | 1.1.1 — Contenido no textual | 2 imágenes enlazadas sin `alt` (logos del header) | Añadir `alt="DorayakiYa - Ir al inicio"` a ambas imágenes |
| **ACC-02** | 🔴 Crítica | Lighthouse | 1.4.3 — Contraste mínimo | Texto de precios y nombres de platos sin contraste suficiente sobre tarjetas azules | Cambiar texto a `#0A3D5C` o aclarar fondo a `#B8E7FA` |
| **ACC-03** | 🟠 Alta | WAVE | 2.4.6 — Encabezados y etiquetas | Sin estructura de headings — 12 títulos visuales no marcados como `<h>` | Convertir títulos de sección a `<h1>` / `<h2>` |
| **ACC-04** | 🟠 Alta | Lighthouse + WAVE | 1.3.1 — Información y relaciones | Página sin regiones semánticas (`<main>`, `<nav>`, `<footer>`) | Añadir landmarks HTML5 a toda la estructura |
| **ACC-05** | 🟡 Media | Visual | 3.2.4 — Identificación consistente | Selector de hora en AM/PM en interfaz en español | Cambiar a formato 24h |
| **ACC-06** | 🟡 Media | WAVE | 2.4.4 — Propósito del enlace | 1 enlace redundante (logo + "Inicio" apuntan al mismo destino) | Añadir `aria-hidden="true"` al enlace del logo |
| **ACC-07** | 🟡 Media | WAVE | 3.2.4 — Identificación consistente | 3 textos subrayados que no son enlaces | Eliminar subrayado de textos no enlazados |
| **ACC-08** | 🟡 Media | WAVE | 4.1.2 — Nombre, función, valor | 9 elementos con `aria-hidden` — posible ocultación de contenido funcional | Auditar cada elemento y eliminar `aria-hidden` si oculta contenido relevante |

---

## 5. Conclusiones y Declaración de Conformidad

**¿Es el sitio accesible?**
El sitio **no cumple plenamente** con el Nivel AA de WCAG 2.1. Aunque supera aspectos básicos (atributo `lang` presente, botones con nombre, viewport correcto), presenta **2 errores críticos** que generan barreras directas: imágenes enlazadas sin texto alternativo y contraste insuficiente. Adicionalmente, la ausencia total de estructura semántica (sin headings, sin regiones) hace que la web sea prácticamente inutilizable para un usuario de lector de pantalla.

**Próximos pasos inmediatos (por prioridad):**
1. Añadir `alt` descriptivo a las 2 imágenes enlazadas del header — cambio de 5 minutos con impacto crítico.
2. Revisar y corregir el contraste de textos sobre las tarjetas azules usando el [Contrast Checker de WebAIM](https://webaim.org/resources/contrastchecker/).
3. Estructurar el HTML con `<h1>`/`<h2>` y añadir `<main>`, `<nav>` y `<footer>` — mejora que resuelve 4 hallazgos de una vez.

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
 
### WAVE — Resumen por página
 
| Página | AIM Score | Errores | Errores Contraste | Alertas |
|---|---|---|---|---|
| **Inicio** | 9.3 / 10 | 2 | 0 | 20 |
| **Carta** | **4.0 / 10** 🔴 | 2 | **24** | 15 |
| **Pedir Online** | 5.2 / 10 🟠 | 3 | 16 | 15 |
| **Carrito** | 9.1 / 10 | 2 | 0 | 18 |
| **Reseñas** | 8.1 / 10 | 4 | 0 | 20 |
 
La página **Carta** es la más problemática con un AIM Score de **4/10** y **24 errores de contraste**, lo que la hace prácticamente ilegible para usuarios con baja visión. La página **Pedir Online** también presenta 16 errores de contraste graves. El resto de páginas tienen un nivel aceptable en contraste pero comparten errores estructurales en todas ellas.

---

## 3. Análisis por Principios POUR
 
![POUR](https://cdn.sanity.io/images/r115idoc/production/e745ae232e5e6760c1392354021aed4eecc4627d-1920x1080.png)
 
---
 
### A. Perceptible
 
**Hallazgo ACC-01 — Contraste muy bajo en páginas Carta y Pedir Online (CRÍTICO)**
 
WAVE detectó **24 errores de contraste en la página Carta** y **16 en Pedir Online**. Afectan a todos los textos (nombres de platos, precios, descripciones y botones "Añadir al carrito") sobre las tarjetas de color azul turquesa. El ratio de contraste de estos elementos es muy inferior al mínimo de 4.5:1 exigido por WCAG.
 
- **Criterio WCAG incumplido:** 1.4.3 — Contraste mínimo (Nivel AA)
- **Impacto:** Las dos páginas más funcionales de la web — donde el usuario consulta el menú y hace pedidos — son prácticamente ilegibles para usuarios con baja visión, daltonismo o en condiciones de luz solar directa.
- **Recomendación:** Cambiar el color del texto sobre tarjetas azules a `#0A3D5C` (ratio superior a 7:1) o cambiar el fondo de las tarjetas a `#B8E7FA`. Verificar con el [Contrast Checker de WebAIM](https://webaim.org/resources/contrastchecker/).
**Hallazgo ACC-02 — Imágenes enlazadas sin texto alternativo (en todas las páginas)**
 
WAVE detectó 2 errores de tipo "Linked image missing alternative text" en todas las páginas analizadas. Se trata de los dos logos del header que actúan como enlace al inicio pero no tienen atributo `alt`.
 
- **Criterio WCAG incumplido:** 1.1.1 — Contenido no textual (Nivel A)
- **Impacto:** Un usuario con lector de pantalla escucha "enlace" sin descripción en cada página. Al ser el header común a toda la web, el error se repite en cada visita.
- **Recomendación:** Añadir `alt="DorayakiYa - Ir al inicio"` a ambas imágenes enlazadas del header.
**Hallazgo ACC-03 — 2 etiquetas de formulario ausentes en página Reseñas**
 
WAVE detectó 2 errores "Missing form label" en la página de Reseñas. Los campos "Tu nombre" y el área de texto para la reseña no tienen etiqueta `<label>` asociada.
 
- **Criterio WCAG incumplido:** 1.3.1 — Información y relaciones (Nivel A) y 3.3.2 — Etiquetas o instrucciones (Nivel A)
- **Impacto:** Un usuario con lector de pantalla no sabe qué debe escribir en cada campo del formulario.
- **Recomendación:** Añadir `<label for="nombre">Tu nombre</label>` y asociarlo al input correspondiente mediante el atributo `id`.
---
 
### B. Operable
 
**Hallazgo ACC-04 — Sin estructura de encabezados en todas las páginas**
 
Todas las páginas muestran la alerta "No heading structure". Los títulos visibles (secciones, nombres de productos) están implementados como `<div>` o `<p>` con estilos visuales, no como elementos `<h1>`-`<h6>`. WAVE identificó entre 6 y 12 posibles headings por página que no están marcados correctamente.
 
- **Criterio WCAG incumplido:** 2.4.6 — Encabezados y etiquetas (Nivel AA)
- **Impacto:** Un usuario de lector de pantalla no puede navegar por secciones usando la tecla H, que es la forma más habitual de moverse en webs largas con muchos productos.
- **Recomendación:** Usar `<h1>` para el título principal de cada página y `<h2>` para los títulos de sección. Especialmente crítico en la página Carta con 8 platos sin título semántico.
**Hallazgo ACC-05 — Enlace vacío en página Pedir Online**
 
WAVE detectó 1 "Empty link" en la página Pedir Online. Hay un elemento `<a>` sin texto ni imagen interior, lo que lo hace completamente inaccesible por teclado o lector de pantalla.
 
- **Criterio WCAG incumplido:** 2.4.4 — Propósito del enlace (Nivel AA)
- **Impacto:** Un usuario que navega con teclado llegará a ese enlace sin saber qué hace ni poder activarlo conscientemente.
- **Recomendación:** Eliminar el enlace vacío o añadirle contenido con `aria-label` descriptivo.
**Hallazgo ACC-06 — 2 enlaces redundantes en todas las páginas**
 
Todas las páginas tienen 2 enlaces redundantes: el logo y el ítem "Inicio" del menú apuntan a la misma URL. Esto genera duplicidad innecesaria para usuarios de lector de pantalla.
 
- **Criterio WCAG relacionado:** 2.4.4 — Propósito del enlace (Nivel AA)
- **Recomendación:** Añadir `aria-hidden="true"` al enlace del logo para que el lector lo omita.
---
 
### C. Comprensible
 
**Hallazgo ACC-07 — Reloj de reserva en formato AM/PM en interfaz en español**
 
La página de Reserva muestra un selector de hora con formato AM/PM. En España el formato estándar es de 24 horas.
 
- **Criterio WCAG relacionado:** 3.2.4 — Identificación consistente (Nivel AA)
- **Impacto:** Un usuario puede reservar a las 8:00 AM creyendo que reserva a las 20:00. Error funcional directo en la tarea más crítica de la web.
- **Recomendación:** Cambiar el componente de hora a formato 24h.
**Hallazgo ACC-08 — 3 textos subrayados que no son enlaces (en todas las páginas)**
 
Todas las páginas muestran 3 elementos de texto subrayados que no son enlaces. El subrayado es convención universal de enlace.
 
- **Criterio WCAG relacionado:** 3.2.4 — Identificación consistente
- **Recomendación:** Eliminar el subrayado de textos no enlazados. Usar negrita o color para énfasis.
---
 
### D. Robusto
 
**Hallazgo ACC-09 — Sin regiones de página en toda la web**
 
Todas las páginas muestran "No page regions". No hay `<main>`, `<nav>`, `<header>` ni `<footer>` semánticos.
 
- **Criterio WCAG incumplido:** 1.3.1 — Información y relaciones (Nivel A)
- **Impacto:** Los lectores de pantalla no pueden ofrecer navegación por regiones en ninguna página de la web.
- **Recomendación:** Añadir landmarks HTML5 a toda la estructura en todas las páginas.
**Hallazgo ACC-10 — Elementos ARIA hidden en todas las páginas**
 
Se detectaron elementos con `aria-hidden="true"` en todas las páginas (9 en Inicio, 11 en Pedir Online, 3 en Carrito, 3 en Reseñas). Si alguno oculta contenido funcional, genera barreras invisibles.
 
- **Criterio WCAG relacionado:** 4.1.2 — Nombre, función, valor (Nivel A)
- **Recomendación:** Auditar cada elemento y aplicar `aria-hidden` únicamente a contenido puramente decorativo.
---
 
## 4. Tabla de Hallazgos y Prioridades
 
| **ID** | **Prioridad** | **Páginas afectadas** | **Criterio WCAG** | **Error detectado** | **Recomendación técnica** |
|---|---|---|---|---|---|
| **ACC-01** | 🔴 Crítica | Carta, Pedir Online | 1.4.3 Contraste | 24 y 16 errores de contraste respectivamente sobre tarjetas azules | Cambiar texto a `#0A3D5C` o fondo a `#B8E7FA` |
| **ACC-02** | 🔴 Crítica | Todas | 1.1.1 Contenido no textual | 2 imágenes enlazadas sin `alt` (logos del header) | `alt="DorayakiYa - Ir al inicio"` en ambos logos |
| **ACC-03** | 🔴 Crítica | Reseñas | 1.3.1 / 3.3.2 | 2 campos de formulario sin etiqueta `<label>` | Añadir `<label>` asociado a cada input |
| **ACC-04** | 🟠 Alta | Todas | 2.4.6 Encabezados | Sin estructura de headings — títulos como `<div>` sin semántica | Convertir títulos de sección a `<h1>`/`<h2>` |
| **ACC-05** | 🟠 Alta | Todas | 1.3.1 | Sin regiones semánticas (`<main>`, `<nav>`, `<footer>`) | Añadir landmarks HTML5 a toda la estructura |
| **ACC-06** | 🟠 Alta | Pedir Online | 2.4.4 Propósito del enlace | 1 enlace vacío sin texto ni `aria-label` | Eliminar o añadir `aria-label` descriptivo |
| **ACC-07** | 🟡 Media | Reserva | 3.2.4 Identificación consistente | Selector de hora AM/PM en interfaz en español | Cambiar a formato 24h |
| **ACC-08** | 🟡 Media | Todas | 2.4.4 Propósito del enlace | 2 enlaces redundantes (logo + "Inicio" al mismo destino) | `aria-hidden="true"` en enlace del logo |
| **ACC-09** | 🟡 Media | Todas | 3.2.4 | 3 textos subrayados que no son enlaces | Eliminar subrayado de textos no enlazados |
| **ACC-10** | 🟡 Media | Todas | 4.1.2 | Múltiples elementos con `aria-hidden` — posible ocultación de contenido funcional | Auditar y aplicar solo a contenido decorativo |
 
---
 
## 5. Conclusiones y Declaración de Conformidad
 
**¿Es el sitio accesible?**
El sitio **no cumple** con el Nivel AA de WCAG 2.1. El análisis multi-página revela que los problemas no son puntuales sino **sistémicos**: los errores de estructura (sin headings, sin regiones, sin labels) se repiten en todas las páginas porque comparten la misma arquitectura HTML deficiente. La situación más grave es la página **Carta**, con un AIM Score de **4/10** y 24 errores de contraste, que es precisamente la página donde el usuario pasa más tiempo tomando decisiones de compra.
 
**Las páginas más críticas por orden de urgencia:**
1. 🔴 **Carta** — AIM 4/10, 24 errores de contraste. Ilegible para usuarios con baja visión.
2. 🟠 **Pedir Online** — AIM 5.2/10, 16 errores de contraste + enlace vacío.
3. 🟡 **Reseñas** — 2 campos de formulario sin etiqueta, formulario inutilizable con lector de pantalla.
**Próximos pasos inmediatos:**
1. Corregir el contraste de las tarjetas azules en Carta y Pedir Online — afecta al 40 elementos de la web de una sola vez.
2. Añadir `alt` a los logos del header — una línea de código, corrige ACC-02 en todas las páginas.
3. Añadir `<label>` a los campos del formulario de Reseñas y estructurar headings en todas las páginas.
 

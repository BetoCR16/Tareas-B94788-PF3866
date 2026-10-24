# Tarea #3: Reporte de Bugs de Accesibilidad - Nova Cinemas

## Introducción
Se presenta el reporte de los defectos de accesibilidad encontrados en el sitio de **Nova Cinemas** ([https://www.novacinemas.cr](https://www.novacinemas.cr)). Los defectos se detectaron con un análisis automático de **axe DevTools (axe Core 4.10.3)** en el sitio principal y el flujo de compra de boletos  y se evaluaron contra las pautas **WCAG 2.1 nivel AA**.

Cada reporte se encuentra en la carpeta [`issues/`](./issues/). Las capturas de evidencia están en [`assets/`](./assets/).

---

## Criterio de Prioridad

| Prioridad | Descripción |
| :-: | :--- |
| 🔴 **Crítica** | Rompe el flujo principal o compromete la seguridad. |
| 🟠 **Alta** | Afecta al usuario de forma notoria. |
| 🟡 **Media** | Molesta, pero tiene solución temporal. |
| ⚪ **Baja** | Estética o detalle menor. |

---

## Bugs Encontrados

| # | ID | Título | Página | Regla axe | Criterio WCAG | Prioridad | Enlace al Reporte |
| :-: | :-: | :--- | :--- | :--- | :-: | :-: | :-: |
| **01** | BUG-001 | El acordeón de horarios usa roles ARIA con hijos no permitidos | Cartelera | `aria-required-children` | 1.3.1 | 🟡 Media | [Ver Reporte](./issues/01-aria-roles-hijos-requeridos.md) |
| **02** | BUG-002 | Las etiquetas de clasificación de edad no cumplen el contraste mínimo (2.37:1) | Cartelera | `color-contrast` | 1.4.3 | 🟡 Media | [Ver Reporte](./issues/02-contraste-color-insuficiente.md) |
| **03** | BUG-003 | El enlace del logo no tiene texto accesible | Todas | `link-name` | 2.4.4, 4.1.2 | 🟠 Alta | [Ver Reporte](./issues/03-enlace-logo-sin-texto.md) |
| **04** | BUG-004 | El título "Lugar" no cumple el contraste mínimo (2.3:1) | Sitio principal | `color-contrast` | 1.4.3 | 🟡 Media | [Ver Reporte](./issues/04-contraste-titulo-lugar.md) |
| **05** | BUG-005 | El iframe de compra de boletos (`#iFrame1`) no tiene nombre accesible | Compra de boletos | `frame-title` | 4.1.2 | 🟠 Alta | [Ver Reporte](./issues/05-iframe-sin-nombre-accesible.md) |
| **06** | BUG-006 | Los enlaces de redes sociales (ícono de Facebook) no tienen texto accesible | Sitio principal | `link-name` | 2.4.4, 4.1.2 | 🟡 Media | [Ver Reporte](./issues/06-enlaces-redes-sociales-sin-texto.md) |
| **07** | BUG-007 | Las listas desplegables del formulario de compra no tienen nombre accesible | Compra de boletos | `select-name` | 4.1.2 | 🟠 Alta | [Ver Reporte](./issues/07-select-sin-nombre-accesible.md) |
| **08** | BUG-008 | Los campos de texto del formulario de compra no tienen etiqueta | Compra de boletos | `label` | 1.3.1, 3.3.2, 4.1.2 | 🟠 Alta | [Ver Reporte](./issues/08-campos-formulario-sin-etiqueta.md) |
| **09** | BUG-009 | La lista de definiciones del resumen de la película tiene una estructura inválida | Compra de boletos | `definition-list` | 1.3.1 | 🟡 Media | [Ver Reporte](./issues/09-estructura-dl-invalida.md) |
| **10** | BUG-010 | El enlace "Términos y Condiciones" no cumple el contraste mínimo (3.99:1) | Compra de boletos | `color-contrast` | 1.4.3 | 🟡 Media | [Ver Reporte](./issues/10-contraste-enlace-terminos.md) |

---

## Resumen de Bugs Reportados

- **Total de bugs reportados:** 10
- **Prioridad Crítica (🔴):** 0
- **Prioridad Alta (🟠):** 4
- **Prioridad Media (🟡):** 6
- **Prioridad Baja (⚪):** 0

### Por categoría

| Categoría | Bugs |
| :--- | :--- |
| Contraste de color | BUG-002, BUG-004, BUG-010 |
| Enlaces sin texto accesible | BUG-003, BUG-006 |
| Formularios sin etiqueta o nombre accesible | BUG-007, BUG-008 |
| Estructura y roles ARIA | BUG-001, BUG-009 |
| Marcos (iframe) sin nombre accesible | BUG-005 |

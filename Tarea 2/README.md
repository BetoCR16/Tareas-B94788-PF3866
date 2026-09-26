# Tarea #2: Documentación de Pruebas Rápidas (Smoke Tests) - Nova Cinemas

## Introducción
Se presenta la documentación y el reporte de ejecución de los **Smoke Tests** diseñados para la página de reserva de boletos de **Nova Cinemas**. 

---

## Política de Despliegue (*Deployment Policy*)
- **Criterio de Aprobación (*Pass Criteria*):** Se exige un **100% de éxito (*Pass Rate*)** en los Smoke Tests críticos de navegación, mapa de asientos y formulario de pago.
- **Procedimiento ante Fallos (*Rollback*):** Si se detecta un fallo de severidad alta o bloqueante (como errores en el enrutamiento o fallos en el proceso de checkout), el despliegue a producción debe congelarse inmediatamente y se procederá con un *Rollback* automático a la última versión estable.

---

## Funcionalidades Críticas Evaluadas

| # | Funcionalidad Crítica | Descripción Breve | Total Pruebas | Enlace al Documento |
| :-: | :--- | :--- | :-: | :-: |
| **01** | **Consulta de Cartelera** | Selección de sucursales, filtrado por fecha, carga de posters y redirección por tanda. | 4 | [Ver Pruebas](./01-consulta-cartelera.md) |
| **02** | **Mapa Interactivo de Asientos** | Renderizado de sala, reubicación de butacas, control de ocupados y temporizador. | 4 | [Ver Pruebas](./02-seleccion-asientos.md) |
| **03** | **Formulario y Checkout** | Validaciones de datos obligatorios, formato de e-mail, resumen de orden y pasarela. | 4 | [Ver Pruebas](./03-formulario-checkout.md) |

---

## Resumen de Ejecución de Pruebas

- **Total de pruebas ejecutadas:** 12
- **Pruebas Exitosas (✅):** 9
- **Pruebas Dudosas (⚠️):** 1
- **Pruebas con Defectos / Fallidas (❌):** 2

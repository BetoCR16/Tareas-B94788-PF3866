# Funcionalidad 3: Formulario de datos personales y checkout

[← Volver al Índice](./README.md)

---

# Caso de Prueba: Captura y validación de datos personales obligatorios

## ID

CT-CHK-01

## Objetivo

Verificar que el formulario de checkout exija completar todos los campos obligatorios (Nombre, Correo, Teléfono) antes de permitir procesar la transacción.

## Precondiciones

- Navegador web actualizado.
- Haber completado la selección de tanda y mapa de asientos.
- Estar posicionado en la pantalla de ingreso de datos para la compra.

## Datos de Entrada

- **Campos en blanco:** Intento de envío con el formulario totalmente vacío.
- **Datos válidos:** Nombre completo, correo electrónico válido (`usuario@ejemplo.com`), teléfono y datos de pago.
- **Dato inválido:** Nombre con números/símbolos (`Juan123 Vainas`).
- **Dato válido:** Nombre en formato de texto estándar (`Juan Vainas`).

## Pasos

1. Avanzar en la selección de película, tanda, boletos, asientos, confitería hasta llegar al formulario final de facturación.
2. Dejar los campos de información personal totalmente vacíos.
3. Ingresar datos en formatos inválidos como el nombre con números y verificar el comportamiento del sistema.
3. Intentar hacer clic en el botón de Siguiente.
4. Llenar los campos requeridos con formato válido y presionar nuevamente el botón Siguiente.

## Resultado Esperado

- Al intentar avanzar con campos vacíos, la interfaz bloquea el proceso e indica visualmente cuáles campos son requeridos.
- Al ingresar datos válidos, los mensajes de alerta desaparecen y el sistema permite continuar hacia el pago.

## Resultado Obtenido

- Mientras al formulario le falten datos o tenga datos inválidos, el botón de Siguiente se encuentra deshabilitado.
- Se debe introducir un dato y luego borrarlo para que parezca un indicativo en el campo requerido.

## Estado de la prueba

❌ Falló

## Observaciones

- Se cumple con exigir los datos necesarios antes de continuar, sin embargo dicha exigencia se muestra por medio de la deshabilitación del botón de Siguiente, el cual únicamente se habilita si se han completado los campos con asterisco y los datos de tarjeta con datos de formatos válidos.
- No se presenta ningún indicativo más explícito de datos faltantes o inválidos a excepción del correo.
- Respecto al campo de nombre y teléfono, no se validan sus formatos, por lo que es posible dar a Siguiente a pesar de contener datos absurdos y el sistema responde con un mensaje de *"Orden completada satisfactoriamente. Su orden fue satisfactoria, pero hubo un error mostrando los detalles de confirmación. Contacte al cine para poder retirar su orden."*

---

# Caso de Prueba: Validación de formato en correo electrónico

## ID

CT-CHK-02

## Objetivo

Validar que el formulario detecte estructuras incorrectas de datos en campos con patrones específicos (ej. correo sin `@` o dominios inválidos).

## Precondiciones

- Formulario de checkout cargado en pantalla.

## Datos de Entrada

- **Correo inválido:** `correo_invalido.com` (sin símbolo `@`).
- **Correo válido:** `cliente_prueba@gmail.com`.

## Pasos

1. Ingresar en el campo de correo electrónico un texto sin el formato estándar (ej. `correo_invalido.com`).
2. Intentar presionar el botón de Siguiente.
3. Corregir el valor ingresando el correo en el formato correcto.

## Resultado Esperado

- El sistema despliega un mensaje de advertencia específico (ej. "Ingrese un correo electrónico válido") y deshabilita la confirmación de la compra.

## Resultado Obtenido

- La aplicación identificó la estructura errónea del correo ingresado e impidió avanzar, deshabilitando el botón de Siguiente, hasta que se proporcionó una dirección válida.

## Estado de la prueba

✅ Pasó

## Observaciones

- Ninguna. El patrón para el correo electrónico responde correctamente.


---

# Caso de Prueba: Verificación del desglose final de orden de compra

## ID

CT-CHK-03

## Objetivo

Verificar que el resumen de la orden refleje con exactitud la película, sucursal, horario, asientos seleccionados e importe total a pagar.

## Precondiciones

- Flujo de compra iniciado con asientos específicos seleccionados previamente (ej. 2 entradas en Plaza Real Alajuela, tanda 07:00 PM).

## Datos de Entrada

- **Detalles seleccionados en pasos previos:** Película elegida, sala, 2 butacas y precio.

## Pasos

1. Revisar el panel de "SU ELECCIÓN" ubicado en la vista de DETALLES PERSONALES.
2. Comparar el título de la película, tanda, sala y butacas mostradas contra la selección realizada en los pasos previos.
3. Validar el desglose matemático: Precio base + Cargos por servicio = Total Final.

## Resultado Esperado

- El resumen de la orden concuerda en un 100% con la selección previa del usuario y presenta la suma correcta del costo total.

## Resultado Obtenido

- Los datos del resumen coincidieron totalmente con las butacas y función seleccionadas previamente, calculando el importe de manera correcta.

## Estado de la prueba

✅ Pasó

## Observaciones

- Ninguna. Los datos se mantienen integros durante el proceso de compra.

---

# Caso de Prueba: Captura directa de tarjeta y enmascaramiento de datos sensibles

## ID

CT-CHK-04

## Objetivo

Verificar que el formulario integrado de pago mediante tarjeta valide el formato numérico de la casilla, enmascare el código de seguridad (CVV) y aplique restricción contra letras.

## Precondiciones

- Formulario de checkout cargado en pantalla.
- Datos personales del comprador completados adecuadamente.

## Datos de Entrada

- **Texto en casilla de tarjeta:** Intento de escribir letras (`ABCD-EFGH`).
- **Valores numéricos de prueba:** Número de tarjeta de 16 dígitos, fecha de vencimiento (`MM/AA`) y código CVV (3 dígitos).

## Pasos

1. Ubicar la sección para el pago con tarjeta dentro del formulario.
2. Intentar ingresar caracteres alfabéticos (letras) en las casillas de Número de Tarjeta, Expiración y CVV.
3. Ingresar una secuencia numérica válida de prueba en los campos de la tarjeta.
4. Verificar el enmascaramiento automático de los dígitos del código CVV/CVC.

## Resultado Esperado

- Los campos de la tarjeta rechazan el ingreso de letras/texto no numérico.
- El campo del código de seguridad (CVV) oculta los dígitos ingresados mediante asterisco o puntos por motivos de seguridad PCI-DSS.

## Resultado Obtenido

- El campo de número de tarjeta permite el tipeo de caracteres alfabéticos, sin embargo el botón de Siguiente se deshabilita por lo que no es posible continuar con el proceso.
- Se enmascaró correctamente el código CVV en la pantalla.

## Estado de la prueba

✅ Pasó

## Observaciones

- El formulario implementa las casillas de pago en la misma pantalla, pero no presenta indicativos explícitos cuando hay algún dato inválido. Se limita a que el botón de Siguiente se mantenga deshabilitado hasta haber introducido datos en un formato válido.

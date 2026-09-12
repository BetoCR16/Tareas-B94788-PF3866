# Tarea # 1: Definición del sistema a probar

## 1. Información del sistema
- **Nombre del sistema:** Nova Cinemas
- **Dirección:** [https://www.novacinemas.cr](https://www.novacinemas.cr)
- **Logo:** ![Logo Nova Cinemas](https://www.novacinemas.cr/wp-content/themes/novacinema_theme/img/logo.svg)

## 2. Propósito del sistema
### ¿Qué problema resuelve?

Permite poder consultar la cartelera del cine, revisar los horarios de películas y poder comprar las entradas al cine de forma anticipada.

- **Desde la perspectiva del usuario**, permite evitar las filas presenciales en las taquillas físicas, lo que reduce los tiempos de espera. Adicionalmente elimina la incertidumbre los horarios de las tandas de películas y permite al usuario escoger el asiento por medio de un mapa interactivo, además siendo una forma más cómoda para asegurar espacios contiguos para familias y grupos.

- **Desde el punto de vista de negocio**, automatiza el proceso de compra de boletos e incluso de la preventa de la dulcería lo que reduce la demanda durante picos de trabajo. Permite un control dinámico de los espacios en las salas, además de ser un medio que está activo 24/7 lo que facilita las ventas principalmente durante estrenos masivos.

### ¿Cuál es su público objetivo?

Está dirigido principalmente para 3 tipos de públicos:

- **Público general y familias:** Son quienes buscan un entretenimiento para fin de semana o tiempo libre y quieren un medio rápido, claro y accesible para obtener entradas con asientos asignados con anticipación y así poder llegar de forma más directa a la proyección, sin tener que realizar largas filas ni tener la incertidumbre si encontrarán espacio para estar juntos. En esto también pueden entrar los jóvenes que están más acostumbrados a utilizar medios digitales como billeteras digitales o tarjetas para realizar pagos y que además tienen preferencia por tener tickets en forma de QR o similar.

- **Cinefilos:** Personas entusiastas del cine interesados en preventas de estrenos masivos, formatos especiales (IMAX, VIP, 3D) o eventos temáticos. Son usuarios frecuentes por lo que priorizan la rapidez, poder seleccionar asientos en ubicaciones específicas a su gusto.

- **Organizadores de Eventos:** Empresas o instituciones que requieren la compra en volumen de entradas para actividades corporativas o funciones privadas como graduaciones, presentaciones de premios, entre otros.

### ¿Cuál es el flujo de uso esperado más común?

El flujo principal corresponde a:

1. **Consulta de cartelera:**
    - El usuario ingresa a la página principal.
    - Busca la sucursal donde desea asistir (Novacinemas Ciudad del Este, Avenida Escazú, etc).
    - Selecciona la fecha que desea.
    - Explora la cartelera disponible, consulta detalles de la película (clasificación de edad), el formato de proyección (2D Dob, 3D, IMAX) y selecciona el horario de la tanda.

2. **Número de entradas:**
    - Se muestra un menú donde el usuario selecciona la cantidad de Adultos, Niños y Adultos Mayores que asistirán, junto con el precio por entrada.

3. **Selección de Asientos (Mapa Interactivo):**
    - El sistema despliega un mapa interactivo de la sala seleccionada.
    - El usuario observa la simbología de butacas (disponibles, seleccionadas, ocupadas o para personas con discapacidad).
    - Selecciona los asientos en la ubicación de su preferencia. En este punto se tiene un temporizador de unos 5 minutos.

4. **Confitería / Snacks:**
    - Se presenta el catálogo de productos de dulcería (refrescos, palomitas, combos, alimentos).
    - El usuario agrega los productos deseados u omite este paso para continuar con la compra de las entradas.

5. **Identificación y Datos del Cliente:**
    - Se presenta un resumen de la compra y el total. A continuación se presenta un formulario donde el usuario ingresa los datos personales (nombre, correo, teléfono).
    - Se ingresan los datos de la tarjeta de crédito/débito, se aceptan términos y condiciones, y se realiza el pago.

6. **Confirmación y Emisión de Boleto Digital:**
    - Al procesarse el pago con éxito, la plataforma genera una pantalla de confirmación con el resumen de la compra.
    - Se emite un comprobante digital por correo que sirve como acceso directo en el cine.

## Lista de Chequeo

### 1. Accesibilidad Inicial y Carga

- [x] El sitio carga correctamente (sin errores de carga o fallos visibles).
- [x] El contenido principal aparece rápidamente (menos de 5 segundos).
- [ ] No hay errores evidentes (mensajes técnicos, 404, pantallas en blanco).
  - Al momento de prueba, se muestra un banner en blanco en la parte superior del sitio.
- [x] El sitio es _responsivo_ (se adapta a pantallas móviles/tablets).

### 2. Navegación General

- [x] El menú principal es visible y funcional.
- [x] Los enlaces llevan a las páginas correctas.
- [x] El botón "Inicio" o logo lleva a la página principal.
- [x] Hay forma de volver atrás fácilmente o de reiniciar una acción.

### 3. Flujos Críticos

_(Estos dependerán del tipo de sistema, adaptar según el contexto y/o si aplican)_

- [ ] ~~Registro de usuario (campos obligatorios, validación, éxito).~~ (**No aplica, no hay perfil**)
- [ ] ~~Inicio de sesión / recuperación de contraseña.~~ (**No aplica, no hay perfil**)
- [ ] ~~Cierre de sesión correcto.~~ (**No aplica, no hay perfil**)
- [x] Creación o envío de datos (formularios, publicaciones, etc.).
- [ ] ~~Edición de datos existentes (perfil, configuraciones).~~ (**No aplica, no hay perfil**)
- [x] Proceso de pago / reserva / acción principal del sistema.

### 4. Formularios y Validaciones

- [x] Los campos requeridos están claramente marcados.
- [ ] El sistema valida entradas incorrectas (email inválido, números, etc.).
  - Solo valida que el correo sea formato texto@texto. Lo demás no lo valida.
- [x] Mensajes de error son comprensibles y útiles.
- [x] Se pueden corregir errores sin reiniciar todo el formulario.
- [x] Los mensajes de éxito aparecen correctamente.

### 5. Contenido y Usabilidad

- [x] Textos sin errores ortográficos o gramaticales.
- [x] Botones y enlaces tienen nombres claros y consistentes ("Guardar", "Cancelar", etc.).
- [x] Las acciones del usuario tienen retroalimentación (mensajes, animaciones tipo _loaders_).
- [x] No se requieren pasos innecesarios o confusos.
- [x] El sistema es intuitivo sin necesidad de instrucciones externas.

### 6. Compatibilidad Básica

- [x] Probar en al menos dos navegadores 
  - Probado en Brave (Chromium), Zen Browser (Firefox)
- [x] Probar en dispositivo móvil vs escritorio.
  - Realizado en dispositivos reales.
- [x] Probar en resolución más baja (ej. 1024x768) y más alta.
  - En resoluciones mayores a 1280x720 no presenta diferencias, pero se adapta a resoluciones pequeñas como en 640x480 utilizando el diseño de dispositivos móviles.

### 7. Manejo de Errores y Casos Límite

- [x] ¿Qué ocurre si el usuario deja todo un formulario vacío?
  - No permite continuar, ya que el botón de 'Siguiente' aparece deshabilitado. 
- [x] ¿Qué pasa si introduce datos absurdos (nombre de 1000 caracteres, símbolos raros)?
  - Una vez completado el formulario, el botón de 'Siguiente' se habilita y permite continuar, y aparece el mensaje "Orden completada satisfactoriamente. Su orden fue satisfactoria, pero hubo un error mostrando los detalles de confirmación. Contacte al cine para poder retirar su orden."
- [x] ¿Qué ocurre si se recarga la página durante una acción?
  - Regresa al inicio del proceso de selección de cantidad de entradas (Punto 2 del flujo).
- [x] ¿Cómo responde el sistema si se pierde la conexión a Internet?
  - La sección donde se seleccionan asientos, aparece el aviso de Sin Internet por defecto del navegador que se está utilizando (ej. en Brave/Chrome aparece el dinosaurio).

### 8. Seguridad básica visible (sin análisis técnico)

- [x] Las contraseñas no se ven mientras se escriben (excepto si tienen un recurso para poder verlas, e.g. el "ojito").
- [ ] ~~No se puede navegar hacia páginas privadas sin haber iniciado sesión.~~ **(No aplica, no hay perfil/inicio de sesión)**
- [ ] ~~El usuario no puede ver información de otros usuarios.~~ **(No aplica, no hay perfil/inicio de sesión)**
- [ ] ~~Después de cerrar sesión, no puedes volver con el botón "atrás".~~ **(No aplica, no hay perfil/inicio de sesión)**

### 9. Feedback y Soporte

- [x] Los mensajes de ayuda, tooltips o instrucciones están presentes (si aplica).
- [x] Hay términos y condiciones / políticas de privacidad visibles (si aplica).

### 10. Aspecto General y Estabilidad

- [x] Diseño consistente entre secciones.
- [x] Imágenes y elementos visuales se cargan correctamente.
- [x] El sitio no se desajusta al hacer zoom (Ctrl + o -).
- [ ] No hay "pantallas muertas" sin contenido o acción clara.
  - En la página de opiniones aparece solamente un texto plano (Texto: `[trustindex data-widget-id=6772a4f23f7733207506fd560a4]`)

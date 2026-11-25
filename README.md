# Reservas Puntada Terca

Página de reservas para Puntada Terca Taller, un taller de costura en Oaxaca, México. Cada clase tiene dos límites: los lugares y las máquinas del taller. Quien reserva elige si lleva su máquina o usa una del taller.

Archivo: [`index.html`](index.html). Es un solo archivo HTML: se abre directamente en el navegador, sin instalar nada.

## Pantallas

1. **Clases y reserva.** Seis tarjetas, una por clase, con nivel, día, horario, duración, precio, lo que se lleva cada persona, lugares libres y máquinas libres. Cada tarjeta tiene su formulario: nombre completo, correo y máquina («Llevo la mía» o «Uso una del taller»), con el total en vivo.
2. **Confirmación.** Código corto, clase, fecha, máquina elegida, total a pagar en el taller, botón para descargar el evento de calendario (.ics) y botón «Cancelar mi lugar» con confirmación.

## Lógica de cupos

- Cada clase tiene dos contadores: lugares y máquinas del taller.
- Toda reserva baja un lugar. Solo «Uso una del taller» baja además una máquina y suma MXN 60, una sola vez.
- Con 2 lugares o menos, la tarjeta muestra «Últimos lugares».
- Con 0 máquinas y lugares libres, la opción del taller se desactiva con el texto «Sin máquinas: hay que traer la propia» y la clase sigue abierta para quien lleva la suya.
- Con 0 lugares, la clase muestra «Clase llena» y oculta el formulario.
- No se acepta un correo repetido en la misma clase.
- Cancelar devuelve el lugar y, si correspondía, la máquina.
- Las clases no se reinician solas. El enlace «Restaurar datos sintéticos», al pie, vuelve todo al inicio después de confirmar.

Cada reserva guarda: clase, nombre, correo, máquina, total y código.

## Catálogo (valores de prueba en pesos mexicanos)

| Clase | Nivel | Día | Horario | Precio | Lugares | Máquinas |
|---|---|---|---|---|---|---|
| Máquina desde cero | Principiante | Sáb 5 dic | 10:00–12:30 | MXN 420 | 8 | 5 |
| Bolsa de manta con forro | Principiante | Sáb 5 dic | 16:00–19:00 | MXN 480 | 8 | 5 |
| Ajuste de pantalón | Básico | Mar 8 dic | 18:00–20:30 | MXN 450 | 6 | 4 |
| Falda con resorte | Básico | Sáb 12 dic | 10:00–13:30 | MXN 620 | 6 | 4 |
| Cojín con cierre invisible | Básico | Jue 17 dic | 18:00–20:30 | MXN 460 | 8 | 5 |
| Blusa con bordado a máquina | Intermedio | Sáb 19 dic | 10:00–14:00 | MXN 780 | 6 | 3 |

## Datos

Las reservas se guardan en el navegador de cada persona (localStorage). Siguen ahí al recargar, pero no se comparten entre dispositivos: la dueña del taller no las ve desde su teléfono. Si el navegador no deja guardar, la página muestra un aviso.

## Identidad visual

- Colores: azul añil `#21386E` (fondo), rosa mexicano `#D6246E` (cabecera), cempasúchil `#E5A13A` (cinta métrica y etiqueta de nivel), crudo `#F6EFE1` (tarjetas) y tinta `#2A2A2A`.
- Tipografía: DM Serif Display para títulos y Work Sans para textos.
- Detalles: tarjetas cosidas a mano, cinta métrica bajo la cabecera y contadores como tramos de cinta.

## Probado

En un celular de 360 px de ancho: nada se sale de la pantalla, los botones miden al menos 44 px y los textos al menos 14 px.

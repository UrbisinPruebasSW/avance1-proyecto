# Proyecto 1 - Primer avance (Pruebas de Software)

## Contexto del curso
Curso: Pruebas de Software (UTEC). Entrega: **Proyecto 1 - Primer avance: Requisitos del cliente detallados**.

Objetivo del avance: convertir los requisitos generales del caso de negocio en **requisitos del cliente claros, verificables y trazables** al comportamiento real del sistema, de forma que sirvan de base sólida para el Análisis y el Diseño de pruebas del Proyecto 1. Un requisito ambiguo no se puede convertir en un caso de prueba confiable: si no queda claro qué dato probar como válido, cuál como inválido, y qué resultado observar, el requisito no está listo.

## Caso asignado: Caso 2 - E-commerce (Advantage Online Shopping)
- **Categoría:** E-commerce / Retail (A)
- **Sistema real para pruebas:** Advantage Online Shopping (Parasoft) — https://www.advantageonlineshopping.com/
- **Integrantes:** Maykol Morales, Sebastián Urbina

### Empresa y problemática
Advantage es una tienda en línea que vende accesorios y productos de marca propia, con carrito de compras, tarjetas de regalo y cuentas de usuario. Está a semanas de su campaña de temporada alta; preocupa que errores en el carrito o en la aplicación de tarjetas de regalo generen pérdida de ventas o descuentos mal calculados, afectando el margen del negocio.

### Alcance funcional del sistema (debe cubrirse el 100%, no una selección parcial)
1. Registro y login de usuarios
2. Navegación y búsqueda de productos por categoría
3. Carrito de compras
4. Aplicación de tarjetas de regalo / promociones
5. Checkout con dirección de envío y método de pago
6. Lista de deseos (wishlist)
7. Historial de pedidos

### Requisitos funcionales clave (enunciado original, punto de partida — hay que detallarlos, no copiarlos tal cual)
1. Registro y login deben validar campos obligatorios y mostrar errores claros ante datos inválidos.
2. La búsqueda de productos debe devolver resultados relevantes al término buscado.
3. Agregar un producto al carrito debe actualizar el contador de items y el subtotal correctamente.
4. Quitar un producto del carrito debe recalcular el subtotal correctamente.
5. Aplicar una tarjeta de regalo o código promocional debe reducir el total en el monto correcto, sin permitir montos negativos.
6. El checkout debe exigir dirección de envío y método de pago antes de confirmar la compra.
7. Al confirmar una compra, el pedido debe aparecer correctamente en el historial de pedidos del usuario.
8. Agregar un producto a la lista de deseos no debe afectar el carrito ni generar un cargo.

### Requisitos no funcionales
- El carrito debe mantenerse consistente si el usuario navega entre páginas.
- Tiempo de carga de catálogo menor a 2 segundos.
- Cálculos monetarios sin errores de redondeo.

### Riesgos iniciales
- Descuentos mal calculados
- Pérdida del contenido del carrito al navegar
- Pedidos duplicados por doble clic en "Comprar"

## Qué hay que entregar en este avance
Documento (para presentar y exponer) con:
1. **Funcionalidades identificadas:** tabla resumen `# | Funcionalidad | Dónde se encuentra en el sistema real (pantalla/URL)`. Debe completarse ANTES de detallar los requisitos — es el mapa de la exposición. Debe cubrir las 7 funcionalidades del alcance funcional (arriba), cada una mapeada a su pantalla/URL real en advantageonlineshopping.com.
2. **Requisitos detallados por funcionalidad:** por cada fila de la tabla anterior, su tabla de Requisitos (RF) correspondiente.

## Formato elegido para todo el documento: **RF (Requisito funcional)**
Decisión del equipo (no HU). Usar esta tabla para cada requisito, en TODAS las funcionalidades, sin mezclar formatos:

| ID | Requisito verificable | Actor | Datos y reglas | Resultado esperado | Prioridad |
|----|----|----|----|----|----|
| RF-01 | ... | ... | ... | ... | Alta/Media/Baja |

Cada requisito debe indicar explícitamente:
- Qué debe hacer el sistema.
- Qué datos recibe.
- Qué valores acepta y rechaza (al menos un caso válido y uno inválido cuando aplique).
- Qué reglas debe cumplir.
- Qué resultado se espera (observable).
- Prioridad.

**No usar frases generales** como "debe funcionar correctamente" o "debe validar los datos". Ejemplo del estilo esperado (del PDF guía, caso de hotel): "El sistema debe rechazar una reserva cuando la fecha de salida sea igual o anterior a la fecha de entrada y debe mostrar un mensaje de validación."

## Estructura sugerida para la exposición
Organizar por funcionalidad, mismo orden que la tabla de funcionalidades:
1. Sistema real elegido (link) e integrantes del grupo.
2. Tabla de funcionalidades identificadas, completa.
3. Un bloque por funcionalidad: nombre, dónde se ubica en el sistema real (mostrar en vivo si es posible) y su tabla RF completa.

## Criterios de entrega (checklist)
- [x] Tabla de funcionalidades identificadas completa (7 funcionalidades del alcance) — ver `Avance1_Requisitos_Cliente.md`.
- [x] Cada funcionalidad tiene su propia tabla RF completa (RF-01 a RF-19).
- [x] Cada requisito indica: acción esperada del sistema, actor, datos/reglas (con caso válido e inválido), resultado observable, prioridad.
- [x] Cobertura del 100% de las funcionalidades del "Alcance funcional del sistema" — incluye 2 funcionalidades documentadas como "no implementadas en el sistema real" (tarjetas de regalo y wishlist), confirmado a nivel de UI y de código fuente (`main.min.js`).
- [x] Formato consistente en todo el documento (solo RF, sin mezclar con HU).

## Entregables de este avance
- `Avance1_Requisitos_Cliente.md` (+ carpeta `img/`) — documento completo con capturas reales embebidas: tabla de funcionalidades + 7 bloques de requisitos RF (19 RFs en total) + 2 hallazgos de gap funcional + resumen de riesgos observados.
- **Slides para la exposición:** https://claude.ai/artifact/USgQLNWuYJsgrCm4FL5UCc — 18 diapositivas (portada, preámbulo del caso de negocio, requisitos funcionales clave y no funcionales/riesgos del enunciado original, objetivo, mapa de funcionalidades, 5 bloques de funcionalidad con evidencia+tabla RF, hallazgos wishlist/gift card, riesgos, cierre). Incluye aclaración sobre las rutas hash (`.../#/...`) de la SPA para que se entiendan en la tabla de funcionalidades y en las slides de evidencia.

Ambos basados en exploración en vivo del sitio real (registro, login válido/inválido, navegación por categoría, búsqueda con/sin resultados, agregar/quitar del carrito con verificación de subtotal, checkout con SafePay/MasterCard, historial de pedidos) y en revisión del bundle JS (`main.min.js`) para confirmar la ausencia de wishlist y tarjetas de regalo.

### Pendiente
- Revisar las slides y ajustar contenido/diseño si el equipo lo desea (redeploy a la misma URL).
- Decidir si se comparte el link de las slides con el profesor o se exporta a PDF/PPTX desde la propia página del artifact.

## Archivos de este directorio
- `caso2_proyecto.md`: enunciado del caso de negocio (Caso 2 - E-commerce).
- `Presentacion_avance_proyecto1.pdf`: guía oficial de este avance (objetivo, entrega, formato RF/HU, ejemplo detallado, criterios de entrega).
- `Plantilla_plan_pruebas.pdf`: plantilla del plan de pruebas mencionada por el profesor — **aún no está en este directorio**, pedir/descargar cuando esté disponible (es para una etapa posterior del Proyecto 1, no bloquea este avance).

## Próximos pasos de trabajo
1. Navegar advantageonlineshopping.com y mapear cada una de las 7 funcionalidades a su pantalla/URL real.
2. Redactar la tabla de funcionalidades identificadas.
3. Redactar la tabla RF completa por cada funcionalidad (mínimo cubriendo casos válidos e inválidos clave, alineado con los requisitos funcionales clave y riesgos iniciales del caso).
4. Armar el documento final siguiendo la estructura de exposición sugerida.

# Caso 2 - E-commerce (Advantage Online Shopping)

**E-COMMERCE / RETAIL (A)**

**Sistema real para pruebas:** Advantage Online Shopping (Parasoft) — https://www.advantageonlineshopping.com/

**Integrantes:**
- Maykol Morales
- Sebastián Urbina

## Empresa y problemática

Advantage es una tienda en línea que vende accesorios y productos de marca propia, con carrito de compras, tarjetas de regalo y cuentas de usuario. La empresa está a semanas de su campaña de temporada alta y le preocupa que errores en el carrito de compras o en la aplicación de tarjetas de regalo generen pérdida de ventas o descuentos mal calculados, afectando directamente el margen del negocio.

## Alcance funcional del sistema

- Registro y login de usuarios
- Navegación y búsqueda de productos por categoría
- Carrito de compras
- Aplicación de tarjetas de regalo / promociones
- Checkout con dirección de envío y método de pago
- Lista de deseos (wishlist)
- Historial de pedidos

## Requisitos funcionales clave

1. El registro y login deben validar los campos obligatorios y mostrar errores claros ante datos inválidos.
2. La búsqueda de productos debe devolver resultados relevantes al término buscado.
3. Agregar un producto al carrito debe actualizar el contador de items y el subtotal correctamente.
4. Quitar un producto del carrito debe recalcular el subtotal correctamente.
5. Aplicar una tarjeta de regalo o código promocional debe reducir el total en el monto correcto, sin permitir montos negativos.
6. El checkout debe exigir dirección de envío y método de pago antes de confirmar la compra.
7. Al confirmar una compra, el pedido debe aparecer correctamente en el historial de pedidos del usuario.
8. Agregar un producto a la lista de deseos no debe afectar el carrito de compras ni generar un cargo.

## Requisitos no funcionales

- El carrito debe mantenerse consistente si el usuario navega entre páginas.
- Tiempo de carga de catálogo menor a 2 segundos.
- Cálculos monetarios sin errores de redondeo.

## Riesgos iniciales

- Descuentos mal calculados
- Pérdida del contenido del carrito al navegar
- Pedidos duplicados por doble clic en "Comprar"

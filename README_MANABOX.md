# ManaBox · Coste real

Web estática para redistribuir el campo `Purchase price` de un CSV exportado de ManaBox según el coste real total de una compra.

## Qué hace

- Mantiene las columnas y datos originales del CSV: carta, edición, número, foil/no foil, estado, idioma, IDs, fecha, cantidad, etc.
- Modifica únicamente `Purchase price` y, si falta la moneda en una fila, rellena `Purchase price currency` con `EUR`.
- Tiene en cuenta `Quantity`: varias copias cuentan como varias cartas físicas.
- Reparte el coste de forma proporcional al `Purchase price` original.
- Un precio vacío o inferior a 0,02 € se usa como 0,02 € de referencia.
- Ninguna carta termina con un `Purchase price` inferior a 0,02 €.
- Ajusta redondeos para que el total final coincida exactamente con el coste introducido, siempre que matemáticamente sea posible con las cantidades del CSV.
- Todo se procesa en el navegador; no se envían archivos a ningún servidor.

## Uso local

Abre `index.html` con Chrome, Edge, Firefox o Safari.

## Publicarlo gratis en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `manabox-coste-real`.
2. Sube `index.html` a la raíz del repositorio.
3. En el repositorio entra en **Settings > Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**.
5. Elige la rama `main` y la carpeta `/ (root)`.
6. Guarda. GitHub mostrará la dirección pública de la web cuando quede publicada.

No necesita servidor, base de datos, API ni claves.

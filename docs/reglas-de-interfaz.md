# Reglas transversales de interfaz

## Mobile first

- Diseñar primero para pantallas angostas y ampliar progresivamente con media queries.
- Toda pantalla debe seguir siendo utilizable desde móvil: contenido legible, acciones alcanzables, controles táctiles y sin desplazamiento horizontal accidental.
- Convertir tablas anchas y paneles densos en presentaciones adaptables, con prioridad clara de información.
- Validar estados de carga, error, vacío y formularios en viewport angosto, además de escritorio.

## Modales y diálogos

- El contenido del diálogo debe permanecer dentro del viewport y permitir desplazamiento interno si excede el alto disponible.
- Tocar o hacer clic en el fondo no debe cerrar, desplazar ni romper el diálogo. El cierre por fondo queda desactivado por defecto; solo habilitarlo cuando el flujo lo requiera explícitamente.
- Proveer control de cierre visible y permitir Escape cuando corresponda.
- Al abrir, mover el foco al diálogo; al cerrar, devolverlo al elemento que lo abrió. En móvil, respetar áreas seguras y evitar que el teclado tape la acción principal.

## Gráficos y períodos

- Los gráficos con datos temporales deben ofrecer períodos seleccionables cuando los datos y el objetivo lo permitan (por ejemplo: semana, mes, trimestre, año o rango personalizado).
- Indicar período, zona temporal, unidades y filtros activos; actualizar título, ejes, leyenda y resumen al cambiarlo.
- No fijar una única ventana temporal en el código si el usuario necesita explorar la tendencia. Elegir un período inicial útil y exponer una forma de cambiarlo.
- Si la fuente no admite un período, mostrarlo como limitación explícita; no simular cambios de rango.
- Incluir una vista alternativa o resumen de datos para accesibilidad y pantallas pequeñas.

## Informes y exportación

- Los informes que representen datos exportables deben ofrecer Excel cuando sea técnicamente posible y útil para ese informe.
- La acción debe llamarse claramente **Exportar a Excel** y usar el icono `assets/icons/export-excel.svg` o el icono `FileSpreadsheet` de Lucide con el verde de Excel `#217346`.
- Usar formato XLSX real, preservar encabezados, tipos de dato, filtros/período seleccionado y nombres de columnas legibles. No cambiar silenciosamente fechas o decimales.
- Ofrecer PDF solo cuando el informe tenga una salida imprimible o de lectura; evitar iconos emoji o caracteres que dependan de la fuente.
- En móvil, mantener la acción de exportación accesible sin hacer que el resto de la pantalla se desborde.

## Iconografía

- Usar Lucide Icons como set general y sus adaptadores oficiales para el framework cuando estén disponibles.
- No usar emojis como iconos de interfaz: su forma y color cambian entre sistemas operativos y fuentes.
- Mantener tamaño, trazo y alineación consistentes; usar `currentColor` o tokens semánticos.
- Los iconos decorativos se ocultan a lectores de pantalla; los iconos que funcionan como único contenido de un control requieren nombre accesible.
- Lucide no incluye logos de marcas; para marcas de archivo (Excel/PDF), utilizar el pictograma funcional con color asociado y etiqueta textual, o un asset de marca autorizado cuando el uso sea correcto.

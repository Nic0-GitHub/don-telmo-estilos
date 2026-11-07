# Uso del sistema visual

## Adopción

1. Importar `templates/css/tokens.css` en la capa global de estilos.
2. Importar `templates/css/controls.css` después de los tokens para aplicar el patrón compartido a controles nativos.
3. Aplicar primero tokens semánticos; agregar tokens específicos solo si existe un patrón compartido.
4. Seleccionar tema con `data-theme="light"` o `data-theme="dark"` en la raíz, o dejar que el sistema operativo indique el tema.
5. Los componentes consumen `var(--dt-...)`; no duplicar valores de marca en estilos locales.
6. Extender con alias del framework cuando haga falta, sin cambiar la fuente semántica.

## Cambios

Un token nuevo debe explicar intención y uso. Un patrón nuevo debe incluir estados, interacción, responsive y accesibilidad. Si dos sistemas discrepan, registrar el valor observado y la propuesta; no borrar diferencias sin revisión visual.

## Componentes

Usar primario para la acción principal de una vista; acciones secundarias deben tener menor peso. Cards agrupan contenido relacionado y deben mantener jerarquía, padding y superficie. Los gráficos requieren título, unidades, periodo, leyenda y alternativa textual/resumen cuando la visualización no sea suficiente.

## Reglas de interfaz

Aplicar también las reglas de eglas-de-interfaz.md: mobile first, modales estables, selección de período en gráficos cuando sea posible, exportación XLSX e iconos Lucide sin emojis.


# Don Telmo UI

Usar este skill al crear o revisar interfaces, componentes, estilos o decisiones de presentación en cualquier sistema Don Telmo.

## Antes de cambiar

1. Leer `docs/identidad-visual.md`, `docs/arquitectura-ui.md`, `docs/uso-del-sistema.md` y `docs/reglas-de-interfaz.md`.
2. Revisar las instrucciones locales y el estado del sistema objetivo; conservar cambios existentes.
3. Distinguir lo observado en aplicaciones actuales de las propuestas comunes todavía no aprobadas.

## Reglas visuales y de interacción

- Diseñar mobile first y comprobar que cada flujo sea utilizable en pantallas angostas.
- Consumir tokens semánticos en lugar de repetir colores, radios, sombras o espacios.
- Cubrir temas claro y oscuro; mantener contraste y no comunicar estados solo con color.
- Mantener modales dentro del viewport y no cerrarlos al tocar fuera salvo requerimiento explícito. Proveer cierre visible y Escape cuando corresponda.
- Para gráficos temporales, ofrecer selección de período siempre que los datos lo permitan e indicar filtros, unidades y rango activo.
- Los informes exportables deben poder ofrecer XLSX cuando sea posible y útil. El botón debe decir “Exportar a Excel” y usar `assets/icons/export-excel.svg` o Lucide `FileSpreadsheet` en verde Excel; conservar datos, encabezados y rango seleccionado.
- Usar Lucide Icons para iconografía funcional, sin emojis como iconos. Mantener nombres accesibles para controles icon-only.

## Arquitectura

- Mantener reglas de negocio y acceso a datos fuera de componentes presentacionales.
- La página o contenedor coordina datos, servicios, navegación y estado de pantalla.
- Los hijos reciben entradas tipadas y emiten intenciones explícitas. Adaptar el contrato a Angular `input()`/`output()`, React props/callbacks, Vue props/emits u otros equivalentes idiomáticos.
- Extraer componentes por responsabilidad, contrato claro o reutilización real; no imponer una estructura idéntica de carpetas entre frameworks.

## Accesibilidad

Foco visible, teclado, reducción de movimiento, etiquetas, contraste y estados de carga/error/vacío. Los gráficos deben tener título, período, unidades, leyenda y resumen o alternativa textual.

## Entrega

Informar tokens y patrones usados, excepciones por legado y validaciones realizadas. No modificar sistemas consumidores cuando el alcance solo sea este repositorio.

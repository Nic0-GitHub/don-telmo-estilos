# Identidad visual observada

## Fuente y alcance

Relevamiento local inicial del CRM Angular y BotApp Angular. No se modificaron esos repositorios. CRM tiene cambios locales previos; sus reglas se leyeron como estado presente, no como aprobación de cada decisión para todos los sistemas.

## Marca

| Token | Valor observado | Origen |
|---|---:|---|
| Naranja de marca BotApp | `#cf4624` | `telmo-bot-front-app/src/styles.css` |
| Naranja primario CRM | `#e4512f` | `don-telmo-crm-front/src/styles/tokens.css` |
| Hover primario CRM | `#bb3427` | CRM |
| Rojo profundo BotApp | `#8d2114` | BotApp |
| Grafito BotApp | `#111111` | BotApp |
| Tipografía CRM | Inter, Segoe UI, sans-serif | CRM |
| Tipografía BotApp | Rubik, sans-serif | BotApp |

**Propuesta de convergencia:** usar naranja cálido como color de acción y conservar valores de marca como escala, sin declarar todavía un único hex oficial. CRM y BotApp hoy usan naranjas distintos; resolverlo requiere validación visual de marca. Los componentes deben consumir tokens semánticos, no fijar hex por pantalla.

## Temas observados

CRM ofrece claro y oscuro mediante `html.crm-dark`. En claro: fondo `#fbf8f5`, superficie `#ffffff`, superficie apagada `#f5efea`, borde `#ded5cc`, texto `#49423c`; en oscuro: fondo `#202225`, superficie `#2a2d31`, superficie apagada `#363a3f`, borde `#4a4f55`, texto `#eef0f2`. BotApp define `data-theme="dark"` y también respeta `prefers-color-scheme`; usa fondos oscuros `#111111`/`#1b1b1b`.

**Propuesta:** exponer tema claro/oscuro con tokens semánticos `--dt-color-bg`, `--dt-color-surface`, `--dt-color-text`, `--dt-color-border`, `--dt-color-primary`; admitir selector del usuario y preferencia del sistema, sin acoplar componentes a la estrategia del framework.

## Formas y superficies observadas

- CRM: tarjeta `1rem`, controles `0.7rem`, píldora `999px`; sombra de tarjeta muy tenue.
- BotApp: sombras en tres niveles; superficies de diálogo/burbujas usan radios aproximados de `1rem` a `1.2rem`.
- CRM: tarjetas con borde, superficie y sombra; hover eleva la tarjeta interactiva `2px`.
- CRM: botón primario naranja; al hover/focus pasa a negro con texto blanco. Documentar esta interacción como patrón observado y validar si será estándar compartido.

## Variantes y tamaño de logotipos

- Elegir la variante de marca aprobada para el fondo y el tema activo; no reemplazar el recurso correcto por una variante con contraste inadecuado.
- Mantener una caja de presentación coherente entre temas y tamaños de pantalla, preservando las proporciones del arte.
- Revisar los límites visibles del recurso: algunos SVG incluyen margen vacío dentro de su `viewBox`. Normalizar ese espacio con recorte del contenedor o posición del objeto, sin deformar el logotipo.
- Evitar variantes rasterizadas con un fondo blanco sobre superficies oscuras. Validar contraste y tamaño visual tanto en claro como en oscuro, en escritorio y móvil.

## Estado y datos

CRM distingue éxito, aviso, peligro e información con tonos separados y superficies suaves; conservar diferencias de significado en ambos temas. Gráficos deben usar una paleta categórica accesible y consistente con estados, con leyendas legibles; los colores de series no deben codificar estado operativo salvo que esa sea la intención del dato.

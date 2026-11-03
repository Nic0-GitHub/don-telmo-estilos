# Arquitectura de interfaz

## Principios

1. Separar presentación, coordinación de pantalla y lógica de dominio.
2. Un componente presentacional recibe datos y emite intenciones; no solicita datos ni conoce reglas comerciales.
3. La página o contenedor compone componentes, conecta servicios y resuelve carga, error, vacío y permisos.
4. Extraer módulos por responsabilidad, contrato o reutilización real, no para maximizar el número de archivos.
5. Mantener API pequeñas y explícitas; tipar entradas, salidas y estados.

## Modelo presentacional

- **Página / contenedor:** coordina flujo, estado de pantalla, datos y navegación.
- **Componente presentacional:** representa datos recibidos; emite eventos como `onSave`, `onSelect`, `onDismiss`.
- **Servicio / caso de uso:** encapsula acceso a API y reglas de negocio.
- **Modelo de dominio o DTO:** describe datos; el componente visual no transforma el dominio en secreto.

```text
Página (estado y coordinación)
  ├── Servicio / caso de uso (datos y reglas)
  └── Componentes presentacionales
       ├── entradas: datos, variantes, estado
       └── salidas: acciones del usuario
```

## Contratos input/output

- Las entradas son datos, no mecanismos para que un hijo controle al padre.
- Las salidas representan acciones o intenciones, no callbacks de efectos secundarios internos.
- Preferir nombres descriptivos (`selectedItemChange`, `saveRequested`) y tipos explícitos.
- Evitar mutar objetos recibidos; enviar nuevos valores o identificadores.
- Mantener consistencia entre frameworks: Angular `input()`/`output()`, React props y callbacks, Vue props y emits, equivalentes idiomáticos en otros entornos.
- No propagar el API de un framework en los tokens, contratos conceptuales o documentación base.

## Estado visual explícito

Cada patrón que dependa de datos debe contemplar loading, error recuperable, vacío, contenido y deshabilitado. Los componentes no inventan datos ni deciden permisos comerciales. Accesibilidad: teclado, foco visible, etiquetas, contraste, reducción de movimiento y mensajes comprensibles.

## Organización sugerida (agnóstica)

```text
ui/
  tokens/       # identidad, semántica y temas
  primitives/   # controles base
  patterns/     # tarjetas, formularios, tablas, gráficos
features/       # composición por capacidad de producto
pages/          # rutas y orquestación de pantalla
services/       # acceso a datos y casos de uso
models/         # contratos de datos por dominio
```

Adaptar nombres y carpetas a la convención de cada framework; conservar responsabilidades y límites.

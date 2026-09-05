# Noctalia LabWC Template

Esta plantilla configura LabWC (gestor de ventanas compatible con Openbox) para adaptar sus colores automáticamente a los esquemas generados por Noctalia, incluyendo un sistema de distribución de botones de ventana estilo macOS (cuadrados simétricos) que también se recolorean dinámicamente.

## Instalación

1. Asegúrate de extraer esta carpeta `labwc` dentro de tus plantillas o directorios de configuración de Noctalia. Por defecto, puedes dejarla en `~/.config/labwc/TEMPLATE/labwc/`.

2. Agrega el siguiente bloque a tu archivo de configuración de plantillas de Noctalia (`~/.config/noctalia/templates.toml`):

```toml
[theme.templates.user.labwc]
input_path = "~/.config/labwc/TEMPLATE/labwc/labwc.conf"
output_path = "~/.config/labwc/noctalia.conf"
post_hook = "bash ~/.config/labwc/TEMPLATE/labwc/apply.sh"
undo_hook = "bash ~/.config/labwc/TEMPLATE/labwc/undo.sh"
```

*(Nota: Asegúrate de que las rutas reflejen el lugar exacto donde extrajiste esta carpeta TEMPLATE)*.

3. Recarga Noctalia para que aplique los cambios:
```bash
noctalia msg config-reload
```

## Características
- Generación automática de botones cuadrados minimalistas (`10x10 px`).
- Interfaz completamente dinámica (Las ventanas usan colores de fondo neutradas para que los botones mantengan buen contraste).
- Botón de Cerrar unificado al color `error`.
- Minimizar `secondary` y Maximizar `primary`.
- Compatible con el sistema de temas dinámicos en tiempo real (Hover color e inactive color).

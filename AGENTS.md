# AGENTS.md

## Propósito

Este archivo define cómo debe trabajar un agente dentro de este proyecto.

## Flujo obligatorio

Antes de hacer cambios:

1. Leer la petición del usuario completa.
2. Revisar los archivos involucrados antes de asumir comportamiento.
3. Identificar la fuente de verdad del cambio.
4. Explicar en una frase qué se va a hacer antes de editar.

Durante el trabajo:

1. Hacer cambios mínimos y directos.
2. No modificar código o archivos no relacionados.
3. Mantener la documentación sincronizada con la implementación real.
4. Si hay ambigüedad, preferir lo que ya está definido en `src/` sobre el `README.md`.

Después de hacer cambios:

1. Verificar el diff generado.
2. Confirmar qué archivos cambiaron.
3. Resumir el resultado de forma breve y concreta.

## Reglas para este repositorio

- `src/settings/_settings.scss` es la fuente de verdad para colores, breakpoints y settings globales.
- Si el `README.md` contradice a `src/`, se debe corregir el `README.md`.
- Evitar cambios cosméticos innecesarios.
- Mantener la documentación en español cuando el cambio sea de documentación interna del proyecto.
- Este proyecto usa skill `caveman`: https://github.com/JuliusBrussee/caveman
- Modo de respuesta por defecto: `/caveman full`
- Regla alternativa para respuestas más claras sin tanto recorte: `/caveman lite`
- Regla alternativa para máxima compresión de tokens: `/caveman ultra`
- Si `caveman` no existe en la PC o no está disponible localmente, clonar `https://github.com/JuliusBrussee/caveman` y usar ese repositorio como referencia.
- Usar modo normal solo si tema requiere advertencia crítica, acción irreversible o máxima claridad para evitar malentendidos.

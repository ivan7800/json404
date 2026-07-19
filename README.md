# JSON Studio Pro 404

**JSON Studio Pro 404** es una aplicación web estática para abrir, entender, auditar, limpiar y convertir archivos `.json` sin subirlos a internet.

Funciona directamente en el navegador y es compatible con GitHub Pages. No usa backend, no requiere instalación y no carga librerías externas.

## Novedades v2.0.0

- **Reparación agresiva con informe de cambios**: además de arreglar comas finales, comillas y claves sin comillas, ahora elimina comentarios estilo JavaScript, convierte literales de Python (`True`/`False`/`None`), sustituye `NaN`/`Infinity`, y **extrae el bloque JSON válido aunque esté rodeado de texto** (logs, respuestas de API con prefijos, etc.). Muestra exactamente qué cambios se aplicaron.
- **Consulta tipo JMESPath** (pestaña "Consulta"): rutas, índices `[0]`/`[-1]`, comodines `[*]`, slices `[0:3]` y filtros `[?campo>valor]` para extraer o filtrar datos sin escribir código.
- **Generador de código** (pestaña "Generar"): interfaces TypeScript, dataclasses de Python y un snippet `fetch()`, inferidos automáticamente de la estructura del JSON cargado.
- **JSON Patch (RFC 6902)** en el comparador: además del resumen de diferencias, genera las operaciones de patch reales y permite descargarlas o copiarlas.
- **Árbol con carga progresiva**: los arrays y objetos muy grandes ya no se cortan sin más; se puede pulsar "Cargar más" para seguir explorando sin congelar el navegador.
- **Recientes (local)**: historial de los últimos 8 archivos analizados, guardado solo en tu navegador vía `localStorage`.

## Para qué sirve


- Revisar si un JSON es válido antes de usarlo.
- Entender qué contiene un archivo JSON aunque no seas programador.
- Detectar si hay tokens, API keys, contraseñas, sesiones, emails, teléfonos o rutas locales antes de subirlo a GitHub.
- Convertir datos JSON a formatos más fáciles de leer o compartir.
- Generar informes técnicos y de privacidad.
- Crear una copia limpia con datos sensibles ocultos.
- Probar estructuras con plantillas listas.

## Funciones principales

- Drag & drop de archivos `.json`.
- Pegado manual de JSON.
- Validación con explicación de errores.
- Reparación básica de JSON frecuente: comas finales, comillas curvas, claves sin comillas y bloques Markdown.
- Formatear, minificar y ordenar claves.
- Vista árbol plegable.
- Vista código con búsqueda.
- Vista tabla automática cuando detecta arrays de objetos.
- Interpretador local por reglas.
- Consulta de datos con sintaxis tipo JMESPath (subconjunto): rutas, comodines, slices y filtros.
- Generador de código: interfaces TypeScript, dataclasses Python y snippet fetch.
- Auditoría de privacidad y seguridad.
- Detección de claves duplicadas.
- Conversión a JSON, CSV, Markdown, YAML, XML, TXT, HTML, JSON Schema y rutas JSONPath.
- Informes exportables: técnico, privacidad y bloque README.
- Comparador básico entre dos JSON con generación de JSON Patch (RFC 6902).
- Plantillas integradas: package.json, API response, catálogo, configuración de app, i18n, videojuego, backup sensible y deploy.
- Skins visuales: Midnight, Aurora, Terminal y Paper.
- Diseño responsive para móvil, tablet y escritorio.

## Privacidad

Todo el procesamiento ocurre en local, dentro del navegador. La app no envía archivos a servidores externos.

Aun así, antes de publicar cualquier JSON en GitHub conviene revisar manualmente el informe de privacidad.

## Cómo usar en GitHub Pages

1. Sube `index.html`, `README.md`, `LICENSE` y `demo.json` a un repositorio.
2. En GitHub entra en **Settings → Pages**.
3. Elige **Deploy from branch**.
4. Selecciona `main` y `/root`.
5. Guarda los cambios.

## Archivos incluidos

- `index.html` — aplicación completa.
- `README.md` — documentación.
- `demo.json` — archivo de prueba.
- `LICENSE` — licencia MIT.

## Limitaciones conocidas

- No sustituye una auditoría profesional de seguridad.
- La reparación automática solo corrige errores comunes, no JSON gravemente roto.
- La conversión YAML/XML es básica y pensada para lectura/interoperabilidad simple.
- La inferencia de JSON Schema es aproximada, basada en la muestra cargada.
- La consulta tipo JMESPath es un subconjunto propio (rutas, `[*]`, slices y filtros con `==`, `!=`, `>`, `<`, `>=`, `<=`); no implementa la especificación JMESPath completa (funciones, pipes, multi-select).
- El código generado (TypeScript/Python/fetch) es un punto de partida inferido de una muestra; revísalo antes de usarlo en producción.
- Los archivos "recientes" se guardan solo en `localStorage` de tu navegador; los archivos grandes (>250 KB) se listan pero no guardan su contenido.

## Recomendación

Úsala especialmente antes de subir archivos JSON a GitHub, compartir backups, publicar ejemplos de API o convertir datos a CSV/Markdown.

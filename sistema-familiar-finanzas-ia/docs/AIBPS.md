# Evaluación AIBPS

## Ágil

La interfaz principal es Telegram, por lo que registrar o consultar información no exige abrir una aplicación contable. Los flujos se dividen en módulos pequeños y especializados.

**Evaluación:** alta, con margen de mejora en la reducción de pasos de algunos cierres.

## Fluida

El usuario puede registrar, consultar, corregir y cerrar períodos desde una interfaz conversacional. Los menús guiados reducen la necesidad de recordar comandos.

**Evaluación:** buena. La convivencia entre rutas guiadas, texto libre y fallback de IA requiere cuidar mensajes de estado y errores.

## Protegida

La arquitectura evita entregar escritura directa al LLM. Credenciales se gestionan en n8n y el workflow de IA opera en sólo lectura. El repositorio académico usa exports sanitizados.

**Evaluación:** buena para un prototipo familiar; una versión productiva multiusuario debería reforzar autenticación, segregación de secretos y minimización de datos enviados al modelo.

## Bajo control humano

El usuario conserva la decisión sobre correcciones, cierres y situaciones ambiguas. Las operaciones sensibles vuelven a flujos determinísticos y la IA no puede confirmar acciones por sí misma.

**Evaluación:** alta. El control humano fue una decisión de diseño explícita.

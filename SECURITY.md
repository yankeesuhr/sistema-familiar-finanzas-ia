# Seguridad y privacidad

Este repositorio está preparado para exposición académica y **no debe contener secretos de producción**.

## Sanitización aplicada

- credenciales de n8n eliminadas;
- IDs personales de Telegram sustituidos;
- Google Sheet ID sustituido;
- CVU/CBU/CUIT y referencias bancarias sensibles anonimizadas;
- nombres personales reemplazados por identificadores genéricos;
- IDs de subworkflows marcados para relink;
- webhook IDs invalidados.

## Recomendaciones

- nunca commitear API keys, tokens de Telegram ni credenciales Google;
- usar el gestor de credenciales de n8n;
- mantener el workflow de IA en sólo lectura;
- usar datos ficticios para demostraciones públicas;
- revisar los exports antes de cada publicación.

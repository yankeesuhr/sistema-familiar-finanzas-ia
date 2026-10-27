# Baseline y versiones

El 25/10/2026 se congeló **Sistema Familiar v1.0** como baseline estable. Ese corte estableció que las mejoras posteriores debían versionarse como `v1.1+`.

La versión utilizada para el TFI conserva ese baseline y agrega la capa de IA posterior.

| Módulo | Versión TFI |
|---|---:|
| 01 Entrada Telegram | v39 |
| 02 Router | v43 |
| 03 PDFs e importaciones | v96 |
| 04 Correcciones | v31 |
| 05 Movimientos / consultas | v38 |
| 06 Cierre mensual | v6.9 |
| 06B Dashboard | v6.9 |
| 07 IA fallback | v7 |
| Power BI | v1.8 |

## Nota de reproducibilidad

El archivo contemporáneo de `06 v6.9` no estaba incluido en el paquete archivado utilizado para construir este repositorio. Por esa razón se documenta su comportamiento en `workflows/06_cierre_mensual_SPEC.md` en lugar de publicar una versión histórica como si fuera la vigente.

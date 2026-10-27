# Metodología de desarrollo

## 1. Empezar por un problema real

El proyecto parte de información financiera familiar dispersa en varias fuentes y de la dificultad de consolidarla sin convertir la gestión cotidiana en un proceso contable pesado.

## 2. Construcción iterativa

La solución evolucionó mediante ciclos cortos:

1. captura de entradas;
2. normalización;
3. persistencia en un ledger;
4. detección de errores reales;
5. corrección de reglas;
6. conciliación;
7. cierre mensual;
8. visualización;
9. incorporación controlada de IA.

Las versiones históricas se conservaron para poder reconstruir el proceso.

## 3. Determinismo antes que IA

Una decisión metodológica central fue postergar la IA hasta estabilizar las rutas básicas. Se priorizaron:

- reglas explícitas;
- idempotencia;
- control de duplicados;
- staging antes de confirmar importaciones;
- conciliación con documentos reales;
- trazabilidad de correcciones;
- preguntas sólo ante ambigüedad material.

## 4. Errores que guiaron el diseño

Algunos problemas relevantes encontrados durante el desarrollo:

- transferencias internas duplicadas entre extractos;
- cierres con diferencias importantes;
- registros de USD que no se reflejaban correctamente en los resúmenes;
- riesgo de doble contar pagos de tarjeta o transferencias propias como gasto;
- consultas complejas que excedían el parser determinístico;
- complejidad excesiva del módulo de vencimientos;
- respuestas de IA que necesitaban formato estructurado y manejo defensivo de errores.

Cada problema se convirtió en una regla, validación o decisión de alcance.

## 5. Incorporación de IA

La IA se agregó al final como fallback de razonamiento. El objetivo no fue “poner IA en todo”, sino utilizarla sólo para preguntas que requieren interpretación, comparación o síntesis a partir de datos ya preparados.

La escritura de datos, los cálculos financieros base y la conciliación siguen en flujos determinísticos.

## 6. Prueba y corrección

Se utilizaron casos reales y luego se verificaron sus efectos en:

- `Movimientos`;
- resúmenes mensuales;
- Dashboard de Google Sheets;
- Power BI;
- respuestas del bot.

Cuando una prueba era sólo técnica, se eliminaba luego para no contaminar los datos reales.

## 7. Criterio de cierre de versión

La versión académica se congeló como un baseline estable. Las mejoras posteriores se versionan sin reescribir la historia previa.

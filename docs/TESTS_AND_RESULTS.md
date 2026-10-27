# Pruebas y resultados

## Casos funcionales

### Registro manual

Se validó la cadena:

`Telegram → n8n → Google Sheets`

mediante un gasto de prueba, verificando su alta en `Movimientos` y eliminándolo después para no alterar la base real.

### USD

Se verificó un caso real de gasto en dólares:

- monto original: USD 2.000;
- cotización real utilizada: ARS 1.510/USD;
- equivalente materializado: ARS 3.020.000.

El objetivo del test fue comprobar que moneda original, cotización, equivalente ARS y categoría permanecieran alineados a lo largo del sistema.

### Conciliación y cierre

El cierre mensual fue diseñado para:

- detectar faltantes;
- validar saldos;
- evitar confirmar diferencias grandes;
- incorporar inversiones;
- actualizar automáticamente el Dashboard.

### Power BI

Se verificó que las visualizaciones consumieran las tablas normalizadas y que los gastos USD materializados quedaran incluidos sin doble conteo.

### Fallback IA

Se enviaron preguntas que exigían razonamiento más complejo que una consulta determinística. A partir de esas pruebas se agregó el desglose obligatorio de:

- resultado operativo;
- resultado financiero;
- resultado total.

## Resultado principal

La solución permite centralizar y consultar información financiera familiar sin depender de IA para los cálculos críticos. La IA aporta valor en interpretación y síntesis, pero queda aislada de las operaciones de escritura.

# IA generativa: módulo 07

## Rol

El módulo 07 es una capa de razonamiento que se ejecuta **sólo cuando el router determinístico no resuelve una consulta**.

Modelo configurado en la versión final: **GPT-6 Luna**, a través de OpenAI Responses API.

## Qué recibe

El workflow construye un contexto financiero acotado y jerarquizado. Según la consulta puede incorporar:

- períodos conciliados;
- movimientos recientes;
- cuentas;
- tarjetas;
- inversiones.

El contexto se reduce para evitar enviar datos innecesarios y controlar consumo.

## Reglas del prompt de sistema

El prompt define, entre otras, estas reglas:

- usar la jerarquía de fuentes ya resuelta por el sistema;
- no inventar cifras ni causas;
- separar resultado operativo, financiero y total;
- no duplicar gastos USD;
- no tratar transferencias propias, pagos de tarjeta o inversiones como gasto salvo clasificación explícita;
- nunca afirmar que modificó datos;
- pedir una sola aclaración concreta cuando falta información;
- devolver acciones de escritura al flujo determinístico;
- responder en español claro y breve.

## Salida estructurada

La respuesta se fuerza a un esquema con campos equivalentes a:

```json
{
  "action": "answer | clarify",
  "answer": "texto",
  "confidence": 0.0,
  "route_suggestion": "none | 04_correcciones | 05_movimientos_consultas | 06_cierre",
  "canonical_text": null,
  "used_data": []
}
```

Esto reduce la fragilidad del parsing y permite que Telegram reciba un mensaje utilizable aun cuando la llamada de IA falle.

## Control de costo

La versión final usa esfuerzo bajo por defecto y lo eleva para consultas de comparación, causas o tendencias. También limita la cantidad de meses y movimientos recientes enviados.

## Control humano

La IA no confirma cierres ni modifica el ledger. Para acciones sensibles sólo puede sugerir la ruta determinística correspondiente.

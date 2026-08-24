# Dashboard Bancario

Plantilla estática preparada para publicarse en un repositorio y alimentarse con `data.json`.

## Archivos

- `index.html`: diseño y lógica del dashboard.
- `data.json`: datos actuales mostrados por el dashboard.
- `data.example.json`: ejemplo de la estructura que Make debe generar.

## Cómo funciona

1. Publica el repositorio en GitHub Pages, Netlify, Vercel u otro hosting estático.
2. El navegador abre `index.html`.
3. `index.html` consulta automáticamente `data.json`.
4. Cada vez que Make actualice `data.json`, el dashboard mostrará los datos nuevos sin modificar el HTML.

## Estructura mínima esperada

```json
{
  "archivo": "BANCOS_24-08-2026.xlsx",
  "fecha_proceso": "24/08/2026 16:30",
  "periodo": "Agosto 2026",
  "saldo_total": 1683669.51,
  "total_creditos": 42000,
  "total_debitos": 18500,
  "cantidad_movimientos": 6,
  "bancos": [
    {
      "nombre": "Banco Agrícola",
      "saldo": 1500074.83,
      "creditos": 20000,
      "debitos": 8000,
      "movimientos": [
        {
          "fecha": "24/08/2026",
          "referencia": "TRX-001",
          "descripcion": "TRANSFERENCIA RECIBIDA",
          "debito": 0,
          "credito": 12500,
          "saldo": 1492574.83
        }
      ]
    }
  ]
}
```

## Integración con Make

El escenario de Make debe procesar el Excel y producir el JSON con esta estructura. Después debe reemplazar o actualizar `data.json` en el repositorio/hosting.

No es necesario generar un nuevo `index.html` en cada ejecución.

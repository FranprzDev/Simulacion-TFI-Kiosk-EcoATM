# Kiosk EcoATM — Simulador de Factibilidad

Trabajo Final Integrador de la materia **Simulación** (Ing. en Sistemas, UTN-FRT). Plataforma web para evaluar, bajo incertidumbre, la factibilidad operativa y económica de configuraciones de kioscos EcoATM.

## Qué responde

- ¿La configuración cumple el SLA de tiempo de procesamiento?
- ¿La utilización está en rango objetivo y el throughput justifica los costos?
- ¿En cuánto se amortiza la inversión (3, 6, 12 meses o años)?

## Cómo funciona

Motor de simulación propio en TypeScript: eventos discretos + Monte Carlo, con generador pseudoaleatorio e implementación de distribuciones (Uniforme, Normal, Poisson) escritos desde cero — sin librerías externas para PRNG ni muestreo, por requisito académico.

Definís una configuración (kioscos, costos, horarios, parámetros estocásticos, horizonte, réplicas, semilla), corrés escenarios A vs B bajo el mismo horizonte y comparás KPIs con intervalos de confianza: throughput, tiempo en sistema, utilización, abandono, ingreso/costo/margen, punto de equilibrio y probabilidad de factibilidad.

## Ejecutar

```bash
pnpm install
pnpm dev
```

Tests del motor:

```bash
pnpm test
```

## Estructura

| Path | Qué |
| --- | --- |
| `src/` | App Next.js 16 + motor de simulación, hooks y componentes |
| `specs/` | Base del simulador y PRDs (alcance académico) |
| `documentation/` · `information/` | Material de la materia y decisiones de modelado |
| `tests/` | Corridas de validación del motor |

> [!NOTE]
> Proyecto académico: el modelo simplifica la realidad a propósito para aislar las variables bajo estudio.

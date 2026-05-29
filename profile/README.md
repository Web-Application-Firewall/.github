# WAF para pymes — Organización del Proyecto

> Repositorio de recursos del artículo **"Estudio de implementación de un WAF en hardware no dedicado para pymes"**  
> Universidad ICESI · Facultad Barberi de Ingeniería, Diseño y CA · Ingeniería Telemática · 2026  
> **Autores:** Lina María Andrade Gómez · Juan José Barrera Gracia · Andrés Mauricio Mesa Franco

---

## Estructura de la organización

Esta organización aloja los repositorios correspondientes a cada fase del estudio. Cada repositorio contiene los scripts, configuraciones, datasets procesados y resultados asociados a su fase.

| Repositorio | Descripción |
|---|---|
| [`fase-2-evaluacion`](#) | Selección de endpoints de DVWA, Scripts de evaluación GoTestWAF, configuraciones base y resultados comparativos |
| [`fase-3-optimizacion`](#) | Modelo de regresión logística con regularización Lasso, vectores de reglas CRS, configuraciones optimizadas y resultados de detección y recursos |
| [`fase-4-simulacion`](#) | Locustfile, escenarios de carga, scripts de monitoreo y resultados por escenario |

---

## Herramientas utilizadas

### Evaluación de WAFs
| Herramienta | Versión | Propósito |
|---|---|---|
| [GoTestWAF](https://github.com/wallarm/gotestwaf) | Latest | Evaluación comparativa de WAFs mediante payloads de evasión |
| [WafBench](https://github.com/microsoft/wafbench) | Latest | Evaluación inicial basada en reglas CRS/ModSecurity |
| [DVWA](https://github.com/digininja/DVWA) | Latest | Aplicación web vulnerable usada como objetivo de pruebas |

### WAFs evaluados
| WAF | Versión | Motor |
|---|---|---|
| [Coraza](https://coraza.io) | Latest | ModSecurity / SecLang |
| [BunkerWeb](https://www.bunkerweb.io) | Latest | NGINX + CRS |
| [SafeLine](https://waf.chaitin.com) | Latest | Detección propia |
| [CrowdSec](https://www.crowdsec.net) | Latest | Coraza + CRS |
| [UusecWAF](https://uusec.com) | Latest | Propio |

### Modelo y entrenamiento
| Herramienta | Propósito |
|---|---|
| [scikit-learn](https://scikit-learn.org) | Regresión logística con regularización Lasso |
| [JAX](https://jax.readthedocs.io) | Backend de cómputo para entrenamiento |
| [Google Cloud Platform](https://cloud.google.com) | Infraestructura de entrenamiento (64 GB RAM, 10 vCPU) |

### Generación de tráfico y monitoreo
| Herramienta | Propósito |
|---|---|
| [Locust](https://locust.io) | Generación de tráfico legítimo por escenarios de carga |
| `docker stats` | Monitoreo de recursos en WAFs contenerizados |
| `pidstat` | Monitoreo de recursos de Coraza como proceso nativo |
| [NetBird](https://netbird.io) | VPN para acceso remoto durante las pruebas |

### Conjuntos de datos
| Dataset | Descripción |
|---|---|
| **Biblio-US17** | Tráfico HTTP etiquetado basado en capturas reales del sitio web de la Universidad de Sevilla |
| **Thirty-Days** | Logs de ataques reales registrados durante 30 días sobre un servidor WordPress en producción |


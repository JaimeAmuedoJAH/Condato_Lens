<p align="center">
  <img src="assets/logo.jpg" alt="Dashboard preview" width="300">
</p>

## Descripción general

Este documento corresponde a un **reporte exportado desde Metabase** que analiza el rendimiento de aplicaciones backend durante un periodo determinado. El objetivo del informe es **monitorizar el comportamiento del sistema, detectar errores y localizar cuellos de botella en los endpoints de la API**.

El reporte está orientado a equipos de **ingeniería, DevOps y producto** para facilitar el seguimiento del estado de la aplicación y apoyar la toma de decisiones técnicas.

---

## 👩‍💻 Contribuyentes

  | Nombre           | GitHub | LinkedIn |
|------------------|--------|----------|
| Jaime Amuedo     | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/JaimeAmuedoJAH) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jaime-amuedo-hidalgo-a432bb354/) |
| Ruben Camacho    | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RubenCG1997) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ruben-camacho-gomez) |
| Pablo Rodríguez  | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/PabloRodMu) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pablo-rodríguez-muñoz-357890185) |
| Andrés Pérez     | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/andresdatalyst) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andresproviraprogramador/) |

---

# Información del reporte

- **Herramienta de análisis:** Metabase  
- **Dataset / fuente:** `Base de datos de MongoDB. Registry`
- **Aplicación analizada:** aplicaciones .backend  
- **Periodo analizado:** Periodo a seleccionar con el filtro de fecha.  

---

# KPIs principales

El dashboard incluye varios indicadores clave para evaluar el estado del sistema.

## Total de peticiones

Número total de requests recibidas por la API durante el periodo analizado.

Este indicador permite:

- Medir la carga del sistema
- Detectar picos de tráfico
- Correlacionar tráfico con errores o degradación de rendimiento

---

## Errores totales

Cantidad total de peticiones que terminaron con códigos de error HTTP.

Sirve para:

- Detectar fallos en el sistema
- Medir estabilidad de la aplicación
- Comparar la evolución del error rate en el tiempo

---

## Tiempo medio por petición

Tiempo promedio de respuesta de la API.

Se utiliza para:

- Medir la latencia general del sistema
- Detectar degradaciones de rendimiento
- Identificar posibles problemas de infraestructura o base de datos

---

## Porcentaje de error

Relación entre peticiones fallidas y peticiones totales.

Este KPI permite evaluar rápidamente la **salud general del servicio**.

---

# Visualizaciones incluidas

## Tendencia diaria de peticiones erróneas

Gráfica temporal que muestra la evolución de errores por día dentro del periodo analizado.

Objetivos:

- Detectar días con anomalías
- Identificar incidentes o despliegues problemáticos
- Analizar patrones de fallo

---

## Errores por código HTTP

Distribución de errores por tipo de código HTTP, por ejemplo:

- `400` – Bad Request  
- `401` – Unauthorized  
- `403` – Forbidden  
- `404` – Not Found  
- `500` – Internal Server Error  

Esto permite distinguir entre:

- Errores del cliente
- Errores de autenticación
- Fallos del servidor

---

## Errores por endpoint

Análisis de qué rutas de la API generan más errores.

Sirve para:

- Localizar endpoints problemáticos
- Identificar funcionalidades inestables
- Priorizar correcciones

---

## Top 10 peticiones más lentas

Listado de los endpoints con mayor tiempo de respuesta.

Este análisis permite:

- Detectar cuellos de botella
- Identificar endpoints que necesitan optimización
- Encontrar posibles problemas de consultas a base de datos o servicios externos

---

# Casos de uso del reporte

Este dashboard se utiliza principalmente para:

- Monitorización del backend
- Análisis de incidentes
- Mejora de rendimiento
- Priorización de optimizaciones
- Seguimiento tras despliegues

---

# Recomendaciones de uso

Se recomienda revisar este reporte:

- Después de despliegues importantes
- Cuando se detecten incidencias en producción
- De forma periódica en revisiones de rendimiento

Además, es útil combinarlo con:

- Logs de aplicación
- Métricas de infraestructura
- Herramientas de observabilidad (APM)

---

# Posibles mejoras futuras

Para ampliar el valor del dashboard se podrían añadir:

- Percentiles de latencia (P95, P99)
- Tiempos de respuesta por endpoint
- Tráfico por cliente o usuario
- Comparación entre versiones de la API
- Métricas de base de datos
- Análisis analítico de las aplicaciones .frontend

---
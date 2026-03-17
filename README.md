# Condato Lens 🔍

Panel de monitorización técnica y analítica sobre el uso de las aplicaciones de Condato,
desarrollado como proyecto pedagógico en el marco del programa
**Data Analyst / Andalucía / P1 · 2025-2026** (Don Bosco Salesianos Social).

---

## 📋 Descripción general

Condato Lens es un dashboard BI que centraliza KPIs técnicos y analíticos
sobre el comportamiento de las aplicaciones de Condato, conectando directamente
con su base de datos MongoDB y visualizando la información en tiempo real
a través de Metabase.

El proyecto nace de la necesidad del equipo de soporte técnico de Condato
de tener visibilidad sobre el rendimiento de sus aplicaciones sin depender
de consultas manuales a base de datos.

El reporte está orientado a equipos de **ingeniería, DevOps y producto** para
facilitar el seguimiento del estado de la aplicación y apoyar la toma de
decisiones técnicas.

---

---

## Contribuyentes

  | Nombre           | GitHub | LinkedIn |
|------------------|--------|----------|
| Jaime Amuedo     | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/JaimeAmuedoJAH) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jaime-amuedo-hidalgo-a432bb354/) |
| Ruben Camacho    | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rubencmg) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ruben-camacho-gomez) |
| Pablo Rodríguez  | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/PabloRodMu) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pablo-rodríguez-muñoz-357890185) |
| Andrés Pérez     | [![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/andresdatalyst) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andresproviraprogramador/) |

---

## 🛠️ Stack tecnológico

- **MongoDB** — Base de datos de origen (registros en crudo)
- **Metabase** — Plataforma BI para construcción de dashboards
- **Docker** — Despliegue y conexión de Metabase con MongoDB

---

## 📦 Requisitos previos

- [Docker](https://www.docker.com/) instalado y en ejecución
- Acceso a la base de datos MongoDB de Condato
- Credenciales de conexión (URI, usuario, contraseña)

---

## 🚀 Instalación y puesta en marcha

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/condato-lens.git
cd condato-lens
```

### 2. Levantar Metabase con Docker
```bash
docker pull metabase/metabase
docker run -d \
  -p 3000:3000 \
  --name condato-lens \
  metabase/metabase
```

### 3. Acceder a Metabase

Abre el navegador en `http://localhost:3000` y completa el asistente de configuración inicial.

### 4. Conectar con MongoDB

1. Ve a **Settings → Admin → Databases → Add Database**
2. Selecciona **MongoDB** como tipo de base de datos
3. Introduce los datos de conexión:
   - **Host:** tu-host-mongodb
   - **Puerto:** 27017
   - **Base de datos:** nombre-de-la-db
   - **Usuario / Contraseña:** tus credenciales
4. Haz clic en **Save**

---

## 📊 Dashboards

### Dashboard Técnico — `.backend`

Orientado al equipo de soporte e ingeniería. Analiza el rendimiento de las
aplicaciones backend durante el periodo seleccionado.

**Información del reporte**
- **Herramienta:** Metabase
- **Fuente de datos:** Base de datos MongoDB · colección `Registry`
- **Aplicación analizada:** aplicaciones `.backend`
- **Periodo:** seleccionable mediante filtro de fecha

**KPIs principales**

| KPI | Descripción |
|-----|-------------|
| Total de peticiones | Número total de requests recibidas por la API |
| Errores totales | Peticiones que terminaron con códigos de error HTTP |
| Tiempo medio por petición | Latencia promedio de respuesta de la API |
| Porcentaje de error | Relación entre peticiones fallidas y totales |
| Usuarios concurrentes | Total de usuarios activos en el periodo |

**Visualizaciones incluidas**

- **Tendencia diaria de errores** → detecta días con anomalías e incidentes
- **Errores por código HTTP** → distingue entre errores de cliente (4xx) y servidor (5xx)
- **Errores por endpoint** → localiza rutas problemáticas de la API
- **Top 10 peticiones más lentas** → identifica cuellos de botella por tiempo de respuesta

---

### Dashboard Analítico — `.frontend`

Orientado a entender el comportamiento del usuario final.

**KPIs principales**

| KPI | Descripción |
|-----|-------------|
| Total usuarios concurrentes | Usuarios activos en el periodo analizado |

**Visualizaciones incluidas**

- **Rutas con más tráfico** → funcionalidades más utilizadas
- **Sistemas operativos más usados** → perfil de dispositivo del usuario
- **Navegadores más usados** → contexto de acceso web vs móvil

---

## 💡 Casos de uso

Este dashboard se utiliza principalmente para:

- Monitorización continua del backend
- Análisis de incidentes en producción
- Mejora y optimización de rendimiento
- Priorización de correcciones técnicas
- Seguimiento post-despliegue

Se recomienda revisar el reporte:
- Después de despliegues importantes
- Cuando se detecten incidencias en producción
- De forma periódica en revisiones de rendimiento

Es útil combinarlo con logs de aplicación, métricas de infraestructura
y herramientas de observabilidad (APM).

---

## 🔮 Posibles mejoras futuras

- Percentiles de latencia (P95, P99)
- Tiempos de respuesta desglosados por endpoint
- Tráfico segmentado por cliente o usuario
- Comparación entre versiones de la API
- Métricas de base de datos
- Análisis completo de aplicaciones `.frontend`
- Alertas automáticas ante picos de error

---

## 📁 Estructura del repositorio
```
condato-lens/
│
│
├── assets/
│   ├── logo.jpg
├── docs/
│   ├── briefing.pdf          # Briefing original del proyecto
│   └── Condato_Lens_Dashboard_técnico.pdf      # Presentación final del proyecto
│
└── README.md
```

---

## 📄 Documentación

| Documento | Descripción |
|-----------|-------------|
| [`/docs/briefing.pdf`](./docs/briefing.pdf) | Briefing pedagógico original facilitado por Don Bosco |
| [`/docs/presentacion.pdf`](./docs/Condato_Lens_Dashboard_técnico.pdf) | Presentación final entregada al cliente |

---

## 🗓️ Contexto del proyecto

| | |
|--|--|
| **Cliente** | Condato · javier.rodriguez@condato.es |
| **Duración** | 2 semanas |
| **Datos procesados** | Millones de registros · filtrado a últimos 90 días |
| **Tecnologías aprendidas** | MongoDB, Metabase, Docker |

---

## 📝 Licencia

Proyecto pedagógico desarrollado en el marco del programa Data Analyst
de Don Bosco Salesianos Social. Uso educativo.

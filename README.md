# 🚢 ANÁLISIS DE CRUCEROS - RENDIMIENTO Y PREDICCIONES

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-green.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3+-orange.svg)](https://scikit-learn.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0+-blue.svg)](https://www.mysql.com/)

> Proyecto completo de análisis de datos para el sector cruceros, abarcando desde la generación de datos sintéticos hasta el análisis exploratorio, modelos predictivos y un dashboard ejecutivo en PowerPoint.

---

## 📊 **RESUMEN EJECUTIVO**

Este proyecto analiza 77,040 reservas de cruceros entre 2017 y 2022, evaluando 8 barcos de diferentes compañías. El análisis revela que:

- **La ocupación no es rentabilidad:** Todos los barcos tienen ~91% de ocupación, pero la rentabilidad varía en un **287%** (Queen Mary 2 vs Disney Dream).
- **Satisfacción = Gasto:** Correlación **0.92** entre satisfacción y gasto diario.
- **Disney Dream, oportunidad de oro:** Mejor satisfacción (4.88) pero peor rentabilidad ($1,173/pax). Aumentar estancias de 3.6 a 7 noches podría triplicar el revenue por pasajero.
- **Queen Mary 2, el benchmark:** Líder en rentabilidad con **$4,541/pax** (+62% vs 2º), gracias a estancias largas (13.5 noches) y alto gasto diario ($219/día).

**Predicción:** Ingresos proyectados de **$28.15M** en los próximos 3 meses, un **+22% vs 2021**.

---

## 📋 **ÍNDICE DEL PROYECTO**

| # | Sección | Descripción |
|---|---------|-------------|
| 1 | [Generación de Datos](#-generación-de-datos) | Script Python para simular datos realistas |
| 2 | [Análisis Exploratorio (EDA)](#-análisis-exploratorio-eda) | Patrones temporales, rentabilidad, geografía |
| 3 | [Visualizaciones](#-visualizaciones) | 11 gráficos clave para entender el negocio |
| 4 | [Modelo de Regresión](#-modelo-de-regresión) | ¿Qué impulsa los ingresos? (R²=0.909) |
| 5 | [Predicciones](#-predicciones) | Holt-Winters · $28.15M en 3 meses |
| 6 | [Dashboard PowerPoint](#-dashboard-powerpoint) | Presentación ejecutiva completa |
| 7 | [Conclusiones](#-conclusiones-y-recomendaciones) | 6 insights · Estrategias por barco |

---

## 🛠️ **GENERACIÓN DE DATOS**

Los datos fueron generados sintéticamente con Python, simulando reservas de cruceros con características realistas. El script incluye:

- **8 barcos** con diferentes capacidades, rutas y perfiles de gasto
- **Período:** 2017 - 2022
- **Variables:** Fechas de viaje, lead time, noches de estancia, tipo de suite, canal de venta, paquete, país de origen, ingresos, gasto diario y satisfacción

## 📊 RESUMEN EJECUTIVO

### Contexto del Proyecto
Este proyecto analiza **77,040 reservas de cruceros** entre 2017 y 2022, evaluando **8 barcos** de diferentes compañías. El objetivo es identificar patrones de rendimiento, rentabilidad y oportunidades de mejora, así como predecir ingresos futuros.

---

### 🔍 Principales Hallazgos

| # | Hallazgo | Dato Clave | Implicación |
|---|----------|------------|-------------|
| 1 | **La ocupación no es rentabilidad** | Todos los barcos ~91% ocupación, pero rentabilidad varía **287%** | Enfocar en estancias y gasto diario, no solo en llenar cabinas |
| 2 | **Satisfacción = Gasto** | Correlación **0.92** entre satisfacción y gasto | Invertir en experiencias premium para aumentar ingresos |
| 3 | **Disney Dream, oportunidad de oro** | Mejor satisfacción (4.88) pero **$1,173/pax** | Aumentar estancias de 3.6 a 7 noches = +$2,000/pax |
| 4 | **Queen Mary 2, el benchmark** | **$4,541/pax** (+62% vs 2º) | Modelo de lujo + estancias largas es el más rentable |
| 5 | **B2B es el motor del negocio** | **44%** de la facturación vía agencias | Fortalecer alianzas B2B y digitalizar canal directo |
| 6 | **Suites premium impulsan rentabilidad** | Barcos con más suites = mayor rentabilidad | Aumentar oferta de balcones y suites |

---

### 📈 KPIs Principales

| Métrica | Valor | Interpretación |
|---------|-------|----------------|
| **Ingreso Total (3 meses)** | **$28,153,853** | Proyección de ingresos a corto plazo |
| **Promedio Diario** | **$312,821** | Referencia para planificación diaria |
| **Ocupación Media** | **91.1%** | Alta ocupación en todos los barcos |
| **Satisfacción Media** | **4.58/5.00** | Experiencia consistente y positiva |
| **Revenue/Pax (Queen Mary 2)** | **$4,541** | Líder absoluto en rentabilidad |
| **Crecimiento vs 2021** | **+22%** | Recuperación post-COVID confirmada |

---

### 🤖 Modelo de Regresión

| Métrica | Valor | Interpretación |
|---------|-------|----------------|
| **R²** | **0.9085** | Explica el **90.9%** de la variabilidad en ingresos |
| **MAE** | **$406** | Error promedio por reserva |
| **Precisión** | **89.6%** | Muy alta precisión predictiva |

**Variables con mayor impacto en ingresos:**

| Variable | Coeficiente | Impacto |
|----------|-------------|---------|
| **Cabinas_Reservadas** | **+$1,392** | Más cabinas ocupadas = más ingreso |
| **Pasajeros_Reserva** | **+$1,306** | Más pasajeros = más ingreso |
| **Noches_Estancia** | **+$553** | Más noches = más ingreso |
| **Satisfacción** | **-$308** | Clientes exigentes gastan menos |

---

### 🔮 Predicciones

**Metodología:** Holt-Winters (suavizado exponencial) · Período pre-COVID (2017-2020) · Horizonte: 90 días

| Métrica | Valor |
|---------|-------|
| **Ingreso Total (3 meses)** | **$28,153,853** |
| **Promedio Diario** | **$312,821** |
| **Desviación Estándar** | **±$3,979** |
| **Día Pico** | **$322,224** (02/03/2020) |
| **Día Más Bajo** | **$304,404** |
| **Crecimiento vs 2021** | **+22%** |

**Top 5 Días con Mayor Ingreso:**

| Fecha | Ingreso Estimado |
|-------|------------------|
| 02/03/2020 | **$322,224** |
| 09/03/2020 | $321,731 |
| 16/03/2020 | $321,238 |
| 23/03/2020 | $320,746 |
| 30/03/2020 | $320,253 |

---

### 🎯 Recomendaciones por Barco

| Barco | Problema | Solución | Impacto Estimado |
|-------|----------|----------|------------------|
| **Disney Dream** | Estancias cortas (3.6 noches) | Paquetes de 7+ noches | **+$2,000/pax** |
| **Costa Smeralda** | Baja satisfacción (4.20) | Mejorar experiencia a bordo | **+0.5 pts sat.** |
| **AIDAcosma** | Bajo gasto diario ($129) | Upselling en paquetes | **+$50/día** |
| **MSC World Europa** | Posición media | Experiencias mediterráneas únicas | **+10% revenue** |

---

### 📊 Resumen de Resultados

| Concepto | Valor |
|----------|-------|
| **Registros analizados** | 77,040 reservas |
| **Barcos evaluados** | 8 |
| **Período** | 2017 - 2022 |
| **R² del modelo** | 0.909 |
| **Precisión del modelo** | 89.6% |
| **Ingresos proyectados** | $28.15M en 3 meses |
| **Crecimiento vs 2021** | +22% |

---

### 🛠️ Tecnologías Utilizadas

Python 3.10+ | Pandas | NumPy | Scikit-learn | StatsModels
Matplotlib | Seaborn | MySQL | SQLAlchemy | Jupyter Notebook

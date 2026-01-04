## Objetivo del Proyecto

- Analizar los factores asociados a la deserción de clientes.
- Identificar las variables numéricas y categóricas.
- Interpretar las variables explicativas de 'Churt' o 'Deserción'.
- Identificar patrones relevantes para la toma de decisiones estratégicas.

---

## Estructura del Proyecto
├── data/
│ ├── raw/ # Datos originales
│ ├── processed/ # Datos limpios y transformados
│
├── scripts/
│ ├── 01_importacion.R # Importación de datos
│ ├── 02_limpieza.R # Limpieza y preparación
│ ├── 03_eda.R # Análisis exploratorio
│ ├── 04_logit_base.R # Modelo LOGIT principal
│ ├── 05_logit_categorico.R # Segundo LOGIT con variables categóricas
│
├── outputs/
│ ├── tablas/ # Tablas de resultados
│ ├── graficos/ # Visualizaciones
│
├── README.md
└── requirements.txt / renv.lock
---

## Flujo Metodológico

### 1️. Importación de datos
- Lectura de la base original.
- Revisión de estructura, tipos de datos y valores faltantes.

### 2️. Limpieza y procesamiento
- Eliminación de duplicados.
- Tratamiento de valores nulos.
- Recodificación de variables categóricas.
- Creación de variables dummy para el modelo LOGIT.
- Exclusión justificada de variables no informativas o redundantes.

### 3️. Exploratory Data Analysis (EDA) 
- Estadísticas descriptivas.
- Distribución de variables clave.
- Relación preliminar entre variables explicativas y deserción.

### 4️. Analisis de correlación - Modelo econométrico LOGIT

- **Modelo 1:** Variables numéricas y contractuales principales.
- **Modelo 2:** Variables categóricas adicionales no incluidas en el primer modelo.

Ambos modelos estiman la probabilidad de deserción mediante máxima verosimilitud.

---

## Interpretación del Modelo LOGIT

### Coeficientes
Los coeficientes representan el **cambio en el logaritmo de las odds de deserción** ante un cambio unitario en la variable explicativa, manteniendo constantes las demás (*ceteris paribus*).

> Un coeficiente positivo indica mayor probabilidad relativa de deserción, mientras que uno negativo indica un efecto protector.

### Odds Ratio
Se calculan como `exp(coeficiente)` y facilitan la interpretación:

- OR > 1 → mayor riesgo de deserción
- OR < 1 → menor riesgo de deserción

### Enfoque no causal
Los resultados **no implican causalidad**, sino **asociaciones estadísticas condicionadas** a las variables incluidas en el modelo.

---

## Consideraciones Importantes

- El análisis puede estar sujeto a **variables omitidas**.
- Algunas asociaciones contraintuitivas (ej. fibra óptica) pueden explicarse por:
  - Expectativas del cliente
  - Mayor competencia
  - Endogeneidad por selección
- Los resultados deben interpretarse en conjunto y no de forma aislada.

---

## Principio Ceteris Paribus

Todas las interpretaciones del modelo se realizan bajo el supuesto *ceteris paribus*, es decir:

> *El efecto de una variable se analiza manteniendo constantes todas las demás variables del modelo.*

Esto permite aislar asociaciones, pero **no establecer relaciones causales**.

---

## Herramientas utilizadas

- `Python con Colab` 
- `R / RStudio`
- `tidyverse`
- `glm()` para regresión logística
- `broom` para limpieza de resultados
- `ggplot2` / `plotly` para visualización

---

## Posibles Extensiones del estudio

- Inclusión de efectos marginales promedio.
- Modelos con interacciones.
- Segmentación por tipo de cliente.
- Validación cruzada del modelo.
- Comparación con modelos de machine learning.

---
## Clases Challenger de Alura Latam
**Ricardo Patricio**    

---

## Licencia

Este proyecto se distribuye bajo licencia Alura Latam - Oracle.  
Uso libre con fines académicos y profesionales, citando la fuente.



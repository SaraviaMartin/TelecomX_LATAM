# 📊 Análisis Exploratorio y Proceso ETL – Churn de Clientes | Telecom X

Este repositorio documenta el desarrollo completo del proceso **ETL (Extracción, Transformación y Carga)** y el **Análisis Exploratorio de Datos (EDA)** aplicado al problema de evasión de clientes en la empresa ficticia **Telecom X**.

---

## 🔄 Proceso ETL

### 1. 📥 Extracción
Los datos fueron obtenidos directamente desde un archivo JSON alojado en un repositorio remoto de GitHub.

- **Fuente de datos**:  
  [TelecomX_Data.json](https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/main/TelecomX_Data.json)

### 2. 🧹 Transformación

Se realizaron las siguientes tareas de procesamiento:

- **Normalización de estructuras anidadas**:  
  - Columnas como `customer`, `phone`, `account`, `internet` fueron desanidadas y reestructuradas.

- **Limpieza de datos**:
  - Conversión de tipos de datos (`object` a `float`, entre otros).
  - Eliminación de columnas redundantes o irrelevantes.
  - Detección y tratamiento de valores nulos y duplicados.

- **Creación y transformación de variables**:
  - Nuevas variables derivadas como:  
    `DailyCharges = ChargesMonthly / 30`
  - Estandarización de columnas categóricas:
    - "Yes"/"No" → `1`/`0`
    - Contratos: `"Month-to-month"` → `1`, `"One year"` → `2`, `"Two year"` → `3`
  - Limpieza y unificación de la columna `Churn`.

### 3. 💾 Carga

El DataFrame final fue procesado y almacenado en formato JSON para uso posterior:

- **Archivo generado**: `Churn_de_Clientes.json`

---

## 📈 Análisis Exploratorio (EDA)

### 🔘 Distribución de Churn

Se visualizó la proporción de clientes que abandonaron el servicio frente a los que permanecen mediante un gráfico de torta.

### 🔥 Análisis cruzado por categoría

Se analizó la evasión en función de variables categóricas clave, como:

- Género y tipo de contrato (eje Y)
- Tipo de servicio de internet (eje X)

Se utilizó un heatmap estilo "semáforo" para destacar zonas con mayor y menor incidencia de churn:

- 🔴 Rojo → Alta tasa de evasión  
- 🟢 Verde → Baja tasa de evasión

### 📊 Variables numéricas

Mediante boxplots, se compararon valores de churn frente a:

- **ChargesMonthly**: Clientes que se dieron de baja tienden a tener mayores costos mensuales.
- **Tenure**: Los clientes que permanecen tienen, en general, mayor antigüedad.

---

## 📌 Principales Conclusiones

- **Mayor riesgo de churn** en clientes con contratos mensuales, altas tarifas y baja antigüedad.
- **Servicios adicionales** como `TechSupport` y `OnlineSecurity` parecen tener un rol protector ante la evasión.
- Estos hallazgos sientan las bases para el desarrollo de:
  - Modelos de predicción de churn.
  - Estrategias de fidelización basadas en datos.

---

## 📁 Archivos Incluidos

- `Churn_de_Clientes.json` → Dataset limpio y transformado.
- Visualizaciones generadas en el análisis exploratorio (mostradas dentro del notebook).

---

## 👤 Autor

Desarrollado por: Juan Martín Saravia  


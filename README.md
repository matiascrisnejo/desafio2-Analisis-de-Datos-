# 📊 Proceso ETL y Análisis Exploratorio – Churn de Clientes | Telecom X

Este repositorio contiene el desarrollo completo del proceso ETL (Extracción, Transformación y Carga) y el análisis exploratorio de los datos de churn de clientes de la empresa ficticia *Telecom X*.

---

## 🔄 Proceso ETL

### 1. 📥 Extracción

- Lectura directa del archivo `.json` desde un repositorio remoto:
  - **URL**:  
    `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json`

---

### 2. 🧹 Transformación

#### 🔄 Normalización de estructuras anidadas:

- Columnas: `customer`, `phone`, `account`, `internet`.

#### 🧼 Limpieza de datos:

- Conversión de tipos (`object` → `float`).
- Eliminación de columnas redundantes.
- Verificación y tratamiento de valores nulos y duplicados.

#### 🏷️ Renombramiento y creación de nuevas variables:

- Ejemplo:  
  `DailyCharges = ChargesMonthly / 30`
#### 🏷️ Conversión de variables categóricas a binarias:

- Ejemplo: `Yes`/`No` -> `1`/ `0`

#### 🏷️ Estandarización de valores:
- Limpieza y homogeneización de la columna `Churn`.
- Mapeo numérico para `Contract`:
- - `"Month-to-month"` → `1`, `"One year"` → `2`, `"Two year"` → `3`

### 3. 🧹 Carga
- El DataFrame final procesado se guarda como: `Churn_de_Clientes.json`

---

## 🔍 Análisis Exploratorio

### ⚪ Proporción de churn

- Gráfico tipo torta que muestra la proporción entre:
  - Clientes que permanecen
  - Clientes que se dieron de baja

---

### 🔥 Heatmap de características categóricas

- Análisis cruzado de:
  - **Eje Y**: Género + Tipo de contrato
  - **Eje X**: Tipo de servicio de internet

- Visualización tipo semáforo:
  - 🟢 Verde → baja evasión
  - 🔴 Rojo → alta evasión

---

### 📊 Variables numéricas

#### 📦 Boxplots comparativos para analizar:

- `ChargesMonthly`: Clientes que se dieron de baja tienen gastos más altos.
- `Tenure`: Clientes que permanecen tienen mayor tiempo de permanencia.


---

## 📌 Conclusiones

- **Contratos a corto plazo**, **gastos mensuales elevados** y **baja antigüedad** están correlacionados con la evasión.
- Servicios de internet y soporte (como `TechSupport` y `OnlineSecurity`) influyen significativamente.
- Este análisis exploratorio permite establecer la base para:
  - Modelos predictivos de churn
  - Estrategias de retención de clientes

---

## 📁 Archivos Generados

- `Churn_de_Clientes.json` → Dataset procesado.
- `grafico_churn.png` → Gráfico de torta de churn.
- Gráficos de análisis visual se muestran inline en notebooks (no se exportan todos).

---

## 📌 Autor

Desarrollado por: **Matias Miguel Crisnejo**  
Repositorio base: [https://github.com/matiascrisnejo/desafio2-Analisis-de-Datos-](https://github.com/matiascrisnejo/desafio2-Analisis-de-Datos-)

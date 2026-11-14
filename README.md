# 🚚 Pipeline ETL y Limpieza de Datos Logísticos en Python

Proyecto de ingeniería y limpieza de datos (ETL) desarrollado en **Python** utilizando **Pandas** y **NumPy**. El objetivo es transformar un dataset crudo de operaciones logísticas (`pedidos_logistica_raw.csv`) en un activo de datos limpio, estandarizado y listo para análisis de Business Intelligence.

## 🛠️ Problemas Detectados y Soluciones Aplicadas

* **Limpieza Financiera:** Eliminación de símbolos monetarios (`$`) y separadores de miles para convertir la columna `monto_venta` de texto a formato numérico (`float64`).
* **Reglas de Negocio y Anomalías:** Identificación de montos negativos. En lugar de eliminarlos y perder trazabilidad contable, se aislaron en `ingreso_total` (valor `0`) y se clasificaron mediante la columna `tipo_movimiento` (*Venta* vs. *Devolución / Ajuste*).
* **Normalización de Texto:** Estandarización de nombres de clientes (`.title()`) y unificación de regiones mediante diccionarios de mapeo (ej. `rm`, `metropolitana` $\rightarrow$ *Región Metropolitana*; corrección ortográfica de *Valparaíso*).
* **Procesamiento de Fechas y KPIs:** Resolución de formatos de fecha mixtos (`YYYY-MM-DD` y `DD/MM/YYYY`) aplicando `format="mixed"` y `dayfirst=True` para calcular el tiempo real de despacho (`dias_entrega` / Lead Time).

## 📁 Estructura del Repositorio

* `etl_pedidos_logistica.ipynb`: Notebook con el flujo completo paso a paso.
* `pedidos_logistica_raw.csv`: Dataset original con datos sucios.
* `pedidos_logistica_limpios.csv`: Dataset procesado y listo para consumo analítico.

## 💻 Tecnologías Utilizadas

* Python 3
* Pandas
* NumPy
* Jupyter Notebook

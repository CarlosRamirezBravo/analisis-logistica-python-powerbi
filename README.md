# 🚚 Pipeline ETL y Análisis de Datos Logísticos en Python

Proyecto de limpieza, transformación y análisis de datos logísticos desarrollado en **Python** con **Pandas** y **NumPy**. El objetivo es convertir un dataset crudo de 500 pedidos (`pedidos_logistica_raw.csv`) en un dataset limpio y estandarizado (`pedidos_logistica_limpios.csv`) listo para análisis comercial y operativo.

## 🛠️ Problemas Detectados y Soluciones Aplicadas
- **Limpieza Financiera:** Normalización de `monto_venta` eliminando símbolos `$` y separadores de miles sin alterar valores flotantes con `.0` ni perder nulos reales (`float64`).
- **Reglas de Negocio y Anomalías:** Clasificación en `tipo_movimiento` (`Venta` vs. `Devolución / Ajuste`) y cálculo de `ingreso_total` (`0` en montos no positivos o devoluciones) para mantener trazabilidad contable.
- **Normalización de Texto:** Estandarización de `cliente`, `categoria`, `region` y `estado_entrega` (eliminación de espacios, unificación de mayúsculas/minúsculas, mapeo de variantes como `rm` y `metropolitana` a `Región Metropolitana` y corrección de `Valparaíso`).
- **Procesamiento de Fechas y KPIs:** Parseo de fechas mixtas (`YYYY-MM-DD` y `DD/MM/YYYY`) con `format="mixed"` y `dayfirst=True`, cálculo de `dias_entrega` y creación de `dias_entrega_limpio` excluyendo valores negativos (`< 0`).

## 📁 Estructura del Repositorio
- `01_etl_pedidos_logistica.ipynb`: Diagnóstico inicial, limpieza, reglas de negocio y exportación del CSV limpio.
- `02_analisis_pedidos_logistica.ipynb`: Cálculo de ingresos, conteo de movimientos y agrupaciones por región y categoría.
- `pedidos_logistica_raw.csv`: Dataset original sin procesar.
- `pedidos_logistica_limpios.csv`: Dataset procesado y listo para análisis.

## 💻 Tecnologías Utilizadas
- Python 3
- Pandas
- NumPy
- Jupyter Notebook / JupyterLab

### ¡Hola! 👋 Soy Paola Montesinos

**Account Manager B2B y Consultora Comercial especializada en entornos tecnológicos y SaaS**, con experiencia en gestión de carteras de clientes, estrategia comercial y optimización de procesos. Actualmente ampliando mi perfil técnico como **Data Analyst** en la Fundación Somos F5.

[![Python](https://img.shields.io/badge/Python-3.11-blue)](https://img.shields.io/badge/Python-3.11-blue)
[![Estado](https://img.shields.io/badge/Estado-Activa-success)](https://img.shields.io/badge/Estado-Activa-success)

---

## 📌 Índice
* [Sobre Mí y Contacto](#sobre-mí-y-contacto)
* [Proyecto Destacado: EcoShop (EDA)](#proyecto-destacado-ecoshop-eda)
* [Stack Tecnológico y Competencias](#stack-tecnológico-y-competencias)

---

## 🌐 Sobre Mí y Contacto

* **LinkedIn:** [www.linkedin.com/in/paolamontesinos](https://www.linkedin.com/in/paolamontesinos)
* **Portafolio / Casos de Estudio:** [Enlace a tu Portafolio]
* **Formación Actual:** 
  * **Data Analyst Bootcamp** | Fundación Somos F5 (Python, SQL, Git, Jupyter Notebooks)
  * **Máster en Dirección Comercial y Ventas** | Formato Educativo Escuela de Negocios Barcelona

---

## 🚀 Proyecto Destacado: Análisis de Ventas y Retención - EcoShop

Este proyecto presenta un Análisis Exploratorio de Datos (EDA) sobre el comportamiento de compra de los usuarios de EcoShop, con el objetivo de *identificar oportunidades para reducir la tasa de abandono* durante el periodo *Enero 2025 - Diciembre 2025*.

### 💡 Resumen Ejecutivo y Hallazgos
> **Insight principal:** Los clientes que realizan una segunda compra dentro de los primeros 30 días tienen un *LTV (Lifetime Value) 3 veces superior al resto*.

* **Estacionalidad marcada:** El pico de ventas ocurre en noviembre (+42% respecto a la media anual) impulsado por el Black Friday.
* **Fricción en móviles:** La columna `device_type` reveló que el 70% del tráfico viene de `mobile`, pero la conversión es un 1.8% menor que en `desktop`.
* **Categoría estrella:** Los productos de la categoría `Hogar_Sostenible` concentran el mayor margen de beneficio neto.

### 📊 Tabla de KPIs
| Métrica | 2024 | 2025 | Variación |
| :--- | :---: | :---: | ---: |
| Ingresos Totales | \$450,000[cite: 3] | \$585,000[cite: 3] | +30.0% |
| Ticket Promedio | \$42.50[cite: 3] | \$46.80[cite: 3] | +10.1%|
| Tasa de Conversión | 2.4%[cite: 3] | 2.9%[cite: 3] | +0.5 pp |
| Tasa de Abandono (Churn) | 18.0%[cite: 3] | 14.5%

### 🛠️ Metodología y Flujo de Trabajo
1. **Extracción:** Conexión a base de datos PostgreSQL mediante SQLAlchemy.
2. **Limpieza:** Tratamiento de valores nulos en `fecha_entrega` y estandarización de categorías.
3. **Análisis:** Segmentación de clientes mediante análisis RFM (Recencia, Frecuencia, Valor Monetario).
4. **Visualización:** Creación de dashboard interactivo en Power BI y gráficos estáticos con Seaborn.

**Estado del proyecto:**
* [x] Limpieza y validación del dataset
* [x] Análisis exploratorio y pruebas de hipótesis
* [ ] Automatización del pipeline semanal con Airflow
* [ ] Modelo predictivo de *churn*

### 💻 Código Destacado
Consulta SQL utilizada para calcular el ticket promedio por categoría:

```sql
SELECT 
    categoria,
    COUNT(DISTINCT order_id) AS total_pedidos,
    ROUND(AVG(total_venta), 2) AS ticket_promedio
FROM ventas_2025
WHERE estado_pedido = 'Completado'
GROUP BY categoria
ORDER BY ticket_promedio DESC;

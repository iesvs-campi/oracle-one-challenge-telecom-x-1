# Challenge: Telecom X - Análisis de Abandono

<p align="center">
  <img src="https://img.shields.io/badge/STATUS-Completado-brightgreen" alt="Estado del Proyecto">
  <img src="https://img.shields.io/badge/Tecnología-Python-blue" alt="Tecnología Python">
  <img src="https://img.shields.io/badge/Entorno-Google%20Colab-yellow" alt="Entorno Google Colab">
  <img src="https://img.shields.io/badge/Bibliotecas-Pandas%20%7C%20Seaborn%20%7C%20Numpy-red" alt="Bibliotecas">
</p>

---

### Tabla de Contenidos
1. [Descripción del Proyecto](#descripción-del-proyecto)
2. [Metodología y Tratamiento de Datos](#metodología-y-tratamiento-de-datos)
3. [Análisis de Factores de Abandono](#análisis-de-factores-de-abandono)
    * [1. Factor Contractual: Tipo de Contrato](#1-factor-contractual-tipo-de-contrato)
    * [2. Factor Tecnológico: Servicio de Internet](#2-factor-tecnológico-servicio-de-internet)
    * [3. Factor Temporal: Antigüedad del Cliente](#3-factor-temporal-antigüedad-del-cliente)
    * [4. Factor Operativo: Métodos de Pago](#4-factor-operativo-métodos-de-pago)
4. [Visualización de Resultados](#visualización-de-resultados)
5. [Conclusión y Recomendación](#conclusión-y-recomendación)
6. [Estructura del Proyecto](#estructura-del-proyecto)
7. [Tecnologías y Dependencias](#tecnologías-y-dependencias)
8. [Cómo Ejecutar el Proyecto](#cómo-ejecutar-el-proyecto)

---

### Descripción del Proyecto

Este proyecto es parte del **Programa ONE - Oracle Next Education** en colaboración con Alura, desarrollado como un **Challenge de Data Science** para aplicar habilidades de limpieza, tratamiento y análisis exploratorio de datos (EDA) utilizando Python.

El objetivo principal es identificar los motivos por los cuales los clientes de la empresa **Telecom X** están cancelando sus servicios (abandono). El análisis busca transformar datos brutos en información estratégica que permita a la gerencia implementar medidas de retención efectivas y mejorar la sostenibilidad del negocio.

---

### Metodología y Tratamiento de Datos

Se realizó un proceso de limpieza profundo para garantizar la integridad de los resultados:
* **Estandarización:** Traducción de las 21 columnas y categorías del dataset al español.
* **Limpieza de Nulos:** Identificación de espacios vacíos en las columnas `cobro_total` y `abandono` mediante expresiones regulares y eliminación de registros incompletos.
* **Casting:** Se ajustó la columna `cobro_total` a formato flotante (`float64`), transformándola de un tipo objeto a numérico para permitir el análisis estadístico.
* **Validación:** Verificación de consistencia lógica entre servicios contratados y confirmación de 0 registros duplicados.


---

### Análisis de Factores de Abandono

#### 1. Factor Contractual: Tipo de Contrato
Se analizó la relación entre la duración del compromiso y la tasa de abandono.

| Tipo de Contrato | Tasa de Abandono | Impacto |
| :--- | :--- | :--- |
| **Mes a mes** | 42.71% | **ALTO RIESGO** |
| **Un año** | 11.27% | Medio |
| **Dos años** | 2.85% | Mínimo |

* **Hallazgo clave:** La modalidad de contrato mensual es el principal disparador de la evasión de clientes.

#### 2. Factor Tecnológico: Servicio de Internet
Se examinó la fidelidad según la tecnología de conexión utilizada.

* **Hallazgo clave:** Los usuarios de **Fibra óptica** presentan una tasa de abandono del **41.89%**, cifra significativamente superior al 18.99% observado en usuarios de DSL. Esto sugiere problemas en la relación precio-calidad de este segmento.

#### 3. Factor Temporal: Antigüedad del Cliente
Se estudió la permanencia de los clientes antes de abandonar el servicio.

* **Hallazgo clave:** El riesgo de abandono es crítico al inicio de la relación. Se identifica un **pico de abandonos en el mes 1**, con una tendencia decreciente a medida que aumenta la antigüedad del cliente.

#### 4. Factor Operativo: Métodos de Pago
Se comparó el impacto de los pagos automáticos frente a los manuales.

* **Hallazgo clave:** Los métodos de pago manuales, específicamente el **Cheque electrónico**, muestran una correlación directa con el abandono debido a la fricción que genera la gestión manual del pago cada mes.

---

### Visualización de Resultados

A continuación, se presentan los gráficos clave generados durante el análisis:

#### Impacto Total del Abandono
Muestra la proporción general de clientes que han dejado la empresa frente a los que permanecen.
![Gráfico: Impacto total del abandono](https://raw.githubusercontent.com/iesvs-campi/oracle-one-challenge-telecom-x-1/main/plots/impacto_total_churn.png)

#### Abandono por Tipo de Contrato
Ilustra cómo el compromiso a largo plazo reduce drásticamente la probabilidad de fuga.
![Gráfico: Relación entre el tipo de contrato y el abandono](https://raw.githubusercontent.com/iesvs-campi/oracle-one-challenge-telecom-x-1/main/plots/impacto_tipo_contrato_churn.png)

#### Tasa de Abandono por Tecnología de Internet
Destaca la vulnerabilidad crítica existente en el segmento de usuarios de fibra óptica.
![Gráfico: Tasa de abandono por tecnología de internet](https://raw.githubusercontent.com/iesvs-campi/oracle-one-challenge-telecom-x-1/main/plots/impacto_tipo_conexion_churn.png)

#### Comportamiento Temporal del Abandono
Visualización de la tendencia de abandono según los meses de antigüedad, destacando el pico inicial.
![Gráfico: Distribución de cobro mensual vs abandono](https://raw.githubusercontent.com/iesvs-campi/oracle-one-challenge-telecom-x-1/main/plots/impacto_mensual_churn.png)

#### Influencia del Método de Pago
Comparativa de la tasa de abandono según la modalidad de pago (Manual vs. Automático).
![Gráfico: Impacto del método de pago en el abandono](https://raw.githubusercontent.com/iesvs-campi/oracle-one-challenge-telecom-x-1/main/plots/impacto_metodo_pago_churn.png)

---

### Conclusión y Recomendación

El abandono en Telecom X está impulsado principalmente por la falta de compromiso contractual y la inestabilidad en los primeros meses de servicio.

| Estrategia Recomendada | Justificación |
| :--- | :--- |
| **Migración Contractual** | Incentivar el paso de contratos mensuales a anuales para reducir el riesgo inmediato. |
| **Plan de Bienvenida** | Reforzar la atención y soporte durante el **Mes 1** para superar el pico crítico de fuga. |
| **Automatización de Pagos** | Promover el registro de tarjetas de crédito o transferencias para reducir la fricción del pago manual. |

---

### Estructura del Proyecto

* **`telecom_x.ipynb`**: Notebook con el código completo de limpieza, traducción y análisis exploratorio.
* **`plots/`**: Carpeta con las visualizaciones generadas para el informe (`.png`).
* **`README.md`**: Descripción del proyecto y resumen de hallazgos.

### Tecnologías y Dependencias

* **Python**
* **Pandas / Numpy**: Manipulación y tratamiento de datos.
* **Seaborn / Matplotlib**: Visualización estadística.
* **Requests**: Para la extracción automatizada del dataset vía API/URL.
* **Google Colab**: Entorno de ejecución.

### Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
    ```bash
    git clone https://github.com/iesvs-campi/oracle-one-challenge-telecom-x-1.git
    cd oracle-one-challenge-telecom-x-1
    ```

2. **Ejecución:**
    * Abre el archivo `telecom_x.ipynb` en Google Colab o Jupyter Notebook.
    * Ejecuta las celdas secuencialmente. El notebook está configurado para **extraer automáticamente los datos** desde la fuente remota de GitHub, por lo que no es necesario cargar archivos externos manualmente.

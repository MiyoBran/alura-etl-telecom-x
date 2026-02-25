# 📄 Informe Final: Análisis de Evasión de Clientes (Churn)
**Proyecto:** Alura
 
**Autor:** Miyen (Lic. en Informática - UNPSJB)

---

## 1. Introducción
El objetivo de este análisis es identificar los factores que impulsan la **evasión de clientes (Churn)** en la empresa de servicios Telecom X. En un mercado altamente competitivo, retener a un cliente existente es significativamente más rentable que adquirir uno nuevo. Este informe busca transformar datos crudos en **insights estratégicos** para reducir la pérdida de clientes y optimizar la rentabilidad de la PyME.

## 2. Limpieza y Tratamiento de Datos
Para garantizar la calidad del análisis, se llevaron a cabo los siguientes pasos técnicos:
* **Importación y Aplanamiento:** Los datos se extrajeron de una estructura anidada (JSON/Diccionarios) y se transformaron en un DataFrame plano.
* **Traducción y Binarización:** Se estandarizaron las columnas al español y se convirtieron las variables categóricas (Sí/No) a valores booleanos (1/0) para permitir el procesamiento estadístico.
* **Ingeniería de Atributos (Feature Engineering):**
    * Se creó la métrica **Cuentas_Diarias** para entender el impacto del gasto micro-diario.
    * Se desarrollaron los indicadores **Puntaje_Inseguro** y **Total_Servicios** para validar hipótesis sobre la lealtad técnica del cliente.
* **Tratamiento de Nulos:** Se identificaron y corrigieron valores nulos en la columna `Cargo_Total`.

## 3. Análisis Exploratorio de Datos (EDA)

### 3.1. Estado Actual de la Cartera
La empresa presenta una tasa de evasión del **26.5%**. Aunque la mayoría de los clientes permanecen, el volumen de fugas (1,869 clientes) requiere atención inmediata.

![Distribución General](https://raw.githubusercontent.com/MiyoBran/alura-etl-telecom-x/main/distribucion_evasion.png)
*[distribucion_evasion.png: Gráfico de barras y anillo mostrando la proporción de clientes retenidos vs fugados]*

### 3.2. Identificación de Factores Críticos
El análisis reveló que el **Tipo de Contrato** es el predictor más fuerte. Los clientes con contratos mensuales tienen un riesgo de fuga del **42.7%**, evidenciando una falta de compromiso a largo plazo.

![Análisis por Contrato](https://raw.githubusercontent.com/MiyoBran/alura-etl-telecom-x/main/analisis_contrato.png)
*[analisis_contrato.png: Comparativa de volumen y tasa de riesgo según la duración del contrato]*

Asimismo, el **Método de Pago** influye drásticamente: los clientes que pagan mediante "Cheque Electrónico" tienen una tendencia a la evasión mucho mayor que aquellos con débito automático.

![Análisis por Método de Pago](https://raw.githubusercontent.com/MiyoBran/alura-etl-telecom-x/main/analisis_pago.png)
*[analisis_pago.png: Gráfico de barras mostrando el riesgo relativo según el medio de pago utilizado]*

### 3.3. Comportamiento Numérico y Temporicidad
Se detectó un "punto crítico" de deserción entre los **0 y 10 meses** de antigüedad. Si un cliente supera el primer año, la probabilidad de fuga cae drásticamente. Respecto al costo, los clientes con cargos superiores a **$70** mensuales presentan la mayor inestabilidad.

![Densidad Numérica](https://raw.githubusercontent.com/MiyoBran/alura-etl-telecom-x/main/densidad_numerica.png)
*[densidad_numerica.png: Gráficos KDE que comparan la distribución de meses de contrato y cargos mensuales entre clientes fugados y retenidos]*

## 4. Conclusiones e Insights
* **La Antigüedad es el Ancla:** Existe una correlación negativa fuerte (-0.35) entre los meses de contrato y la evasión.
* **Hipótesis del "Inseguro Digital":** Se confirmó que la falta de servicios de seguridad y soporte técnico correlaciona positivamente con la fuga (+0.17). Los clientes con menor "vínculo técnico" se van más fácil.
* **Impacto del Precio:** El costo diario percibido (`Cuentas_Diarias`) y el cargo mensual actúan como aceleradores de la evasión cuando superan ciertos umbrales psicológicos.

![Correlación e Influencia](https://raw.githubusercontent.com/MiyoBran/alura-etl-telecom-x/main/correlacion_final.png) 
*[correlacion_final.png: Mapa de calor global y ranking de las variables con mayor impacto matemático sobre el Churn]*

## 5. Recomendaciones Estratégicas
1. **Plan de Fidelización Temprana:** Implementar incentivos automáticos (descuentos o servicios extra) durante los primeros 6 meses de vida del cliente.
2. **Migración Contractual:** Diseñar campañas para convertir clientes "Mes a mes" a planes anuales, enfocándose en aquellos que utilizan "Cheque Electrónico".
3. **Estrategia de Seguridad Online:** Ofrecer el paquete de seguridad y soporte técnico como un beneficio bonificado para aumentar el "costo de salida" y reducir el `Puntaje_Inseguro`.
4. **Optimización de Métodos de Pago:** Incentivar el registro de tarjetas de crédito o débito automático para reducir la fricción del pago manual que facilita la evasión.


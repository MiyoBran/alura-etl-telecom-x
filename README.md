# 🚀 Gestión PyME Inteligente: Análisis de Evasión (Churn)

Este proyecto nace como una solución de analítica avanzada para **Telecom X**, enfocada en identificar los factores críticos que provocan la pérdida de clientes. A través de un enfoque de **Data Science**, transformamos datos crudos en estrategias de retención accionables.

---

## 📌 Objetivo del Proyecto
El propósito principal es predecir la probabilidad de evasión de clientes utilizando técnicas de análisis exploratorio (EDA) y preparación de datos para Machine Learning. El foco está en entender el **"por qué"** detrás de los números para ofrecer recomendaciones gerenciales sólidas.

## 🛠️ Tecnologías y Herramientas
* **Lenguaje:** Python 3.x
* **Librerías principales:** Pandas, NumPy, Seaborn, Matplotlib
* **Entorno de desarrollo:** Eclipse 2025 / IntelliJ IDEA / Google Colab
* **Metodología:** Clean Code y comentarios didácticos para asegurar la mantenibilidad.

## 📊 Hallazgos Clave (Insights)
Tras auditar el dataset, identificamos tres pilares de comportamiento:
1. **El Factor Tiempo:** Los clientes en sus primeros 10 meses tienen la tasa de fuga más alta. La antigüedad tiene una correlación negativa de **-0.35** con la evasión.
2. **Hipótesis del "Inseguro Digital":** Validamos que la falta de servicios de seguridad y soporte técnico incrementa el riesgo de abandono ($r = 0.17$).
3. **Umbral de Precio:** El riesgo de fuga se dispara cuando los cargos mensuales superan los **$70**, sugiriendo una sensibilidad al precio en el segmento premium.

## 📂 Estructura del Repositorio
* `data/`: Contiene el dataset original (JSON/CSV).
* `notebooks/`: Proceso completo de limpieza, EDA y visualización.
* `output/`: Reportes ejecutivos y gráficas de correlación exportadas.
* `src/`: Funciones modulares para auditoría de variables.

## 🚀 Instalación y Uso
1. Clonar el repositorio:
   ```bash
   git clone [https://github.com/tu-usuario/gestion-pyme-inteligente.git](https://github.com/tu-usuario/gestion-pyme-inteligente.git)
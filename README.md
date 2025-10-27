<p align="center">
  <img src="telecom.jpg" alt="Telecom Analysis Banner" width="800">
</p>

# 📞 Telecom Inefficiency Analysis

## 🎯 Descripción del Proyecto
Este proyecto tiene como objetivo **identificar operadores con desempeño ineficiente** dentro de una compañía de telecomunicaciones.  
El análisis permite detectar oportunidades de mejora en **capacitación**, **redistribución de carga de trabajo** y **dimensionamiento de plantilla**.

El trabajo combina **análisis exploratorio de datos (EDA)** con la creación de un **dashboard interactivo en Tableau**, facilitando la toma de decisiones estratégicas basadas en evidencia.

🔗 **Dashboard en Tableau Public:**  
[Dashboard Call Me Maybe](https://public.tableau.com/app/profile/andres.esquivel7728/viz/Dashboard-LlamadasCallMeMaybe/DashboardLlamadasCallMeMaybe?publish=yes)

📂 **Carpeta con datos y entregables:**  
[Google Drive - Telecom Analysis](https://drive.google.com/drive/folders/10AzsaG4r9RNzZtQdPYJ-TR46czblzL8c?usp=sharing)

---

## 🧩 Objetivo General
Detectar operadores con desempeño por debajo del promedio para respaldar decisiones de:
- **Capacitación personalizada**
- **Reasignación de carga de llamadas**
- **Optimización de recursos humanos**

---

## 🚨 Criterios de Ineficiencia
Los indicadores considerados para evaluar el desempeño son:

1. **Tasa alta de llamadas entrantes perdidas**  
   - Internas o externas.  
   - Señal de falta de atención o sobrecarga.

2. **Tiempo de espera elevado**  
   - Calculado como:  
     ```python
     wait_time = total_call_duration - call_duration
     ```

3. **Bajo volumen de llamadas salientes**  
   - En roles que requieren tareas outbound.

---

## 📚 Datos Utilizados

### Archivos
- `telecom_dataset_us.csv`: métricas diarias por operador (`user_id`, `operator_id`, `date`).  
- `telecom_clients_us.csv`: información del cliente y su plan tarifario (`tariff_plan`, `date_start`).

### Diccionario de columnas
| Columna | Descripción |
|:--|:--|
| `user_id` | Identificador único del cliente |
| `date` | Fecha del registro |
| `direction` | Tipo de llamada (`in` = entrante, `out` = saliente) |
| `internal` | `True` si la llamada fue interna |
| `operator_id` | Identificador del operador |
| `is_missed_call` | `True` si la llamada entrante se perdió |
| `calls_count` | Número de llamadas en el registro |
| `call_duration` | Duración efectiva de conversación (segundos) |
| `total_call_duration` | Duración total de la llamada, incluyendo espera |
| `tariff_plan` | Plan tarifario del cliente |
| `date_start` | Fecha de alta del cliente |

---

## 🔍 Metodología

1. **Carga y validación de datos**  
   - Comprobación de nulos, duplicados y rangos de fechas.  
   - Unificación de estructuras y tipos de datos.  

2. **Transformación y limpieza**  
   - Creación de métricas derivadas: `wait_time`, `missed_call_rate`, `outbound_ratio`.  
   - Filtrado de valores atípicos y registros inconsistentes.  

3. **Análisis exploratorio (EDA)**  
   - Tendencias de llamadas por operador, día y tipo.  
   - Comparación entre llamadas internas vs. externas.  
   - Identificación de los operadores con mayor pérdida de llamadas y tiempos de espera.  

4. **Visualización interactiva (Tableau)**  
   - Se construyó un dashboard con filtros por operador, cliente y tipo de llamada.  
   - Permite observar desempeño individual y colectivo.  

---

## 📈 Resultados Destacados
- Los **operadores con mayor tasa de llamadas perdidas** también mostraron **tiempos de espera más altos**, lo que sugiere sobrecarga o deficiencia operativa.  
- Algunos operadores con bajo número de llamadas salientes pertenecen a clientes con planes más básicos, lo que resalta la **influencia del tipo de cliente en el desempeño**.  
- La correlación entre **tiempo de espera** y **duración total de llamada** permitió identificar **ineficiencias estructurales** en la distribución del tráfico.  
- El dashboard en Tableau facilita **comparaciones dinámicas** y decisiones basadas en evidencia.

---

## 🧠 Conclusiones
- El análisis permitió identificar patrones de ineficiencia en tiempo real y validar la necesidad de **rediseñar la carga operativa**.  
- Se recomienda implementar un sistema de **alertas tempranas** para operadores con desempeño por debajo del umbral.  
- Las visualizaciones ayudan a priorizar **entrenamientos específicos por grupo** y evaluar su impacto en la mejora del servicio.

---

## ⚙️ Tecnologías Utilizadas
- **Python:** pandas, numpy, matplotlib, seaborn  
- **Visualización:** Tableau Public  
- **Entorno:** Jupyter Notebook  

---

## 📂 Estructura del Repositorio
```
📁 Telecom-Inefficiency-Analysis/
│
├── data/                       # Archivos CSV con datos de llamadas
├── Telecom Inefficiency Analysis.ipynb   # Notebook principal
├── README.md                   # Descripción del proyecto
└── images/                     # Visualizaciones o gráficos complementarios
```

---

## 👤 Autor
**Andrés Esquivel Díaz**  
📍 *Data Analyst | Python · SQL · Tableau · Power BI*  
🔗 [LinkedIn](https://www.linkedin.com/in/andres-esquivel-diaz-08691337) · [GitHub](https://github.com/aesquivel91)

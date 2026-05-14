# S7-Project-ConnectaTel
# 📊 ConnectaTel - Análisis de Clientes y Patrones de Uso

## 📌 Descripción del Proyecto

Este proyecto tiene como objetivo analizar el comportamiento de los usuarios de **ConnectaTel**, una empresa de telecomunicaciones, mediante técnicas de limpieza, exploración y segmentación de datos.

El análisis se enfoca en:

* Detectar problemas de calidad de datos.
* Analizar patrones de uso de llamadas y mensajes.
* Identificar segmentos de clientes según edad y nivel de uso.
* Detectar outliers y comportamiento extremo.
* Generar recomendaciones de negocio basadas en los hallazgos.

---

# 🎯 Objetivos

* Realizar limpieza y validación de datos.
* Analizar variables numéricas y categóricas.
* Identificar segmentos de clientes.
* Evaluar patrones de uso según el tipo de plan.
* Detectar valores atípicos.
* Traducir hallazgos técnicos en insights accionables para negocio.

---

# 🛠️ Tecnologías Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

# 🧹 Limpieza de Datos

Durante el proceso de preparación de datos se identificaron y corrigieron varios problemas:

## ⚠️ Problemas encontrados

* Valores faltantes en variables como `duration` y `length`.
* Valores inválidos:

  * `-999` en `age`
  * `?` en `city`
  * Fechas futuras en `reg_date`
* Datos faltantes tipo MAR (*Missing At Random*) en `duration`.

## 🔧 Acciones realizadas

* Conversión de tipos de datos.
* Reemplazo de sentinels por valores nulos.
* Imputación con mediana y moda cuando fue necesario.
* Validación de fechas.
* Creación de variables auxiliares.

---

# 📊 Análisis Exploratorio (EDA)

Se realizó un análisis descriptivo de las principales variables:

## Variables analizadas

* Edad (`age`)
* Cantidad de mensajes (`cant_mensajes`)
* Cantidad de llamadas (`cant_llamadas`)
* Minutos de llamadas (`cant_minutos_llamada`)
* Tipo de plan (`plan`)

## Principales hallazgos

* Las variables de uso presentan distribuciones sesgadas a la derecha.
* Existen usuarios con comportamiento extremo (power users).
* Los usuarios Premium presentan mayor actividad promedio.

---

# 👥 Segmentación de Usuarios

## Segmentación por edad

Se creó la variable `grupo_edad`:

| Grupo        | Condición |
| ------------ | --------- |
| Joven        | age < 30  |
| Adulto       | age < 60  |
| Adulto Mayor | age >= 60 |

---

## Segmentación por nivel de uso

Se creó la variable `grupo_uso`:

| Grupo     | Condición                     |
| --------- | ----------------------------- |
| Bajo uso  | llamadas < 5 y mensajes < 5   |
| Uso medio | llamadas < 10 y mensajes < 10 |
| Alto uso  | resto de casos                |

---

# 📈 Visualizaciones

Se realizaron:

* Histogramas
* Boxplots
* Distribuciones por plan
* Comparaciones entre segmentos

Estas visualizaciones permitieron detectar:

* Distribuciones sesgadas.
* Outliers.
* Diferencias entre usuarios Básico y Premium.

---

# ⚠️ Detección de Outliers

Se utilizó el método IQR para identificar valores atípicos en:

* `age`
* `cant_mensajes`
* `cant_llamadas`
* `cant_minutos_llamada`

## Hallazgos

* Los outliers se concentran principalmente en variables de uso.
* Estos usuarios representan clientes altamente activos.
* No fueron eliminados automáticamente, ya que podrían representar segmentos estratégicos para el negocio.

---

# 💡 Conclusiones de Negocio

## Hallazgos principales

* Los usuarios jóvenes presentan mayor actividad digital.
* Los usuarios Premium muestran mayor consumo promedio.
* Existe un pequeño grupo de usuarios intensivos que concentra gran parte del uso.

## Recomendaciones

* Crear planes diferenciados según nivel de uso.
* Ofrecer beneficios premium a usuarios intensivos.
* Diseñar estrategias de fidelización para usuarios jóvenes.
* Monitorear usuarios de alto consumo como segmento estratégico.

---


Aspiring Data Analyst | Python | SQL | Power BI | Data Visualization

# 📊 Análisis de Recibos de Servicios Públicos — Power BI

## 📌 Descripción

Proyecto de análisis y visualización de datos desarrollado en Power BI
para analizar el comportamiento histórico de los servicios públicos,
el consumo, los cargos fijos y los valores unitarios asociados a cada servicio.

El proyecto busca transformar datos transaccionales en información útil
para facilitar el análisis de tendencias y apoyar la toma de decisiones.

---

## 🎯 Objetivos

- Analizar el comportamiento del consumo a través del tiempo.
- Comparar diferentes servicios públicos.
- Analizar la evolución de los cargos fijos.
- Analizar el comportamiento del valor unitario.
- Calcular el valor total estimado de los recibos.
- Construir un modelo de datos estructurado.
- Crear un dashboard interactivo en Power BI.

---

## 🗂️ Datos

El conjunto de datos contiene información relacionada con:

- Fecha
- Identificador del servicio
- Consumo
- Cargo fijo
- Valor unitario
- Servicio

Los datos fueron transformados y preparados mediante Power Query
antes de construir el modelo analítico.

---

## 🧹 Preparación de los datos

Durante la etapa de transformación se realizaron procesos como:

- Eliminación de registros completamente nulos.
- Verificación de valores faltantes.
- Conversión de tipos de datos.
- Estandarización de columnas.
- Preparación de campos de fecha.
- Organización de las tablas para el modelado.

---

## 🏗️ Modelado de datos

Se construyó un modelo basado en una estructura de dimensiones y hechos.

### Dimensiones

- `Date`
- `Servicio`

### Tablas de hechos

- `Consumo`
- `Cargo Fijo`
- `Valor Unitario`

Las relaciones permiten analizar los datos utilizando dimensiones comunes
como fecha y servicio.

---

## 📅 Tabla calendario

Se creó una tabla `Date` para facilitar el análisis temporal.

La tabla contiene campos como:

- Fecha
- Año
- Año-Mes
- Mes
- Número de mes

Esto permite realizar análisis por año, mes y períodos de tiempo.

---

## 🧮 DAX

Se desarrollaron medidas para calcular indicadores relevantes.

### Recibo Total

El valor total del recibo se calcula considerando:

- Consumo
- Valor unitario
- Cargo fijo

La lógica utilizada es:

```DAX
Recibo Total =
IF(
    SELECTEDVALUE(Consumo[Consumo]) = 0,
    SELECTEDVALUE('Valor Unitario'[Valor_Unitario])
        + SELECTEDVALUE('Cargo Fijo'[Cargo_fijo]),
    (
        SELECTEDVALUE(Consumo[Consumo])
        * SELECTEDVALUE('Valor Unitario'[Valor_Unitario])
    )
    + SELECTEDVALUE('Cargo Fijo'[Cargo_fijo])
)
.

📊 Dashboard

El dashboard permite analizar:

Consumo por fecha.
Cargo fijo por fecha.
Valor unitario por fecha.
Recibo total por fecha.
Comportamiento según el servicio seleccionado.

El usuario puede interactuar con los diferentes servicios
para analizar su comportamiento histórico.

.

🛠️ Tecnologías utilizadas
Power BI
Power Query
DAX
Modelado dimensional
Visualización de datos
Análisis temporal
💡 Aprendizajes

Este proyecto permitió fortalecer conocimientos en:

Limpieza y transformación de datos.
Diseño de modelos de datos.
Relaciones uno a muchos.
Tablas de dimensiones y hechos.
Construcción de tablas calendario.
Creación de medidas DAX.
Diseño de dashboards.
Análisis exploratorio y temporal.
Comunicación visual de información


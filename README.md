# 📊 Ejercicio de Pandas: Manipulación y Análisis de Datos
## Descripción

Este ejercicio tiene como objetivo practicar el uso de pandas, una de las librerías más importantes en Python para análisis de datos.
Se trabajan conceptos fundamentales como: selección de datos, filtrado, limpieza, agregación y exportación de resultados.

## Funcionalidades incluidas

1. Exploración de datos

 - df.shape → Conocer número de filas y columnas.

- df.columns → Ver nombres de columnas.

2. Selección de columnas y filas

- df["columna"] → Seleccionar una columna.

- df[["col1","col2"]] → Seleccionar varias columnas.

- df.loc[] → Selección por etiquetas.

- df.iloc[] → Selección por posición.

- df[df["Age"] > 30] → Filtrar por condiciones.

- df.query() → Filtrado usando expresiones tipo SQL.

3. Limpieza de datos

- df.isna() / df.isna().sum() → Detectar valores nulos.

- df.dropna() → Eliminar filas o columnas con valores nulos.

- df.fillna() → Rellenar valores nulos con un valor o método.

4. Creación y transformación de columnas

- df["new_col"] = ... → Crear o modificar columnas.

- df.assign() → Crear columnas adicionales sin modificar el DataFrame original.

- df.apply() → Aplicar funciones personalizadas a columnas o filas.

5. Análisis de datos

- df.groupby().mean() → Agrupar datos y calcular promedio.

- df.value_counts() → Contar ocurrencias de valores.

- df.unique() → Obtener valores únicos de una columna.

- df.sort_values() → Ordenar valores de una columna.

6. Combinación y unión

- pd.concat() → Combinar DataFrames vertical u horizontalmente.

- pd.merge() → Unir DataFrames según columnas comunes (tipo JOIN).

7. Exportación

- df.to_csv() → Guardar el DataFrame en un archivo CSV.

## Ejemplo de uso


import pandas as pd
import numpy as np

### Crear DataFrame
df = pd.DataFrame({
    "Name": ["Ana", "Luis", "Pedro", None],
    "Age": [25, 35, 45, np.nan]
})

### Limpieza de datos
df["Age"] = df["Age"].fillna(df["Age"].mean())

### Crear nueva columna
df["Age_in_10_Years"] = df["Age"] + 10

### Filtrar datos
adults = df[df["Age"] > 30]

### Agrupar y analizar
average_age = df.groupby("Name")["Age"].mean()

### Exportar resultado
df.to_csv("output.csv", index=False)

# Requisitos

- Python 3.x

- pandas

- numpy
# Unidad 1. Introducción

## 1.1. Manipulación de datos

**¿Qué es la forma rectangular de los datos? 📊**

La **forma rectangular de los datos** se refiere a la manera en que la información se organiza en **filas y columnas**, similar a una tabla en una base de datos, una hoja de cálculo de Excel o un DataFrame en Pandas.

**Estructura de los Datos Rectangulares**

Un conjunto de datos en forma rectangular se representa mediante una **tabla bidimensional**, donde:

•	**Las filas** representan **observaciones** o **registros**.

•	**Las columnas** representan **variables** o **atributos**.

**Ejemplo de una tabla con datos rectangulares:**

| **Nombre** | **Raza** | **Color** | **Altura (cm)** | **Peso (kg)** | **Fecha de Nacimiento** |
| --- | --- | --- | --- | --- | --- |
| Bella | Labrador | Marrón | 56 | 25 | 2013-07-01 |
| Charlie | Poodle | Negro | 43 | 23 | 2016-09-16 |
| Lucy | Chow Chow | Marrón | 46 | 22 | 2014-08-25 |
| Cooper | Schnauzer | Gris | 49 | 17 | 2011-12-11 |
| Max | Labrador | Negro | 59 | 29 | 2017-01-20 |

**Características Claves de los Datos Rectangulares**

- **Cada fila representa una observación** (por ejemplo, un perro en este dataset).
- **Cada columna representa una variable** (nombre, raza, color, altura, peso, etc.).
- **Los valores dentro de la tabla representan datos estructurados** que pueden ser analizados y manipulados fácilmente.

**Datos Rectangulares en Pandas**

En **Pandas**, los datos rectangulares se almacenan en un **DataFrame**, que es una estructura de datos bidimensional similar a una tabla.

**Ejemplo en Pandas:**

```python
import pandas as pd

# Crear un DataFrame en Pandas
datos = {
    "Nombre": ["Bella", "Charlie", "Lucy", "Cooper", "Max"],
    "Raza": ["Labrador", "Poodle", "Chow Chow", "Schnauzer", "Labrador"],
    "Color": ["Marrón", "Negro", "Marrón", "Gris", "Negro"],
    "Altura_cm": [56, 43, 46, 49, 59],
    "Peso_kg": [25, 23, 22, 17, 29],
    "Fecha_Nacimiento": ["2013-07-01", "2016-09-16", "2014-08-25", "2011-12-11", "2017-01-20"]
}

df = pd.DataFrame(datos)
print(df)
```

**Ver los primeros registros:**

```
df.head()
```

**Obtener la estructura de los datos:**

```
df.shape  # Devuelve (número de filas, número de columnas)
```

**Importancia de los Datos Rectangulares en Ciencia de Datos**

- Facilitan la manipulación y análisis de datos.
- Permiten aplicar técnicas estadísticas y de machine learning.
- Se pueden importar/exportar desde y hacia bases de datos, archivos CSV y hojas de cálculo.
- Son la forma estándar de representar datos estructurados en herramientas como **SQL, Excel y Pandas**.


## 1.2. Ordenamiento y Filtrado

En análisis de datos, es común necesitar ordenar los datos en función de una o más columnas. La función `sort_values` de pandas nos permite realizar este ordenamiento de manera sencilla y eficiente.

**Sintaxis de `sort_values`**

```python
DataFrame.sort_values(by, axis=0, ascending=True, inplace=False, kind='quicksort', na_position='last')
```

### Parámetros clave:

- `by`: Nombre de la columna (o lista de columnas) por la que se ordenará el DataFrame.
- `ascending`: Booleano o lista de valores booleanos. `True` (por defecto) ordena en orden ascendente; `False`, en orden descendente.
- `inplace`: Si es `True`, modifica el DataFrame original; si es `False` (por defecto), devuelve un nuevo DataFrame ordenado.
- `na_position`: Define la posición de los valores nulos (`'first'` para colocarlos al inicio, `'last'` para colocarlos al final).
- `kind`: Tipo de algoritmo de ordenamiento (`'quicksort'`, `'mergesort'`, `'heapsort'`, `'stable'`).

---

**Ejemplos de Uso**

1. Ordenamiento por una sola columna

```python
import pandas as pd

# Crear un DataFrame de ejemplo
df = pd.DataFrame({
    'Nombre': ['Ana', 'Carlos', 'Beatriz', 'David'],
    'Edad': [29, 35, 23, 32],
    'Salario': [50000, 70000, 45000, 65000]
})

# Ordenar por la columna 'Edad'
df_ordenado = df.sort_values(by='Edad')
print(df_ordenado)
```

2. Ordenamiento en orden descendente

```python
# Ordenar por 'Salario' de mayor a menor
df_desc = df.sort_values(by='Salario', ascending=False)
print(df_desc)
```

3. Ordenamiento por múltiples columnas

```python
# Ordenar por 'Edad' ascendente y luego por 'Salario' descendente
df_multi = df.sort_values(by=['Edad', 'Salario'], ascending=[True, False])
print(df_multi)
```

4. Manejo de valores nulos en el ordenamiento

```python
df_con_nulos = pd.DataFrame({
    'Nombre': ['Ana', 'Carlos', 'Beatriz', 'David', 'Elena'],
    'Edad': [29, None, 23, 32, 27]
})

# Ordenar colocando los valores nulos al inicio
df_nulos_first = df_con_nulos.sort_values(by='Edad', na_position='first')
print(df_nulos_first)
```

**Consideraciones Adicionale**s

- Para ordenamientos estables (manteniendo el orden relativo de elementos con el mismo valor), usa `kind='stable'`.
- Si `inplace=True`, el DataFrame se modificará directamente sin necesidad de reasignarlo a una nueva variable.

[`Example`](./code/1.2.-sort_filter.ipynb) - [`Ejercicio`]()

## 1.3. Agregación de datos
1.4. Slicing e indexado de datos
1.5. Visualización de datos
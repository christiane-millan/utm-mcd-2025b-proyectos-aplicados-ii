# Unidad 1. Introducción

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
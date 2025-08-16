# PandasPractica
Este repositorio contiene ejercicios y apuntes personales del curso Pandas de kaggle. Lo uso para repasar y reforzar fundamentos de manipulación de datos con python

## Creating, Reading an writing

### DataFrame
> Tabla
pd.DataFrame() -> Contructor
La sintaxis es un diccionario, Keys = Columnas Values = Lista de entrada
El index del DF comienza en 0, para cambiarlo usar index


pd.DataFrame({'Bob': [5, 2], 'Sue':[5, 4]}, index=['Product A', 'Product B'])

### Serie
> Secuencia de datos -  Columna de un DataFrame

pd.Series() -> Constructor
El index comienza en 0, para cambiar usar index

pd.Series([30, 40], index=['2012 Sales', '2013 Sales'])

Atributo descriptivo

Usar name

ingredients = pd.Series(['4 cups','1 cup','2 large', '1 can'], index=['Flour','Milk', 'Eggs', 'Spam'], name='Dinner')


### Lectura

pd.read_csv()

> Importante
> Para descargar un archivo de kaggle, es necesario
> Descargar kaggle hub
bash
pip install kagglehub

> Agregar al cuaderno
import kagglehub

path = kagglehub.dataset_download("christopheiv/winemagdata130k")
print("Path to dataset files:", path)

y concatenar la direccion del archivo y el nombre
cv_path = os.path.join(path,"winemag-data-130k-v2.csv")

### Escritura

pd.to_csv("nombre_archivo")


## Indexing, Selecting & Assigning

### Accesos nativos

Python de forma nativa provee buenas maneras de indexar la data.

"In Python, we can access the property of an object by accessing it as an attribute"

Para acceder a un diccionario en python usar []

Ejemplo:
reviews = pd.read_csv("../input/archivo.csv")

reviews
reviews.country
reviews['country']

### Indexing con pandas

El operador indexing y atributo de seleccion, a traves de pandas, es *loc* y *iloc*
.loc  -> Seleccion por etiqueta, no por posicion numerica
         *lo que importa es el valor del índice de datos, no su posición*
.iloc -> Seleccion por posicion, el indice no se incluye

df.iloc[fila, columna]
df.loc[fila, columna]

#### .iloc vs .loc

> ***iloc*** utiliza el esquema de indexación de la biblioteca estándar de Python, donde se incluye el primer elemento del rango y ***se excluye el último.*** Por lo tanto, 0:10 seleccionará las entradas 0,...,9. 
Por su parte, ***loc*** ***indexa de forma inclusiva.*** Por lo tanto, 0:10 seleccionará las entradas 0,...,10.


![loc VS iloc](/imgs/locVSiloc.jpg)

## Manipulando index

df.set_index("nombre_columna")

> cambia el indice de DataFrame usando una columna existente.


## Condicionales seleccionales

Usa las propiedades de la estructura del DataFrame, basado en condiciones

df.country == 'Italy'
df.loc[reviews.country == 'Italy']

.isin():  df.nombre_columna.isin([1 , 2])
.isnull(): df.nombre_columna.isnull()\

## Summary Functions and Maps

No todos los datos vienen en formatos sencillos para almacenar en un DF, por ello es necesario el maps

### Some sommary functions
* describe()
* mean()
* unique()
* value_counts()

### Maps
 Hay dos metodos:
 * map(): One by one, simple and efficient, only works works on a **single column (Series)**
 * apply():  **level up**, A single column (Series), Multiple columns (DataFrame), Rows and Columns (axis control) 

``` python
```
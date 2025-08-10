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
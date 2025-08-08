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

### Lectura de archivos

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


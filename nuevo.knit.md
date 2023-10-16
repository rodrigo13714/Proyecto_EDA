
<!-- rnb-text-begin -->

---
title: "Proyecto EDA"
author: Grupo 3 
date: "16 Octubre, 2023"
output:
  html_document:
    toc: yes
    df_print: paged
  html_notebook:
    toc: no
    toc_float:
      collapsed: no
      smooth_scroll: no
    number_sections: yes
    theme: journal
---
# Introducción


## Contexto

Actualmente las tecnologías de información y el uso de Internet son herramientas vitales para los estudiantes universitarios de UTEC. Por un lado, constituyen una fuente valiosa de información y de interacción social, pero, por otro lado, existen algunos riesgos como la dependencia que se pueden suscitar en esta población. 

La procrastinación académica es una realidad que puede llevar a los estudiantes a tener bajo rendimiento académico o incluso la deserción y en especial en los adolescentes en los cuales las conductas de procrastinación se mantienen. El hábito de procrastinar no solo afectará a su desempeño académico, sino, que a largo plazo se verá reflejado en actividades familiares, sociales, laborales entre otras. Por ello, se realizará un estudio estadístico que nos ayude a identificar y analizar los factores que causan la procrastinación, así se podrán brindar sugerencias para mejorar el rendimiento académico en los estudiantes.

## Integrantes


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuaWYoIXJlcXVpcmUoZ2dwbG90Mikpe2luc3RhbGwucGFja2FnZXMoJ2dncGxvdDInKX1cbmxpYnJhcnkoZ2dwbG90MilcbmBgYCJ9 -->

```r
if(!require(ggplot2)){install.packages('ggplot2')}
library(ggplot2)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->




<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->




# Métodos

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgcHl0aG9uXG4jSW1wb3J0YXIgbGlicmVyaWFzXG5pbXBvcnQgcGFuZGFzIGFzIHBkXG5gYGAifQ== -->

```python
#Importar librerias
import pandas as pd
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiVHJhY2ViYWNrIChtb3N0IHJlY2VudCBjYWxsIGxhc3QpOlxuICBGaWxlIFwiPHN0cmluZz5cIiwgbGluZSAxLCBpbiA8bW9kdWxlPlxuICBGaWxlIFwiXHUwMDFiXTg7bGluZT0xMTk7ZmlsZTovL0M6XFxVc2Vyc1xcUm9kcmlnbyBBbWF5YVxcQXBwRGF0YVxcTG9jYWxcXFJcXHdpbi1saWJyYXJ5XFw0LjJcXHJldGljdWxhdGVcXHB5dGhvblxccnB5dG9vbHNcXGxvYWRlci5weVx1MDAwN0M6XFxVc2Vyc1xcUm9kcmlnbyBBbWF5YVxcQXBwRGF0YVxcTG9jYWxcXFJcXHdpbi1saWJyYXJ5XFw0LjJcXHJldGljdWxhdGVcXHB5dGhvblxccnB5dG9vbHNcXGxvYWRlci5weVx1MDAxYl04OztcdTAwMDdcIiwgbGluZSAxMTksIGluIF9maW5kX2FuZF9sb2FkX2hvb2tcbiAgICByZXR1cm4gX3J1bl9ob29rKG5hbWUsIF9ob29rKVxuICBGaWxlIFwiXHUwMDFiXTg7bGluZT05MztmaWxlOi8vQzpcXFVzZXJzXFxSb2RyaWdvIEFtYXlhXFxBcHBEYXRhXFxMb2NhbFxcUlxcd2luLWxpYnJhcnlcXDQuMlxccmV0aWN1bGF0ZVxccHl0aG9uXFxycHl0b29sc1xcbG9hZGVyLnB5XHUwMDA3QzpcXFVzZXJzXFxSb2RyaWdvIEFtYXlhXFxBcHBEYXRhXFxMb2NhbFxcUlxcd2luLWxpYnJhcnlcXDQuMlxccmV0aWN1bGF0ZVxccHl0aG9uXFxycHl0b29sc1xcbG9hZGVyLnB5XHUwMDFiXTg7O1x1MDAwN1wiLCBsaW5lIDkzLCBpbiBfcnVuX2hvb2tcbiAgICBtb2R1bGUgPSBob29rKClcbiAgRmlsZSBcIlx1MDAxYl04O2xpbmU9MTE3O2ZpbGU6Ly9DOlxcVXNlcnNcXFJvZHJpZ28gQW1heWFcXEFwcERhdGFcXExvY2FsXFxSXFx3aW4tbGlicmFyeVxcNC4yXFxyZXRpY3VsYXRlXFxweXRob25cXHJweXRvb2xzXFxsb2FkZXIucHlcdTAwMDdDOlxcVXNlcnNcXFJvZHJpZ28gQW1heWFcXEFwcERhdGFcXExvY2FsXFxSXFx3aW4tbGlicmFyeVxcNC4yXFxyZXRpY3VsYXRlXFxweXRob25cXHJweXRvb2xzXFxsb2FkZXIucHlcdTAwMWJdODs7XHUwMDA3XCIsIGxpbmUgMTE3LCBpbiBfaG9va1xuICAgIHJldHVybiBfZmluZF9hbmRfbG9hZChuYW1lLCBpbXBvcnRfKVxuTW9kdWxlTm90Rm91bmRFcnJvcjogTm8gbW9kdWxlIG5hbWVkICdwYW5kYXMnXG4ifQ== -->

```
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "]8;line=119;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 119, in _find_and_load_hook
    return _run_hook(name, _hook)
  File "]8;line=93;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 93, in _run_hook
    module = hook()
  File "]8;line=117;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 117, in _hook
    return _find_and_load(name, import_)
ModuleNotFoundError: No module named 'pandas'
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgcHl0aG9uXG5pbXBvcnQgc2VhYm9ybiBhcyBzbnNcbmBgYCJ9 -->

```python
import seaborn as sns
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiVHJhY2ViYWNrIChtb3N0IHJlY2VudCBjYWxsIGxhc3QpOlxuICBGaWxlIFwiPHN0cmluZz5cIiwgbGluZSAxLCBpbiA8bW9kdWxlPlxuICBGaWxlIFwiXHUwMDFiXTg7bGluZT0xMTk7ZmlsZTovL0M6XFxVc2Vyc1xcUm9kcmlnbyBBbWF5YVxcQXBwRGF0YVxcTG9jYWxcXFJcXHdpbi1saWJyYXJ5XFw0LjJcXHJldGljdWxhdGVcXHB5dGhvblxccnB5dG9vbHNcXGxvYWRlci5weVx1MDAwN0M6XFxVc2Vyc1xcUm9kcmlnbyBBbWF5YVxcQXBwRGF0YVxcTG9jYWxcXFJcXHdpbi1saWJyYXJ5XFw0LjJcXHJldGljdWxhdGVcXHB5dGhvblxccnB5dG9vbHNcXGxvYWRlci5weVx1MDAxYl04OztcdTAwMDdcIiwgbGluZSAxMTksIGluIF9maW5kX2FuZF9sb2FkX2hvb2tcbiAgICByZXR1cm4gX3J1bl9ob29rKG5hbWUsIF9ob29rKVxuICBGaWxlIFwiXHUwMDFiXTg7bGluZT05MztmaWxlOi8vQzpcXFVzZXJzXFxSb2RyaWdvIEFtYXlhXFxBcHBEYXRhXFxMb2NhbFxcUlxcd2luLWxpYnJhcnlcXDQuMlxccmV0aWN1bGF0ZVxccHl0aG9uXFxycHl0b29sc1xcbG9hZGVyLnB5XHUwMDA3QzpcXFVzZXJzXFxSb2RyaWdvIEFtYXlhXFxBcHBEYXRhXFxMb2NhbFxcUlxcd2luLWxpYnJhcnlcXDQuMlxccmV0aWN1bGF0ZVxccHl0aG9uXFxycHl0b29sc1xcbG9hZGVyLnB5XHUwMDFiXTg7O1x1MDAwN1wiLCBsaW5lIDkzLCBpbiBfcnVuX2hvb2tcbiAgICBtb2R1bGUgPSBob29rKClcbiAgRmlsZSBcIlx1MDAxYl04O2xpbmU9MTE3O2ZpbGU6Ly9DOlxcVXNlcnNcXFJvZHJpZ28gQW1heWFcXEFwcERhdGFcXExvY2FsXFxSXFx3aW4tbGlicmFyeVxcNC4yXFxyZXRpY3VsYXRlXFxweXRob25cXHJweXRvb2xzXFxsb2FkZXIucHlcdTAwMDdDOlxcVXNlcnNcXFJvZHJpZ28gQW1heWFcXEFwcERhdGFcXExvY2FsXFxSXFx3aW4tbGlicmFyeVxcNC4yXFxyZXRpY3VsYXRlXFxweXRob25cXHJweXRvb2xzXFxsb2FkZXIucHlcdTAwMWJdODs7XHUwMDA3XCIsIGxpbmUgMTE3LCBpbiBfaG9va1xuICAgIHJldHVybiBfZmluZF9hbmRfbG9hZChuYW1lLCBpbXBvcnRfKVxuTW9kdWxlTm90Rm91bmRFcnJvcjogTm8gbW9kdWxlIG5hbWVkICdzZWFib3JuJ1xuIn0= -->

```
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "]8;line=119;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 119, in _find_and_load_hook
    return _run_hook(name, _hook)
  File "]8;line=93;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 93, in _run_hook
    module = hook()
  File "]8;line=117;file://C:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.pyC:\Users\Rodrigo Amaya\AppData\Local\R\win-library\4.2\reticulate\python\rpytools\loader.py]8;;", line 117, in _hook
    return _find_and_load(name, import_)
ModuleNotFoundError: No module named 'seaborn'
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgcHl0aG9uXG5pbXBvcnQgbWF0cGxvdGxpYi5weXBsb3QgYXMgcGx0XG5gYGAifQ== -->

```python
import matplotlib.pyplot as plt
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgcHl0aG9uXG4jQ2FyZ2FyIGxhIGJhc2UgZGUgZGF0b3MgZW4gdW4gZGZcbmRmID0gcGQucmVhZF9jc3YoXCJsaXN0aW5ncy5jc3ZcIilcbmBgYCJ9 -->

```python
#Cargar la base de datos en un df
df = pd.read_csv("listings.csv")
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiVHJhY2ViYWNrIChtb3N0IHJlY2VudCBjYWxsIGxhc3QpOlxuICBGaWxlIFwiPHN0cmluZz5cIiwgbGluZSAxLCBpbiA8bW9kdWxlPlxuTmFtZUVycm9yOiBuYW1lICdwZCcgaXMgbm90IGRlZmluZWRcbiJ9 -->

```
Traceback (most recent call last):
  File "<string>", line 1, in <module>
NameError: name 'pd' is not defined
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



## Métodos no Gráficos




## Métodos Gráficos


## Variables

+---------------------------+----------------+--------------------------------+
| VARIABLE                  | TIPO DE        | Descripción                    |
|                           | VARIABLE       |                                |
+===========================+================+================================+
|                           |                | Se utiliza para identificar de | 
|      ID                   | cualitativa    | manera unica a cada propiedad  |
+---------------------------+----------------+--------------------------------+
|                           |                | Contiene el nombre de la       |
|      NAME                 | cualitativa    | propiedad                      |
+---------------------------+----------------+--------------------------------+
|      HOST_ID              | cuantitativa   | Representa el id único del     |
|                           | discreta       | anfitrión                      |
+---------------------------+----------------+--------------------------------+
|                           |                | Contiene el nombre del         |
|      HOST_NAME            | cualitativa    | anfitrión                      |
+---------------------------+----------------+--------------------------------+
|                           |                | Representa grupos o categorías |
|      NEIGHTBOURHOOD_GROUP | cualitativa    | del vecindario                 |
+---------------------------+----------------+--------------------------------+
|                           |                | Contiene el nombre del         |
|      NEIGHTBOURHOOD       | cualitativa    | vecindario                     |
+---------------------------+----------------+--------------------------------+
|      LATITUDE             | cuantitativa   | Números enteros no negativos   |
|                           | continua       | mayores a 12 y menores a 26    |
+---------------------------+----------------+--------------------------------+
|                           |                | Representa la latitud          |
|      LONGITUDE            | cuantitativa   | geográfica de la propiedad     |
|                           | continua       |                                |
+---------------------------+----------------+--------------------------------+
|      ROOM_TYPE            | cualitativa    | Describe el tipo de habitación |
+---------------------------+----------------+--------------------------------+
|                           | cuantitativa   | Representa el precio de la     |
|      PRICE                | continua       | propiedad                      |
+---------------------------+----------------+--------------------------------+
|                           | cuantitativa   | Representa el número mínimo de |
|      MINIMUN_NIGHT        | discreta       | noches                         |
+---------------------------+----------------+--------------------------------+
|                           | cuantitativa   | Representa el número de reseñas|
|      NUMBER_OF_REVIEWS    | discreta       |                                |
+---------------------------+----------------+--------------------------------+
|      LAST_REVIEW          | cualitativa    | Contiene fechas de reseñas     |
+---------------------------+----------------+--------------------------------+
|      REVIEWS_PER_MONTH    | cuantitativa   | Cantidad de reseñas por mes    |
|                           | continua       |                                |
+---------------------------+----------------+--------------------------------+
|                           | cuantitativa   | Representa la disponibilidad   |
|      AVAILABILITY_365     | discreta       | de la propiedad en dias al año |
+---------------------------+----------------+--------------------------------+
|                           |                | Cantidad de propiedades que un |
|      CALCULATED_HOST_     | cuantitativa   | anfitrión gestiona             |
|      LISTINGS_COUNT       | discreta       |                                |
+---------------------------+----------------+--------------------------------+
|                           | numérica       | Cantidad de reseñas a lo largo |
|      NUMBER_OF_REVIEWS_LTM| discreta       | del tiempo                     |
+---------------------------+----------------+--------------------------------+





<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



# Conclusiones




<!-- rnb-text-end -->


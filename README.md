# EDA_ANIME
Análisis exploratorio de la popularidad del anime
IMPORTACIONES:

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

from scipy.stats import (pearsonr, f_oneway, ttest_ind, shapiro, mannwhitneyu, kruskal)

import statsmodels.api as sm

import scipy.stats as stats

from itertools import combinations

from statsmodels.stats.multitest import multipletests

from statsmodels.stats.multicomp import pairwise_tukeyhsd

import warnings

from scipy.stats import ttest_1samp, ttest_ind, levene, ttest_rel, wilcoxon, f_oneway, ks_2samp, spearmanr

warnings.filterwarnings("ignore", category=UserWarning)

PRIMER ANALISIS:

-Un head()para ver las primeras filas de mi base de datos

-Un tail() para ver las ultimas filas 

-info() para ver la informacion general de mi base de datos

-shape para ver el total de filas y columnas

-describe incluide object y otro exclude object para ver las estadisticas descriptivas

-isna().sum() para ver si mi base de datos tiene valores nulos y despues otro .sum() para ver el total

-.duplicated().sum() para ver si tengo valores duplicados

-unknowns= (anime =="Unknown").sum().sum() para ver los valores llamados unknown


LIMPIEZA:

-Visualizar los valores nulos con un countplot

-.copy() para no alterar mi base de datos original

-Borrar columnas innecesarias

-.dropduplicates para borrar los valores duplicados

-columnas: aired 

Un regex para separar el mes de salida y el año en una columna llamada meses y luego otro para separar la columna meses en month aired y year aired

-Comprobar otra vez los nan y arreglarlos con un fillna por ahora

-Columnas: premiered

Una funcion lambda para que segun el mes de lanzamiento me ponga en la columna premiered la estacion del año que le corresponde y quitar los unknowns

-nans y unknowns de la columna year aired y year season 

El año de la columna Year Aired que este con unknowns en le voy a poner el año que tenga year season

-Columna: generos

En la columna generos los valores vienen en lista asi que con un get dummies los he separado y puesto en otro dataframe

-Columna: rating

Un regex para separar la R, PG, G y que solo se vea la columna con esos. Despues voy a quitar los unknowns sacando el valor mas comun del rating por genero

-Columna:Duracion 

Convertir todas las duraciones en minutos para luego poder analizarlo mejor con regex y bucles

-Columna: English name

Me sera mas facil ver los animes con el nombre en ingles pero esta incompleto asi que los valores unknown los voy a sustituir por los nombres que estan en la columna name

con una funcion lambda

-Eliminar lo que no me interesa:

Elimino ya todas las columnas que no me hacen falta


ANALISIS EXPLORATORIO

-Subir dataframe limpio, el de generos y uno de valores numericos

-Significado de las columnas

-Informacion general, describe, into, shape 

-Correlacion de todos los valores numericos de mi dataframe y heatmap

-Analisis univariante:

medidas de tendencia central con un hisplot

un countplot de tipos de anime hay 

-Analisis bivariante

-Un lineplot de las 10 series y peliculas de anime con mas puntuacion

-correlacion entre la puntuacion media y popularidad

-correlacion de la puntuacion media con animes completados

-Analisis multivariante

Relacion entre favoritos, popularidad y animes completados

Relacion entre popularidad miembros, abandonados y pausados

Relacion de la popularidad y score entre animes de tipo tv y animes de tipo pelicula


TEST DE HIPOTESIS

1.pperarson 

2.ppearson

3.Kruskal

4.spearmanr

5.regresion lineal

6.Kruskal-Wallis

7.T

8.T

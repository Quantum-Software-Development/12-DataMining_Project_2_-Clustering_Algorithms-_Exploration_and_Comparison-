
<br>

**\[[🇧🇷 Português](README.pt_BR.md)\] \[**[🇺🇸 English](README.md)**\]**


<br><br>

# 12- [Data Mining]()  / [Project 2 – Clustering Algorithms Exploration and Comparison]()




<!-- ======================================= Start DEFAULT HEADER ===========================================  -->

<br><br>


[**Institution:**]() Pontifical Catholic University of São Paulo (PUC-SP)  
[**School:**]() Faculty of Interdisciplinary Studies  
[**Program:**]() Humanistic AI and Data Science
[**Semester:**]() 2nd Semester 2025  
Professor:  [***Professor Doctor in Mathematics Daniel Rodrigues da Silva***](https://www.linkedin.com/in/daniel-rodrigues-048654a5/)

<br><br>

#### <p align="center"> [![Sponsor Quantum Software Development](https://img.shields.io/badge/Sponsor-Quantum%20Software%20Development-brightgreen?logo=GitHub)](https://github.com/sponsors/Quantum-Software-Development)


<br><br>

<!--Confidentiality statement -->

#

<br><br><br>

> [!IMPORTANT]
> 
> ⚠️ Heads Up
>
> * Projects and deliverables may be made [publicly available]() whenever possible.
> * The course emphasizes [**practical, hands-on experience**]() with real datasets to simulate professional consulting scenarios in the fields of **Data Analysis and Data Mining** for partner organizations and institutions affiliated with the university.
> * All activities comply with the [**academic and ethical guidelines of PUC-SP**]().
> * Any content not authorized for public disclosure will remain [**confidential**]() and securely stored in [private repositories]().  
>


<br><br>

#

<!--END-->




<br><br><br><br>



<!-- PUC HEADER GIF
<p align="center">
  <img src="https://github.com/user-attachments/assets/0d6324da-9468-455e-b8d1-2cce8bb63b06" />
-->


<!-- video presentation -->


##### 🎶 Prelude Suite no.1 (J. S. Bach) - [Sound Design Remix]()

https://github.com/user-attachments/assets/4ccd316b-74a1-4bae-9bc7-1c705be80498

####  📺 For better resolution, watch the video on [YouTube.](https://youtu.be/_ytC6S4oDbM)


<br><br>


> [!TIP]
> 
>  This repository is a review of the Statistics course from the undergraduate program Humanities, AI and Data Science at PUC-SP.
>
> ### ☞ **Access Data Mining [Main Repository](https://github.com/Quantum-Software-Development/1-Main_DataMining_Repository)**
>
>


<!-- =======================================END DEFAULT HEADER ===========================================  -->


<br><br><br>



## Introduction / Introdução


*🇬🇧 This code performs an exploratory and clustering analysis of the dataset "Grupo4.csv" for a classroom project. It includes data cleaning, preprocessing, and applies three clustering algorithms (K-Means, Mean-Shift, Affinity Propagation), visualizing and comparing the results in Python.

<br>


🇧🇷 Este código realiza uma análise exploratória e de agrupamento no dataset "Grupo4.csv" para um projeto de sala de aula. Inclui limpeza e pré-processamento dos dados, além de aplicar três algoritmos de agrupamento (K-Means, Mean-Shift, Propagação por Afinidade), visualizando e comparando os resultados em Python.


<br>


## 🚦 Steps/Células do Código

<br>


### 1. **Import pandas and load the dataset**

<br>

**🇬🇧 Import the pandas library and load your group's dataset.**
**🇧🇷 Importe a biblioteca pandas e carregue o dataset do seu grupo.**

<br>

```python
import pandas as pd
df = pd.read_csv('Grupo4.csv')
df.head()
```

<br><br>


### 2. **Display dataset dimensions and statistics**

<br>

**🇬🇧 Show the number of rows and columns, and display basic statistical measures.**
**🇧🇷 Mostre o número de linhas e colunas, e exiba as medidas estatísticas básicas.**


<br>


```python
num_rows, num_cols = df.shape
print(f"🇬🇧 Number of rows: {num_rows}, Number of columns: {num_cols}")
print(f"🇧🇷 Número de linhas: {num_rows}, Número de colunas: {num_cols}")
display(df.describe())
```

<br><br>


### 3. **Remove 'Unnamed: 0' column if exists**

<br>

**🇬🇧 Remove the 'Unnamed: 0' column if present.**
**🇧🇷 Remova a coluna 'Unnamed: 0' caso exista

<br>

```python
if 'Unnamed: 0' in df.columns:
    df.drop('Unnamed: 0', axis=1, inplace=True)
    print("🇬🇧 'Unnamed: 0' column dropped. 🇧🇷 Coluna 'Unnamed: 0' removida.")
else:
    print("🇬🇧 'Unnamed: 0' column not found. 🇧🇷 Coluna 'Unnamed: 0' não encontrada.")
```


<br><br>

### 4. **Fill missing values with column median**

<br>

**🇬🇧 Check for missing values and fill them with the median of each column.**
**🇧🇷 Verifique valores faltantes e preencha com a mediana de cada coluna.**

<br>


```python
column_medians = df.median()
df.fillna(column_medians, inplace=True)
print("🇬🇧 Missing values filled with medians. 🇧🇷 Valores faltantes preenchidos com as medianas.")
```

<br><br>


### 5. **Remove duplicate rows**

<br>

**🇬🇧 Check for and remove duplicate records.**
**🇧🇷 Verifique e remova registros duplicados.**

<br>

```python
initial_rows = df.shape[0]
df.drop_duplicates(inplace=True)
rows_after_duplicates = df.shape[0]
print(f"🇬🇧 Duplicates removed: {initial_rows - rows_after_duplicates}")
print(f"🇧🇷 Duplicados removidos: {initial_rows - rows_after_duplicates}")
```

<br><br>

### 6. **Display the preprocessed DataFrame**

<br>

**🇬🇧 Show first rows after preprocessing.**
**🇧🇷 Mostre as primeiras linhas após o pré-processamento.**

<br>

```python
display(df.head())
num_rows_preprocessed, num_cols_preprocessed = df.shape
print(f"🇬🇧 After preprocessing: {num_rows_preprocessed} rows, {num_cols_preprocessed} columns")
print(f"🇧🇷 Após o pré-processamento: {num_rows_preprocessed} linhas, {num_cols_preprocessed} colunas")
```


<br><br>


### 7. **Scatter Plot** - ColunScatter Plot of Coluna1 vs Coluna2 - Gráfico de Dispersão de Coluna1 vs Coluna2a1', y='Coluna2png

<br>

<img width="1002" height="699" alt="Image" src="https://github.com/user-attachments/assets/b983a001-187c-4b20-bdac-75473ed6235f" />

<br>


```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_style('darkgrid')
sns.set_palette('viridis')

plt.figure(figsize=(12, 8))
sns.scatterplot(data=df, x='Coluna1', y='Coluna2')
plt.title('Scatter Plot of Coluna1 vs Coluna2 / Gráfico de Dispersão Coluna1 vs Coluna2')
plt.show()
```


<br><br>



### 8. **Standardize features**

**🇬🇧 Standardize columns for clustering.**
**🇧🇷 Padronize as colunas para agrupamento.**

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
df[['Coluna1', 'Coluna2']] = scaler.fit_transform(df[['Coluna1', 'Coluna2']])
```

<br><br>





























<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>


## 21-  [Our Crew:]()


- 👨🏽‍🚀 **Andson Ribeiro** - [Slide into my inbox]()

- 👩🏻‍🚀 **Fabiana ⚡️ Campanari** - [Shoot me an email](mailto:fabicampanari@proton.me)

- 👨🏽‍🚀  **José Augusto de Souza Oliveira**  - [email]()

- 🧑🏼‍🚀 **Luan Fabiano**  - [email]()

- 👨🏽‍🚀 **Pedro Barrenco**  - [email]()
  
- 🧑🏼‍🚀 **Pedro Vyctor** - [Hit me up by email](mailto:pedro.vyctor00@gmail.com)



<br><br>


<!-- ========================== [Bibliographr ====================  -->

<br><br>


## [Bibliography]()


[1](). **Castro, L. N. & Ferrari, D. G.** (2016). *Introdução à mineração de dados: conceitos básicos, algoritmos e aplicações*. Saraiva.

[2](). **Ferreira, A. C. P. L. et al.** (2024). *Inteligência Artificial - Uma Abordagem de Aprendizado de Máquina*. 2nd Ed. LTC.

[3](). **Larson & Farber** (2015). *Estatística Aplicada*. Pearson.


<br><br>


<!-- ======================================= Start Footer ===========================================  -->


<br><br>


## 💌 [Let the data flow... Ping Me !](mailto:fabicampanari@proton.me)

<br><br>



#### <p align="center">  🛸๋ My Contacts [Hub](https://linktr.ee/fabianacampanari)


<br>

### <p align="center"> <img src="https://github.com/user-attachments/assets/517fc573-7607-4c5d-82a7-38383cc0537d" />




<br><br><br>

<p align="center">  ────────────── 🔭⋆ ──────────────


<p align="center"> ➣➢➤ <a href="#top">Back to Top </a>

<!--
<p align="center">  ────────────── ✦ ──────────────
-->



<!-- Programmers and artists are the only professionals whose hobby is their profession."

" I love people who are committed to transforming the world "

" I'm big fan of those who are making waves in the world! "

##### <p align="center">( Rafael Lain ) </p>   -->

#

###### <p align="center"> Copyright 2025 Quantum Software Development. Code released under the [MIT License license.](https://github.com/Quantum-Software-Development/Math/blob/3bf8270ca09d3848f2bf22f9ac89368e52a2fb66/LICENSE)














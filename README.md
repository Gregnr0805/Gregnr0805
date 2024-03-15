# -*- coding: utf-8 -*-
"""Gregory_titanic.ipynb

Automatically generated by Colaboratory.    

# 1. **Importe a biblioteca `pandas`:**
"""

import pandas as pd

"""# 2. **Acesse e carregue os dados:**"""
https://github.com/Gregnr0805/phython-.git

# Carregando os dados em um DataFrame
titanic_data = pd.read_csv(titanic_url)

"""# 3. **Explore os dados:**"""

# Exibir as primeiras linhas do DataFrame
print(titanic_data.head())

"""# 4. **Atributos de dados (campos)**"""

# Informações sobre as colunas e tipos de dados
print(titanic_data.info())

"""# 5. **Graficos usando a biblioteca: numpy**"""

# Estatísticas básicas
print(titanic_data.describe())

# Atributos de dados (campos)
titanic_campos=titanic_data.head()
titanic_campos.columns

#Atributos de dados (campos) fazendo uma tradução.
titanic_campos.columns=['PassageiroId', 'Sobreviveu', 'Classe', 'Nome', 'Sexo', 'Idade', 'Id','Janela', 'Bilhete', 'Tarifa', 'Cabine', 'Embarcado']

#Grafico Sobreviveu
import numpy as np
from google.colab import autoviz

def value_plot(df, y, figscale=1):
  from matplotlib import pyplot as plt
  df[y].plot(kind='line', figsize=(8 * figscale, 4 * figscale), title=y)
  plt.gca().spines[['top', 'right']].set_visible(False)
plt.tight_layout()
  return autoviz.MplChart.from_current_mpl_state()

chart = value_plot(titanic_campos, *['Sobreviveu'], **{})
chart

#Grafico Idade
import numpy as np
from google.colab import autoviz

def value_plot(df, y, figscale=1):
  from matplotlib import pyplot as plt
  df[y].plot(kind='line', figsize=(8 * figscale, 4 * figscale), title=y)
  plt.gca().spines[['top', 'right']].set_visible(False)
  plt.tight_layout()
  return autoviz.MplChart.from_current_mpl_state()

chart = value_plot(titanic_campos, *['Idade'], **{})
chart

#Grafico Sexo (Masculino , Feminino)
import numpy as np
from google.colab import autoviz

def categorical_histogram(df, colname, figscale=1, mpl_palette_name='Dark2'):
  from matplotlib import pyplot as plt
  import seaborn as sns
  df.groupby(colname).size().plot(kind='barh', color=sns.palettes.mpl_palette(mpl_palette_name), figsize=(8*figscale, 4.8*figscale))
  plt.gca().spines[['top', 'right',]].set_visible(False)
  return autoviz.MplChart.from_current_mpl_state()

chart = categorical_histogram(titanic_campos, *['Sexo'], **{})
chart

display(titanic_campos) #executando o FrameWork tranduzido os atributos




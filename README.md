# Pokemon
- Analise feita de um Dataset com os dados Pokemon utilizando Python e a biblioteca Pandas

![full_pokemon](https://user-images.githubusercontent.com/51414398/76796676-b9f27f80-67aa-11ea-8258-e04c0fd579f3.jpg)

- Neste projeto utilizei um Dataset do site Kiggle de um anime chamado Pokemon, esse projeto é semelhante ao meu outro repositório chamado Yu-Gi-Oh que também peguei do site Kiggle. Então ele vai mostrar as evoluções dos principais Pokemons, os Pokemons mais fortes e fracos de todos os tipos, a contagem de todos tipos de Pokemons como por exemplo água ou fogo e pra finalizar passei tudo para alguns tipos de gráficos para você meu consagrado ter uma noção das coisas incríveis que podemos fazer na área de Data Science.


### Módulos

Importando Bibliotecas

<details><summary>Pandas</summary>
  Importando a biblioteca Pandas para análise de dados
</details>

```
import pandas as pd
```

<details><summary>Matplotlib</summary>
  Importando a biblioteca matplotlib para gráficos
</details>

```
import matplotlib.pyplot as plt
```

### Leitura

<details><summary>Leitura de arquivo</summary>
  Criando uma variavel que vai armazenar um arquivo e fazendo leitura do mesmo
  </details>
  
 ```
 df = pd.read_csv('pokemon_data.csv')
 ```

### Colunas

<details><summary>Colunas do arquivo</summary>
  Todas as colunas do arquivo
</details>

```
df.columns
```

### Deletando colunas

<details><summary>Deletando colunas do arquivo</summary>
  Deletando a coluna "#" para não ocorrer problemas para o índice
</details>

```
df = df.drop(columns=['#'])
```

### Colunas e dados

<details><summary>Dados que contem nas colunas</summary>
  Mostrando os dados
</details>

```
df[['Name', 'Type 1', 'Type 2', 'HP', 'Attack', 'Defense', 'Sp. Atk', 'Sp. Def', 'Speed', 'Generation', 'Legendary']]
```

### Criando colunas

<details><summary>Criando uma nova coluna</summary>
  Criando uma coluna que vai somar os ataques e defesas
</details>

```
df['Total'] = df['HP'] + df['Attack'] + df['Defense'] + df['Sp. Atk'] + df['Sp. Atk'] + df['Sp. Def'] + df['Speed']
```

- ## Evolução dos 10 primeiros Pokemons

### Principais Pokemons

<details><summary>1°</summary>
  Evolução: Bulbasaur > Ivysaur > Venusaur
</details>

```
df.iloc[0:3]
```

<details><summary>2°</summary>
  Evolução: Charmander > Charmeleon > Charizard
</details>

```
df.iloc[4:7]
```

<details><summary>3°</summary>
  Evolução: Squirtle > Wartortle >Blastoise
</details>

```
df.iloc[9:12]
```

<details><summary>4°</summary>
  Evolução: Caterpie > Metapod > Butterfree
</details>

```
df.iloc[13:16]
```

<details><summary>5°</summary>
  Evolução: Weedle > Kakuna > Beedrill
</details>

```
df.iloc[16:19]
```

<details><summary>6°</summary>
  Evolução: Pidgey > Pidgeotto > Pidgeot
</details>

```
df.iloc[20:23]
```

<details><summary>7°</summary>
  Evolução: Rattata > Raticate
</details>

```
df.iloc[24:26]
```

<details><summary>8°</summary>
  Evolução: Speaarow > Fearow
</details>

```
df.iloc[26:28]
```

<details><summary>9°</summary>
  Evolução: Ekans > Arbok
</details>

```
df.iloc[28:30]
```


<details><summary>10°</summary>
  Evolução: Pichu > Pikachu > Raichu
</details>

```
df.sort_values(['Name']).loc[df['Name'].str.contains('chu') & (df['Attack'] >= 40)]
```


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

### Deletando Colunas

<details><summary>Deletando colunas do arquivo</summary>
  Deletando a coluna "#" para não ocorrer problemas para o índice
</details>

```
df = df.drop(columns=['#'])
```

### Colunas e Dados

<details><summary>Dados que contem nas colunas</summary>
  Mostrando os dados
</details>

```
df[['Name', 'Type 1', 'Type 2', 'HP', 'Attack', 'Defense', 'Sp. Atk', 'Sp. Def', 'Speed', 'Generation', 'Legendary']]
```

### Criando Colunas

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

- ## Os Pokemons mais fortes e mais fracos de todos os tipos

### Os 10 mais fortes e fracos

<details><summary>Tipo Normais Fortes</summary>
  Os 10 Pokemons do tipo Normal mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Normal')].iloc[0:10]
```

<details><summary>Tipo Normais Fracos</summary>
  Os 10 Pokemons do tipo Normal mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Normal')].iloc[0:10]
```


<details><summary>Tipo Fogo Fortes</summary>
  Os 10 Pokemons do tipo fogo mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fire')].iloc[0:10]
```

<details><summary>Tipo Fogo Fracos</summary>
  Os 10 Pokemons do tipo fogo mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fire')].iloc[0:10]
```

<details><summary>Tipo Água Fortes</summary>
  Os 10 Pokemons do tipo água mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Water')].iloc[0:10]
```

<details><summary>Tipo Água Fracos</summary>
  Os 10 Pokemons do tipo água mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Water')].iloc[0:10]
```

<details><summary>Tipo Elétricos Fortes</summary>
  Os 10 Pokemons do tipo elétrico mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Electric')].iloc[0:10]
```

<details><summary>Tipo Elétrico Fracos</summary>
  Os 10 Pokemons do tipo elétrico mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Electric')].iloc[0:10]
```

<details><summary>Tipo Grama Fortes</summary>
  Os 10 Pokemons do tipo grama mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Grass')].iloc[0:10]
```

<details><summary>Tipo Grama Fracos</summary>
  Os 10 Pokemons do tipo grama mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Grass')].iloc[0:10]
```

<details><summary>Tipo Gelo Fortes</summary>
  Os 10 Pokemons do tipo gelo mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ice')].iloc[0:10]
```

<details><summary>Tipo Gelo Fracos</summary>
  Os 10 Pokemons do tipo gelo mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ice')].iloc[0:10]
```

<details><summary>Tipo Lutador Fortes</summary>
  Os 10 Pokemons do tipo lutador mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fighting')].iloc[0:10]
```

<details><summary>Tipo Lutador Fracos</summary>
  Os 10 Pokemons do tipo lutador mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fighting')].iloc[0:10]
```

<details><summary>Tipo Veneno Fortes</summary>
  Os 10 Pokemons do tipo veneno mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Poison')].iloc[0:10]
```

<details><summary>Tipo Veneno Fracos</summary>
  Os 10 Pokemons do tipo veneno mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Poison')].iloc[0:10]
```

<details><summary>Tipo Terra Fortes</summary>
  Os 10 Pokemons do tipo terra mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ground')].iloc[0:10]
```

<details><summary>Tipo Terra Fracos</summary>
  Os 10 Pokemons do tipo terra mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ground')].iloc[0:10]
```

<details><summary>Tipo Voador Fortes</summary>
  Os 10 Pokemons do tipo voador mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Flying')].iloc[0:10]
```

<details><summary>Tipo Voador Fracos</summary>
  Os 4 Pokemons do tipo voador mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Flying')].iloc[0:10]
```

<details><summary>Tipo Psíquico Fortes</summary>
  Os 10 Pokemons do tipo psíquico mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Psychic')].iloc[0:10]
```

<details><summary>Tipo Psíquico Fracos</summary>
  Os 10 Pokemons do tipo psíquico mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Psychic')].iloc[0:10]
```

<details><summaryTipo Inseto Fortes></summary>
  Os 10 Pokemons do tipo inseto mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Bug')].iloc[0:10]
```

<details><summary>Tipo Inseto Fracos</summary>
  Os 10 Pokemons do tipo inseto mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Bug')].iloc[0:10]
```

<details><summary>Tipo Pedra Fortes</summary>
  Os 10 Pokemons do tipo pedra mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Rock')].iloc[0:10]
```

<details><summary>Tipo Pedra Fracos</summary>
  Os 10 Pokemons do tipo pedra mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Rock')].iloc[0:10]
```

<details><summary>Tipo Fantasma Fortes</summary>
  Os 10 Pokemons do tipo fantasma mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ghost')].iloc[0:10]
```

<details><summary>Tipo Fantasma Fracos</summary>
  Os 10 Pokemons do tipo fantasma mais fracos 
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ghost')].iloc[0:10]
```

<details><summary>Tipo Dragão Fortes</summary>
  Os 10 Pokemons do tipo dragão mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Dragon')].iloc[0:10]
```

<details><summary>Tipo Dragão Fracos</summary>
  Os 10 Pokemons do tipo dragão mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Dragon')].iloc[0:10]
```

<details><summary>Tipo Noturno Fortes</summary>
  Os 10 Pokemons do tipo noturno mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Dark')].iloc[0:10]
```

<details><summary>Tipo Noturno Fracos</summary>
  Os 10 Pokemons do tipo noturno mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Dark')].iloc[0:10]
```

<details><summary>Tipo Aços Fortes</summary>
  Os 10 Pokemons do tipo aço mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Steel')].iloc[0:10]
```

<details><summary>Tipo Aços Fracos</summary>
  Os 10 Pokemons do tipo aço mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Steel')].iloc[0:10]
```

<details><summary>Tipo Fada Fortes</summary>
  Os 10 Pokemons do tipo fada mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fairy')].iloc[0:10]
```

<details><summary>Tipo Fada Fracos</summary>
  Os 10 Pokemons do tipo fada mais fracos
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fairy')].iloc[0:10]
```

- ## A contagem de todos os tipos de Pokemons

<details><summary>Todos os Tipos de Pokemons</summary>
  Contando quantos Pokemons de todos os tipos existem no arquivo
</details>

```
df.groupby(['Type 1']).count()
```

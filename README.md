# Pokemon
- Analysis made from a Dataset with Pokemon data using Python and the Pandas library

![full_pokemon](https://user-images.githubusercontent.com/51414398/76796676-b9f27f80-67aa-11ea-8258-e04c0fd579f3.jpg)

- In this project I used a Dataset from the Kiggle website of an anime called Pokemon, this project is similar to my other repository called Yu-Gi-Oh which I also got from the Kiggle website. Then it will show the evolution of the main Pokemons, the strongest and weakest Pokémon of all types, the count of all types of Pokemons such as water or fire and to finish I passed everything to some types of graphics for you my consecrated to have a sense of the incredible things that we can do in the field of Data Science.


### Modules
Importing Libraries

<details><summary>Pandas</summary>
  Importing the Pandas library for data analysis
</details>

```
import pandas as pd
```

<details><summary>Matplotlib</summary>
  Importing the matplotlib library for graphics
</details>

```
import matplotlib.pyplot as plt
```

### Reading

<details><summary>Reading file</summary>
  Creating a variable that will store a file and reading it
  </details>
  
 ```
 df = pd.read_csv('pokemon_data.csv')
 ```

### Columns

<details><summary>File columns</summary>
  All columns in the file
</details>

```
df.columns
```

### Deleting Columns

<details><summary>Deleting columns from the file</summary>  
  Deleting the "#" column to avoid problems with the index
</details>

```
df = df.drop(columns=['#'])
```

### Columns and Data

<details><summary>Data in columns</summary>
  Showing the data
</details>

```
df[['Name', 'Type 1', 'Type 2', 'HP', 'Attack', 'Defense', 'Sp. Atk', 'Sp. Def', 'Speed', 'Generation', 'Legendary']]
```

### Creating columns

<details><summary>Creating a new column</summary>
  Creating a column that will add the attacks and defenses
</details>

```
df['Total'] = df['HP'] + df['Attack'] + df['Defense'] + df['Sp. Atk'] + df['Sp. Atk'] + df['Sp. Def'] + df['Speed']
```

- ## Evolution of the first 10 Pokémon

### Main Pokemon

<details><summary>1°</summary>
  Evolution: Bulbasaur > Ivysaur > Venusaur
</details>

```
df.iloc[0:3]
```

<details><summary>2°</summary>
  Evolution: Charmander > Charmeleon > Charizard
</details>

```
df.iloc[4:7]
```

<details><summary>3°</summary>
  Evolution: Squirtle > Wartortle >Blastoise
</details>

```
df.iloc[9:12]
```

<details><summary>4°</summary>
  Evolution: Caterpie > Metapod > Butterfree
</details>

```
df.iloc[13:16]
```

<details><summary>5°</summary>
  Evolution: Weedle > Kakuna > Beedrill
</details>

```
df.iloc[16:19]
```

<details><summary>6°</summary>
  Evolution: Pidgey > Pidgeotto > Pidgeot
</details>

```
df.iloc[20:23]
```

<details><summary>7°</summary>
  Evolution: Rattata > Raticate
</details>

```
df.iloc[24:26]
```

<details><summary>8°</summary>
  Evolution: Speaarow > Fearow
</details>

```
df.iloc[26:28]
```

<details><summary>9°</summary>
  Evolution: Ekans > Arbok
</details>

```
df.iloc[28:30]
```


<details><summary>10°</summary>
  Evolution: Pichu > Pikachu > Raichu
</details>

```
df.sort_values(['Name']).loc[df['Name'].str.contains('chu') & (df['Attack'] >= 40)]
```

- ## The strongest and weakest Pokemon of all types

### The 10 strongest and weakest

<details><summary>Strong Normal Type</summary>
  The 10 strongest Normal Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Normal')].iloc[0:10]
```

<details><summary>Type Normal Weak</summary>
  The 10 weakest Normal Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Normal')].iloc[0:10]
```


<details><summary>Strong Fire Type</summary>
  The 10 strongest fire Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fire')].iloc[0:10]
```

<details><summary>Weak Fire Type</summary>
  The 10 weakest fire type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fire')].iloc[0:10]
```

<details><summary>Strong Water Type</summary>
  The 10 strongest water-type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Water')].iloc[0:10]
```

<details><summary>Poor Water Type</summary>
  The 10 weakest water type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Water')].iloc[0:10]
```

<details><summary>Type Electric Strong</summary> 
  The 10 strongest electric type Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Electric')].iloc[0:10]
```

<details><summary>Weak Electric Type</summary>
  The 10 weakest electric type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Electric')].iloc[0:10]
```

<details><summary>Strong Grass Type</summary>
  The 10 strongest grass-type Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Grass')].iloc[0:10]
```

<details><summary>Weak Grass Type</summary>
  The 10 weakest grass-type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Grass')].iloc[0:10]
```

<details><summary>Strong Ice Type</summary> 
  The 10 strongest ice type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ice')].iloc[0:10]
```

<details><summary>Weak Ice Type</summary>
  The 10 weakest ice type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ice')].iloc[0:10]
```

<details><summary>Strong Fighter Type</summary>
  The 10 strongest fighter type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fighting')].iloc[0:10]
```

<details><summary>Weak Fighter Type</summary>
 The 10 weakest fighter Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fighting')].iloc[0:10]
```

<details><summary>Strong Poison Type</summary>
  Os 10 Pokemons do tipo veneno mais fortes
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Poison')].iloc[0:10]
```

<details><summary>Weak Poison Type</summary>
  The 10 weakest poison Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Poison')].iloc[0:10]
```

<details><summary>Strong Earth Type</summary>
  The 10 strongest earth-type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ground')].iloc[0:10]
```

<details><summary>Weak Earth Type</summary>
 The 10 weakest earth type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ground')].iloc[0:10]
```

<details><summary>Strong Flying Type</summary>
  The 10 strongest flying type Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Flying')].iloc[0:10]
```

<details><summary>Weak Flying Type</summary> 
  The 4 weakest flying type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Flying')].iloc[0:10]
```

<details><summary>Strong Psychic Type</summary>
  The 10 strongest psychic type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Psychic')].iloc[0:10]
```

<details><summary>Weak Psychic Type</summary>
  The 10 weakest psychic type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Psychic')].iloc[0:10]
```

<details><summary>Strong Insect Type></summary>
  The 10 strongest insect-type Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Bug')].iloc[0:10]
```

<details><summary>Type Insect Weak</summary>
  The 10 weakest insect type Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Bug')].iloc[0:10]
```

<details><summary>Type Strong Stone</summary>
  The 10 strongest stone type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Rock')].iloc[0:10]
```

<details><summary>Type Weak Stone</summary>
  The 10 weakest stone Pokemon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Rock')].iloc[0:10]
```

<details><summary>Strong Ghost Type</summary>
  The 10 strongest ghost type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Ghost')].iloc[0:10]
```

<details><summary>Weak Phantom Type</summary>
  The 10 weakest ghost type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Ghost')].iloc[0:10]
```

<details><summary>Strong Dragon Type</summary>
 The 10 strongest dragon type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Dragon')].iloc[0:10]
```

<details><summary>Weak Dragon Type</summary>
  The 10 weakest dragon type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Dragon')].iloc[0:10]
```

<details><summary>Strong Night Type</summary>
  The 10 strongest night type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Dark')].iloc[0:10]
```

<details><summary>Weak Night Type</summary>
  The 10 weakest night type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Dark')].iloc[0:10]
```

<details><summary>Type Strong Steels</summary>
  The 10 strongest steel-type Pokémon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Steel')].iloc[0:10]
```

<details><summary>Type Weak Steels</summary>
  The 10 weakest steel-type Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Steel')].iloc[0:10]
```

<details><summary>Strong Fairy Type</summary>
  The 10 strongest fairy Pokemon
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Type 1'] == 'Fairy')].iloc[0:10]
```

<details><summary>Weak Fairy Type</summary>
  The 10 weakest fairy Pokémon
</details>

```
df.sort_values('Total', ascending=True).loc[(df['Type 1'] == 'Fairy')].iloc[0:10]
```

- ## Counting all types of Pokemon

<details><summary>All Types of Pokemons</summary>
  Counting how many Pokemons of all types are in the file
</details>

```
df.groupby(['Type 1']).count()
```

<details><summary>Calculating</summary>
  Calculating all types of Pokémon
</details>

```
bug = df[df['Type 1'] == 'Bug'].shape[0]
dark = df[df['Type 1'] == 'Dark'].shape[0]
dragon = df[df['Type 1'] == 'Dragon'].shape[0]
eletric = df[df['Type 1'] == 'Eletric'].shape[0]
fairy = df[df['Type 1'] == 'Fairy'].shape[0]
fighting = df[df['Type 1'] == 'Fighting'].shape[0]
fire = df[df['Type 1'] == 'Fire'].shape[0]
flying = df[df['Type 1'] == 'Flying'].shape[0]
ghost = df[df['Type 1'] == 'Ghost'].shape[0]
grass = df[df['Type 1'] == 'Grass'].shape[0]
ground = df[df['Type 1'] == 'Ground'].shape[0]
ice = df[df['Type 1'] == 'Ice'].shape[0]
normal = df[df['Type 1'] == 'Normal'].shape[0]
poison = df[df['Type 1'] == 'Poison'].shape[0]
psychic = df[df['Type 1'] == 'Psychic'].shape[0]
rock = df[df['Type 1'] == 'Rock'].shape[0]
steel = df[df['Type 1'] == 'Steel'].shape[0]
water = df[df['Type 1'] == 'Water'].shape[0]
```

- ## Graphics View

<details><summary>Graphic 1</summary>
  Percentage of Pokemon types
</details>

```
# Protecting Area

figl, axl = plt.subplots()

# Graphics

axl.pie(tamanhos, labels=tipos, autopct='%1.1f%%', shadow=True, startangle=100)

# Circle chart
axl.axis('equal')
plt.title('Porcentagem dos tipos de Pokemons')
plt.plot
fig=plt.gcf()
fig.set_size_inches(10,10)

plt.show()

```

<details><summary>Graph 2</summary>
  Fire Vs Water
</details>

```
# Type 1 and 2 containing all types of Fire Pokémon
fogo = df[(df['Type 1'] == 'Fire') | ((df['Type 2']) == 'Fire')]


# Type 1 and 2 containing all types of Water Pokemons
agua = df[(df['Type 1'] == 'Water') | ((df['Type 2']) == 'Water')]


# Graphic Scatter PLot
plt.scatter(fogo.Attack.head(50), fogo.Defense.head(50), color='R', label = 'Fire', marker='*', s=50)

plt.scatter(agua.Attack.head(50), agua.Defense.head(50), color='B', label = 'Water', s=25)

plt.xlabel("ATAQUE")
plt.ylabel("DEFESA")
plt.legend()
plt.plot()
fig = plt.gcf()
fig.set_size_inches(12,12) #
plt.show()
```

<details><summary>Graphic 3</summary>
  Pokemon numbers by types and generations
</details>

```
tipo = df.groupby(['Generation', 'Type 1']).count().reset_index()
tipo = tipo[['Generation', 'Type 1', 'Total']]
tipo = tipo.pivot('Generation','Type 1','Total')
tipo[['Grass', 'Water', 'Fire', 'Rock', 'Normal', 'Dragon', 'Flying', 'Electric', 'Bug', 'Dark', 'Fairy', 'Fighting',
     'Fire', 'Ghost', 'Ground', 'Ice', 'Poison', 'Psychic', 'Steel']].plot(color= ['G', '#1E90FF', 'R', '#363636', 
     '#00FFFF', '#F4A460', '#FF4500', '#FFFF00', '#7FFFD4', '#000000','#6A5ACD','#CD5C5C', '#FF1493', 
     '#8A2BE2', '#F5DEB3', '#556B2F', '#5F9EA0'], marker='o')

fig=plt.gcf()
fig.set_size_inches(18,10)
plt.show()
```

# Exercício 1
#### Estruturas de Dados com JSON

## Requisitos:

- Clone o projeto [`python-cli-starter`](https://github.com/thothinnovations/python-cli-starter) no GitHub e leia seu `README.md`
- Use o arquivo [`nobel-prizes.json`](nobel-prizes.json) como sua fonte de dados

<br/>

## Instruções

#### Escreva commandos para rodar com **`py -m cli <command-name>`** seguindo suas instruções:
- [Comando 1: `all-categories`](#comando-1)
- [Comando 2: `laureates-from`](#comando-2)
- [Comando 3: `from-category`](#comando-3)
- [Comando 4: `single-laureates`](#comando-4)

---

<br/>

### Comando 1
Um comando chamado **`all-categories`** que mostre uma lista com todas as categorias contempladas pelo pelo Prêmio Nobel: 
- **A lista deve ser bem formatada e não pode conter repetições**
- Por fim, o comando deve printar `XX Nobel Prize categories listed.`, onde: 
  - `XX` é o número de categorias listadas.

---

<br/>

### Comando 2
Um comando chamado **`laureates-from`** que receba os argumentos **`category` e `year`** e mostre uma lista **bem formatada** de todos os laureados da categoria `category` no ano `year`.
- Por fim, o comando deve printar `XX {category} laureates in {year} listed.` onde: 
  - `XX` é o número de laureados listados
  - `category` é a categoria selecionada
  - `year` é o ano selecionado
- Se nenhum laureado for encontrado, o comando deve printar: 
  - `No laureates found for {category} in {year}` (seguindo a formatação anterior)

---

<br/>

### Comando 3

Um comando chamado **`from-category`** que receba o argumento **`category`** e mostre uma lista **bem formatada** com todos os laureados da categoria `category`:
- Cada laureado listado deve ter seu campo **`id`** removido
- Cada laureado listado deve ser acrescido das seguintes informações **da categoria**:
  - **`year`** o ano da premiação
  - **`overallMotivation`** (se disponível) a motivação geral da premiação
- Por fim, o comando deve printar `XX {category} laureates listed.` onde: 
  - `XX` é o número de laureados listados
  - `category` é a categoria selecionada

#### Exemplo da saída esperada (categoria `physics`):
Note os campos presentes e ausentes em cada laureado:
```json
[
    (...)
    {
       "firstname": "Donna",
       "surname": "Strickland",
       "motivation": "for their method of generating high-intensity, ultra-short optical pulses",
       "share": "4",
       "year": "2018",
       "overallMotivation": "for groundbreaking inventions in the field of laser physics"
    },
    {
       "firstname": "Rainer",
       "surname": "Weiss",
       "motivation": "for decisive contributions to the LIGO detector and the observation of gravitational waves",
       "share": "2",
       "year": "2017"
    },
    {
       "firstname":" Barry C.",
       "surname": "Barish",
       "motivation": "for decisive contributions to the LIGO detector and the observation of gravitational waves",
       "share": "4",
       "year": "2017"
    },
    (...)
]
```
```
97 physics laureates listed.
```
> **Obs.:**<br/>O número 97 acima é apenas ilustrativo e fictício

---

<br/>

### Comando 4

Um comando chamado **`single-laureates`** sem argumentos que mostre uma lista **bem formatada** com todas as **premiações** que contenham **apenas um laureado**:
- A lista `laureates` de cada prêmio deve ser substituída por um objeto `laureate` com:
  - os campos **`id`** e **`share`** removidos
  - os campos **`firstname`** e **`surname`** concatenados em um só campo `name`
- Por fim, o comando deve printar `XX prizes with single laureates were listed.` onde `XX` é o número de laureados listados

#### Exemplo da saída esperada:
Note os campos ausentes / presentes em cada `laureate`:
```json
[
    {
       "year": "2024",
       "category": "literature",
       "laureate": {
          "name": "Kang Han",
          "motivation": "for her intense poetic prose that confronts historical traumas and exposes the fragility of human life"
       }
    },
    {
       "year": "2024",
       "category": "peace",
       "laureate": {
          "name": "Nihon Hidankyo",
          "motivation": "for its efforts to achieve a world free of nuclear weapons and for demonstrating through witness testimony that nuclear weapons must never be used again"
       }
    },
    {
       "year": "2023",
       "category": "economics",
       "laureate": {
          "name": "Claudia Goldin",
          "motivation": "for having advanced our understanding of womens labour market outcomes",
       }
    },
    (...)
]
```
```
23 prizes with single laureates were listed.
```
> **Obs.:**<br/>O número 23 acima é apenas ilustrativo e fictício
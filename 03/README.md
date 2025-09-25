# Exercício 3
#### Estruturas de Dados com CSV

## Novidades neste exercício
Você também usará dados **estruturados** com:
- `Decimal` (para cálculos numéricos determinísticos e arredondamento configurável)
- `datetime` (para parsing/agrupamento/ordenação por tempo)

## Requisitos

- Clone o projeto [`python-cli-starter`](https://github.com/thothinnovations/python-cli-starter) no GitHub e leia seu `README.md`
- Use o arquivo **`weather_feed_data_750k.csv`** como fonte de dados: é um `.csv` contendo uma **série temporal** com 750 mil entradas: 
  - É um feed de dados meteorológicos dos municípios de **MG - Brasil**, com amostragem a cada 10 minutos.

<br/>

## Instruções

#### Escreva commandos para rodar com **`py -m cli <command-name>`** seguindo suas instruções:
- [Comando 1: `top`](#comando-1)
- [Comando 2: `all-top`](#comando-2)
- [Comando 3: `???`](#comando-3)
- [Comando 4: `???`](#comando-4)
- [Comando 5: `???`](#comando-5)

---

<br/>

### Comando 1

Um comando chamado **`top`** que mostre as **N mínimas OU máximas** registradas **para um determinado município** em uma única métrica.

**Argumentos posicionais (nesta ordem):**
1. **`metric`** *(str, obrigatório, apenas um)*:
   - `"temp"` para `temperature` 
   - `"humidity"` para `humidity_relative` 
   - `"pressure"` para `pressure_kpa` 
   - `"wind"` para `wind_speed_kmh`
   
2. **`extreme`** *(str, obrigatório, apenas um)*: 
   - `"min"` para mínima
   - `"max"` para máxima
   
3. **`city_or_code`** *(str, obrigatório)*: nome **OU** código do município (case-insensitive).

**Flags opcionais:**
- `--num` **ou** `-n` *(int, default: 1)*: quantas ocorrências extremas são exibidas.

**Regras de processamento/saída:**
- Filtre o dataset pelo município (por nome **ou** código).
- Se `extreme = "min"`, ordene por valor **asc**; se `"max"`, por valor **desc**.
- Considere empates (valores iguais) respeitando a ordenação por `timestamp` **asc** como critério secundário.
- A saída deve uma lista de objetos **bem formatada**, contendo para cada objeto: `timestamp`, `city`, `code` e `value` (como string com sua unidade):
    - `°C` para temperatura (com uma casa decimal, arredondado para cima)
    - `kPa` para pressão (com uma casa decimal, arredondado para cima)
    - `km/h` para vento (com NENHUMA casa decimal, arredondado para cima)
    - `%` para humidade (com NENHUMA casa decimal, arredondado para cima)
- Ao final, printar:  
  `Top {N} {extreme} {metric} for {city} ({code}) listed.`

#### Exemplo de saída esperada

```json
[
  {
    "timestamp": "2024-10-01 03:40:00",
    "city": "Pouso Alegre",
    "code": "POUS",
    "value": "12.3 °C"
  },
  {
    "timestamp": "2024-10-02 05:50:00",
    "city": "Pouso Alegre",
    "code": "POUS",
    "value": "12.4 °C"
  }
]
````

```
Top 2 min temperatures for Pouso Alegre (POUS) listed.
```

---

<br/>

### Comando 2

Continua...
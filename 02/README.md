# Exercício 2
#### Estruturas de Dados com CSV

## Requisitos

- Clone o projeto [`python-cli-starter`](https://github.com/thothinnovations/python-cli-starter) no GitHub e leia seu `README.md`
- Use o arquivo **`products-60k.csv`** como fonte de dados: é um `.csv` com 60 mil produtos listados.

<br/>

## Instruções

#### Escreva commandos para rodar com **`py -m cli <command-name>`** seguindo suas instruções:
- [Comando 1: `all-categories`](#comando-1)
- [Comando 2: `low-stock`](#comando-2)
- [Comando 3: `top-brands`](#comando-3)
- [Comando 4: `products-from`](#comando-4)

---

<br/>

### Comando 1

Um comando chamado **`all-categories`** sem argumentos que mostre uma lista **bem formatada** com todas as categorias e a **contagem de produtos listados em cada uma**.

- Não repita categorias.
- Os resultados devem ser ordenados por `count` (descendente).
- Ao final, printar: `XX categories were listed, with a total of YY products.` onde
  - `XX` é o número de categorias listadas
  - `YY` é a soma de todas as quantidades de produtos

#### Exemplo da saída esperada

```json
[
  {
    "category": "Electronics", 
    "count": 248
  },
  {
    "category": "Home & Kitchen", 
    "count": 173
  }
]
```

```
2 categories were listed, with a total of 421 products.
```

---

<br/>

### Comando 2

Um comando chamado **`low-stock`** que receba o argumento **`min_stock`** e mostre uma lista **bem formatada** de produtos cujo **`stock` seja menor ou igual a `min_stock`**: 
- Cada produto listado deve incluir: `id`, `name`, `category`, `stock` e `price`.
- Ordene por `stock` (asc).
- Ao final, printar: `There are XX products with {min_stock} or less units in stock.`

#### Exemplo da saída esperada

```json
[
  {
    "id": 221, 
    "name": "Bluetooth Speaker Mini", 
    "category": "Electronics", 
    "stock": 1, 
    "price": 149.0
  },
  {
    "id": 944, 
    "name": "Chef Knife 8\"", 
    "category": "Home & Kitchen", 
    "stock": 3, 
    "price": 99.9
  }
]
```

```
There are 2 products with 3 or less units in stock.
```

---

<br/>

### Comando 3

Um comando chamado **`top-brands`** que receba os argumentos **`category`** e **`limit` (com padrão 10)** e mostre as **N marcas** com mais produtos na categoria:

- Cada marca listada deve incluir: `brand`, `count` e `average_price`.
- `average_price` deve ser o preço médio dos produtos da marca, arredondado para duas casas decimais
- Os resultados devem ser ordenados por `count` (descendente).
- Ao final, printar: `Top N brands in {category} listed.`

#### Exemplo da saída esperada

```json
[
  {
    "brand": "Acme", 
    "count": 18, 
    "average_price": 42.35
  },
  {
    "brand": "Volt", 
    "count": 12, 
    "average_price": 38.1
  },
  {
    "brand": "Nova", 
    "count": 9, 
    "average_price": 27.55
  }
]
```

```
Top 3 brands in Electronics listed.
```

---

<br/>

### Comando 4

Um comando chamado **`products-from`** que receba o argumento **`category`** e suporte as flags opcionais **`(--price_min, --min)`** e **`(price_max, --max)`**, que mostre uma lista **bem formatada** dos produtos da categoria: 
- Cada produto listado deve conter `id`, `name`, `brand` (se houver) e `price`.
- Os resultados devem ser ordenados por `price` (ascendente).
- Ao final, printar: 
```
XX products in {category} were found with:
- Minimum price: {price_min}
- Maximum price: {price_max}
```
> Onde `XX` deve ser o número de produtos listados

#### Exemplo da saída esperada

```json
[
  {
    "id": 1021, 
    "name": "USB-C Cable 1m", 
    "brand": "Acme", 
    "price": 19.9
  },
  {
    "id": 875, 
    "name": "USB-C Charger 20W", 
    "brand": "Volt", 
    "price": 59.0
  }
]
```

```
2 products in cables were found with:
- Minimum price: 19.90
- Maximum price: 59.00
```
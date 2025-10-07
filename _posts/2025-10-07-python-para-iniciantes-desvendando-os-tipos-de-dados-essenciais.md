---
title: 'Python para Iniciantes: Desvendando os tipos de dados essenciais'
date: Thu, 07 Oct 2025 07:30:00 +0000
draft: false
tags: ['python', 'google colab', 'colab', 'programação para iniciante', 'iniciante', 'aprender a programar', 'artigo', 'guia', 'tipos de dados']
---

Se você está começando, saiba que o Python é uma das linguagens mais amigáveis para iniciantes, e o Google Colab é o seu laboratório perfeito para praticar.

Neste artigo, vamos desvendar um dos conceitos mais fundamentais de qualquer linguagem de programação: **os Tipos de Dados**. Pense neles como as diferentes categorias de informações que o Python consegue entender e manipular.

---

## O Que São Tipos de Dados?

Imagine que você está organizando uma cozinha. Você não guarda o leite (líquido) da mesma forma que guarda os ovos (sólidos) ou os talheres (objetos de metal). Cada item tem uma natureza diferente e exige um tratamento específico.

Em Python, é a mesma coisa. Quando você cria uma **variável** (aquela "caixinha" que guarda informação), o Python precisa saber que tipo de informação está dentro dela: é um número inteiro? É um texto? É uma lista de itens?

O **Tipo de Dado** é exatamente isso: a classificação que diz ao Python como armazenar e como lidar com aquela informação.

Vamos conhecer os tipos mais importantes para quem está começando. Lembre-se: você pode copiar e colar todos os exemplos de código no seu Google Colab e pressionar **Shift + Enter** para executá-los!

---

## 1. Tipos Numéricos: Contando e Medindo

Os números são a base de qualquer cálculo, e em Python, eles se dividem em duas categorias principais:

### A. Inteiros (`int`)

Os inteiros são números **sem casas decimais** (números "redondos"), sejam eles positivos, negativos ou zero.

**Exemplo Prático no Colab:**

```python
# Declarando variáveis do tipo inteiro (int)
idade = 35
quantidade_alunos = 150
ano_de_nascimento = -1990

# Operações com inteiros
soma = 10 + 5
multiplicacao = 4 * 3

print(f"Minha idade é: {idade}")
print(f"Resultado da soma: {soma}")
print(f"Resultado da multiplicação: {multiplicacao}")
```

### B. Ponto Flutuante (`float`)

Os números de ponto flutuante, ou simplesmente *floats*, são números que possuem **casas decimais**. Eles são usados para representar valores que não são exatos, como preços, medidas ou resultados de divisões.

**Exemplo Prático no Colab:**

```python
# Declarando variáveis do tipo ponto flutuante (float)
preco_produto = 19.99
altura_metros = 1.75
pi = 3.14159

# Operações que resultam em float
divisao = 10 / 3

print(f"O preço é: R$ {preco_produto}")
print(f"Minha altura é: {altura_metros} metros")
print(f"Resultado da divisão: {divisao}")
```

| Tipo    | Descrição                             | Exemplo                 | Uso Comum                              |
|:------- |:------------------------------------- |:----------------------- |:-------------------------------------- |
| `int`   | Números inteiros (sem casas decimais) | `10`, `-5`, `1000`      | Contagem, anos, quantidades exatas     |
| `float` | Números com casas decimais            | `10.5`, `3.14`, `-0.01` | Preços, medidas, resultados de divisão |

---

## 2. Tipo de Texto: Strings (`str`)

O tipo **String** (`str`) é usado para armazenar qualquer sequência de caracteres, ou seja, **textos**. Em Python, você define uma string colocando o texto entre aspas simples (`'`) ou aspas duplas (`"`).

**Exemplo Prático no Colab:**

```python
# Declarando variáveis do tipo string (str)
nome = "Carlos"
mensagem = 'Bem-vindo ao curso de Python!'
frase_longa = "O Colab é ótimo para aprender a programar."

# Concatenando (juntando) strings
saudacao = "Olá, " + nome + "!"

print(saudacao)
print(f"O tamanho da mensagem é: {len(mensagem)} caracteres")
```

**Dica:** A função `len()` é muito útil para strings, pois ela retorna o número de caracteres que o texto possui.

---

## 3. Tipo de Coleção: Listas (`list`)

As listas são um dos tipos de dados mais poderosos e flexíveis do Python. Uma **Lista** (`list`) é uma coleção ordenada de itens. Pense nela como uma lista de supermercado: você pode guardar diferentes tipos de itens (textos, números, e até outras listas!) dentro dela.

Você define uma lista usando **colchetes** (`[]`) e separando os itens por vírgulas.

**Exemplo Prático no Colab:**

```python
# Declarando uma lista (list)
lista_compras = ["Pão", "Leite", "Ovos", "Café"]
numeros_primos = [2, 3, 5, 7, 11]
dados_misturados = ["Ana", 25, 1.70, True] # Listas podem misturar tipos!

# Acessando itens da lista (a contagem começa em 0!)
primeiro_item = lista_compras[0]
segundo_item = lista_compras[1]

# Adicionando um novo item
lista_compras.append("Manteiga")

print(f"A lista original é: {lista_compras}")
print(f"O primeiro item é: {primeiro_item}")
print(f"A lista atualizada é: {lista_compras}")
```

**Conceito Chave: Índice (Indexação)**

Em Python, a contagem de itens em uma lista **sempre começa em zero (0)**. O primeiro item está no índice 0, o segundo no índice 1, e assim por diante. Isso é crucial para acessar e manipular os elementos de uma lista.

---

## Como o Python Sabe o Tipo? (A Função `type()`)

Uma das grandes vantagens do Python é que você não precisa dizer explicitamente qual é o tipo da variável. O Python é "inteligente" e descobre isso automaticamente.

Mas, se você quiser conferir qual é o tipo de uma variável, pode usar a função `type()`.

**Exemplo Prático no Colab:**

```python
# Variáveis de teste
idade = 28
salario = 1500.50
nome = "Pedro"
itens = ["Mouse", "Teclado"]

# Usando a função type() para verificar
print(f"O tipo da variável 'idade' é: {type(idade)}")
print(f"O tipo da variável 'salario' é: {type(salario)}")
print(f"O tipo da variável 'nome' é: {type(nome)}")
print(f"O tipo da variável 'itens' é: {type(itens)}")
```

**Saída Esperada:**

```
O tipo da variável 'idade' é: <class 'int'>
O tipo da variável 'salario' é: <class 'float'>
O tipo da variável 'nome' é: <class 'str'>
O tipo da variável 'itens' é: <class 'list'>
```

---

## Conclusão: O Primeiro Passo para a Lógica

Dominar os tipos de dados é o seu primeiro grande passo na programação. Eles são os blocos de construção de qualquer programa.

| Tipo    | O que armazena            | Como declarar                 | Exemplo         |
|:------- |:------------------------- |:----------------------------- |:--------------- |
| `int`   | Números inteiros          | Sem aspas, sem ponto          | `10`            |
| `float` | Números decimais          | Sem aspas, com ponto          | `10.5`          |
| `str`   | Textos                    | Entre aspas simples ou duplas | `"Olá"`         |
| `list`  | Coleção ordenada de itens | Entre colchetes `[]`          | `["a", 1, 2.5]` |

Agora que você entende como o Python classifica as informações, você está pronto para o próximo nível: **Operadores e Estruturas de Controle**.

Continue praticando no Google Colab! Tente criar suas próprias variáveis, misturar tipos em listas e usar a função `type()` para se familiarizar com cada um deles.

Até a próxima aula!

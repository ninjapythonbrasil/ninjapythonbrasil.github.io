---
title: 'Protegendo dados sensíveis em Python com a biblioteca maskify-py'
date: Thu, 26 Oct 2024 20:30:00 +0000
draft: false
tags: ['proteger', 'python', 'py','dados', 'biblioteca', 'maskify-py', 'sensiveis', 'maskify', 'masker']
---

No cenário atual do desenvolvimento de software, a segurança dos dados é uma prioridade inegociável. Com o aumento das preocupações sobre privacidade e proteção de informações sensíveis, como números de cartões de crédito, senhas e dados pessoais, é essencial que os desenvolvedores adotem práticas eficazes para proteger essas informações. Neste artigo, vamos explorar a biblioteca [maskify-py](https://pypi.org/project/maskify-py/), uma ferramenta que desenvolvi para mascarar dados sensíveis em aplicações Python, inspirada na já existente [Maskify.Core](https://github.com/djesusnet/Maskify.Core) desenvolvida para .NET.

## O que é maskify-py?

A [maskify-py](https://pypi.org/project/maskify-py/) é uma biblioteca Python projetada para facilitar a proteção de dados sensíveis através da mascaramento. A ideia é que, ao invés de expor informações críticas em logs ou interfaces de usuário, você possa apresentar uma versão mascarada desses dados, garantindo que a privacidade do usuário seja mantida.

### Principais funcionalidades

- **Mascaramento de números de cartão de crédito:** A biblioteca permite que você oculte todos os dígitos de um número de cartão de crédito, exceto os últimos quatro, que são frequentemente necessários para identificação.

- **Mascaramento de senhas:** As senhas podem ser mascaradas para que não sejam exibidas em texto claro, mesmo em logs de erro ou mensagens de depuração.

- **Flexibilidade:** A biblioteca é projetada para ser fácil de usar e integrar em projetos existentes, permitindo que você aplique o mascaramento de forma rápida e eficiente.

## Como usar maskify-py

Para começar a usar a biblioteca maskify-py, você precisa instalá-la. Você pode fazer isso usando o gerenciador de pacotes `pip`:

```bash
pip install maskify-py
```

### Como usar a biblioteca

A utilização da biblioteca maskify-py é bastante simples. A seguir, apresentamos alguns exemplos básicos de como mascarar número de cartão de crédito, e-mail, cpf, cnpj e até mesmo textos.

#### Exemplo 1 - Máscara de CPF

```python
from maskify.masker import Masker

cpf = "123.456.789-01"
masked_cpf = Masker.mask_cpf(cpf, "*")
print("Masked CPF:", masked_cpf)  

# Output: "123.***.**9-01"
```

#### Exemplo 2 - Máscara de CNPJ

```python
from maskify.masker import Masker

cnpj = "12.345.678/0001-99"
masked_cnpj = Masker.mask_cnpj(cnpj, "*")
print("Masked CNPJ:", masked_cnpj)  

# Output: "12.***.***/**01-99"
```

#### Exemplo 3 - Máscara de e-mail

```python
from maskify.masker import Masker

email = "usuario@exemplo.com"
masked_email = Masker.mask_email(email, "*")
print("Masked email:", masked_email)  

# Output: "u*****o@exemplo.com"
```

#### Exemplo 4 - Máscara de cartão de crédito

```python
from maskify.masker import Masker

credit_card = "1234 1234 1234 1234"
masked_credit_card = Masker.mask_credit_card(credit_card, "*")
print("Masked credit card:", masked_credit_card)  

# Output: "**** **** **** 1234"
```

#### Exemplo 5 - Máscara de telefone 

```python
from maskify.masker import Masker

mobile_phone = "(11) 91234-5678"
masked_mobile_phone = Masker.mask_mobile_phone(mobile_phone)
print("Masked mobile phone:", masked_mobile_phone)  

# Output: "(11) *****-5678"
```

```python
from maskify.masker import Masker

residential_phone = "(11) 1234-5678"
masked_residential_phone = Masker.mask_residential_phone(residential_phone)
print("Masked residential phone:", masked_residential_phone)  

# Output: "(11) ****-5678"
```

#### Exemplo 6 - personalizando a máscara

```python
from maskify.masker import Masker

text = "Confidential"
masked_text = Masker.mask(text, start_position=2, length=8)
print("Masked custom:", masked_text)  

# Output: "Co********al"
```

## Conclusão

A biblioteca [maskify-py](https://pypi.org/project/maskify-py/) é uma solução prática e eficaz para proteger dados sensíveis em aplicações Python. Ao implementar o mascaramento de informações críticas, você não apenas melhora a segurança da sua aplicação, mas também demonstra um compromisso com a privacidade dos usuários.

No próximo artigo, continuaremos a explorar mais recursos e boas práticas de segurança em Python.

Participe do nosso grupo no [WhastApp](https://chat.whatsapp.com/DeshTGsaqy53ZfUDvYzfy9).

Bons estudos e mãos à obra!

#### Referências

- [Documentação da biblioteca maskify-py](https://github.com/ninjapythonbrasil/maskify-py)
- [Repositório do maskify-py no PyPi](https://pypi.org/project/maskify-py/)

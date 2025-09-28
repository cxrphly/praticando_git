# Programar em Python :D

## Ferramentas Necessárias

Antes de começar, você vai precisar de:

- **Visual Studio Code**
- **Python 3.13**
- Extensões para apoio ao código (ex: Python extension da Microsoft, Pylance, Error Lens, Python Indent, Live Code)

### Variáveis — uma "caixa" que guarda algo

Nome da variável recebe valor. Exemplo:

```python
idade = 25
nome = "João"
altura = 1.70
```

#### Exemplos certos:

```python
idade = 25
nome = "Maria"
altura = 1.65
ligado = True
```

#### Exemplos errados (NÃO FAÇA ISSO):

```python
# 1idade = 10            <- não pode começar com número
# nome-da-pessoa = "Ana" <- hífen não é aceito
# if = 20                <- palavra reservada não pode ser usada
```

### Regras para Variáveis

- Começa com `_` ou letra do alfabeto latino.
- Python é **sensível a maiúsculas/minúsculas** (`idade` ≠ `Idade`).
- Pode conter letras, números e `_`.
- Seja descritivo ao criar variáveis.
- Evite palavras reservadas: `if`, `while`, `for`, `class`, `pass`, `continue`, `break`, `def`, `return`, `sum`, `import`, `try`, `except`, entre outras.

### Tipos de Dados

- **Número inteiro** → `int`  
  Ex.: `24`, `1`, `420`

```python
idade: int = 24
```

- **Número quebrado** → `float`  
  Ex.: `1.403`, `4.2`, `0.4`

```python
altura: float = 1.70
```

- **Verdadeiro ou falso** → `bool`  
  Ex.: `True`, `False`

```python
ligado: bool = True
desligado: bool = False
```

- **Texto** → `str`  
  Ex.: `"Oi"`, `"tExTo LeGaL"`, `"Olá Mundo!"`

```python
nome: str = "João"
```

### Mostrando textos na telinha

```python
print("Olá")
texto = "Tudo bem?"
print(texto)  # <- imprimir variáveis de qualquer tipo
print("Idade:", idade, "anos")
```

### Tipagem Dinâmica e Type Hint

Python atribui o tipo automaticamente, mas **type hints** ajudam na leitura.
(Hint = "dica", em inglês)

```python
idade: int = 25
```

### Recebendo Dados

```python
a = input()  # recebe dados do teclado
b = input("Insira sua idade: ")  # texto explicativo
c: int = int(input("Espero um inteiro! "))  # converte entrada em inteiro, poderia ser para decimais com float().
```

### Recebendo vários valores de uma vez só:

```python
d, e, f, g = map(int, input("Digite 4 números separados por espaço: ").split(" "))
# Ex.: entrada "4 5 6 7"
```

# Funções Padrão Essenciais do Python

---

## 1. Funções Matemáticas

## `abs()` - Valor Absoluto

Retorna o **valor absoluto** de um número.

```python
print(abs(-5))        # 5
print(abs(3.14))      # 3.14

# Exemplo prático:
temperatura = -5
print(f"Temperatura absoluta: {abs(temperatura)}°C") # Temperatura absoluta: 5°C
```

## `max()` e `min()` - Maior e Menor Valor

Retornam o maior (max) e o menor (min) valor de uma sequência ou de um conjunto de argumentos.

```python
print(max(10, 20, 5)) # 20
print(min(10, 20, 5)) # 5

numeros = [15, 8, 42, 3, 27]
print(max(numeros))   # 42
print(min(numeros))   # 3

# Com textos (ordem alfabtica)
nomes = ["Ana", "Bruno", "Carlos"]
print(max(nomes))  # "Carlos"
print(min(nomes))  # "Ana"
```

## `round()` - Arredondamento

Arredonda um número para o número inteiro mais próximo ou para um número específico de casas decimais.

```python
print(round(3.14159))    # 3
print(round(3.14159, 2)) # 3.14
print(round(3.14159, 3)) # 3.142
```

### Regra de arredondamento para .5:

### Arredonda para o número par mais próximo

```python
print(round(2.5))        # 2
print(round(3.5))        # 4
```

## 2. Funções para Strings

## `len()` - Tamanho

Retorna o número de itens de um objeto (o comprimento).

```python
texto = "Python"
print(len(texto))    # 6

lista = [1, 2, 3, 4, 5]
print(len(lista))    # 5
```

## Métodos de string que retornam a string em letras maiúsculas ou minúsculas.

```python
texto = "Python é Incrível"
print(texto.upper()) # PYTHON É INCRÍVEL
print(texto.lower()) # python é incrível
```

## 3. Funções de Conversão de Tipo

int(), float(), str()

Funções que convertem valores para os tipos inteiro (int), ponto flutuante (float) ou string (str).

```python
# inteiro (int)
print(int("10"))  # 10
print(int(3.14))  # 3 (descarta decimais)

# float
print(float("3.14")) # 3.14
print(float(10))  # 10.0

# Para string (str)
print(str(100))   # "100"

# Exemplo com input:
idade = int(input("Digite sua idade: "))
print(f"Daqui 10 anos você terá {idade + 10} anos")
```

### bool() - Conversão para Booleano

Converte um valor para um tipo booleano (True ou False). Retorna False para "valores vazios" ou zero.

```python
print(bool(0))        # False
print(bool(1))        # True (qualquer número diferente de zero)

print(bool(""))       # False (vazio)
print(bool("Texto"))  # True (não vazio)
```

---

### Print e Manipulação de Strings

#### Usando f-strings

```python
nome = "João"
idade = 20
print(f"Meu nome é {nome} e tenho {idade} anos.") # aqui voce passa os valores direto no texto, usando as {} e dentro delas a variavel

# Definindo casas decimais
preco = 49.95678
print(f"Preço: R$ {preco:.2f}")        # 2 casas decimais
print(f"Preço: R$ {preco:.1f}")        # 1 casa decimal
print(f"Preço: R$ {preco:.6f}")        # 6 casas decimais
# Saída: Preço: R$ 49.96
#        Preço: R$ 50.0
#        Preço: R$ 49.956780

taxa = 0.1567
print(f"Taxa: {taxa:.1%}")             # Percentual com 1 casa decimal
print(f"Taxa: {taxa:.2%}")             # Percentual com 2 casas decimais
# Saída: Taxa: 15.7%
#        Taxa: 15.67%

nome = "Carlos"
salario = 2500.50
print("Nome: %s, Salário: R$ %.2f" % (nome, salario))
# Saída: Nome: Carlos, Salário: R$ 2500.50
```

#### Usando `.format()`

```python
print("Meu nome é {} e tenho {} anos.".format(nome, idade)) # mesma coisa, porem voce separa a parte de formatacao

pi = 3.14159
print("Pi: {:.2f}".format(pi))         # 2 casas decimais
print("Pi: {:.4f}".format(pi))         # 4 casas decimais
# Saída: Pi: 3.14
#        Pi: 3.1416

x = 10
y = 3
print("{0} + {1} = {2}".format(x, y, x+y))
# Saída: 10 + 3 = 13


```

#### Concatenar strings

```python
print("Olá " + nome + "!") # usando o + vc cola textos ou variveis a textos
```

#### Manipular strings(texto)

```python
texto = "Python é incrível!"
print(texto.upper())  # MAIÚSCULO
print(texto.lower())  # minúsculo
print(texto.replace("Python", "Programar"))  # Substituir texto
```

### Operadores Aritméticos

- `=` → recebe valor
- `+` → soma
- `-` → subtração
- `*` → multiplicação
- `/` → divisão
- `//` → divisão inteira (descarta decimais)
- `%` → resto da divisão (útil para saber se é par/impar)
- `**` → potência

#### Exemplos:

```python
x = 10
y = 3
print(x + y)   # 13
print(x - y)   # 7
print(x * y)   # 30
print(x / y)   # 3.333...
print(x // y)  # 3
print(x % y)   # 1
print(x ** y)  # 1000 (10³)
```

### Operadores Atribuição Composta

#### Exemplos:

```python
x = 5
x += 3  # equivalente a x = x + 3 → 8
x *= 2  # equivalente a x = x * 2 → 16
```

### Operadores Lógicos — Portões Lógicos

- `==` → igual
- `!=` → diferente
- `>` → maior que
- `<` → menor que
- `>=` → maior ou igual a
- `<=` → menor ou igual a
- `and` → E
- `or` → OU
- `not` → negação

#### Exemplos:

```python
a = 5
b = 10
print(a == b)            # False
print(a != b)            # True
print(a > 2 and b < 20)  # True
print(not (a == 5))      # False
```

### Tabelas Verdade

#### and (E)

| A     | B     | A and B |
| ----- | ----- | ------- |
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

#### or (OU)

| A     | B     | A or B |
| ----- | ----- | ------ |
| True  | True  | True   |
| True  | False | True   |
| False | True  | True   |
| False | False | False  |

#### not (negação)

| A     | not A |
| ----- | ----- |
| True  | False |
| False | True  |

### Identaçao em Python - Importante de mais

diferente de outras linguagens, python nao tem delimitadores explicitos como as {} que marcam um bloco de codigo, ou seja precisamos seguir uma regra para escrever nosso codigo, assim o programa consegue executar com sucesso.

```python
# CORRETO - indentação com 4 espaços
if idade >= 18:
    print("Maior de idade")  # ← 4 espaços ou 1 TAB
    print("Pode votar")      # ← 4 espaços ou 1 TAB

# ERRADO - sem indentação
if idade >= 18:
print("Isso vai dar erro")  # ← IndentationError
```

### Estruturas de Seleção

### If, Elif e Else

```python
idade : int= 18
if idade >= 18:
    print("Você é maior de idade!")
elif idade >= 12:
    print("Você é adolescente!")
else:
    print("Você é criança!")
```

### Match Case

```python
letra: str = input("Primeira letra do seu nome: ")
match letra:
    case "h":
        print("A letra H é a sétima letra do alfabeto latino")
    case "m":
        print("A letra M é a décima terceira letra do alfabeto latino")
    case _: # o caso _ é um coringa e voce pode inserir outros blocos de codigo e logicas dentro dele.
        print("Sua letra não está nos casos esperados :(")
```

# Sites de apoio

[W3Schools - Python Tutorial](https://www.w3schools.com/python)
</br>
[GeeksForGeeks - Python Tutorial](https://www.geeksforgeeks.org/python/python-programming-language-tutorial/)
</br>
StackOverflow - fórum tira duvidas

# Exercícios de Programação

---

## 1. Soma de Três Números

**Descrição:** Recebe três números inteiros e retorna a soma deles.

**Entrada:** Três linhas, cada uma com um número inteiro.  
**Saída:** Um único número: a soma.

**Testes:**

```
Entrada:
2
3
4
Saída:
9

Entrada:
12
17
24
Saída:
53
```

---

## 2. Divisão com Quociente e Resto

**Descrição:** Recebe dois inteiros positivos e calcula quociente e resto da divisão.

**Entrada:** Dois inteiros, um por linha.  
**Saída:** Quociente e resto separados por espaço.

**Testes:**

```
Entrada:
51
31
Saída:
1 20

Entrada:
398
50
Saída:
7 48
```

---

## 3. Média Aritmética

**Descrição:** Recebe dois números inteiros e retorna a média.

**Entrada:** Dois números inteiros, um por linha.  
**Saída:** Média com uma casa decimal.

**Testes:**

```
Entrada:
2
4
Saída:
3.0

Entrada:
34
21
Saída:
27.5
```

---

## 4. Conversão Celsius → Fahrenheit

**Descrição:** Converte temperatura em Celsius para Fahrenheit.

**Entrada:** Temperatura em Celsius (float).  
**Saída:** Fahrenheit com 6 casas decimais.

**Testes:**

```
Entrada:
43.0
Saída:
109.400000

Entrada:
55.0
Saída:
131.000000
```

---

## 5. Valor Absoluto da Diferença

**Descrição:** Calcula valor absoluto da diferença entre dois números inteiros.

**Entrada:** Dois números inteiros, um por linha.  
**Saída:** Valor absoluto da diferença.

**Testes:**

```
Entrada:
1
5
Saída:
4

Entrada:
5
1
Saída:
4
```

---

## 6. Maior de Dois Números

**Descrição:** Recebe dois números inteiros e imprime o maior.

**Entrada:** Dois números inteiros.  
**Saída:** Maior número.

**Testes:**

```
Entrada:
4
5
Saída:
5

Entrada:
5
4
Saída:
5
```

---

## 7. Verificação de Número Positivo

**Descrição:** Imprime `"SIM"` se número for maior ou igual a zero, `"NAO"` caso contrário.

**Entrada:** Um número inteiro.  
**Saída:** `"SIM"` ou `"NAO"`.

**Testes:**

```
Entrada:
3
Saída:
SIM

Entrada:
-12
Saída:
NAO
```

---

## 8. Número 3 ou 5

**Descrição:** Imprime `"SIM"` se o número for 3 ou 5, `"NAO"` caso contrário.

**Entrada:** Um número inteiro.  
**Saída:** `"SIM"` ou `"NAO"`.

**Testes:**

```
Entrada:
3
Saída:
SIM

Entrada:
12
Saída:
NAO
```

---

## 9. Pedra, Papel e Tesoura (Jokenpô)

**Descrição:** Recebe as jogadas de dois jogadores e indica quem ganhou.

**Entrada:** Dois caracteres (`R`, `P` ou `S`).  
**Saída:** `"jog1"`, `"jog2"` ou `"empate"`.

**Testes:**

```
Entrada:
R
P
Saída:
jog2

Entrada:
P
P
Saída:
empate

Entrada:
S
P
Saída:
jog1
```

## Resolução a baixo

continue apenas se voce nao conseguiu mesmo resolver.

<br><br><br><br><br>
<br><br><br><br><br>
<br><br><br><br><br>
<br><br><br><br><br>

## Exemplo de Resolução

### Q1

```python
num1 = int(input())
num2 = int(input())
num3 = int(input())
soma = num1 + num2 + num3
print(soma)
```

### Q2

```python
n = int(input())
d = int(input())
quociente = n // d
resto = n % d
print(quociente, resto)
```

### Q3

```python
num1 = int(input())
num2 = int(input())
media = (num1 + num2) / 2
print(f"{media:.1f}")
```

```python
celsius = float(input())
fahrenheit = 1.8 * celsius + 32
print(f"{fahrenheit:.6f}")
```

### Q5

```python
num1 = int(input())
num2 = int(input())
print(abs(num1 - num2))
```

### Q6

```python
num1 = int(input())
num2 = int(input())
print(max(num1, num2))
```

### Q7

```python
numero = int(input())
if numero >= 0:
    print("SIM")
else:
    print("NAO")
```

### Q&

```python
numero = int(input())
if numero == 3 or numero == 5:
    print("SIM")
else:
    print("NAO")
```

### Q9

```python
jogador1 = input().strip().upper()
jogador2 = input().strip().upper()

if jogador1 == jogador2:
    print("empate")
elif (jogador1 == "R" and jogador2 == "S") or      (jogador1 == "S" and jogador2 == "P") or      (jogador1 == "P" and jogador2 == "R"):
    print("jog1")
else:
    print("jog2")
```

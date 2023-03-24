
# Introdução de Clojure

Tudo em clojure é uma função. Isso inclui números, strings, listas, conjuntos, mapas, etc. Isso é o que torna o clojure tão poderoso e flexível.

Esse tutorial é uma introdução ao Clojure. Ele não é um tutorial de Clojure, mas sim uma introdução. O objetivo é mostrar o que é possível fazer com Clojure e como fazer isso. O tutorial não é um guia passo a passo, mas sim uma introdução a linguagem. O objetivo é mostrar o que é possível fazer com Clojure e como fazer isso. O tutorial não é um guia passo a passo, mas sim uma introdução a linguagem. Principalmente para os programadores Python que estão começando a aprender Clojure.


## Primeiro Conceito 

Um `def` é como se fosse uma variavel. E o `defn` é como se fosse uma função.

Exemplo de declarçao de uma variavel x com valor 10:

Em Python:

```python
x = 10
```

Em Clojure:

```clojure
(def x 10)
```

Aqui esta um exemplo de uma função que soma dois números em Python:


```python
def soma(a, b):
    return a + b
```

Aqui esta um exemplo de uma função que soma dois números em Clojure:
    
```clojure
(defn soma [a b]
        (+ a b))
```

Como tudo é uma função, podemos passar funções como argumentos para outras funções. Isso é chamado de *Higher Order Function*.

Se então Python temos a soma de 2 +2 assim:

```python
2 + 2
```
Em Clojure, temos a soma de 2 + 2 assim:
Onde o + é uma função que recebe dois argumentos e retorna a soma deles.

```clojure
(+ 2 2)
```
Um exemplo de 2 + 2 + 5
    
```clojure
(+ 2 2 5)
```

ou

```clojure
(+ (+ 2 2) 5)
```

## Condicionais

Em Python, temos o if assim:

```python
if a > b:
    x = a
else:
    x = b
```

Em Clojure, temos o if assim:

```clojure
(if (> a b)
    x = a
    x = b)
```

Vamos ver uma uma função com condicionais para um variavel é maior que 10 ou não.
Em Python, temos assim:

```python
def maior_que_dez(x):
    if x > 10:
        return True
    else:
        return False
```

Em Clojure, temos assim:

```clojure
(defn maior-que-dez? [x]
    (if (> x 10)
        true
        false))
```

O ? no final do nome da função é uma convenção para indicar que a função retorna um booleano.



## Segundo Conceito

Vamos falar um pouco do lein. Lein é uma ferramenta de linha de comando para gerenciar projetos Clojure. Ele é usado para criar novos projetos, executar testes, executar projetos, gerenciar dependências e muito mais. Ele é o equivalente do pip para Python. Para saber mais sobre o lein, acesse o site oficial pelo link: https://leiningen.org/. 

Vamos criar um novo projeto Clojure com o lein. Para isso, abra o terminal e digite:

```bash
lein new app clojure-introducao
```

Onde clojure-introducao é o nome do projeto.

Isso irá criar a seguinte estrutura de diretórios:

```bash
clojure-introducao
├── project.clj
├── README.md
├── resources
└── src
    └── clojure_introducao
        └── core.clj
```

O arquivo `project.clj` contém informações sobre o projeto, como nome, versão, dependências, etc. O arquivo README.md contém informações sobre o projeto. O diretório resources contém arquivos de recursos, como arquivos de configuração, arquivos de propriedades, etc. O diretório src contém o código-fonte do projeto. O arquivo `core.clj` contém o código-fonte do projeto.

O project.clj é como se fosse o PIP do Python. 

Para rodar o projeto digite:

```bash
lein run
```

Voce pode executar o projeto com o comando `lein run` ou `lein repl`. O comando `lein run` executa o projeto. O comando `lein repl` inicia o REPL (Read-Eval-Print-Loop) do Clojure. O REPL é uma ferramenta interativa que permite que você execute código Clojure diretamente no terminal. O REPL é muito útil para testar pequenos pedaços de código. Para sair do REPL, digite `Ctrl + D`.

So um conceito é o `nill` que é o equivalente ao `None` do Python. 


## Terceiro Conceito - Maps

Em Python, temos um dicionário assim:

```python
dicionario = {
    'nome': 'João',
    'idade': 20,
    'cidade': 'São Paulo'
}
```

Em Clojure, temos um mapa assim:

```clojure
(def dicionario
    {:nome "João"
     :idade 20
     :cidade "São Paulo"})
```
Maps sao muito usado em Clojure. 

## Quarto Conceito - Listas

Em Python, temos uma lista assim:

```python
lista = [1, 2, 3, 4, 5]
```

Em Clojure, temos uma lista assim:

```clojure
(def lista [1 2 3 4 5])
```

Como pegar o valor de um elemento de um mapa? Em Python, fazemos assim:

```python
dicionario['nome']
```

Em Clojure, fazemos assim:

```clojure
(:nome dicionario)
```

Como fazemos para acessar um elemento da lista? Em Python, fazemos assim:

```python
lista[0]
```

Em Clojure, fazemos assim:

```clojure
(first lista)
```

Ou assim:

```clojure
(nth lista 0)
```

Um foreach em Python:

```python
for item in lista:
    print(item)
```

Um foreach em Clojure:

```clojure
(doseq [item lista]
    (println item))
```
ou com map:

```clojure
(map println lista)
```

Temos o map com fn, essa é menos recomendada. 
    
```clojure
(map (fn [item] (println item)) lista)
```

E também com  #

```clojure
(map #(println %) lista)
```

Onde % é o item da lista.

## Quinto Conceito - Funções Anônimas

Em Python, temos uma função anônima assim:

```python
(lambda x: x + 1)
```

Em Clojure, temos uma função anônima assim:

```clojure
(fn [x] (+ x 1))
```

Quando vamos de Map, temos que falar do reduce. 

```clojure
(reduce + lista)
```

O reduce é uma função que recebe uma função e uma lista. A função deve receber dois parâmetros e retornar um valor. A função é aplicada a cada elemento da lista, começando pelo primeiro elemento e o segundo elemento. O resultado da aplicação da função no primeiro e segundo elemento é passado como primeiro parâmetro para a próxima aplicação da função. Este processo é repetido até o final da lista. No final, o reduce retorna o resultado da aplicação da função em todos os elementos da lista.

E também temos o filter:
Filter é uma função que recebe uma função e uma lista. A função deve receber um parâmetro e retornar um booleano. A função é aplicada a cada elemento da lista e retorna uma nova lista contendo apenas os elementos para os quais a função retornou true.

```clojure
(dfn even? [x] (= (mod x 2) 0))

(filter even? lista)
```


## Sexto Conceito - Funções Recursivas

Em Python, temos uma função recursiva assim:

```python
def soma_recursiva(n):
    if n == 0:
        return 0
    else:
        return n + soma_recursiva(n - 1)
```

Em Clojure, temos uma função recursiva assim:

```clojure
(defn soma-recursiva [n]
    (if (= n 0)
        0
        (+ n (soma-recursiva (- n 1)))))
```

## Sétimo Conceito - Funções de Alta Ordem

Em Python, temos uma função de alta ordem assim:

```python
def soma(x, y):
    return x + y

def subtracao(x, y):
    return x - y

def calculadora(x, y, funcao):
    return funcao(x, y)

print(calculadora(10, 5, soma))
print(calculadora(10, 5, subtracao))
```

Em Clojure, temos uma função de alta ordem assim:

```clojure
(defn soma [x y]
    (+ x y))

(defn subtracao [x y]
    (- x y))

(defn calculadora [x y funcao]
    (funcao x y))

(print (calculadora 10 5 soma))
(print (calculadora 10 5 subtracao))
```
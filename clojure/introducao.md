
# Introdução de Clojure

Tudo em clojure é uma função. Isso inclui números, strings, listas, conjuntos, mapas, etc. Isso é o que torna o clojure tão poderoso e flexível.


## Primeiro Conceito 

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



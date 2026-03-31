# Fundamentos de POO

A Programação Orientada a Objetos organiza o software a partir de entidades que reúnem dados e comportamentos.

## Conceitos fundamentais

- classe;
- objeto;
- atributo;
- método;
- encapsulamento;
- herança;
- polimorfismo;
- abstração.

## Como abordar neste guia

Em cada conceito, a idéia é observar:

1. o que ele significa;
2. como costumava ser escrito em Java;
3. como passa a ser implementado em Python;
4. quais diferenças merecem atenção.

## Exemplo inicial: classe e objeto

### Em Java

```java
public class Produto {
    String nome;
    double preco;
}
```

### Em Python

```python
class Produto:
    def __init__(self, nome, preco):
        self.nome = nome
        self.preco = preco
```

        

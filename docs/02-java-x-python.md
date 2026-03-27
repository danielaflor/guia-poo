# Java x Python

A transição de Java para Python não significa abandonar os conceitos já aprendidos. O que muda, em muitos casos, é a forma de escrever e organizar o código.

## Diferenças iniciais

### Sintaxe
Em Java, a escrita do código costuma ser mais detalhada, com uso explícito de tipos, chaves e ponto e vírgula. Em Python, a sintaxe tende a ser mais enxuta e a indentação passa a ter papel estrutural.

### Tipagem
Java trabalha, de modo geral, com tipagem explícita nas declarações. Python adota tipagem dinâmica, o que reduz a quantidade de informação necessária na escrita inicial do código.

### Instanciação
Em Java, é comum utilizar `new` para criar objetos. Em Python, a instanciação acontece de forma direta, chamando a classe como função.

## O que permanece

Apesar das diferenças de sintaxe, continuam presentes conceitos como:

- classe;
- objeto;
- atributos;
- métodos;
- encapsulamento;
- herança;
- polimorfismo.

## Exemplo comparativo

### Em Java

```java
public class Pessoa {
    String nome;

    public Pessoa(String nome) {
        this.nome = nome;
    }

    public void apresentar() {
        System.out.println("Olá, meu nome é " + nome);
    }
}

class Pessoa:
    def __init__(self, nome):
        self.nome = nome

    def apresentar(self):
        print(f"Olá, meu nome é {self.nome}")
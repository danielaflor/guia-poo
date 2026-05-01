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

## Classe

Classe é a estrutura usada para definir um tipo de objeto. Ela funciona como um modelo que reúne atributos (dados) e métodos (comportamentos).

### Em Java

```java

public class Pessoa {
    String nome;
}
```

### Em Python

```python

class Pessoa:
    def __init__(self, nome):
        self.nome = nome
```

### Diferenças

- Em Python não existe a palavra `class` acompanhada de modificadores como `public`.
- O método construtor em Python é chamado `__init__`.
- O parâmetro `self` representa a própria instância do objeto.
- Python não exige declaração explícita de tipos.
- A identação define os blocos de código, substituindo chaves `{}`.

## Objeto

Objeto é uma instância criada a partir de uma classe. Ele representa um elemento concreto que possui atributos e pode executar métodos definidos pela classe.

### Em Java

```java
 public class Pessoa {
>    public Pessoa(String nome) {
         this.nome = nome;
     }
 }

>Pessoa p1 = new Pessoa("Ana");
```

### Em Python

```python
 class Pessoa:
>    def __init__(self, nome):
         self.nome = nome

>p1 = Pessoa("Ana")
```

### Diferenças

- Em Java, normalmente utiliza-se `new` para criar objetos.
- Em Python, a criação do objeto ocorre diretamente pelo nome da classe.
- Python permite uma sintaxe mais simples e menos verbosa.
- O acesso aos atributos é semelhante nas duas linguagens usando `.`.

## Atributos

Atributos são características associadas a um objeto. Eles representam os dados armazenados pela classe.

### Em Java

```java
 public class Pessoa {
>    String nome;
>    int idade;
}
```

### Em Python

```python
 class Pessoa:
     def __init__(self, nome, idade):
>        self.nome = nome
>        self.idade = idade
```

### Diferenças

- Em Java, os atributos geralmente são declarados fora do construtor.
- Em Python, é comum criar atributos dentro do método `__init__`.
- Python não exige definição explícita de tipo.
- Os atributos de instância em Python normalmente usam `self`.

## Métodos

Métodos são funções definidas dentro de uma classe. Eles representam os comportamentos ou ações que os objetos podem executar.

### Em Java

```java
 public class Pessoa {

     String nome;

     public Pessoa(String nome) {
         this.nome = nome;
     }

>    public void apresentar() {
>        System.out.println("Olá, meu nome é " + nome);
>    }
}
```

### Em Python

```python
 class Pessoa:
 
     def __init__(self, nome):
         self.nome = nome

>    def apresentar(self):
>        print(f"Olá, meu nome é {self.nome}")
```

### Diferenças

- Em Python, todo método de instância recebe `self` como primeiro parâmetro.
- Em Java, o objeto é acessado implicitamente dentro da classe.
- Python possui uma sintaxe mais enxuta e sem necessidade de declarar tipos.
- Métodos em Python são definidos com `def`.

## Encapsulamento

Encapsulamento é o princípio de proteger os dados internos de um objeto, controlando como eles podem ser acessados ou modificados.

### Em Java

```java
 public class Pessoa {
 
     // atributo privado
>    private String nome;
 
>    public String getNome() {
         return nome;
     }
 
     public void setNome(String nome) {
         this.nome = nome;
     }
 }
```

### Em Python

```python
 class Pessoa:
 
     def __init__(self, nome):  
         # atributo privado
>        self._nome = nome 

>     def nome(self):
         return self._nome

>    @nome.setter
     def nome(self, nome):
         self._nome = nome
```

### Diferenças

- Em Java, o encapsulamento normalmente utiliza modificadores como `private`.
- Em Python, não existe encapsulamento estrito como em Java.
- A convenção `_atributo` indica uso interno da classe.
- Python utiliza mais convenções de escrita do que restrições obrigatórias de acesso.


## Herança

Herança é o mecanismo que permite que uma classe reutilize atributos e métodos de outra classe, possibilitando extensão e reaproveitamento de código.

### Em Java

```java
 public class Animal {

    public void emitirSom() {
         System.out.println("Som genérico");
     }
 }

>public class Cachorro extends Animal {

     public void latir() {
        System.out.println("Au au");
     }
 }

 Cachorro dog = new Cachorro();

 dog.emitirSom();
 dog.latir();
```

### Em Python

```python
 class Animal:

     def emitir_som(self):
         print("Som genérico")

>class Cachorro(Animal):

     def latir(self):
         print("Au au")

dog = Cachorro()

dog.emitir_som()
dog.latir()
```

### Diferenças

- Em Java, utiliza-se a palavra `extends` para herança.
- Em Python, a classe pai é informada entre parênteses na definição da classe.
- Python permite herança múltipla; Java não permite herança múltipla de classes.
- Métodos da classe pai podem ser sobrescritos na classe filha de forma semelhante nas duas linguagens.

## Polimorfismo

Polimorfismo é a capacidade de diferentes objetos responderem ao mesmo método de maneiras diferentes.

### Em Java

```java
 public class Animal {

>    public void emitirSom() {
        System.out.println("Som genérico");
     }
 }
 public class Cachorro extends Animal {

    
>    public void emitirSom() {
         System.out.println("Au au");
     }
 }
 public class Gato extends Animal {

     
>    public void emitirSom() {
         System.out.println("Miau");
     }
 }
 
 Animal a1 = new Cachorro();
 Animal a2 = new Gato();

>a1.emitirSom();
>a2.emitirSom();
```

### Em Python

```python
 class Animal:

>    def emitir_som(self):
         print("Som genérico")
 class Cachorro(Animal):

>    def emitir_som(self):
         print("Au au")
 class Gato(Animal):

>    def emitir_som(self):
         print("Miau")
 
 a1 = Cachorro()
 a2 = Gato()

>a1.emitir_som()
>a2.emitir_som()
```

### Diferenças

- Em Java, o polimorfismo normalmente está associado ao uso de herança e interfaces.
- Em Python, o polimorfismo é mais flexível devido à tipagem dinâmica.
- Python permite aplicar polimorfismo sem exigir implementação formal de interfaces.
- Métodos com o mesmo nome podem apresentar comportamentos diferentes dependendo do objeto utilizado.

## Abstração

Abstração é o processo de representar apenas as características essenciais de um objeto, ocultando detalhes desnecessários de implementação.

### Em Java

```java
>abstract class Animal {

>    public abstract void emitirSom();
 }
 public class Cachorro extends Animal {

      public void emitirSom() {
         System.out.println("Au au");
    }
 }

 Animal dog = new Cachorro();

 dog.emitirSom();
```

### Em Python

```python
>from abc import ABC, abstractmethod

>class Animal(ABC):

>    def emitir_som(self):
        pass

 class Cachorro(Animal):

     def emitir_som(self):
         print("Au au")

 dog = Cachorro()

 dog.emitir_som()
```

### Diferenças

- Em Java, a abstração normalmente utiliza classes abstratas e interfaces.
- Em Python, a abstração pode ser aplicada de forma mais flexível.
- Python possui suporte a classes abstratas por meio do módulo `abc`.
- Em Python, muitas vezes a abstração é aplicada por convenção, sem necessidade de estruturas rígidas.
        

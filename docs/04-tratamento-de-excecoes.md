
### `docs/04-tratamento-de-excecoes.md`
```md
# Tratamento de Exceções

O tratamento de exceções permite lidar com situações inesperadas durante a execução do programa.

## Em Java

Java utiliza estruturas como `try`, `catch` e `finally`.

```java
try {
    int resultado = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Erro na divisão.");
} finally {
    System.out.println("Fim do processo.");
}

try:
    resultado = 10 / 0
except ZeroDivisionError:
    print("Erro na divisão.")
finally:
    print("Fim do processo.")

    
# Laços de Repetição

Laços de repetição permitem executar um bloco de código várias vezes enquanto uma condição for satisfeita ou durante uma quantidade definida de repetições.

## `for`

Utilizado principalmente quando sabemos quantas vezes queremos repetir um bloco de código.

### Sintaxe

```java
for (inicializacao; condicao; atualizacao) {
    // Código a repetir
}
```

- **Inicialização:** executada uma vez, antes da primeira repetição.
- **Condição:** verificada antes de cada repetição. Se for falsa, o laço termina.
- **Atualização:** executada ao final de cada repetição.

### Exemplo

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

Saída:

```text
1
2
3
4
5
```

Nesse exemplo, `i` começa em `1`, aumenta uma unidade a cada repetição e o laço termina quando `i <= 5` for falso.

## `while`

Utilizado quando queremos repetir um bloco de código enquanto uma condição for verdadeira, especialmente quando não sabemos antecipadamente quantas repetições serão necessárias.

### Sintaxe

```java
while (condicao) {
    // Código a repetir
}
```

A condição é verificada **antes** de cada repetição. Se for falsa desde o início, o código dentro do laço não será executado.

### Exemplo

```java
int contador = 1;

while (contador <= 5) {
    System.out.println(contador);
    contador++;
}
```

O resultado é a impressão dos números de `1` a `5`.

É importante atualizar as variáveis envolvidas na condição para evitar laços infinitos.

## `do while`

Semelhante ao `while`, mas a condição é verificada **depois** da execução do bloco. Portanto, o código é executado pelo menos uma vez.

### Sintaxe

```java
do {
    // Código a repetir
} while (condicao);
```

Atenção: existe um ponto e vírgula (`;`) após o `while`.

### Exemplo

```java
int numero = 1;

do {
    System.out.println(numero);
    numero++;
} while (numero <= 5);
```

O resultado também é a impressão dos números de `1` a `5`.

### Diferença entre `while` e `do while`

```java
int numero = 10;

while (numero < 5) {
    System.out.println("while");
}

do {
    System.out.println("do while");
} while (numero < 5);
```

Saída:

```text
do while
```

O `while` não executa o bloco porque a condição já é falsa. O `do while` executa o bloco uma vez antes de verificar a condição.

## `break` e `continue`

### `break`

Interrompe imediatamente o laço.

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;
    }

    System.out.println(i);
}
```

Saída: `1 2 3 4`

### `continue`

Interrompe a repetição atual e passa para a próxima, verificando a condição do laço quando aplicável.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }

    System.out.println(i);
}
```

Saída: `1 2 4 5`

## Quando Usar Cada Laço?

| Laço | Quando utilizar |
|---|---|
| `for` | Quando a quantidade de repetições é conhecida ou controlada por um contador. |
| `while` | Quando a repetição depende de uma condição verificada antes de executar o bloco. |
| `do while` | Quando o bloco precisa ser executado pelo menos uma vez, como em menus interativos. |

## Cuidados

- **Laço infinito:** acontece quando a condição nunca se torna falsa.
- **Contador:** verifique a inicialização, a condição e a atualização para evitar repetições a mais ou a menos.
- **Escopo:** uma variável declarada na inicialização de um `for`, como `int i`, normalmente só pode ser utilizada dentro do próprio laço.

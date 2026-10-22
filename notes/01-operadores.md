# Operadores

## Operadores de Atribuição

Usados para atribuir valores a variáveis.

### Atribuição simples (`=`)

```java
int valor = 5;
```

### Atribuição composta

Permitem realizar uma operação e atribuir o resultado à própria variável.

```java
int valor = 10;

valor += 15; // valor = valor + 15
valor -= 5;  // valor = valor - 5
valor *= 2;  // valor = valor * 2
valor /= 4;  // valor = valor / 4
valor %= 3;  // valor = valor % 3
```

## Operadores Aritméticos

Usados para realizar operações matemáticas.

| Operador | Operação |
|---|---|
| `+` | Adição |
| `-` | Subtração |
| `*` | Multiplicação |
| `/` | Divisão |
| `%` | Resto da divisão |

```java
int a = 10 + 5; // 15
int b = 10 - 5; // 5
int c = 10 * 5; // 50
int d = 10 / 5; // 2
int e = 10 % 3; // 1
```

**Atenção à divisão de inteiros:** o resultado é um inteiro, sem a parte decimal.

```java
int resultado = 10 / 3; // 3
double decimal = 10.0 / 3; // 3.333...
```

## Operadores Relacionais

Comparam valores e retornam um booleano (`true` ou `false`).

| Operador | Significado |
|---|---|
| `==` | Igual a |
| `!=` | Diferente de |
| `>` | Maior que |
| `>=` | Maior ou igual a |
| `<` | Menor que |
| `<=` | Menor ou igual a |

```java
int a = 10;
int b = 5;

boolean igual = (a == b);       // false
boolean diferente = (a != b);  // true
boolean maior = (a > b);       // true
boolean menor = (a < b);       // false
boolean maiorIgual = (a >= 10); // true
boolean menorIgual = (b <= 5);  // true
```

**Atenção:** `=` atribui um valor; `==` compara valores.

## Operadores Lógicos

Usados para combinar ou negar expressões booleanas.

| Operador | Significado | Resultado |
|---|---|---|
| `&&` | AND (E) | `true` se ambas forem verdadeiras |
| `||` | OR (OU) | `true` se pelo menos uma for verdadeira |
| `!` | NOT (NÃO) | Inverte o valor lógico |

### AND (`&&`)

```java
boolean a = true;
boolean b = false;

boolean resultado = a && b; // false
```

Retorna `true` somente quando ambas as condições são verdadeiras.

### OR (`||`)

```java
boolean a = true;
boolean b = false;

boolean resultado = a || b; // true
```

Retorna `true` quando pelo menos uma das condições é verdadeira.

### NOT (`!`)

```java
boolean a = true;

boolean resultado = !a; // false
```

Inverte o valor booleano: `true` passa a ser `false` e vice-versa.

### Uso em condicionais

```java
int idade = 25;

if (idade >= 18 && idade <= 65) {
    System.out.println("Dentro da faixa etária");
}
```

## Operadores de Incremento e Decremento

Incrementam ou decrementam uma variável em uma unidade.

| Operador | Operação |
|---|---|
| `++variavel` | Pré-incremento |
| `variavel++` | Pós-incremento |
| `--variavel` | Pré-decremento |
| `variavel--` | Pós-decremento |

### Pré-incremento (`++variavel`)

Incrementa a variável antes de utilizar seu valor na expressão.

```java
int num = 5;
int resultado = ++num;

System.out.println(num);      // 6
System.out.println(resultado); // 6
```

### Pós-incremento (`variavel++`)

Utiliza o valor atual na expressão e incrementa a variável em seguida.

```java
int num = 5;
int resultado = num++;

System.out.println(num);      // 6
System.out.println(resultado); // 5
```

### Decremento

Segue a mesma lógica do incremento, mas subtrai uma unidade.

```java
int a = 5;
int b = --a; // a = 4, b = 4

int c = 5;
int d = c--; // c = 4, d = 5
```

**Dica:** quando o incremento ou decremento aparece sozinho, como `num++;`, o valor final da variável é o mesmo independentemente de ser prefixado ou pós-fixado. A diferença importa quando o operador faz parte de uma expressão.

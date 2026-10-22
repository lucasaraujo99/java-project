# Tipos Primitivos

Java possui oito tipos primitivos para representar valores simples: números inteiros, números decimais, caracteres e valores lógicos.

## Tipos Primitivos

| Tipo | Tamanho | Faixa / Valores |
|---|---:|---|
| `boolean` | Dependente da JVM | `true` ou `false` |
| `byte` | 8 bits | -128 a 127 |
| `short` | 16 bits | -32.768 a 32.767 |
| `int` | 32 bits | -2.147.483.648 a 2.147.483.647 |
| `long` | 64 bits | Aproximadamente -9,22 × 10¹⁸ a 9,22 × 10¹⁸ |
| `float` | 32 bits | Precisão aproximada de 6 a 7 dígitos decimais |
| `double` | 64 bits | Precisão aproximada de 15 a 16 dígitos decimais |
| `char` | 16 bits | Valores UTF-16 de `\u0000` a `\uFFFF` |

## Valores Lógicos

### `boolean`

Armazena um valor lógico: `true` ou `false`.

```java
boolean ativo = true;
boolean aprovado = false;
```

## Tipos Inteiros

### `byte`, `short`, `int` e `long`

Armazenam números inteiros. O `int` é a escolha mais comum para números inteiros no uso geral.

```java
byte idade = 25;
short ano = 2026;
int populacao = 1000000;
long distancia = 9000000000L;
```

**Atenção:** literais do tipo `long` podem utilizar o sufixo `L`.

### `char`

Armazena um único valor UTF-16, representado por aspas simples.

```java
char letra = 'A';
char numero = '7';
char simbolo = '#';
```

## Tipos Decimais

### `float` e `double`

Armazenam números de ponto flutuante. O `double` é geralmente preferido por oferecer maior precisão.

```java
float altura = 1.75f;
double preco = 19.99;
double pi = 3.141592653589793;
```

**Atenção:** literais `float` precisam do sufixo `f` ou `F`. Literais decimais são considerados `double` por padrão.

Os tipos `float` e `double` têm precisão limitada e podem apresentar pequenos erros de representação. Para cálculos financeiros que exigem precisão decimal, considere `BigDecimal`.

## Declaração de Variáveis

A declaração informa o tipo e o nome da variável, podendo incluir sua inicialização.

```java
int quantidade;
quantidade = 10;

double preco = 25.50;
boolean disponivel = true;
char categoria = 'A';
```

**Importante:** os tipos primitivos são diferentes dos tipos de referência, como `String`, que representa textos.

```java
String nome = "Maria";
int idade = 25;
```

## Casting

Casting é a conversão de um tipo de dado em outro. Pode ocorrer automaticamente (conversão implícita) ou exigir uma conversão explícita.

### Casting Implícito

Ocorre automaticamente quando o tipo de destino aceita os valores do tipo de origem sem perda de informação numérica.

```java
int x = 10;
double y = x;

System.out.println(y); // 10.0
```

Conversões numéricas comuns:

```java
byte -> short -> int -> long -> float -> double
                  ^
                char
```

**Atenção:** conversões para `float` ou `double` podem perder precisão em determinados valores inteiros.

### Casting Explícito

Utiliza o operador `(tipo)` para converter um valor manualmente. Pode ocorrer perda de informação.

```java
double x = 10.5;
int y = (int) x;

System.out.println(y); // 10
```

Na conversão de `double` para `int`, a parte decimal é descartada, sem arredondamento.

```java
int a = (int) 9.99;  // 9
int b = (int) -9.99; // -9
```

### Conversões entre Tipos Inteiros

O casting explícito também pode ser usado para converter tipos inteiros maiores em menores.

```java
int valor = 130;
byte resultado = (byte) valor;

System.out.println(resultado); // -126
```

Nesse caso, ocorre estouro de faixa (*overflow*), pois `byte` só comporta valores de -128 a 127.

**Importante:** o casting explícito não garante que o valor original será preservado. Verifique a faixa e a precisão do tipo de destino antes de converter.

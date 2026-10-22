# Estruturas Condicionais

Estruturas condicionais permitem executar diferentes trechos de código dependendo de uma condição.

## `if`

Executa um bloco de código se a condição for verdadeira.

```java
int idade = 20;

if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

## `if` e `else`

O `else` define o bloco executado quando a condição do `if` é falsa.

```java
int idade = 16;

if (idade >= 18) {
    System.out.println("Maior de idade");
} else {
    System.out.println("Menor de idade");
}
```

## `if`, `else if` e `else`

O `else if` permite verificar condições adicionais quando as anteriores são falsas. O `else` é opcional e trata os casos restantes.

```java
int nota = 8;

if (nota >= 9) {
    System.out.println("Excelente");
} else if (nota >= 7) {
    System.out.println("Aprovado");
} else if (nota >= 5) {
    System.out.println("Recuperação");
} else {
    System.out.println("Reprovado");
}
```

As condições são avaliadas em ordem. O primeiro bloco cuja condição seja verdadeira é executado.

## Condições Compostas

Utilizam operadores lógicos para combinar condições.

```java
int idade = 25;
boolean possuiCarteira = true;

if (idade >= 18 && possuiCarteira) {
    System.out.println("Pode dirigir");
}
```

| Operador | Significado |
|---|---|
| `&&` | E: todas as condições devem ser verdadeiras |
| `||` | OU: pelo menos uma condição deve ser verdadeira |
| `!` | NÃO: inverte o valor lógico |

## `switch`

Permite selecionar um bloco de código com base no valor de uma expressão. É útil quando há várias alternativas específicas.

### Sintaxe tradicional

```java
switch (expressao) {
    case valor1:
        // Código
        break;
    case valor2:
        // Código
        break;
    default:
        // Caso nenhuma alternativa corresponda
}
```

- `case`: define um valor possível.
- `break`: encerra o `switch`, evitando a execução dos próximos casos.
- `default`: executa quando nenhum caso corresponde; é opcional.

### Exemplo

```java
int dia = 3;
String nomeDia;

switch (dia) {
    case 1:
        nomeDia = "domingo";
        break;
    case 2:
        nomeDia = "segunda-feira";
        break;
    case 3:
        nomeDia = "terça-feira";
        break;
    case 4:
        nomeDia = "quarta-feira";
        break;
    case 5:
        nomeDia = "quinta-feira";
        break;
    case 6:
        nomeDia = "sexta-feira";
        break;
    case 7:
        nomeDia = "sábado";
        break;
    default:
        nomeDia = "Dia inválido";
}

System.out.println("O dia " + dia + " é " + nomeDia);
```

Resultado:

```text
O dia 3 é terça-feira
```

### Agrupando casos

É possível agrupar vários casos para executar o mesmo código.

```java
int dia = 2;

switch (dia) {
    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        System.out.println("Dia útil");
        break;
    case 1:
    case 7:
        System.out.println("Fim de semana");
        break;
    default:
        System.out.println("Dia inválido");
}
```

Na sintaxe tradicional, sem `break`, a execução pode continuar pelos casos seguintes (*fall-through*).

## `switch` com Setas

A partir do Java 14, a sintaxe com `->` está disponível de forma definitiva. Ela evita a necessidade de `break` e não executa automaticamente os casos seguintes.

```java
int dia = 3;

switch (dia) {
    case 1 -> System.out.println("Domingo");
    case 2 -> System.out.println("Segunda-feira");
    case 3 -> System.out.println("Terça-feira");
    default -> System.out.println("Outro dia");
}
```

## Quando Usar Cada Estrutura?

- **`if` / `else`:** condições baseadas em comparações, intervalos e expressões lógicas.
- **`switch`:** seleção entre alternativas específicas de uma expressão, como opções de menu, comandos ou dias da semana.

As duas estruturas podem resolver problemas semelhantes. Escolha a que deixar a lógica mais clara e legível.

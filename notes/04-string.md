# Strings e Text Blocks

## Criação de Strings

A classe `String` representa uma sequência de caracteres. Strings são delimitadas por aspas duplas.

```java
String nome = "Alura";
String mensagem = "Olá, mundo!";
```

## Concatenação de Strings

Utiliza o operador `+` para unir textos.

```java
String saudacao = "Olá, ";
String nome = "Alura";

String mensagem = saudacao + nome + "!";
// "Olá, Alura!"
```

Também é possível concatenar textos com outros tipos de dados.

```java
String nome = "Maria";
int idade = 25;

String mensagem = nome + " tem " + idade + " anos.";
// "Maria tem 25 anos."
```

## Comparação de Strings

### `equals()`

Compara o conteúdo de duas Strings, diferenciando letras maiúsculas de minúsculas.

```java
String senha = "12345";

if (senha.equals("12345")) {
    System.out.println("Acesso autorizado!");
} else {
    System.out.println("Senha incorreta.");
}
```

### `equalsIgnoreCase()`

Compara o conteúdo ignorando diferenças entre letras maiúsculas e minúsculas.

```java
String nome = "Alura";

System.out.println(nome.equalsIgnoreCase("alura")); // true
System.out.println(nome.equals("alura"));           // false
```

**Atenção:** o operador `==` compara referências de objetos, não o conteúdo das Strings. Para comparar textos, utilize `equals()` ou `equalsIgnoreCase()`.

## Text Blocks

Introduzidos no Java 15, permitem representar Strings com múltiplas linhas usando três aspas duplas (`"""`).

```java
String mensagem = """
        Olá, mundo!
        Este é um Text Block.
        Ele permite escrever textos em múltiplas linhas.
        """;
```

### Uso

São úteis para textos longos, mensagens formatadas e conteúdos como HTML, JSON e SQL.

```java
String html = """
        <html>
            <body>
                <h1>Olá, mundo!</h1>
            </body>
        </html>
        """;
```

**Observação:** a quebra de linha após as três aspas iniciais é obrigatória. A indentação é ajustada conforme a posição do delimitador de fechamento e do conteúdo.

## Formatação de Textos

### `String.format()`

Permite inserir valores em um texto utilizando especificadores de formato (`%`).

| Especificador | Tipo |
|---|---|
| `%s` | String |
| `%d` | Inteiro |
| `%f` | Ponto flutuante |
| `%.2f` | Ponto flutuante com 2 casas decimais |
| `%n` | Quebra de linha independente do sistema operacional |

```java
String nome = "Maria";
int idade = 30;
double valor = 55.9999;

String mensagem = String.format(
    "Meu nome é %s, tenho %d anos e gastei %.2f reais.%n",
    nome, idade, valor
);

System.out.println(mensagem);
```

Resultado (com localidade que utiliza ponto decimal):

```text
Meu nome é Maria, tenho 30 anos e gastei 56.00 reais.
```

O especificador `%.2f` limita a exibição a duas casas decimais, aplicando arredondamento.

### `formatted()`

Permite formatar uma String diretamente, inclusive Text Blocks, substituindo os especificadores pelos valores fornecidos.

```java
String nome = "João";
int aulas = 4;

String mensagem = """
        Olá, %s!
        Boas-vindas ao curso de Java.
        Teremos %d aulas para aprender a linguagem.
        """.formatted(nome, aulas);

System.out.println(mensagem);
```

Resultado:

```text
Olá, João!
Boas-vindas ao curso de Java.
Teremos 4 aulas para aprender a linguagem.
```

### Formatação de Números

É possível formatar as casas decimais.

```java
double valor = 12.3456;

System.out.printf("%.2f%n", valor); // 12,35 ou 12.35
System.out.printf("%.1f%n", valor); // 12,3 ou 12.3
```

O separador decimal depende da localidade utilizada. `printf()` também permite formatar e imprimir diretamente, sem precisar criar uma String.

**Importante:** para garantir um separador decimal específico, é possível informar a localidade, por exemplo, `String.format(Locale.US, "%.2f", valor)`. Para usar `Locale.US`, importe `java.util.Locale`.

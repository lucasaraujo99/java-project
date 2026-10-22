# Classe `Scanner`

A classe `Scanner` permite ler dados de entrada, como informações digitadas pelo usuário no teclado.

## Importação

```java
import java.util.Scanner;
```

## Criando um Scanner

```java
Scanner scanner = new Scanner(System.in);
```

- `Scanner`: classe utilizada para ler entradas.
- `System.in`: indica que a entrada vem do teclado.
- `scanner`: variável que armazena o objeto criado.

## Métodos de Leitura

| Método | Tipo de dado | Exemplo |
|---|---|---|
| `nextLine()` | Linha de texto (`String`) | `String nome = scanner.nextLine();` |
| `next()` | Próxima palavra | `String nome = scanner.next();` |
| `nextInt()` | Inteiro (`int`) | `int idade = scanner.nextInt();` |
| `nextDouble()` | Decimal (`double`) | `double valor = scanner.nextDouble();` |
| `nextBoolean()` | Booleano (`boolean`) | `boolean ativo = scanner.nextBoolean();` |

## Exemplo Completo

```java
import java.util.Scanner;

public class ExemploScanner {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Digite seu nome: ");
        String nome = scanner.nextLine();

        System.out.print("Digite sua idade: ");
        int idade = scanner.nextInt();

        System.out.print("Digite o valor que pretende investir: ");
        double valor = scanner.nextDouble();

        System.out.println(
            nome + " tem " + idade
            + " anos e pretende investir R$ " + valor
        );

        scanner.close();
    }
}
```

- `System.out.print()`: exibe uma mensagem sem pular de linha.
- `System.out.println()`: exibe uma mensagem e pula de linha.
- `scanner.close()`: fecha o leitor quando ele não é mais necessário.

## Atenção ao `nextLine()`

Métodos como `nextInt()` e `nextDouble()` leem o valor digitado, mas não consomem a quebra de linha final. Se um `nextLine()` vier logo depois, ele poderá ler essa quebra de linha em vez do texto esperado.

**Exemplo do problema:**

```java
int idade = scanner.nextInt();
String nome = scanner.nextLine(); // Pode ler uma linha vazia
```

**Solução:** consumir a quebra de linha antes de ler o texto.

```java
int idade = scanner.nextInt();
scanner.nextLine(); // Consome a quebra de linha
String nome = scanner.nextLine();
```

## Observações

- `nextLine()` lê a linha inteira, incluindo espaços entre palavras.
- `next()` lê somente até encontrar um espaço em branco.
- `nextInt()` e `nextDouble()` esperam entradas compatíveis com seus tipos; valores inválidos podem gerar `InputMismatchException`.
- `nextDouble()` pode interpretar o separador decimal conforme a configuração regional. Em ambientes configurados para o Brasil, normalmente se utiliza vírgula (`10,5`); em outros, pode ser necessário usar ponto (`10.5`).

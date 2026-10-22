# Convenção de Código

Convenções de código são recomendações para manter o código legível, consistente e fácil de manter.

## Nomenclatura

### Classes — PascalCase

Começam com letra maiúscula e cada palavra é iniciada com maiúscula.

```java
public class MinhaClasse { }
public class CadastroDeUsuario { }
```

### Métodos e Variáveis — camelCase

Começam com letra minúscula e as palavras seguintes começam com maiúscula.

```java
int minhaVariavel = 10;

void calcularTotal() { }
void cadastrarUsuario() { }
```

### Constantes — UPPER_SNAKE_CASE

Usam letras maiúsculas e separam as palavras com `_`. Em Java, constantes são normalmente declaradas com `static final` quando pertencem à classe.

```java
static final double TAXA_JUROS = 0.05;
static final int LIMITE_MAXIMO = 100;
```

## Formatação

### Espaços em branco

Utilize espaços para separar operadores e elementos de controle de fluxo.

```java
int resultado = a + b;

if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

### Comprimento das linhas

Prefira linhas curtas e fáceis de ler. O limite de 80 caracteres é uma referência tradicional, mas não é uma regra universal do Java.

### Indentação

Utilize indentação consistente para destacar os blocos de código. Quatro espaços por nível são uma convenção comum.

```java
if (condicao) {
    executarAcao();

    if (outraCondicao) {
        executarOutraAcao();
    }
}
```

## Comentários

Use comentários para explicar decisões, regras de negócio ou trechos que não sejam óbvios.

```java
// Aplica o desconto promocional ao valor total.
double totalComDesconto = total * 0.90;
```

Prefira nomes descritivos e código claro para evitar comentários desnecessários.

```java
// Evitar:
int x = 10;

// Preferir:
int quantidadeProdutos = 10;
```

## Resumo das Convenções

| Elemento | Convenção | Exemplo |
|---|---|---|
| Classes | PascalCase | `MinhaClasse` |
| Métodos | camelCase | `calcularTotal()` |
| Variáveis | camelCase | `valorTotal` |
| Constantes | UPPER_SNAKE_CASE | `VALOR_MAXIMO` |
| Indentação | Consistente, geralmente 4 espaços | Blocos aninhados |
| Espaçamento | Espaços ao redor de operadores | `a + b` |

**Importante:** convenções são recomendações, não necessariamente regras impostas pelo compilador. Segui-las facilita a leitura, a manutenção e a colaboração em projetos Java.

### Classe Main
---
```java
public class Main {
    public static void main(String[] args){ }
}
```

### Variaveis
---
```java
int minhaIdade = 20;
String meuNome = "Fernanda"
var x = 10; //int
```

### Tipos
---
**Definição dos tipos:**
```java
//inteiros
byte  // 08 bits (-128 a 127)
short // 16 bits 
int   // 32 bits | Mais usado
long  // 64 bits | Adicionar l no final do valor

//Decimais
float  // 32 bits -> usar numeros com duas casas decimais | adicionar f no final do valor
double // 64 bits -> usar numeros com mais de duas casas decimais

//Caracters
string // Textos -> ("")
char   // Unico caracter -> ('')

//boleanos
boolean //true ou false
```

**Casting:**
```java
//Explicito
double resultado = 4.25;
int resultadoInt = (int) resultado;

//Implicito
int meuInt = 10;
double meuDouble = meuInt;

//String
String minhaString = "10";
int meuInt2 = Integer.parseInt(minhaString);

String minhaString2 = String.valueOf(meuInt2);
```

### Vetores
---
```java
int[] colecaoDeInteiros = {1, 2, 3, 4, 5};
int[] colecaoDeInteiros2 = new int[5];

System.out.println(colecaoDeInteiros[0]);
for(int i = 0; i < 5; i++)
	System.out.println(colecaoDeInteiros[i]);

for(int i : colecaoDeInteiros)
	System.out.println(i);

System.out.println(colecaoDeInteiros.length);
```

### Strings
---
 ```java
String nome = "João da Silva"; 
Tamanho nome.length(); // 13 

//Comparação (nunca use == para Strings) 
nome.equals("João da Silva"); // true 
nome.equalsIgnoreCase("joão da silva"); // true (ignora maiúsculas) 

// Busca 
nome.contains("João"); // true 
nome.startsWith("João"); // true 
nome.endsWith("Silva"); // true 
nome.indexOf("da"); // 5 (posição) 

// Transformação 
nome.toUpperCase(); // "JOÃO DA SILVA" 
nome.toLowerCase(); // "joão da silva"
nome.trim(); // remove espaços nas pontas 
nome.replace("João", "Ana"); // "Ana da Silva" 
nome.substring(5); // "da Silva" 
nome.substring(5, 7); // "da" 

// Verificação 
nome.isEmpty(); // false 
nome.isBlank(); // false (também checa espaços) 

// Formatação 
String.format("Olá, %s! Você tem %d anos.", "Ana", 25); // "Olá, Ana! Você tem 25 anos."
 ```

### Classes e objetos
---
```java
// Definição da classe
public class Pessoa {
    // Atributos
    String nome;
    int idade;
}

// Criando objeto (instância)
Pessoa p1 = new Pessoa();
p1.nome = "Ana";
p1.idade = 25;

System.out.println(p1.nome); // Ana
```
### Métodos e construtores e this
---
 ```java
 public class Pessoa {
    String nome;
    int idade;

    // Construtor padrão
    public Pessoa() { }

    // Construtor com parâmetros
    // "this" referencia o atributo da própria classe
    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Método sem retorno
    public void apresentar() {
        System.out.println("Olá, meu nome é " + this.nome);
    }

    // Método com retorno
    public int calcularAniversario(int anoAtual) {
        return anoAtual - this.idade;
    }
}

// Uso na Main
Pessoa p1 = new Pessoa("Ana", 25);
p1.apresentar(); // Olá, meu nome é Ana
int ano = p1.calcularAniversario(2025); // 2000
 ```
### Encapsulamento e abstração
---
**Encapsulamento:**
```java
// Encapsulamento: atributos privados + getters e setters
public class Pessoa {
    private String nome;  // private = só acessível dentro da classe
    private int idade;

    public Pessoa(String nome, int idade) {
        this.nome = nome;
        setIdade(idade); // usa o setter para validar
    }

    // Getter: lê o valor
    public String getNome() {
        return nome;
    }

    // Setter: define o valor (permite validação)
    public void setIdade(int idade) {
        if (idade >= 0) {
            this.idade = idade;
        }
    }

    public int getIdade() {
        return idade;
    }
}

// Uso na Main
Pessoa p1 = new Pessoa("Ana", 25);
System.out.println(p1.getNome()); // Ana
p1.setIdade(30);
```

### Saida e entrada de dados
---
**Saida de dados:**
`sout` no intelij -> escreve `System.out.println`

```java
System.out.print("Meu nome é "); 
System.out.print("Joãeo da Silva");
//Saida -> Meu nome é João da Silva

System.out.println("Meu nome é "); 
System.out.println("João da Silva");
//Saida -> Meu nome é 
//      -> João da Silva

//Concatenação
int idade=35; 
System.out.println("Tenho "+idade+" anos de idade");
//Saida -> Tenho 35 anos de idade
```

**Entrada de dados:**
- Importar classe scaner
	`import java.util.Scanner;`

- Criar objeto para receber via teclado
- `Scanner ler = new Scanner(System.in)`

```java
//ler um numero inteiro
System.out.print("Informe o valor: ");
int x = ler.nextInt();

//ler um decimal
System.out.print("Informe o valor: ");
double y = ler.nextDouble();

//ler um string sem espaço
System.out.print("Informe o nome: ");
String s = ler.next();

//ler um string com espaço
System.out.print("Informe o nome: ");
String s = ler.nextLine();
```

### Switch case
```java
switch (expressão) {
	 case valor1: 
		 comandos; 
		 break; 
	case valor2: 
		comandos; 
		break; 
	default: 
		comandos; 
}
```


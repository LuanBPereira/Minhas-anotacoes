___

Essa página vai ser usada pra anotações que preciso por um tempo, até organiza-la depois. Então, vão ficar por um tempo até ser decidido onde vou usar essas infos.
___

tipo primitivo - copia o valor

tipo referencia - cria uma nova referencia para o mesmo objeto

**int/Integer - pode ser números inteiros que vão de um numero X até um numero Y. Também podem ser números binários, que vão de 0 até 1 (afinal são binários), podem ser números octais, que vão de 0 até 7, podem ser hexadecimal, que vão até 0 até 9 e + 6 caracteres (a, b, c, d, e, f).**

```java
int a; // declarando variavel int

a = 07 // número na base 8, octal.
a = 0x1f // número hexadecimal
a = 0B110 // número binário
```

double/Double - podem ser escritos como notação cientifica também. Como por exemplo `double d = 3.1E2` , que é `3.1x10² = 3.1x100 = 310`. float/Float - também podem ser escritos como notação cientifica: `float f2 = 2e3f` , que é `2x10³ = 2x1000 = 2000` .

long/Long - é possivel separar os números com underscore “_” caso queira representar por exemplo dinheiro. Ex: `long x2 = 1_234_567_891_011l **OBS: Isso só funciona se o underscore estiver entre números, entre underscores ou letras que dão VALORES REAIS para uma variável. Como por exemplo as letras do Hexadecimal.`**

---

Outro ponto importante é que por padrão, números inteiros são considerados **int**, e com casas decimais são considerados **double**.

Podemos forçar um **valor literal** para um tipo usando uma letra no final como `long l = 13L` .

Se criarmos um `float f = 13.1`, o sistema lerá como um `double`, então teríamos que adiocionar uma letra no final também, para o sistema saber que isso é um `float` e não um `double` : `float f = 13.1f`. Então podemos usar as letras `d` , `l` , e `f` para indicar quais os tipos corretos. Caso ao contrários, eles vão ser identificados como **int** e **double por padrão**.

---

# import static - apenas para eu saber que existe - JAVA

O `CLASSPATH` é uma variável de ambiente usada pela JVM para localizar as classes e pacotes necessários para a execução de um programa Java. Por padrão, ele inclui apenas o diretório atual (`.`). Se precisar rodar um programa com classes ou pacotes localizados em outro lugar, é possível especificar o `CLASSPATH` manualmente.

Não é recomendado configurar o `CLASSPATH` globalmente nas variáveis de ambiente, porque isso pode causar conflitos ao trabalhar com diferentes projetos. O mais comum é defini-lo no momento da execução. Aqui estão alguns exemplos:

```bash

# Executa uma classe no pacote "pacote" dentro do diretório atual.
java -classpath . pacote.teste

# Forma abreviada de -classpath (usando -cp):
java -cp . pacote.teste

# Define um diretório específico como CLASSPATH:
java -cp diretorio-projeto pacote.teste

# Define múltiplos caminhos no CLASSPATH:
# (No Windows, usa-se ";", no Linux/Mac usa-se ":")
java -cp diretorio1;diretorio2 pacote.teste

```

Além de diretórios, você pode incluir arquivos JAR ou até mesmo arquivos ZIP no `CLASSPATH`. Por exemplo:

```bash

java -cp diretorio1;arquivo.jar pacote.teste

```

### Dicas:

- Ferramentas como Maven ou Gradle ajudam a gerenciar dependências e o `CLASSPATH` automaticamente em projetos maiores.
- Evite configurar o `CLASSPATH` globalmente; prefira defini-lo por projeto ou no comando de execução.

### Sobre as Interfaces em Java

1. **Variáveis em Interfaces**
    
    - Por padrão, as variáveis declaradas em uma interface são:
        - **`public`**: acessíveis de qualquer lugar.
        - **`static`**: pertencem à interface, não a instâncias.
        - **`final`**: seu valor é constante e não pode ser alterado após a atribuição inicial.
    - Mesmo que você não declare explicitamente `public static final`, o compilador assume esses modificadores.
    
    **Exemplo:**
    
    ```java
    java
    Copiar código
    interface Exemplo {
        int VALOR = 10; // Equivalente a: public static final int VALOR = 10;
    }
    
    ```
    
2. **Métodos em Interfaces**
    
    - Por padrão, os métodos declarados em interfaces são:
        - **`public`**: acessíveis de qualquer lugar.
        - **`abstract`**: devem ser implementados pelas classes que implementam a interface.
    - Assim, declarar `public abstract` em métodos é redundante, pois o compilador já assume esses modificadores.
    
    **Exemplo:**
    
    ```java
    java
    Copiar código
    interface Exemplo {
        void metodo(); // Equivalente a: public abstract void metodo();
    }
    
    ```
    
3. **Métodos com Implementação (desde Java 8):**
    
    A partir do Java 8, interfaces podem conter métodos com implementação, mas eles precisam ser marcados como:
    
    - **`default`**: para métodos que podem ser sobrescritos pelas classes implementadoras.
    - **`static`**: para métodos utilitários que pertencem à interface.
    
    **Exemplo:**
    
    ```java
    java
    Copiar código
    interface Exemplo {
        default void metodoPadrao() {
            System.out.println("Método com implementação padrão.");
        }
    
        static void metodoEstatico() {
            System.out.println("Método estático na interface.");
        }
    }
    
    ```
    
4. **Métodos Privados (desde Java 9):**
    
    Interfaces podem ter métodos `private` para encapsular lógica e evitar repetição em métodos `default` ou `static`.
    
    **Exemplo:**
    
    ```java
    java
    Copiar código
    interface Exemplo {
        private void metodoPrivado() {
            System.out.println("Método privado na interface.");
        }
    
        default void metodoPadrao() {
            metodoPrivado();
        }
    }
    
    ```
    

---

### Compilar e Executar um Arquivo Java pelo Terminal

1. **Compilar um Arquivo Java:**
    
    O comando para compilar um arquivo Java é:
    
    ```bash
    
    javac diretorio/arquivo.java
    
    ```
    
    - Isso cria um arquivo `.class` no mesmo diretório do arquivo `.java`.
    - Certifique-se de estar no diretório base ou ajuste o caminho para o arquivo.
2. **Executar uma Classe Java:**
    
    Para executar, o comando é:
    
    ```bash
    
    java diretorio.ClasseDoArquivo
    
    ```
    
    - **Importante:**
        - Use o nome completo da classe, incluindo o pacote (se houver).
        - O `diretorio` no comando refere-se ao nome do pacote, **não ao caminho físico**.
        - Certifique-se de que o diretório base (`.`) está no `CLASSPATH`.
    
    **Exemplo Completo:** Suponha o seguinte cenário:
    
    ```bash
    
    projeto/
    ├── pacote/
    │   └── MinhaClasse.java
    
    ```
    
    - Compile:
        
        ```bash
        
        javac pacote/MinhaClasse.java
        
        ```
        
    - Execute:
        
        ```bash
        
        java pacote.MinhaClasse
        
        ```
        

---

### Dicas Adicionais:

1. **Evitar Erros Comuns:**
    
    - Se o arquivo `.java` contiver um pacote declarado, você deve incluí-lo na execução. Por exemplo:O comando para execução será:
        
        ```java
        java
        Copiar código
        package pacote;
        public class MinhaClasse {
            public static void main(String[] args) {
                System.out.println("Olá, mundo!");
            }
        }
        
        ```
        
        ```bash
        bash
        Copiar código
        java pacote.MinhaClasse
        
        ```
        
2. **Organização Recomendada:**
    
    - Sempre mantenha seu código organizado em pacotes. Isso facilita a manutenção e previne conflitos de nomes.

---
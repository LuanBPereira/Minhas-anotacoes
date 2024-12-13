___

Para permitir que a gente trabalhe com Strings mutáveis, ou seja, Strings que a gente pode mudar em tempo de execução, o Java oferece para nós essas duas classes: **`StringBuffer`** e **`StringBuilder`**. Elas são utilizadas para manipular sequência de caracteres de forma eficiente, principalmente quando precisamos fazer várias alterações em uma String, como concatenação, inserção ou remoções. Ambas pertencem ao pacote `java.lang` e oferecem funcionalidades similares, mas com diferenças importantes relacionada à *thread safety*.

#### Diferenças principais entre `String`, `StringBuffer` e `StringBuilder`

- **`String`**:
    
    - Imutável (uma vez criada, não pode ser modificada).
        
    - Operações como concatenações geram uma nova instância, o que pode ser ineficiente em operações repetitivas.
        
- **`StringBuffer`**:
    
    - Mutável (permite alterações diretamente no objeto).
        
    - _Thread-safe_: os métodos são sincronizados, tornando-o seguro para uso em aplicações multithread.
        
    - Mais lento comparado ao `StringBuilder` devido à sincronização.
        
- **`StringBuilder`**:
    
    - Mutável, assim como o `StringBuffer`.
        
    - Não é _thread-safe_: os métodos não são sincronizados.
        
    - Mais rápido que o `StringBuffer`, sendo ideal para aplicações de uma única thread.
        
___

#### Quando usar cada um

- **`String`**: Quando os dados são imutáveis ou poucas alterações serão feitas.
    
- **`StringBuffer`**: Quando é necessário manipular strings em aplicações multithread.
    
- **`StringBuilder`**: Quando há muitas alterações em strings em aplicações de uma única thread.
___

#### Principais métodos

Os métodos abaixo são comuns às classes `StringBuffer` e `StringBuilder`:

1. **`append(String s)`**: Adiciona uma string ao final da sequência.
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb); // Saída: Hello World
```

2. **`insert(int offset, String s)`**: Insere uma string em uma posição específica.
```java
StringBuffer sb = new StringBuffer("Hello World");
sb.insert(6, "Java ");
System.out.println(sb); // Saída: Hello Java World
```

3. **`replace(int start, int end, String s)`**: Substitui parte da sequência por outra string.
```java
StringBuilder sb = new StringBuilder("Hello World");
sb.replace(6, 11, "Java");
System.out.println(sb); // Saída: Hello Java`
```

4. **`delete(int start, int end)`**: Remove parte da sequência.
```java
StringBuffer sb = new StringBuffer("Hello Java World");
sb.delete(5, 10);
System.out.println(sb); // Saída: Hello World
```

5. **`reverse()`**: Inverte a ordem dos caracteres na sequência.
```java
StringBuilder sb = new StringBuilder("Hello");
sb.reverse();
System.out.println(sb); // Saída: olleH
```

6. **`capacity()`**: Retorna a capacidade atual do buffer.
```java
StringBuffer sb = new StringBuffer();
System.out.println(sb.capacity()); // Valor padrão: 16
```

7. **`ensureCapacity(int minimumCapacity)`**: Garante que o buffer tenha uma capacidade mínima.
```java
StringBuffer sb = new StringBuffer();
sb.ensureCapacity(50);
System.out.println(sb.capacity()); // Saída: 50
```
___

#### Exemplo prático
```Java
class TestaStringBufferEBuilder {
	public static void main(String[] args) {
		/* ==:Coisas a se notar:==
			no SYSOUT pode se usar tanto o toString
			do StringBuffer(Builder) ou colocar direto a refêrecia dele,
			pois a método println recebe um objeto e com isso, como todo
			objeto tem um toString, ele pega o toString daquele objeto 
			e exbie na tela
		*/
		
		StringBuffer sbfHello = new StringBuffer("Hello");
		System.out.println(sbfHello.toString); // Saída: Hello
		// adicionando String ao final da sequencia
		sbfHello.append(" World!");
		System.out.println(sbfHello.toString); // Saída: Hello World!
		
		StringBuilder sbHelloW = new StringBuilder("Hello World");
		// adicionando String em uma posição especifica, no caso no 6° indice
		sbHelloW.insert(6, "Java");
		System.out.println(sbHelloW.toString); // Saída: Hello Java World
		
		StringBuffer sbfHello2 = new StringBuffer("Hello World");
		// substituindo parte da sequencia por outra String, no caso a partir
		// do 6° elemento até o 11° elemento
		sbfHello2.replace(6, 11, "Java");
		System.out.println(sbfHello2); // Saída: Hello Java`
		
		StringBuilder sbHelloW2 = new StringBuilder("Hello Java World");
		// deletando uma String da sequencia, no caso a partir do 5° elemento
		// até o 10° elemento
		sbHelloW2.delete(5, 10);
		System.out.println(sbHelloW2); // Saída: Hello World
		
		StringBuffer sbfHello3 = new StringBuffer("Hello");
		// invertendo a ordem de caracteres da sequencia
		sbfHello3.reverse();
		System.out.println(sbfHello3.toString); // Saída: olleH
		
		StringBuilder sbHelloW3 = new StringBuilder();
		System.out.println(sbHelloW3.capacity()); // Saida: Valor padrão: 16
		/*
			==:IMPORTANTE COMENTAR:==
			Retorna o valor padrão de capacidade, que é 16.
			Porém, se colocarmos um valor específico de capacidade
			dentro do construtor do StringBuilder(ou StringBuffer),
			ele retorna o valor que foi colocado. Segue o exemplo abaixo:
		*/
		sbHelloW3 = new StringBuilder(30); 
		System.out.println(sbHelloW3.capacity()); // Saída: Valor 30
		
		StringBuffer sbfHello4 = new StringBuffer();
		// garantindo, colocando uma capacidade mínima no buffer
		sbfHello4.ensureCapacity(50);
		System.out.println(sbfHello4.capacity()) // Saída: Valor 50
		
	/*
	    ==:PONTO IMPORTANTE:== 
	    se você tem certeza de que o buffer precisará de um   
	    espaço X desde o começo e que esse espaço não precisará ser ajustado ao 
	    longo do tempo, utilize o **construtor** com a capacidade inicial. 
	    Isso evita realocações de memória durante o uso inicial, melhorando o 
	    desempenho.
	    
	    Se você não tem certeza se a capacidade precisará crescer, utilize o 
	    **método ensureCapacity()**, que permite ajustar a capacidade mínima 
	    dinamicamente durante o uso. Lembre-se que o **`ensureCapacity()`** 
	    **só aumentará** a capacidade quando necessário e **nunca a diminuirá**.
	    
	    A vantagem do **construtor** é que ele já aloca a quantidade necessária 
	    de memória desde o início, evitando a sobrecarga de realocações durante o 
	    uso, o que pode melhorar o desempenho se o espaço for bem calculado.
	    
	    ==:OBSERVAÇÃO:==
	    Se a capacidade do `StringBuilder` ou `StringBuffer` for 
	    maior do que o necessário e você quiser liberar memória, use o **método 
	    `trimToSize()`**, que ajusta a capacidade para corresponder ao conteúdo 
	    armazenado. Tenha em mente que esse método **não pode reduzir a 
	    capacidade** se o objeto precisar crescer no futuro.
	    
	    ==:EXEMPLO ABAIXO:==
	*/
		
	/*
		Se você percebe que a capacidade do StringBuilder está ultrapassando o 
		esperado, e para evitar que ele precise realocar memória toda vez que a 
		capacidade for ultrapassada, você pode definir a capacidade mínima 
		desejada com ensureCapacity().
	*/
		StringBuilder sb = new StringBuilder(20); // capacidade inicial 20
		// Aumenta a capacidade do StringBuilder para 50, se necessário.
		// No caso, ele só aumenta caso a capacidade for menor que 50. 
		sb.ensureCapacity(50); 
	}
}
```
___

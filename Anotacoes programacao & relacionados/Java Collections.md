___

A API **Collections** em Java fornece várias classes e interfaces úteis para trabalhar com estruturas de dados, como listas, conjuntos, mapas e filas. Abaixo, vamos explorar algumas das coleções mais usadas, seus métodos e a diferenciação entre as principais classes da API.
___
## **Sobrescrevendo o Método `toString()`**

Quando trabalhamos com listas de objetos e queremos exibi-los de forma legível (por exemplo, ao usar o método `System.out.println()`), é necessário sobrescrever o método `toString()` da classe do objeto. O método `toString()` fornece uma representação em string de um objeto, e sem ele, o Java exibirá algo como `NomeDaClasse@hashCode`, o que geralmente não é útil.
___

### **Por que sobrescrever `toString()`?**

Se você deseja listar objetos em uma coleção, como uma `List<Filme>`, o `toString()` precisa ser sobrescrito para garantir que a saída mostre informações úteis sobre o objeto. Caso contrário, a lista imprimirá a referência de memória do objeto, ao invés de suas propriedades.
___

### **Exemplo de Sobrescrita do `toString()`**

Vamos supor que você tenha uma classe `Filme` com os atributos `titulo`, `diretor` e `duracao`. Para exibir uma lista de filmes de forma legível, você pode sobrescrever o método `toString()` dessa forma:

```java
public class Filme {
	private String titulo;
	private String diretor;
	private int duracao;
	// Construtor, getters e setters
	
	@Override     
	public String toString() {
		return "Filme: " + titulo + " | Diretor: " + diretor + " | Duração: " +
		duracao + " minutos";
	} 
}
```

Agora, ao imprimir uma lista de filmes, o método `toString()` será chamado automaticamente para cada objeto, e a saída será algo mais amigável e informativo:

```java
List<Filme> filmes = new ArrayList<>();
filmes.add(new Filme("Filme A", "Diretor X", 120));
filmes.add(new Filme("Filme B", "Diretor Y", 90));
System.out.println(filmes);
```

**Saída:**
```java
[Filme: Filme A | Diretor: Diretor X | Duração: 120 minutos, Filme: Filme B | Diretor: Diretor Y | Duração: 90 minutos]
```
___

### **Importante:**

- Quando você sobrescreve o `toString()`, você pode personalizar a forma como os objetos serão representados em qualquer lugar que utilizem o método `System.out.println()`.
- Isso melhora a legibilidade e facilita a depuração e o trabalho com listas de objetos.
___

## **Ordenando Objetos com Comparator**

Uma das maneiras de ordenar coleções é usando o `Comparator`. A partir do Java 8, você pode usar métodos de ordenação diretamente nas listas.

### **Exemplo de Uso:**

```java
filmes.sort(Comparator.comparing(Filme::getDuracao));
```

Neste exemplo, a lista de filmes será ordenada com base no tempo de duração dos filmes.
A vantagem disso é que você não precisa ficar se preocupando em ficar implementando a interface `Comparable` e sobrescrever o método `compareTo`, pois dessa forma você está passando como parâmetro do método comparing, do Comparator, o que comparar entre os objetos.
___

## **Diferenças entre `ArrayList` e `LinkedList`**

- **`ArrayList`**: Usa arrays internamente. É eficiente para acessar elementos (`get(index)`), mas a inserção e remoção de elementos no início da lista pode ser mais lenta, pois exige o deslocamento dos elementos.

- **`LinkedList`**: Usa uma lista ligada. É eficiente para inserção e remoção no início ou no meio da lista, mas o acesso a elementos específicos pode ser mais lento, pois a lista precisa ser percorrida até o item desejado.
---

## **Listas Imutáveis**

Em Java, você pode criar listas imutáveis para evitar modificações posteriores nos dados.

### **Criando uma Lista Imutável:**

```java
public List<Aula> getAulas() {
	return Collections.unmodifiableList(aulas);
}
```

**Modificando uma Lista Imutável:**

Para modificar uma lista imutável, você precisa criar uma nova lista com base na original e aplicar as alterações desejadas:

```java
List<Aula> aulasImutaveis = javaColecoes.getAulas();
List<Aula> aulas = new ArrayList<>(aulasImutaveis);
Collections.sort(aulas);
System.out.println(aulas);
```
---

## **Métodos Úteis da Classe Collections**

A classe `Collections` fornece vários métodos úteis para trabalhar com coleções.

### 1. **`Collections.reverse()`**

Inverte a ordem dos elementos em uma lista.

**Exemplo:**
```java
import java.util.*;  
public class ExemploReverse {
	public static void main(String[] args) {
	    List<String> lista = new ArrayList<>();
	    lista.add("Java");
		lista.add("Python");
		lista.add("C++");
		System.out.println("Antes de inverter: " + lista);
		Collections.reverse(lista);
		System.out.println("Depois de inverter: " + lista);
	} 
}
```

**Saída:**
```java
Antes de inverter: [Java, Python, C++]
Depois de inverter: [C++, Python, Java]
```
---

### 2. **`Collections.shuffle()`**

Embaralha os elementos de uma lista, útil para sorteios ou aleatoriedade.

**Exemplo:**
```java
import java.util.*;
public class ExemploShuffle {
	public static void main(String[] args) {
	    List<String> lista = new ArrayList<>();
	    lista.add("Java");
	    lista.add("Python");
	    lista.add("C++");
		System.out.println("Antes de embaralhar: " + lista);
		Collections.shuffle(lista);
		System.out.println("Depois de embaralhar: " + lista);     
	} 
}
```

**Saída (o embaralhamento pode variar):**
```java
Antes de embaralhar: [Java, Python, C++] 
Depois de embaralhar: [Python, C++, Java]
```
---

### 3. **`Collections.singletonList()`**

Cria uma lista imutável contendo um único elemento.

**Exemplo:**
```java
import java.util.*;
public class ExemploSingletonList {
	public static void main(String[] args) {
	    List<String> lista = Collections.singletonList("Java");
	    System.out.println("Lista com um único elemento: " + lista);   
	} 
}
```

**Saída:**
```java
Lista com um único elemento: [Java]
```
---

### 4. **`Collections.nCopies()`**

Cria uma lista imutável com várias cópias de um elemento.

**Exemplo:**
```java
import java.util.*;
public class ExemploNCopies {
	public static void main(String[] args) {
		List<String> lista = new ArrayList<>(Collections.nCopies(5, "Java"));              System.out.println("Lista com 5 cópias de 'Java': " + lista);
	} 
}
```

**Saída:**
```java
Lista com 5 cópias de 'Java': [Java, Java, Java, Java, Java]
```
---

### 5. **`Collections.synchronizedSet()`**

Converte um conjunto (`Set`) em uma versão segura para múltiplas threads.

**Exemplo:**
```java
import java.util.*;  
public class ExemploSynchronizedSet {
	public static void main(String[] args) {
		Set<String> conjunto = new HashSet<>();
		conjunto.add("Java");
		conjunto.add("Python");
		conjunto.add("C++");
		Set<String> conjuntoSincronizado = Collections.synchronizedSet(conjunto);      
		
		// exemplo de acesso seguro a partir de várias threads
		synchronized(conjuntoSincronizado) {
			for (String linguagem : conjuntoSincronizado) {
				System.out.println(linguagem);             
			}         
		}     
	} 
}
```

**Saída:**
```java
Java Python C++
```
---

## **Uso de HashMap com `getOrDefault`**

O método `getOrDefault` de um `HashMap` permite buscar o valor associado a uma chave, ou retornar um valor padrão caso a chave não exista.

### **Exemplo de Uso:**
```java
HashMap<String, Integer> map = new HashMap<>();
map.put("maca", 3);
map.put("banana", 5);

int valor1 = map.getOrDefault("maca", 0); //  Retorna 3 
int valor2 = map.getOrDefault("laranja", 0); // Retorna 0
```
---

## **Diferenças entre `ArrayList`, `HashSet` e `TreeSet`**

Essas três classes são amplamente usadas para armazenar dados em Java, mas têm características diferentes.

### **1. `ArrayList`**

- Mantém a ordem de inserção dos elementos.
- Permite duplicatas.

**Exemplo:**
```java
List<Integer> v = new ArrayList<>();
v.add(20); // index 0 
v.add(3); // index 1 
v.add(125); // index 2 
v.add(4); // index 3 
System.out.println(v);
```

**Saída:**
```java
[20, 3, 125, 4]
```
___

### **2. `HashSet`**

- Não permite duplicatas.
- Não mantém a ordem de inserção. A ordem pode variar.

**Exemplo:**
```java
Set<Integer> v = new HashSet<>();
v.add(20);
v.add(3);
v.add(125);
v.add(4);
System.out.println(v);
```

**Saída:**
```java
[3, 20, 4, 125]
```
___

### **3. `TreeSet`**

- Ordena os elementos de forma natural ou com um comparador fornecido.
- Não permite duplicatas.

**Exemplo:**
```java
Set<Integer> v = new TreeSet<>();
v.add(20);
v.add(3);
v.add(125);
v.add(4);
System.out.println(v);
```

**Saída:**
```java
[3, 4, 20, 125]
```
---

## **Outros Métodos Úteis da API Collections**

Além dos métodos básicos mencionados acima, a API `Collections` também oferece outras funcionalidades valiosas.

### **1. `Collections.sort()`**

Ordena os elementos de uma lista de acordo com a ordem natural ou com um `Comparator`.

**Exemplo:**
```java
Collections.sort(listaDeFilmes);
```
___

### **2. `Collections.min()` e `Collections.max()`**

Encontra o menor ou maior elemento de uma coleção, usando a ordem natural ou um `Comparator`.

**Exemplo:**
```java
Filme filmeMaisLongo = Collections.max(listaDeFilmes, Comparator.comparing(Filme::getDuracao));
```
___

### **3. `Collections.copy()`**

Copia os elementos de uma lista para outra, desde que as duas listas tenham o mesmo tamanho.

**Exemplo:**
```java
List<String> listaDestino = new ArrayList<>(Arrays.asList(new String[listaOrigem.size()])); Collections.copy(listaDestino, listaOrigem);
```
___

### **4. `Collections.rotate()`**

Rotaciona os elementos de uma lista para a direita ou para a esquerda.

**Exemplo:**
```java
Collections.rotate(lista, 2);  // Rotaciona para a direita
```
---

### **Referências**:

- [Curso de Java Collections - Alura](https://cursos.alura.com.br/course/java-collections)
- [Vídeo sobre Coleções - YouTube](https://www.youtube.com/watch?v=pDTNUS8mgc0)
- [Discussão sobre HashSet e TreeSet](https://cursos.alura.com.br/forum/topico-pq-se-usa-o-hashset-o-linkedhashset-nao-seria-mais-vantajoso-130785#:~:text=O%20HashSet%20n%C3%A3o%20mant%C3%A9m%20nenhuma,acordo%20com%20o%20Comparador%20fornecido)
___
___


> [!NOTE] Colocar mais tarde!
>Um texto nessa área aqui, logo abaixo do titulo. Pra ser tipo uma introdução
>Métodos da String, pesquisar

___

```java
public class TestaString {
	public static void main(String[] args) {
		// Strings são imutáveis!
		String s = "caelum";
		s.toUpperCase(); // colocando o valor em maiúsculo
		System.out.println(s)// Saída: caelum
		
		/* 
		A String 's' referencia um objeto na memória, naquele objeto, o 's', eu 
		chamei o método toUpperCase(), que vai criar um novo objeto em que 
		'caelum' é todo maiusculo e vai devolver uma referencia a esse objeto.
		Só que a gente não fez nada com a referencia desse objeto criado! Por isso 
		que o 'caelum' veio como minusculo.
		*/
		
		s = s.toUpperCase();
		/* aqui mandamos o 's' apontar para a nova String
		que foi criado pelo método toUpperCase().
		é que como se falassemos "Objeto 's' de String, cria uma novo objeto de  
		String com esse método, que devolve uma referencia a esse objeto criado, 
		e aponte para a referencia dele."
		E então, o resultado que a gente esperava, que era o CAELUM sair em 
		maiusculo, vai ser correspondido.
		*/
		System.out.println(s) // Saída: CAELUM
		
		/*
			==:IMPORTANTE LEMBRAR:==
			Os métodos de String não vão alterar os valores internos dela, mas sim
			vão devolver uma nova String, uma referencia, e aí você usa essa 
			referencia como quiser.
			
			Outra coisa legal que vale reelembrar é que a String é uma array, 
			então ela começa no indice 0.
			Se for acessar com o método charAt, tem que começar acessando pelo 
			indice 0. Além disso, não é possivel acessar indices menores ou 
			maiores que a array de String.
			Além disso, como é uma array, ele pode usar todos os métodos que uma 
			array, não uma arraylist, tem.
			==:EXEMPLOS ABAIXO:==
		*/
		System.out.println(s.charAt(0)); // Saida: C
		System.out.println(s.chatAt(-1)); = // StringIndexOutOfBoundsException
		System.out.println(s.length()); // Saída: 6
		System.out.println(s.isEmpty()) // Saída: false
		// Jeitos de criar Strings
		
		String nomeDireto = "Java";
		String nomeIndireto = new String("Java");
		
		char[] nome = new char[]{'J', 'a', 'v', 'a'};
		String nome1 = new String(nome);
		
		StringBuilder sb1 = new StringBuilder("Java");
		String nome2 = new String(sb1);
		
		// String é uma referencia para um objeto,
		// portanto ela pode ter o valor de nulo
		String nomeNulo = null;
		
		// Concatenando Strings
		String nomeDaProva = "Certificação" + " " + "Java";
		// Concatenar String com null, tranquilo. Apenas concatenou de boa.
		// Agora, chamar um método null (ex: toString) = NullPointerException
		String nomeDaProvaComNulo = nomeDaProva + " " + null;
		
		// Concatena
		System.out.println("Certificação: " + 1500); // Saída: Certificação: 1500
		// Realiza a operação e concatena.
		System.ou.println(15 + 1 + " Certificação"); //Saida: 16 Certificação
		// Concatenação, sempre da esquerda pra direita.
		// Se houver números logo no inicio, vai realizar uma operação e 
		// depois concatenar
	}
}

```
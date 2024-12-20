A Programação Orientada a Objetos (OOP - _Object-Oriented Programming_) é um paradigma de programação que organiza o código em **objetos**. Cada objeto representa uma entidade do mundo real ou uma abstração, e esses objetos interagem entre si para resolver problemas.

OOP promove o uso de estruturas modulares, reutilizáveis e organizadas, facilitando a manutenção, expansão e compreensão do sistema.
___

### **Estrutura da OOP**

#### **Classe**

- É o molde ou a definição de um tipo de objeto. Define os **atributos** (dados) e os **métodos** (comportamentos) que os objetos daquele tipo terão.
- Uma classe sozinha não faz nada; ela precisa ser usada para criar **objetos**.

#### **Objeto**

- É uma **instância** de uma classe, ou seja, um elemento concreto baseado na definição da classe.
- Cada objeto pode ter valores diferentes para os atributos, mas todos compartilham os métodos definidos na classe.

#### **Exemplo de classe e objeto (em Java):**

```java
class Carro {
	String marca;
	String modelo;
	int ano;
	
	void acelerar() {
		System.out.println("O carro está acelerando!");
	} 
}  
public class Main {
	public static void main(String[] args) {
		Carro meuCarro = new Carro(); // Objeto criado
		meuCarro.marca = "Toyota";
		meuCarro.modelo = "Corolla";
		meuCarro.ano = 2020;
		System.out.println(meuCarro.marca + " " + meuCarro.modelo); // Toyota 
		Corolla
		meuCarro.acelerar(); // O carro está acelerando!
	} 
}
```

---

### **Princípios da OOP**

Existem quatro pilares fundamentais na Programação Orientada a Objetos:

#### 1. **Encapsulamento**

- O encapsulamento consiste em **ocultar os detalhes internos** de um objeto, permitindo o acesso apenas às informações e comportamentos necessários. Isso é feito controlando o acesso aos atributos e métodos da classe.

##### **Como implementar?**

- Atributos são geralmente definidos como **privados** (`private`) para que só possam ser acessados ou alterados através de métodos **públicos** (`public`), chamados de **getters** e **setters**.

##### **Exemplo:**
```java
class Pessoa {
    private String nome;
    private int idade;
    
    // Getter
    public String getNome() {
        return nome;
    }
    
    // Setter
    public void setNome(String nome) {
        this.nome = nome;
    }
    
    // Getter
    public int getIdade() {
        return idade;
    }
    
    // Setter
    public void setIdade(int idade) {
        if (idade >= 0) { // Validação de dados
            this.idade = idade;
        }
    }
}
```

Com o encapsulamento, você protege os dados e controla como eles podem ser manipulados.
___

#### 2. **Herança**

- A herança permite que uma classe (chamada de **subclasse**) herde atributos e métodos de outra classe (chamada de **superclasse**).
- Isso promove a **reutilização de código** e a criação de hierarquias entre classes.

##### **Exemplo de herança:**
```java
// Classe base
class Animal {
    void comer() {
        System.out.println("O animal está comendo.");
    }
}

// Subclasse que herda de Animal
class Cachorro extends Animal {
    void latir() {
        System.out.println("O cachorro está latindo.");
    }
}

public class Main {
    public static void main(String[] args) {
        Cachorro meuCachorro = new Cachorro();
        meuCachorro.comer(); // Método herdado
        meuCachorro.latir(); // Método da subclasse
    }
}

```

---

#### 3. **Polimorfismo**

- Polimorfismo significa "muitas formas". Ele permite que **objetos de diferentes classes** sejam tratados como se fossem da mesma classe base, desde que compartilhem métodos em comum.
- Existem dois tipos principais de polimorfismo:
    - **Em tempo de compilação**: Ocorre com **sobrecarga de métodos** (mesmo nome, diferentes assinaturas).
    - **Em tempo de execução**: Ocorre com **sobrescrita de métodos** (mesmo nome, mesma assinatura, mas comportamentos diferentes em subclasses).

##### **Exemplo de polimorfismo em tempo de execução:**
```java
class Animal {
    void fazerSom() {
        System.out.println("Som genérico de animal.");
    }
}

class Gato extends Animal {
    @Override
    void fazerSom() {
        System.out.println("Miau");
    }
}

class Cachorro extends Animal {
    @Override
    void fazerSom() {
        System.out.println("Au au");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal meuAnimal;
        
        meuAnimal = new Gato();
        meuAnimal.fazerSom(); // Miau
        
        meuAnimal = new Cachorro();
        meuAnimal.fazerSom(); // Au au
    }
}

```

---

#### 4. **Abstração**

- A abstração consiste em **esconder detalhes complexos** e mostrar apenas o essencial. Isso é útil para representar conceitos genéricos que serão detalhados em subclasses.

##### **Como implementar?**

- Com **classes abstratas** ou **interfaces**:
    - Uma **classe abstrata** pode ter métodos com ou sem implementação.
    - Uma **interface** define apenas métodos abstratos, que devem ser implementados pelas classes que a utilizam.

##### **Exemplo com classe abstrata:**
```java
abstract class Forma {
    abstract void desenhar(); // Método abstrato
}

class Circulo extends Forma {
    @Override
    void desenhar() {
        System.out.println("Desenhando um círculo.");
    }
}

class Quadrado extends Forma {
    @Override
    void desenhar() {
        System.out.println("Desenhando um quadrado.");
    }
}

public class Main {
    public static void main(String[] args) {
        Forma forma;
        
        forma = new Circulo();
        forma.desenhar(); // Desenhando um círculo.
        
        forma = new Quadrado();
        forma.desenhar(); // Desenhando um quadrado.
    }
}

```

---

### **Vantagens da OOP**

1. **Reutilização de código**
    
    - Herança permite aproveitar código existente em novas classes.
2. **Organização e modularidade**
    
    - Objetos e classes dividem responsabilidades, tornando o código mais organizado.
3. **Fácil manutenção**
    
    - Alterações em uma classe não impactam diretamente outras partes do sistema.
4. **Extensibilidade**
    
    - Novas funcionalidades podem ser adicionadas sem grandes alterações no código existente.

---

### **Resumo: os pilares da OOP**

| Princípio          | O que é?                                                              | Como implementar?                       |
| ------------------ | --------------------------------------------------------------------- | --------------------------------------- |
| **Encapsulamento** | Ocultar dados internos e permitir acesso controlado.                  | Atributos privados + getters e setters. |
| **Herança**        | Reutilizar código herdando características de uma classe base.        | `class Subclasse extends Superclasse`.  |
| **Polimorfismo**   | Permitir múltiplas formas para um mesmo método.                       | Sobrecarga e sobrescrita de métodos.    |
| **Abstração**      | Ocultar detalhes complexos e expor apenas funcionalidades essenciais. | Classes abstratas e interfaces.         |
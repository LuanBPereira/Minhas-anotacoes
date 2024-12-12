___
## Stack

Geralmente, nossos métodos são armazenados na memória Stack, que funciona como uma pilha onde os métodos são empilhados em uma ordem específica. Vamos supor que existe um método chamado `func1()`, que chama `func2()`, e `func2()`, por sua vez, chama `func3()`, que apenas exibe um texto na tela. O primeiro a ser chamado é `func1()`. Nesse momento, a memória Stack cria uma estrutura chamada Stack Frame, que é como um quadrado que armazena tudo relacionado a `func1()`, incluindo variáveis, os parâmetros desse método e o endereço de retorno, que indica onde o programa deve voltar após a execução.

Em seguida, é criada outra Stack Frame para `func2()`, que pode, por exemplo, conter uma variável `a` que recebe o valor de uma referência à `func3()`. Por fim, uma nova Stack Frame é criada para `func3()`, onde ocorre a exibição da mensagem de texto. Após a conclusão das chamadas, a memória Stack vai encerrando as funções de cima para baixo, ou seja, do último para o primeiro. Assim, o que é chamado primeiro termina por último na pilha.

**Exemplo de como funciona a memória Stack**
```C
#include <stdio.h>

void func3() {
    printf("Executando func3()\n");
}

void func2() {
    int a = 5;  // Variável local na Stack Frame de func2
    printf("Executando func2(), a = %d\n", a);
    func3();  // Chama func3
}

void func1() {
    printf("Executando func1()\n");
    func2();  // Chama func2
}

int main() {
    func1();  // Inicia a chamada de func1
    return 0;
}
```

**Como funciona:**
```C++
main() chama func1(), criando uma Stack Frame para func1().
func1() chama func2(), criando uma Stack Frame para func2().
func2() chama func3(), criando uma Stack Frame para func3().
Quando func3() termina, sua Stack Frame é removida,
e o controle retorna para func2(), e assim por diante.
```
___
## Heap

A memória Heap é um tipo de memória onde o programador precisa ter um cuidado especial, pois tudo que você coloca na Heap deve ser removido posteriormente. Caso contrário, ocorrerá um vazamento de memória, onde a memória fica ocupada, mas nunca é liberada. Ao contrário da Stack, que gerencia isso automaticamente, a Heap é uma memória dinâmica que permanece até você decidir “chega, pode acabar por aqui”. Por exemplo, se você quiser criar uma lista que cresce dinamicamente, como uma lista de clientes armazenados em um sistema, a Heap é ideal para isto. Para alocar memória na Heap em C ou C++, usamos `new` ou `malloc`, e para liberar a memória, utilizamos `delete` ou `free`. Em linguagens como Java, C# e Python, você não precisa se preocupar com isso, pois um Garbage Collector (GC) gerencia automaticamente a memória Heap. No entanto, é importante que o programador evite criar referências desnecessárias, pois isso pode limitar a eficácia do GC. Em essência, o GC assume parte do trabalho de gerenciamento de memória que, em C++, deve ser feito manualmente pelo programador, o que traz suas próprias limitações.

**Exemplo de como funciona a memória Heap**
```C++
#include <iostream>

int main() {
    // Alocando memória na Heap para um inteiro
    int* numero = new int; // Aloca memória
    *numero = 42; // Atribui um valor
    std::cout << "Valor alocado na Heap: " << *numero << std::endl;
    
    // Lembre-se de liberar a memória para evitar vazamentos
    delete numero; // Libera a memória
    return 0;
}
```

**Exemplo de lista dinãmica usando a Heap**
```C++
#include <iostream>

// Tipo uma classe, mas que por padrão todos atibutos e métodos são publicos    
struct Cliente { 
std::string nome;
};

int main() {
    int tamanho = 5;
    
    // Alocação dinâmica de um array de Clientes 
    Cliente* clientes = new Cliente[tamanho];
    
    // Atribuindo nomes aos clientes
    for (int i = 0; i < tamanho; i++) {
        clientes[i].nome = "Cliente " + std::to_string(i + 1);
	    std::cout << "Nome do " << i + 1 << "º cliente: " << clientes[i].nome <<
	    std::endl; 
    }
    
    // Liberando a memória alocada
    delete[] clientes; // Libera o array de Clientes
    return 0;
}
```

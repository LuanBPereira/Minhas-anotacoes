___
Ponteiros podem parecer complicados, mas são mais simples do que parecem! Um ponteiro é um tipo de dado que se refere diretamente a um valor alocado em um espaço de memória, usando um endereço de memória. Por exemplo, vamos supor que temos uma variável do tipo inteiro chamada `numero`, que recebe o valor `2` (`int numero = 2;`). Para criar um ponteiro que aponta para o endereço de memória onde essa variável `numero` está armazenada, usamos um ponteiro do tipo inteiro, como `int* ponteiroParaInt`. Em seguida, podemos atribuir o endereço de `numero` ao ponteiro usando o caractere `&`: `ponteiroParaInt = &numero`. Com isso, o ponteiro irá conter o endereço de memória onde está alocada essa variável.
Para acessar o valor que o ponteiro está referenciando, usamos o caractere `*`, como em `int valor = *ponteiroParaInt;`. Isso nos permite acessar diretamente o valor armazenado na memória, que no nosso caso é o `2`. Além disso, ponteiros são frequentemente utilizados em funções para passar grandes estruturas de dados de forma mais eficiente, evitando a cópia desnecessária de dados.
É importante ressaltar que, em C++, também podemos passar diretamente a referência para um valor, sem precisar criar um ponteiro para acessar o valor em um determinado endereço. Isso torna a passagem de parâmetros mais simples e reduz as chances de erros comuns associados ao uso de ponteiros.

#### Exemplos de uso de ponteiros

 **Uso em C**
```C
#include <stdio.h>

void modificarPorPonteiro(int* ponteiro) {
*ponteiro = 10; // Acessa e modifica o valor que o ponteiro aponta
} 

int main() {
	int numero = 2; // Declara uma variável inteira
	printf("Valor original de numero: %d\n", numero);
	
	// Mostrando o endereço de memória da variável numero 
	printf("Endereco de memoria de numero: %p\n", &numero);
	
	// Chama a função passando o endereço de numero 
	modificarPorPonteiro(&numero);
	printf("Novo valor de numero (por ponteiro): %d\n", numero);
	return 0;
} 
```

**Saída**:
```C
A execução deste código gerará a seguinte saída:
Valor original de numero: 2
Endereco de memoria de numero: 0x7ffeeec4a7bc 
Novo valor de numero: 10
```
___

**Uso em C++**
```C++
#include <iostream>
using namespace std;

// Função que modifica o valor de um inteiro usando um ponteiro
void modificarPorPonteiro(int* ponteiro) {
    *ponteiro = 10;  // Acessa e modifica o valor que o ponteiro aponta
}

// Função que modifica o valor de um inteiro usando uma referência
void modificarPorReferencia(int& referencia) {
    referencia = 20;  // Modifica o valor da referência diretamente
}

int main() {
    int numero = 2;  // Declara uma variável inteira
    cout << "Valor original de numero: " << numero << endl;
	
	// Mostrando o endereço de memória da variável numero
	cout << "Endereco de memoria de numero: " << &numero << endl;
	
    // Chama a função passando o endereço de numero
    modificarPorPonteiro(&numero);
    cout << "Novo valor de numero (por ponteiro): " << numero << endl;
    
    // Chama a função passando a referência de numero
    modificarPorReferencia(numero);
    cout << "Novo valor de numero (por referência): " << numero << endl;
    return 0;
}

```

**Saída:**
```C++
A execução deste código gerará a seguinte saída:
Valor original de numero: 2
Endereco de memoria de numero: 0x7ffeeec4a7bc
Novo valor de numero (por ponteiro): 10
Novo valor de numero (por referência): 20
```
___

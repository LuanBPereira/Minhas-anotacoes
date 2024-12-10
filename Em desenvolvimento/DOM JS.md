___
setInterval/clearInterval - se precisar de fazer algo como um temporizador ou algo ocorrer durante um certo intervalo, pesquisar sobre esses dois.
caso eu precise mexer com formatação de data - [https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Date](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Date)
___

document - bem dizer é o HTML, Arquivo do HTML. Se digitarmos só "document" no console de uma página, retorna o HTML da página inteira.

document.querySelector(’id/class/tag’) - pega o primeiro elemento dado uns dos params.
```JavaScript
// Seleciona o primeiro elemento com a classe "classe".
const elemento = document.querySelector('.classe'); 
```

document.querySelectorAll(’id, class, tag’) retorna todos os elementos dado um dos params.
```JavaScript
// Selecionando todos os elementos com classe 'exemplo'
const todos = document.querySelectorAll('.exemplo');
```

getElementById: Busca um elemento único pelo seu ID (deve ser único no documento).
getElementsByClassName: Retorna uma coleção de elementos com uma determinada classe.
getElementsByTagName: Retorna uma coleção de elementos de um tipo específico de tag.
```JavaScript
 // Seleciona o elemento com o ID "meuId".
const elemento = document.getElementById('meuId');
 // Retorna uma coleção de elementos com a classe "classe".
const elementos = document.getElementsByClassName('classe');
 // Retorna uma coleção de elementos com a classe "classe".
const tags = document.getElementsByTagName('div');
```

## Método `addEventListener`

Antes de mergulharmos nos diferentes tipos de eventos, vamos entender rapidamente como o método addEventListener funciona. Ele é um método disponível para todos os elementos HTML e permite que registremos funções (callbacks) que serão chamadas quando um evento específico ocorrer.

**A sintaxe básica é a seguinte:**
```JavaScript
elemento.addEventListener(evento, callback);
```

**Onde:**

- ==**elemento:**== É o elemento HTML ao qual queremos associar o evento.
- ==**evento:**== É uma string que representa o tipo de evento que desejamos capturar.
- ==**callback:**== É a função que será chamada quando o evento ocorrer.
___

### Tipos de evento

#### Eventos de clique (`click`)

Os eventos de clique são alguns dos mais utilizados em desenvolvimento web. Eles ocorrem quando o usuário clica em um elemento específico da página, como um botão, um link ou até mesmo em uma imagem. Podemos usar o evento click para executar ações quando o usuário interage com esses elementos.

**Exemplo:**
```JavaScript
// HTML <button id="meuBotao">Clique aqui</button>

const meuBotao = document.getElementById("meuBotao")
meuBotao.addEventListener("click", function(){
alert("O botão foi clicado!")
})
```

Quando o usuário clicar no botão com o texto "Clique aqui", um alerta será exibido com a mensagem "O botão foi clicado!".
___
#### Eventos de submissão de formulário (`submit`)

Quando temos um formulário em nossa página, podemos usar o evento submit para capturar a submissão do formulário pelo usuário. Isso nos permite executar ações como validar os dados inseridos antes de enviá-los para o servidor.

**Exemplo:**
```JavaScript
//HTML <form id="meuFormulario">
//HTML     <input type="text" name="nome" />
//HTML     <input type="submit" value="Enviar" />
//HTML  </form>

const meuFormulario = document.getElementById("meuFormulario");
meuFormulario.addEventListener("submit", function(event) {
  event.preventDefault(); // Impede o envio padrão do formulário
  const nome = event.target.elements.nome.value;
  alert(`O formulário foi enviado com o nome: ${nome}`);
});
```

Quando o usuário preencher o campo de texto do formulário e clicar no botão "Enviar", um alerta será exibido com a mensagem "O formulário foi enviado com o nome: {nome inserido no campo}".
___

#### Eventos de teclado (`keydown, keyup, keypress`)

Os eventos de teclado permitem que respondamos às ações do usuário no teclado, como pressionar ou soltar uma tecla específica. Existem três principais tipos de eventos de teclado:

==**keydown:**== ocorre quando uma tecla é pressionada.
==**keyup:**== ocorre quando uma tecla é solta.
==**keypress:**== ocorre quando uma tecla é pressionada e ainda não foi solta.

**Exemplo:**
```JavaScript
//HTML<input type="text" id="meuInput" />

const meuInput = document.getElementById("meuInput");
meuInput.addEventListener("keydown", function(event) {
  console.log(`Tecla pressionada: ${event.key}`);
});
```

Quando o usuário pressiona uma tecla enquanto o cursos está no campo de texto, o evento **keydown** será acionado e o código imprimirá no console a mensagem "Tecla pressionada: {tecla pressionada}".
___

#### Eventos de foco (`focus, blur`)

Os eventos de foco são usados quando queremos capturar quando um elemento recebe ou perde o foco. O evento **focus** ocorre quando um elemento ganha o foco (por exemplo, quando clicamos em um campo de formulário), enquanto o evento **blur** ocorre quando o elemento perde o foco.

**Exemplo:**
```JavaScript
//HTML <input type="text" id="meuCampo" />

const meuCampo = document.getElementById("meuCampo");
meuCampo.addEventListener("focus", function() {
  console.log("Campo ganhou o foco.");
});

meuCampo.addEventListener("blur", function() {
  console.log("Campo perdeu o foco.");
});
```

Quando o usuário clicar no campo de texto, o evento **focus** será acionado e o código imprimirá no console a mensagem "Campo ganhou foco.". Quando o usuário clicar fora do campo, fazendo-o perder o foco, o evento **blur** será acionado e o código imprimirá no console a mensagem "Campo perdeu o foco."
___

## Métodos (`Attributes`)

#### getAttribute

O método `getAttribute` é usado para obter o valor de um atributo específico de um elemento HTML. Ele recebe um argumento, que é o nome do atributo que desejamos recuperar o valor.

**Exemplo:**
```JavaScript
// HTML: <div id="meuElemento" data-info="Exemplo de atributo">

const elemento = document.getElementById('meuElemento');
const valorDoAtributo = elemento.getAttribute('data-info');
console.log(valorDoAtributo); // Saída: "Exemplo de atributo"
```

Neste exemplo, o método `getAttribute` foi usado para obter o valor do atributo data-info do elemento com o ID "meuElemento".
___

#### setAttribute

O método setAttribute é usado para definir ou modificar o valor de um atributo em um elemento HTML. Ele aceita dois argumentos: o primeiro é o nome do atributo que queremos definir ou modificar, e o segundo é o valor que queremos atribuir a esse atributo. Se o atributo já existir, o método setAttribute irá sobrescrevê-lo; caso contrário, ele criará um novo atributo.

**Exemplo:**
```JavaScript
// HTML: <p id="meuParagrafo">Texto inicial</p>

const paragrafo = document.getElementById('meuParagrafo');
paragrafo.setAttribute('id', 'paragrafoModificado');
paragrafo.setAttribute('data-novo-atributo', 'Novo valor');
```

Após a execução deste código, o parágrafo terá seu ID alterado para "paragrafoModificado" e será adicionado um novo atributo data-novo-atributo com o valor "Novo valor".
___

#### hasAttribute

O método `hasAttribute` é usado para verificar se um elemento possui um atributo específico. Ele recebe um argumento, que é o nome do atributo que queremos verificar. O método retornará true se o atributo existir e false se o atributo não estiver presente.

**Exemplo:**
```JavaScript
// HTML: <a href="https://www.exemplo.com" id="meuLink">Link de exemplo</a>

const link = document.getElementById('meuLink');
const temHref = link.hasAttribute('href');
console.log(temHref); // Saída: true
const temTarget = link.hasAttribute('target');
console.log(temTarget); // Saída: false
```

Neste exemplo, o método `hasAttribute` foi usado para verificar se o elemento com o ID "meuLink" possui o atributo "href" (que é verdadeiro) e se possui o atributo "target" (que é falso).
___

#### removeAttribute

O método `removeAttribute` é usado para remover um atributo específico de um elemento HTML. Ele recebe um argumento, que é o nome do atributo que desejamos remover.

**Exemplo:**
```JavaScript
// HTML: <img src="imagem.jpg" alt="Imagem de exemplo" id="minhaImagem">

const imagem = document.getElementById('minhaImagem');
imagem.removeAttribute('alt');
```

Após a execução desse código, o atributo alt da imagem será removido, tornando-a menos acessível para pessoas com deficiência visual e fazendo com que o navegador não exiba um texto alternativo quando a imagem não puder ser carregada.
___

## InnerHTML

Propriedade que é usada em JavaScript para manipular ou acessar o conteúdo em HTML de um elemento no DOM (Documento Object Model) de uma página web. Ele permite definir ou obter o conteúdo interno de um elemento, incluindo elementos filhos e suas marcações HTML.

#### Como funciona o `innerHTML`

1. **Obter o conteúdo:**  Se você acessar o valor de `innerHTML` de um elemento, ele retorna o conteúdo HTML dentro desse elemento como uma string
```html
<div id="exemplo"> Olá, <b>Mundo!</b></div>
<script>
	const elemento = document.getElementById("exemplo")
	console.log(elemento.innerHTML) // Output: "Olá, <b.Mundo!</b>"
</script>
```

2. **Modificar o conteúdo:** Se você atribuir um valor a `innerHTML`, ele substitui todo o conteúdo existente do elemento com o novo HTML que você especificar.
```html
<div id="exemplo"></div>
<script>
	const elemento = document.getElementById("exemplo")
	elemento.innetHTML = "<p>Conteúdo atualizado!</p>"
	// Agora a div contém: <p>Conteúdo atualizado"</p>
</script>
```
___

#### Cuidados ao usar `innerHTML`

1. **Risco de segurança (XSS):** Se o conteúdo a ser inserido no DOM incluir entradas do usuário sem validação ou sanitização, isso pode levar a vulnerabilidades de **Cross-Site Scripting (XSS)**.
   **Exemplo:**
```JavaScript
   const userInput = "<img src='x' onerror='alert(\"hacked!\")'>"
   document.getElementById("exemplo").innerHTML = userInput
```
   Aqui, o código malicioso embutido no `userInput` será executado no navegador do usuário.
   
2. **Sobrescreve o conteúdo existente:** Quando você usa `innerHTML` para modificar um elemento, ele substitui todo o conteúdo existente, incluindo eventos associados. Isso significa que você pode perder funcionalidades que foram previamente anexadas.

3. **Impacto no desempenho:** Modificar grandes blocos de HTML com `innerHTML` pode ser menos eficiente do que alterar elementos individuais, especialmente em páginas grandes ou dinâmicas.
___

#### Alternativas ao `innerHTML`

- `textContent`: Use quando você deseja manipular apenas o texto de um elemento, sem interpretar HTML.
  ```JavaScript
  elemento.textContent = "<b>Texto literal</b>" // Renderiza como texto literal
```

- **Manipulação direta de DOM**: Em vez de substituir todo o HTML, você pode criar e adicionar elementos diretamente usando métodos como `createElement` e `appendChild`.
  ```JavaScript
  const novoElemento = document.createElement("p")
  novoElemento.textContent = "Conteúdo dinâmico"
  elemento.appendChild(novoElemento)
```
___
#### Quando usar `innerHTML`

O `innerHTML` é útil para tarefas rápidas e simples como:
- Atualizar o conteúdo de um elemento HTML dinâmico.
- Adicionar ou substituir pequenos trechos de conteúdo onde os riscos de XSS estão controlados.
___

## ClassList

o `classList` é uma propriedade do JavaScript que representa uma lista de classes CSS. Ele fornece métodos que facilitam a adição, remoção e verificação de classes, tornando a manipulação de classes CSS mais eficiente e menos suscetível a erros de programação.
___

#### Adicionando uma classe

Para adicionar uma classe a um elemento HTML, podemos usar o método `add()` do `classList`. Este método aceita o nome da classe como argumento e adiciona a classe ao elemento, se ela ainda não estiver presente.

**Exemplo:**
```javaScript
const element = document.getElementById('meuElemento')
element.classList.add('minhaClasse')
```
___

#### Removendo uma classe

Para remover uma classe de um elemento HTML, podemos utilizar o método `remove()` do `classList`. Este método aceita o nome da classe argumento e remove a classe do elemento, se ela estiver presente.

**Exemplo:**
```JavaScript
const element = document.getElementById('meuElemento')
element.classList.remove('minhaClasse')
```
___
#### Alternando uma classe

O método `toggle()` do `classList` permite alternar uma classe em um elemento. Se a classe já estiver presente no elemento, o método a remove; caso contrário, ele a adiciona.

**Exemplo:**
```JavaScript
const element = document.getElementById('meuElemento')
element.classList.toggle('minhaClasse')
```
___

#### Verificando se uma classe está presente

Para verificar se uma classe específica está associada a um elemento, podemos usar o método `contains()` do `classList`.

**Exemplo:**
```JavaScript
const element = document.getElementById('meuElemento')
if (element.classList.contains('minhaClasse')) {
 // A classe 'minhaClasse' está presente no elemento
 // Faça algo aqui...
}
```
___

#### Substituindo classes

Como feito em aula, podemos substituir uma classe por outra usando os métodos `add()` e `remove()` em sequência.
```JavaScript
const element = document.getElementById('meuElemento')
element.classList.remove('classeAntiga')
element.classList.add('classeNova')
```
___

#### Manipulando várias classes simultaneamente

É possível adicionar ou remover várias classes de uma vez usando o método `add()` ou `remove()` passando vários argumentos separados por vírgula.
```JavaScript
const element = document.getElementById('meuElemento')
element.classList.add('classe1', 'classe2', 'classe3')
element.classList.remove('classe2', 'classe3')
```
___

O `classList` em JavaScript é uma ferramenta poderosa e eficiente para manipular classes CSS em elementos HTML. Com os métodos `add()`, `remove()`, `toggle()`, `contains()` e outras funcionalidades, podemos realizar tarefas de manipulação de classes de forma mais segura e simplificada, tornando nossas aplicações web mais interativas e dinâmicas.

**Fica aqui uma tabela de métodos que existem do `classList`.**

| **Método/Propriedade** | **Descrição**                                                     |
| ---------------------- | ----------------------------------------------------------------- |
| **add()**              | Adiciona um ou mais tokens (classes) à lista.                     |
| **contains()**         | Retorna `true` se a lista contém a classe especificada.           |
| **entries()**          | Retorna um Iterador com pares de chave/valor da lista.            |
| **forEach()**          | Executa uma função de callback para cada token (classe) na lista. |
| **item()**             | Retorna o token (classe) no índice especificado.                  |
| **keys()**             | Retorna um Iterador com as chaves na lista.                       |
| **length**             | Retorna o número de tokens (classes) na lista.                    |
| **remove()**           | Remove um ou mais tokens (classes) da lista.                      |
| **replace()**          | Substitui um token (classe) na lista por outro.                   |
| **supports()**         | Retorna `true` se um token é suportado pelos atributos da lista.  |
| **toggle()**           | Alterna entre adicionar e remover tokens (classes) na lista.      |
| **value**              | Retorna a lista de tokens (classes) como uma string.              |
| **values()**           | Retorna um Iterador com os valores (tokens/classes) na lista.     |
___

## Objeto `Audio`

 Uma das funcionalidades mais interessantes que o JavaScript oferece é a capacidade de manipular áudio, permitindo que os desenvolvedores adicionem e controlem elementos de áudio em seus sites de forma dinâmica. Uma das formas mais comuns de fazer isso é usando o objeto `Audio`.
 
O objeto `Audio` é uma parte do HTML5 e fornece uma interface fácil e poderosa para reproduzir e controlar arquivos de áudio em tempo real. 
___

#### Criando um objeto `Audio`

Para criar um novo objeto `Audio`, podemos simplesmente usar a seguinte sintaxe:
```JavaScript
const audioElement = new Audio('caminho/do/arquivo-de-audio.mp3')
```
___

#### Controles básicos de áudio

Após criar um objeto `Audio`, podemos controlar sua reprodução e outras propriedades usando métodos e propriedades disponíveis.
- `play()`: inicia a reprodução do áudio;
- `pause()`: pausa a reprodução do áudio;
- `currentTime`: propriedade que retorna ou define uma posição atual de reprodução de áudio, em segundos;
- `volume`: propriedade que retorna ou define o nível de volume do áudio, variando de 0 a 1.

**Exemplo de utilização dos métodos do objeto Audio**
```JavaScript
const audioElement = new Audio('caminho/do/arquivo-de-audio.mp3')

audioElement.play() // Inicia a reprodução
audioElement.pause() // Pausa a reprodução
audioElement.currentTime = 10 // Move para 10 segundos no áudio
audioElement.volume = 0.5 // Define o volume para a metade (50%)
```
___

## Propriedades node (continuar a desenvolver)

#### Propriedade parentNode 


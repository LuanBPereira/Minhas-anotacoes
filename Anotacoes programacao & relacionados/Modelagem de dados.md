___
## Minimundo, levantamento de requisitos e modelo conceitual

Ao desenvolver sistemas de banco de dados, é fundamental entender como as informações serão organizadas e manipuladas. Três conceitos-chave neste processo são o Minimundo, o Levantamento de Requisitos e o Modelo Conceitual. Vamos explorar cada um deles de maneira simplificada para facilitar a compreensão de como eles contribuem para a modelagem de dados.
___

### Minimundo

O conceito de Minimundo refere-se a uma parte específica do mundo real que é relevante para o sistema que está sendo desenvolvido. Imagine que você está construindo um sistema para uma biblioteca; o minimundo incluiria coisas como livros, empréstimos, leitores e funcionários, mas não incluiria elementos irrelevantes como o café vendido na cafeteria ao lado. O minimundo ajuda a definir claramente o escopo do que será incluído no sistema de banco de dados.
___

### Levantamento de Requisitos

O Levantamento de Requisitos é o processo de coletar informações sobre o que os usuários precisam e esperam do sistema. No contexto da biblioteca, isso poderia envolver entender como os leitores gostariam de pesquisar livros, quais informações sobre os livros são importantes (como título, autor, gênero), e como os funcionários gerenciam os empréstimos. Esse processo é crucial porque define as funcionalidades que o sistema precisa suportar e influencia diretamente como o banco de dados será projetado.
___

## Modelo Conceitual

Após definir o minimundo e coletar os requisitos, o próximo passo é criar um Modelo Conceitual. Este modelo é uma representação visual de alta abstração de como os dados no sistema são organizados. Ele usa elementos como entidades (objetos do mundo real como 'Livro' ou 'Leitor'), atributos (propriedades das entidades como 'Título do Livro' ou 'Nome do Leitor') e relacionamentos (como 'empresta' entre 'Leitor' e 'Livro'). O modelo conceitual é geralmente criado usando um Diagrama Entidade-Relacionamento (DER), que ajuda a visualizar como os diferentes elementos estão interconectados.
___

### **Conclusão**

Esses três componentes — Minimundo, Levantamento de Requisitos e Modelo Conceitual — são fundamentais na modelagem de dados porque juntos eles garantem que o sistema de banco de dados será bem projetado, funcional e capaz de atender às necessidades dos usuários. Ao começar com uma compreensão clara do minimundo, passando por uma coleta meticulosa de requisitos, até a criação de um modelo conceitual eficaz, os desenvolvedores podem construir bases de dados robustas e eficientes que apoiam os processos e operações críticas de negócios.
___

## Algumas ferramentas que podem ser usadas para criar um modelo conceitual:

Erwin, Microsoft Visio, LucidChart, Excalidraw e Miro.
___

Quando você começa a trabalhar em um novo projeto, seja ele um aplicativo, um site ou qualquer outro tipo de sistema, uma das primeiras e mais importantes etapas é entender o que exatamente você precisa construir. Isso é conhecido como levantamento de requisitos. Imagine que você está planejando construir uma casa. Antes de começar, você precisa saber quantos quartos ela terá, se haverá um jardim, quantos andares, entre outros detalhes. No mundo do desenvolvimento de software, esse processo é semelhante e extremamente crucial para o sucesso do projeto.
___

## Entrevistas

Uma das técnicas mais diretas para coletar requisitos é através de entrevistas. Aqui, você conversa diretamente com as pessoas que vão usar o sistema (os usuários finais) ou com quem tem uma visão do que o sistema deve fazer (como os stakeholders, que podem ser gerentes, investidores, ou clientes). O objetivo é fazer perguntas que te ajudem a entender o que eles precisam que o sistema faça.

### **Como fazer:**

1. **Prepare-se**: Antes da entrevista, faça sua lição de casa. Pesquise sobre o projeto e quem você vai entrevistar.
2. **Perguntas abertas**: Use perguntas que incentivem a pessoa a falar mais, como "O que você espera que o sistema faça?".
3. **Escute ativamente**: Mostre que você está interessado no que a pessoa está dizendo. Isso pode encorajá-la a compartilhar mais informações.
___

## Questionários

Questionários são úteis quando você precisa coletar informações de muitas pessoas. Eles podem ser distribuídos fisicamente ou online e permitem coletar dados de forma estruturada e em grande escala.

### **Como fazer:**

1. **Questões claras e concisas**: As perguntas devem ser fáceis de entender e responder.
2. **Tipos de perguntas**: Use uma mistura de perguntas fechadas (sim/não, escolha múltipla) e abertas para coletar uma variedade de dados.
3. **Pilote seu questionário**: Teste-o com um pequeno grupo antes de enviar para todos. Isso ajuda a identificar e corrigir problemas.
___

## Observação Direta

Observar as pessoas enquanto elas realizam suas tarefas diárias pode te dar insights valiosos sobre o que elas realmente precisam. Isso pode ser especialmente útil para identificar requisitos que as pessoas podem não perceber ou esquecer de mencionar em entrevistas ou questionários.

### **Como fazer**

1. **Seja discreto**: Você quer observar o comportamento natural das pessoas, então tente não interferir.
2. **Tome notas**: Anote tudo o que achar relevante, mesmo que pareça pequeno ou insignificante no momento.
3. **Procure padrões**: Depois da observação, analise suas notas procurando padrões ou problemas recorrentes.
___

## Motivação

O levantamento de requisitos é a fundação de qualquer projeto de desenvolvimento. Fazer isso corretamente significa economizar tempo, dinheiro e esforço mais tarde, evitando mal-entendidos e retrabalho. Além disso, entender claramente o que os usuários finais precisam garante que o produto final seja útil e bem recebido.
___

### **Conclusão**

Levantar requisitos é uma arte tanto quanto uma ciência. Usar uma combinação de entrevistas, questionários e observação direta pode te dar uma visão completa do que é necessário para o seu projeto. Lembre-se, a chave para um levantamento de requisitos bem-sucedido é a comunicação clara e eficaz. Quanto melhor você entender o que precisa ser construído, mais suave será o processo de desenvolvimento.
___

## Entidades

Em modelagem de dados, o conceito de **entidades** é fundamental para compreender como as informações são organizadas em um sistema de banco de dados. Uma entidade pode ser vista como um objeto ou conceito do mundo real que possui dados relevantes a serem armazenados e gerenciados. A seguir, vamos explorar de forma simplificada o que são entidades e como elas são utilizadas na modelagem de dados.

### Definição de Entidade

Uma **entidade** é um elemento dentro do modelo de dados que representa algo capaz de ser identificado de forma única. Em outras palavras, é uma "coisa" que existe por si só e possui características específicas. Essas características são chamadas de **atributos**, que registram informações sobre a entidade.

### Exemplos de Entidades

- **Pessoa**: Uma entidade comum em muitos sistemas. Os atributos de uma pessoa podem incluir nome, endereço, telefone e data de nascimento.
- **Produto**: Em um sistema de gestão de estoque, cada produto é uma entidade com atributos como código do produto, descrição, preço e quantidade em estoque.
- **Pedido**: Em sistemas de vendas, um pedido pode ser uma entidade com atributos como número do pedido, data do pedido, status e total do pedido.

### Características das Entidades

- **Agrupamento de Atributos**: As entidades são definidas não apenas por suas identidades, mas também pelos atributos que carregam. Estes atributos dão significado à entidade e detalham suas características.
- **Relacionamentos**: Entidades frequentemente mantêm relações com outras entidades. Por exemplo, uma entidade 'Cliente' pode estar relacionada a várias entidades 'Pedido', indicando que esse cliente fez vários pedidos.

### Uso das Entidades na Modelagem de Dados

Na modelagem de dados, as entidades são usadas para estruturar e organizar as informações de forma que reflitam os processos e regras do negócio. Elas são a base para a criação de tabelas em bancos de dados relacionais. Cada entidade se torna uma tabela, e cada atributo da entidade se torna uma coluna na tabela.

### Importância das Entidades

- **Organização de Dados:** As entidades ajudam a organizar dados em formatos logicamente coerentes, facilitando o armazenamento, recuperação e manipulação dos dados.
- **Eficiência**: A correta definição de entidades e seus relacionamentos é crucial para a construção de um banco de dados eficiente, que possa responder rapidamente às consultas e manter a integridade dos dados.
- **Desenvolvimento de Software**: No desenvolvimento de sistemas, a definição clara de entidades ajuda na comunicação entre desenvolvedores e stakeholders, garantindo que todos os aspectos necessários do sistema estejam bem representados e entendidos.

Entidades são, portanto, peças-chave na construção de qualquer sistema de banco de dados, agindo como a espinha dorsal para a organização e a gestão de dados dentro de um ambiente computacional.
No modelo conceitual de um banco de dados, as entidades são classificadas como fortes ou fracas com base em sua capacidade de existir independentemente:

### Entidades Fortes

Uma entidade forte é uma entidade que pode existir por si só, sem depender de outra entidade para a sua existência.

### Entidades Fracas

Uma entidade fraca, ao contrário da entidade forte, não existe por si só, ou seja, depende de uma outra entidade para existir.
___

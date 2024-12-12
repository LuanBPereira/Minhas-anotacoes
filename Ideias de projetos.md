___
## Ideia projeto JAVA com PYTHON

Fazer um programa em que: pegue um arquvio csv, no caso arquivo do excel, e veja o quanto de gasto teve no mês, o quanto entrou de dinheiro (por exemplo salário, mesada, etc…) e guarde esse valores.

Também quero ver o quanto de dinheiro eu estou guardando, é importante ter todos esses valores.

Então a ideia é: alimentar esse arquivo .csv e, com o programa, poder visualizar o quanto eu tive de entrada de dinheiro no mês, o quanto eu tenho guardado, o quanto eu gastei e o que me sobrou de dinheiro com os gastos.
___

> [!NOTE] Para o projeto da Locadora!
> Trocar a biblioteca de log que to usando na locadora. Começar a usar a Log4j.
> Fazer as requests da api da omdb com a biblioteca do apache http.

## Projeto de Filme com **Java**, **React** e **Python**

### Arquitetura do Sistema

1. **Frontend (React - Web App)**
    - Interface web interativa para visualização de filmes, pesquisa, compra de filmes, etc.
    - Comunicação com a **API Java** (via HTTP) para listar filmes, realizar compras e enviar dados para o banco de dados.
    - Consome dados da API e exibe em componentes React.
    - Responsividade para uso em diferentes dispositivos.
2. **Backend (Java - API de Filmes)**
    - **API RESTful** que fornece dados sobre os filmes.
    - Manipulação de dados de filmes no **banco de dados**.
    - Gerenciamento de compras realizadas pelos usuários e salvamento no banco de dados.
3. **Integração (Python - Geração de Relatórios)**
    - **Python** acessa diretamente o banco de dados para geração de relatórios analíticos.
    - Geração de relatórios como:
        - Filme mais comprado.
        - Cliente que mais comprou.
        - Total de vendas no mês.
---

### Fluxo de Dados e Interações

1. **React (Frontend)** envia requisições HTTP para a **API Java** para listar filmes, pesquisar e realizar compras.
2. O **usuário** interage com o frontend para realizar ações como escolher filmes e realizar compras.
3. O **React** envia os dados da compra para a **API Java**, que armazena no banco de dados.
4. **Python** acessa os dados do banco de dados para geração de relatórios.
---

### Diagrama de Fluxo/Arquitetura

```
plaintext
Copiar código
+----------------------+      +---------------------------+      +--------------------+
|  Frontend (React)    |      |   Backend (API Java)      |      | Python (Relatórios)|
+----------------------+      +---------------------------+      +--------------------+
        |                            |                              |
        | (1) Solicitação de filmes   |                              |
        |---------------------------->|                              |
        |                             | (2) Retorno de filmes         |
        |                             |-----------------------------> |
        |                             |                              |
        |  (3) Escolha e compra de    |                              |
        |      filme (Armazenamento)  |                              |
        |---------------------------->|                              |
        |                             |                              |
        |                             | (4) Armazenamento no banco   |
        |                             |-----------------------------> |
        |                             |                              |
        |                             | (5) Python consulta dados     |
        |                             |-----------------------------> |
        |                             |                              |
        |   (6) Exportação ou         |                              |
        |     visualização            |                              |
        |<----------------------------|                              |
        |                             |                              |
        +----------------------+      +---------------------------+      +--------------------+

```
---

### **1. Backend (Java + Spring Boot)**

O backend será a base do sistema, então é importante dominar os fundamentos.

- **Java Básico**:
    - Sintaxe, controle de fluxo (`if`, `for`, `while`).
    - Estruturas de dados (listas, mapas).
    - Orientação a Objetos (classes, herança, polimorfismo, encapsulamento).
- **APIs RESTful**:
    - O que são APIs e como funcionam.
    - Conceitos de HTTP (GET, POST, PUT, DELETE, status codes).
- **Spring Boot**:
    - Criar um projeto simples no Spring Boot.
    - Configurar endpoints com `@RestController`.
    - Usar **Spring Data JPA** para conectar ao banco de dados.
- **Banco de Dados**:
    - SQL básico: criar tabelas, inserir dados, fazer consultas.
    - Relacionamento entre tabelas (chaves estrangeiras, `JOIN`).
---

### **2. Frontend (React)**

Com React, você vai criar uma interface amigável para os usuários.

- **HTML e CSS**:
    - Estrutura básica de uma página (tags, formulários, botões).
    - Como estilizar elementos.
- **JavaScript**:
    - Manipulação de DOM.
    - Funções, variáveis, `async/await`, `fetch`.
- **React**:
    - Criar componentes funcionais.
    - Gerenciar estados com `useState` e `useEffect`.
    - Fazer requisições HTTP com **Axios** ou `fetch`.
    - Roteamento com **React Router** (para páginas diferentes, como lista de filmes e detalhes do filme).
---

### **3. Banco de Dados**

O banco será o "coração" do sistema, onde todas as informações serão armazenadas.

- Escolha um banco como **MySQL**, **PostgreSQL** ou **SQLite** para começar.
- Estude:
    - **DDL (Data Definition Language)**: criar e alterar tabelas.
    - **DML (Data Manipulation Language)**: inserir, atualizar e excluir dados.
    - Consultas com `SELECT`, `WHERE`, `GROUP BY`.
---

### **4. Relatórios (Python)**

Python será usado para análises e relatórios.

- **Python Básico**:
    - Estruturas de dados (listas, dicionários, loops).
    - Manipulação de arquivos (`open`, `read`, `write`).
- **Acesso ao Banco de Dados**:
    - Usar bibliotecas como **sqlite3** ou **SQLAlchemy** para executar consultas SQL.
- **Manipulação de Dados**:
    - **Pandas**: limpar e organizar dados para relatórios.
- **Gráficos e Visualizações**:
    - **Matplotlib** ou **Seaborn** para criar gráficos simples.
    - Exemplo: gráfico de barras para vendas por mês.
---

### **5. Ferramentas Gerais**

Algumas ferramentas vão ajudar no desenvolvimento como um todo:

- **Git e GitHub**:
    - Controle de versões (salvar o progresso do código).
    - Colaborar em projetos.
- **Postman**:
    - Testar sua API sem precisar de frontend pronto.
- **IDE/Editor de Código**:
    - Backend: **IntelliJ IDEA** ou **Eclipse**.
    - Frontend: **VS Code**.
---

### **Plano de Estudo**

1. Comece pelo básico de cada linguagem:
    - Aprenda **Java** e como criar APIs simples.
    - Estude **HTML, CSS e JavaScript** para criar páginas básicas.
    - Experimente **Python** para manipulação de arquivos e gerar dados simples.
2. Escolha um foco inicial:
    - Aprenda **Spring Boot** para criar a API.
    - Estude **React** para consumir APIs e exibir informações.
3. Faça pequenos projetos:
    - API simples em Java para listar filmes fictícios.
    - Um app React que consome essa API e exibe dados na tela.
    - Um script Python que lê dados de um arquivo e gera relatórios simples.
4. Combine as peças:
    - Integre a API com React.
    - Use Python para acessar o banco e gerar relatórios
___

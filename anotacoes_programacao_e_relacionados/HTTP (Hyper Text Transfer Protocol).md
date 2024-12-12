___
O HTTP funciona no modelo client-server (cliente-servidor). Isso significa que sempre há um cliente, como um navegador, que faz requisições para obter informações. Por outro lado, existe um servidor, que é responsável por receber essas requisições, processá-las e enviar uma resposta ao cliente. Por exemplo, quando você acessa um site, o navegador (cliente) faz uma requisição ao servidor pedindo os arquivos necessários, como o HTML, CSS e JavaScript. O servidor responde enviando essas informações, que o navegador usa para montar e exibir o site. O HTTP foi criado para definir as regras dessa troca de informações entre cliente e servidor, ou seja, para estabelecer como essa "conversa" deve acontecer. Por ser um protocolo, ele define um conjunto de normas que tanto o cliente quanto o servidor devem seguir para que a comunicação funcione corretamente.

## Métodos HTTP (continuar desenvolvendo depois)

**Os principais métodos HTTP são:**

#### 1. POST (Criar)

O método **POST** é usado para enviar dados ao servidor para criar algo novo. Por exemplo, cadastrar um novo usuário ou adicionar um produto.

**Exemplo:**
- **Cenário:** Cadastrar um novo usuário em um sistema.
- **Requisição**:
```JSON
POST /usuarios
Body:
{
	"nome": "João",
	"email": "joao@gmail.com",
	"senha": "123456"
}
```
- **Resposta do servidor:**
```JSON
201 Created
Body:
{
	"id": 1,
	"nome": "João",
	"email": "joao@gmail.com"
}
```
___

#### 2. GET (Ler)
O método **GET** é usado para buscar informações no servidor, sem modificar nada. Por exemplo, visualizar a lista de produtor ou consultar detalhes de um item.

**Exemplo:**
- **Cenário:** Buscar a lista de usuários.
- **Requisição:**
```JSON
GET /usuarios
```
- **Resposta do servidor:**
```JSON
200 OK
Body:
[
  { "id": 1, "nome": "João" },
  { "id": 2, "nome": "Maria" }
]
```
___

#### 3. PUT (Atualizar)
O método **PUT** é usado para atualizar completamente um recurso existente. Por exemplo, modificar as informações de um usuário.

**Exemplo:**
- **Cenário:** Atualizar o e-mail de um usuário.
- **Requisição:**
```JSON
PUT /usuarios/1
Body:
{
  "nome": "João",
  "email": "novo-email@email.com",
  "senha": "123456"
}
```
- **Resposta do servidor:**
```JSON
200 OK
Body:
{
  "id": 1,
  "nome": "João",
  "email": "novo-email@email.com"
}
```
___

#### 4. DELETE (Apagar)
O método **DELETE** é usado para remover um recurso no servidor. Por exemplo, deletar um usuário ou apagar um item do carrinho.

**Exemplo:**
- **Cenário:** Apagar um usuário.
- **Requisição:**
```JSON
DELETE /usuarios/1
```
- **Resposta do servidor:**
```JSON
204 No Content
```
___

#### Resumo dos exemplos em um sistema de gerenciamento de usuários:

- **POST:** Criar um novo usuário.
- **GET:** Obter informações de usuários existentes.
- **PUT:** Atualizar as informações de um usuário.
- **DELETE:** Apagar um usuário do sistema.
___

Um ponto importante a lembrar sobre o **servidor HTTP** é que ele é **stateless** (sem estado). Isso significa que o servidor **não guarda informações sobre as interações anteriores**. Cada requisição que o cliente faz é independente, ou seja, o servidor não "lembra" de quem fez a requisição antes.

Por exemplo, se um usuário se autentica em uma aplicação, o servidor não vai "lembrar" dessa autenticação nas próximas requisições. Portanto, a cada nova requisição, o cliente precisa informar ao servidor quem está acessando, geralmente por meio de **cookies** ou **tokens(sessão)**, para que o servidor saiba qual usuário está realizando a ação.
___

## URL

As URLs são um endereço padronizado para definir onde vai ser localizado algum recurso da web, como imagens, APIs, vídeos, sites, etc.

Por exemplo, no mundo físico, seria algo como: "Vá para a Rua Principal, nº 100 (domínio), na cidade X (protocolo), entre pela porta lateral (porta), e procure o quarto nº 3 (caminho)."

![imagem url](anotacoes_programacao_e_relacionados/imagens/image-url.png)
___

### URL ou URI?

Muitas vezes, desenvolvedores usam a sigla URI (Uniform Resource Identifier) quando falam de endereços na web. Alguns preferem URL (Uniform Resource Locator), e alguns misturam as duas siglas à vontade. Há uma certa confusão no mercado a respeito e mesmo desenvolvedores experientes não sabem explicar a diferença. Então, qual é a diferença?

Resposta 1 (fácil): Uma URL é uma URI. No contexto do desenvolvimento web, ambas as siglas são válidas para falar de endereços na web. As siglas são praticamente sinônimos e são utilizadas dessa forma.

Resposta 2 (mais elaborada): Uma URL é uma URI, mas nem todas as URI's são URL's! Existem URI's que identificam um recurso sem definir o endereço, nem o protocolo. Em outras palavras, uma URL representa uma identificação de um recurso (URI) através do endereço, mas nem todas as identificações são URL's.

Humm ... ficou claro? Não? Vamos dar um exemplo! Existe um outro padrão que se chama URN (Uniform Resource Name). Agora adivinha, os URN's também são URI's! Um URN segue também uma sintaxe bem definida, algo assim urn:cursos:alura:course:introducao-html-css. Repare que criamos uma outra identificação do curso Introdução ao HTML e CSS da Alura, mas essa identificação não é um endereço.

![imagem uri](anotacoes_programacao_e_relacionados/imagens/image-uri.png)
___

#### Portas padrão

| 80                 | Padrão HTTP     |
| ------------------ | --------------- |
| 443                | Padrão HTTPS    |
| de 1023* até 65535 | Livras para uso |
**OBS**: Portas entre 0 e 1023 são reservadas para serviços padronizados.
___

## DNS

O **DNS** (Domain Name System) é como uma "agenda telefônica" da internet. Ele traduz os **nomes de domínio** (como `www.google.com`) em **endereços IP** (como `142.250.187.78`), que são os "endereços reais" que os computadores usam para se comunicar na rede.

**Por que o DNS é necessário?**
Os computadores se conectam uns aos outros usando **endereços IP**, que são conjuntos de números. Porém, para os humanos, lembrar nomes como `www.example.com` é muito mais fácil do que lembrar números como `192.168.1.1`. O DNS resolve isso fazendo a tradução automaticamente.

**Como o DNS funciona?**
Quando você digita um endereço de site (URL) no navegador, o DNS faz o seguinte:

1. **Consulta ao DNS**
    
    O navegador pergunta ao sistema DNS: "Qual é o endereço IP de `www.google.com`?"
    
2. **Procura pelo endereço**
    
    O DNS verifica em diferentes servidores até encontrar o endereço IP correspondente.
    
3. **Resposta com o IP**
    
    O DNS retorna o endereço IP, por exemplo, `142.250.187.78`, para o navegador.
    
4. **Conexão com o servidor**
    
    O navegador usa o endereço IP para se conectar ao servidor do site e carregar a página.
    
___

Outro ponto interessante de comentar é que o **DNS** (Domain Name System) é **hierárquico**! Ele organiza e armazena informações sobre domínios em uma estrutura que lembra uma **árvore invertida**, onde cada nível da hierarquia é responsável por uma parte do domínio.

**Como funciona a hierarquia do DNS?**
1. **Root (Raiz)**
    
    No topo da hierarquia está o **servidor root** (representado como um ponto `.` no final de um  domínio, embora geralmente não seja exibido).
    
    Exemplo: Para `www.google.com`, a raiz seria `.`.
    O servidor root aponta para os servidores que gerenciam os domínios de nível superior  (TLDs).
    
2. **TLD (Domínio de Nível Superior)**
    
    Logo abaixo da raiz, estão os domínios de nível superior, como:
    - **Genéricos**: `.com`, `.org`, `.net`.
    - **Países**: `.br` (Brasil), `.us` (Estados Unidos), `.uk` (Reino Unido).Cada TLD tem servidores que gerenciam informações sobre os domínios registrados com essa extensão.
    
1. **Domínios (Nível Secundário)**
    
    Esses são os nomes registrados pelos proprietários, como `google` em `google.com`. Os  servidores TLD apontam para os servidores autoritativos responsáveis por esses domínios.
    
4. **Subdomínios**
    
    Dentro de um domínio, podem existir subdomínios, como `www` em `www.google.com` ou  `mail` em `mail.google.com`. Esses subdomínios podem ser gerenciados por servidores específicos.
___

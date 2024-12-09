___
Para a chave ser criada, você vai precisar abrir o git bash (ou qualquer outro prompt que preferir, pode ser da própria IDE que esteja usando mesmo), copiar esse código: ssh-keygen -t ed25519 -C "[emailexemplo@gmail.com](mailto:emailexemplo@gmail.com)", colar, trocar para seu email do github e dar “enter”. Após isso, ele vai te perguntar se tu quer colocar esse arquivo, que vai ser a chave, em um local especifico. Caso queira, tu pode especificar o caminho de onde o arquivo vai ser gerado. Senão, ele vai gerar em um local padrão mesmo, que é dentro da pasta .ssh.

Depois, ele vai perguntar se tu quer criar uma senha, em que, toda vez que for sincronizar com o GitHub, ele vai pedir pra inserir. Literalmente uma senha de acesso. Dai se tu quiser, digita uma senha e pronto, sempre vai ter essa senha. Senão, só dá “enter” e segue em frente. Depois disso ele vai gerar tipo uma imagem da chave e é só dar “enter” e acabou! Chave gerada.

Agora, é só ir na pasta que tu escolheu pra chave ser guardada, abrir o arquivo da chave com algum bloco de nota, copiar essa chave e colar lá onde tinha “Key” no GitHub, como foi mostrado na imagem logo acima e pronto! Agora você tem um repositório com uma chave SSH para sincronizar os dois!

Vou deixar umas curiosidades do porquê usar uma chave SSH em vez de HTTPS:

Usar chaves SSH no GitHub tem várias vantagens, incluindo:

- **Segurança -** A autenticação via chave SSH é mais segura que usar senhas, pois evita que elas sejam vulneráveis.
- **Produtividade -** O processo de autenticação é rápido e não é necessário inserir senhas, o que economiza tempo.
- **Colaboração -** A possibilidade de compartilhar chaves públicas facilita a colaboração entre equipes.
- **Não é necessário fornecer login e senha a cada visita -** Com as chaves SSH, não é preciso inserir o nome de usuário e o token de acesso pessoal a cada vez que se visita o GitHub.
- **Assinatura de commits -** As chaves SSH podem ser usadas para assinar commits.

O SSH é um protocolo de rede que usa criptografia de chave pública para autenticar o computador remoto e o usuário. Ele permite que os administradores de um servidor acessem um computador remoto de forma segura, mesmo em conexões inseguras.

link de referencia: [https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
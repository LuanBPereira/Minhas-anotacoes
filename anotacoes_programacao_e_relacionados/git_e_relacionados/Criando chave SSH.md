### Como Gerar e Adicionar uma Chave SSH no GitHub

Para criar e configurar uma chave SSH para o GitHub, siga os passos abaixo:

1. **Abrir o Terminal**:
    
    - Abra o Git Bash ou o terminal da sua IDE preferida.
2. **Gerar a Chave SSH**:
    
    - Digite o seguinte comando, substituindo pelo seu e-mail do GitHub:
        
	    `ssh-keygen -t ed25519 -C "seu-email@exemplo.com"` ;      
        Pressione **Enter**.
3. **Escolher o Local para Armazenar a Chave**:
    
    - O terminal vai te perguntar onde deseja salvar a chave. Se quiser salvar em um local específico, forneça o caminho. Caso contrário, basta pressionar **Enter**, e a chave será gerada na pasta padrão `.ssh`.
4. **Criar uma Senha (Opcional)**:
    
    - Em seguida, será solicitado se você deseja criar uma senha para a chave. Se quiser, digite uma senha e pressione **Enter**. Caso não queira configurar uma senha, basta pressionar **Enter** novamente para seguir sem senha.
5. **Gerar a Chave SSH**:
    
    - Após a confirmação, a chave SSH será gerada. Você verá uma representação da chave no terminal. Agora, a chave está pronta para ser usada!
6. **Adicionar a Chave SSH no GitHub**:
    
    - Navegue até a pasta onde a chave foi salva (por padrão, ela fica na pasta `.ssh`).
    - Abra o arquivo da chave com um editor de texto (por exemplo, o Bloco de Notas).
    - Copie o conteúdo da chave pública.
    - Acesse o GitHub e vá para **Configurações** > **SSH and GPG keys** > **New SSH key**.
    - Cole a chave copiada no campo **Key** e adicione um título para identificá-la.

Agora você tem uma chave SSH configurada para sincronizar com seu repositório GitHub!
___

### Por que Usar uma Chave SSH em vez de HTTPS?

Aqui estão algumas vantagens de usar chaves SSH para autenticação no GitHub:

- **Segurança**: A autenticação via chave SSH é mais segura que o uso de senhas, pois evita vulnerabilidades de senhas.
- **Produtividade**: O processo de autenticação é mais rápido, pois não é necessário inserir senhas constantemente.
- **Colaboração**: A chave pública pode ser compartilhada facilmente entre equipes, facilitando a colaboração.
- **Facilidade de Acesso**: Não é necessário fornecer seu nome de usuário ou token de acesso pessoal a cada vez que acessar o GitHub.
- **Assinatura de Commits**: Chaves SSH também podem ser usadas para assinar commits, garantindo a autenticidade deles.
___

### O que é o SSH?

O **SSH** (Secure Shell) é um protocolo de rede que usa criptografia de chave pública para autenticar o computador remoto e o usuário. Ele permite que administradores acessem um servidor de forma segura, mesmo em conexões inseguras.

---

Referência: [GitHub Docs - Gerando uma Nova Chave SSH e Adicionando ao SSH Agent](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
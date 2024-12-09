___
### **Inicialização e Configuração**

1. ==**`git init`**== – Inicializar um repositório Git vazio:
    - Exemplo: `git init`
    - Cria um novo repositório Git no diretório atual.
2. ==**`git config --global user.email "emailexemplo@gmail.com"`**== – Configurar o email globalmente:
    - Exemplo: `git config --global user.email "emailexemplo@gmail.com"`
    - Define o email padrão para commits em todos os repositórios do sistema.
3. ==**`git config --global user.name "Nome Exemplo"`**== – Configurar o nome globalmente:
    - Exemplo: `git config --global user.name "Nome Exemplo"`
    - Define o nome de usuário padrão para commits.

---

### **Gerenciamento de Arquivos**

1. ==**`git status`**== – Verificar o estado atual do repositório:
    - Exemplo: `git status`
    - Mostra quais arquivos foram modificados ou estão prontos para commit.
2. ==**`git add`**== – Adicionar arquivos ao stage:
    - Exemplo: `git add arquivo.txt`
    - Move um ou mais arquivos para o estágio (staging area) para serem commitados.
3. ==**`git rm`**== – Remover arquivos do repositório:
    - Exemplo: `git rm arquivo.txt`
    - Remove o arquivo do repositório e o apaga do diretório local.
4. ==**`git rm --cached arquivo.txt`**== – Parar de rastrear um arquivo, mas mantê-lo no sistema de arquivos:
    - Exemplo: `git rm --cached arquivo.txt`
    - Remove o arquivo do repositório (não será mais versionado), mas o mantém no diretório local.
5. ==**`git commit -m "mensagem"`**== – Registrar mudanças no repositório:
    - Exemplo: `git commit -m "Adiciona nova funcionalidade"`
    - Cria um commit com as mudanças, incluindo uma mensagem explicativa.

> [!NOTE]
> git branch -r - vê as branchs remotas que existem
> 
> git push —delete nome-da-branch - deleta uma branch remota

---

### **Sincronização com Repositórios Remotos**

1. ==**`git push`**== – Enviar commits para o repositório remoto:
    - Exemplo: `git push origin main`
    - Envia os commits do branch local para o branch `main` no repositório remoto.
2. ==**`git pull`**== – Baixar e incorporar mudanças do repositório remoto:
    - Exemplo: `git pull origin main`
    - Atualiza o branch local com mudanças do branch `main` do repositório remoto.
3. ==**`git clone`**== – Clonar um repositório remoto:
    - Exemplo: `git clone <https://github.com/usuario/repositorio.git`>
    - Faz uma cópia completa de um repositório remoto para a sua máquina local.
4. ==**`git remote add origin URL_DO_REPOSITORIO`**== – Adicionar um repositório remoto:
    - Exemplo: `git remote add origin <https://github.com/usuario/repositorio.git`>
    - Associa um repositório remoto ao repositório local.
5. ==**`git remote -v`**== – Verificar os repositórios remotos:
    - Exemplo: `git remote -v`
    - Lista os repositórios remotos configurados.
6. ==**`git remote remove origin`**== – Remover um repositório remoto:
    - Exemplo: `git remote remove origin`
    - Remove a URL do repositório remoto associado.
7. ==**`git remote set-url origin NOVA_URL`**== – Alterar a URL do repositório remoto:
    - Exemplo: `git remote set-url origin <https://novorepositorio.com`>
    - Atualiza a URL de um repositório remoto existente.

---

### **Gerenciamento de Branches**

1. ==**`git branch`**== – Listar branches existentes:
    - Exemplo: `git branch`
    - Mostra todas as branches do repositório local.
2. ==**`git branch nomeNovaBranch`**== – Criar uma nova branch:
    - Exemplo: `git branch feature-nova`
    - Cria uma nova branch chamada `feature-nova`.
3. ==**`git checkout branch`**== – Mudar para outra branch:
    - Exemplo: `git checkout develop`
    - Muda para a branch `develop`.
4. ==**`git switch branch`**== – Mudar para outra branch (comando mais novo):
    - Exemplo: `git switch develop`
    - Alterna para a branch `develop`. (Equivalente ao `checkout`, mas mais simples.)
5. ==**`git merge branch`**== – Mesclar mudanças de outra branch:
    - Exemplo: `git merge feature-nova`
    - Mescla as alterações da branch `feature-nova` na branch atual.
6. ==**`git branch -m branch`**== – Renomear uma branch:
    - Exemplo: `git branch -m nova-branch`
    - Renomeia a branch atual para `nova-branch`.
7. ==**`git branch -d branch`**== – Remover uma branch:
    - Exemplo: `git branch -d feature-antiga`
    - Apaga a branch `feature-antiga`.
8. ==**`git checkout -b`**== – Criar e mudar para uma nova branch:
    - Exemplo: `git checkout -b hotfix`
    - Cria e muda para a branch `hotfix`.
9. ==**`git switch -c nomeNovaBranch`**== – Criar e mudar para uma nova branch:
    - Exemplo: `git switch -c nova-branch`
    - Cria e alterna para `nova-branch`.
10. ==**`git rebase branch`**== – Reaplicar commits de uma branch em outra:
    - Exemplo: `git rebase main`
    - Reaplica os commits da branch `main` na branch atual.
11. ==**`git cherry-pick commitID`**== – Aplicar as mudanças de um commit específico:
    - Exemplo: `git cherry-pick a1b2c3d4`
    - Aplica as mudanças do commit `a1b2c3d4` à branch atual, criando um novo commit com essas alterações.

---

### **Visualização de Histórico e Diferenças**

1. ==**`git log`**== – Exibir o histórico de commits:
    - Exemplo: `git log`
    - Lista o histórico completo de commits no repositório.
2. ==**`git log --oneline`**== – Histórico resumido:
    - Exemplo: `git log --oneline`
    - Exibe um histórico de commits de forma mais compacta (resumido a uma linha por commit).
3. ==**`git log -p`**== – Histórico com diferenças detalhadas:
    - Exemplo: `git log -p`
    - Exibe o histórico dos commits com as mudanças feitas em cada commit.
4. ==**`git log --graph`**== – Exibir o histórico com um gráfico de branches:
    - Exemplo: `git log --graph`
    - Mostra o histórico de commits com um gráfico que representa a estrutura de branches.
5. ==**`git diff`**== – Mostrar diferenças entre o working directory e o último commit:
    - Exemplo: `git diff`
    - Exibe as alterações que ainda não foram commitadas.
6. ==**`git show hash_commit`**== – Exibir detalhes de um commit específico:
    - Exemplo: `git show a1b2c3d4`
    - Mostra informações detalhadas de um commit específico, incluindo mudanças feitas.
7. ==**`git blame arquivo.txt`**== – Exibir quem modificou cada linha de um arquivo:
    - Exemplo: `git blame arquivo.txt`
    - Mostra uma linha a linha do arquivo `arquivo.txt`, indicando qual commit e autor modificaram cada linha. Isso ajuda a rastrear a origem das alterações e entender a história do arquivo.

---

### **Desfazendo Alterações**

1. ==**`git revert id`**== – Desfazer um commit específico:
    
    - Exemplo: `git revert a1b2c3d4`
    - Cria um novo commit que reverte as mudanças de um commit anterior.
2. ==**`git reset --hard id`**== – Apagar alterações até um commit específico:
    
    - Exemplo: `git reset --hard a1b2c3d4`
    - Remove todos os commits e alterações posteriores ao commit especificado, voltando o repositório para aquele estado.
    - `git reset HEAD~5` - reseta os últimos 5 commits
3. ==**`git commit --amend`**== – Modificar o último commit:
    
    - Exemplo: `git commit --amend -m "Nova mensagem"`
    - Permite editar a mensagem ou o conteúdo do último commit.
4. ==**`git stash`**== – Armazenar temporariamente mudanças não commitadas:
    
    - Exemplo: `git stash`
    - Salva as alterações no stash (área de armazenamento temporário) e limpa o working directory, permitindo que você volte ao último estado commitado.
5. ==**`git stash pop`**== – Recuperar as mudanças armazenadas no stash:
    
    - Exemplo: `git stash pop`
    - Aplica as alterações salvas no stash de volta ao working directory e remove o stash correspondente.
6. ==**`git stash list`**== – Listar stashes salvos:
    
    - Exemplo: `git stash list`
    - Exibe uma lista de todas as alterações temporariamente armazenadas no stash, permitindo que você veja o histórico de stashes salvos e escolha qual aplicar.
7. ==**`git stash apply`**== – Aplicar as mudanças de um stash sem removê-lo:
    
    - Exemplo: `git stash apply stash@{0}`
    - Aplica as alterações de um stash específico ao working directory, mas mantém o stash salvo para uso posterior.
8. ==**`git stash clear`**== – Limpar todos os stashes:
    
    - Exemplo: `git stash clear`
    - Remove todos os stashes armazenados, limpando o stash completamente. Use com cuidado, pois essa ação não pode ser desfeita.
9. ==**`git stash push -m "mensagem"`**== – Armazenar mudanças com uma mensagem descritiva:
    
    - Exemplo: `git stash push -m "Alterações no layout da página"`
        
    - Salva as mudanças no stash com uma mensagem personalizada, facilitando a identificação e o gerenciamento de stashes. Os comandos `pop`, `drop` e `apply` do `git stash` possuem semelhanças e diferenças bem importantes, então vamos fazer um pequeno resumo de suas funcionalidades aqui:
        
        ### **Apply**
        
        O comando `git stash apply` espera um índice de um item na _stash_ e o aplica ao repositório, porém, esse comando **não remove** o item da _stash_, ou seja, se após executar o comando `git stash apply 1` você executar `git stash list`, o item referente ao índice 1 continuará na _stash_.
        
        ### **Pop**
        
        O `git stash pop` faz exatamente a mesma coisa que o `git stash apply`, porém, além de aplicar o item da _stash_, ele também o remove de lá. Esse comando, sem nenhum parâmetro extra, vai aplicar o último item adicionado à _stash_, mas nós também podemos informar um índice para ele, como `git stash pop 1`.
        
        ### **Drop**
        
        O `git stash drop` funciona exatamente como o `pop`, mas com uma simples diferença: ele apenas remove o item da _stash_, sem aplicá-lo em nosso repositório. Dessa forma, `git stash drop` remove o último item adicionado à _stash_, enquanto o `git stash drop 1` remove da _stash_ o item com índice 1.
10. ==**`git restore arquivo.txt`**== – Descartar mudanças em um arquivo:
    
    - Exemplo: `git restore arquivo.txt`
    - Restaura o arquivo `arquivo.txt` ao seu último estado no commit, descartando as mudanças feitas no working directory.
11. ==**`git restore --staged arquivo.txt`**== – Remover arquivo do estágio (unstage):
    
    - Exemplo: `git restore --staged arquivo.txt`
    - Retira o arquivo `arquivo.txt` do estágio (staging area), mantendo as mudanças no working directory.
12. ==**`git restore --source=commitID arquivo.txt`**== – Restaurar arquivo para um commit específico:
    
    - Exemplo: `git restore --source=a1b2c3 arquivo.txt`
    - Restaura o arquivo `arquivo.txt` para o estado em um commit específico (`a1b2c3`), descartando as alterações feitas após esse commit.
13. ==**`git restore --worktree`**== – Restaurar arquivos no working tree:
    
    - Exemplo: `git restore --worktree arquivo.txt`
    - Recupera o arquivo da árvore de trabalho (`working tree`), revertendo mudanças no arquivo local.

### **Gerenciamento de Tags**

---

1. ==**`git tag`**== – Listar todas as tags:
    - Exemplo: `git tag`
    - Exibe todas as tags existentes no repositório.
2. ==**`git tag -a nomeTag -m "mensagem"`**== – Criar uma tag anotada:
    - Exemplo: `git tag -a v1.0 -m "Primeira versão estável"`
    - Cria uma tag anotada com a mensagem associada. As tags anotadas contêm metadados adicionais, como a mensagem, data, e autor.
3. ==**`git tag nomeTag`**== – Criar uma tag leve:
    - Exemplo: `git tag v1.0`
    - Cria uma tag simples (leve) no commit atual, sem mensagem ou metadados.
4. ==**`git tag nomeTag commitID`**== – Criar uma tag em um commit específico:
    - Exemplo: `git tag v1.0 a1b2c3d4`
    - Cria uma tag leve no commit `a1b2c3d4`, apontando para esse commit específico.
5. ==**`git tag -d nomeTag`**== – Remover uma tag local:
    - Exemplo: `git tag -d v1.0`
    - Remove a tag `v1.0` localmente, sem afetar o repositório remoto.
6. ==**`git push origin --tags`**== – Enviar todas as tags para o repositório remoto:
    - Exemplo: `git push origin --tags`
    - Envia todas as tags criadas localmente para o repositório remoto.
7. ==**`git push origin nomeTag`**== – Enviar uma tag específica para o repositório remoto:
    - Exemplo: `git push origin v1.0`
    - Envia a tag `v1.0` para o repositório remoto.
8. ==**`git push origin :refs/tags/nomeTag`**== – Remover uma tag do repositório remoto:
    - Exemplo: `git push origin :refs/tags/v1.0`
    - Apaga a tag `v1.0` no repositório remoto.
9. ==**`git show nomeTag`**== – Ver detalhes de uma tag:
    - Exemplo: `git show v1.0`
    - Exibe os detalhes do commit associado à tag `v1.0` e, se for uma tag anotada, mostra também a mensagem e metadados.
10. ==**`git tag -v nomeTag`**== – Verificar a assinatura de uma tag:
	- Exemplo: `git tag -v v1.0`
	- Verifica a autenticidade de uma tag assinada usando GPG. Se a tag foi criada com uma assinatura, esse comando valida se a assinatura é autêntica e se corresponde a uma chave confiável.
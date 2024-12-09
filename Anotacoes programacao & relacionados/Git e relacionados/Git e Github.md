___
#### Páginas
- [[Comandos Git]]
- [[Sincronizando chave SSH no GitHub]]
- 
___
> Esse documento foi criado pra deixar curiosidades e conhecimentos sobre o Git e Github, quero deixar registrado as coisas que vou aprendendo.
> Talvez algumas coisas sejam meio verbossas, meio grande, mas acho importante deixar algumas coisas bem explicadas.
> Em fim, vou deixar um resuminho do que é o Git e o GitHub só para curiosidade. :]
### Git

O Git é um **sistema de controle de versão distribuído** que registra o histórico de alterações em arquivos monitorados. Ele foi criado por **Linus Torvalds** (criador do Linux) e é uma ferramenta fundamental para gerenciamento de projetos de software. Suas principais características incluem:

- **Controle de Versão**: Git permite criar um histórico de alterações, possibilitando a restauração de versões anteriores dos arquivos.
- **Distribuído**: Cada desenvolvedor tem uma cópia completa do repositório, o que permite trabalhar localmente e sincronizar alterações com outros quando necessário.
- **Branches**: É possível criar ramificações independentes do código (branches) para desenvolver novas funcionalidades, corrigir bugs ou experimentar ideias, sem interferir na versão principal do projeto. O que significa que não precisamos mexer no código principal em si, tu cria como se fosse uma espécie de ramo mesmo, que liga com a branch principal.
- **Eficiente e rápido**: Git é otimizado para armazenar e comparar mudanças de forma eficiente.
- **Descentralizado**: Diferente de sistemas de controle de versão centralizados, com Git, as operações não dependem de uma conexão com um servidor central, já que o repositório completo é mantido localmente.
___
### GitHub

GitHub é uma **plataforma de desenvolvimento colaborativo** que utiliza o Git como sistema de versionamento. Ele atua como um hub onde os desenvolvedores podem armazenar, compartilhar e colaborar em projetos de forma organizada. Principais funcionalidades:

- **Hospedagem de Repositórios**: GitHub armazena projetos versionados usando Git, permitindo o trabalho colaborativo e a exposição de códigos ao público.
- **Portfólio e Visibilidade**: Desenvolvedores podem usar o GitHub como um portfólio, exibindo seus projetos e contribuições para a comunidade.
- **Colaboração**: A plataforma facilita o trabalho em equipe com recursos como:
    - **Pull Requests**: Requisições de mudanças no código, usadas para revisar e mesclar alterações de outros colaboradores.
    - **Issues**: Ferramenta para rastreamento de tarefas, bugs e melhorias.
    - **Forks**: Cópias de repositórios, permitindo que qualquer pessoa possa fazer modificações em um projeto sem interferir no código original.
- **Integração e Automação**: Com o **GitHub Actions**, é possível configurar automações, como execução de testes, validação de código e deployment.
- **Comunidade**: GitHub também é uma rede social para desenvolvedores, promovendo o código aberto e a troca de conhecimento, onde qualquer pessoa pode contribuir com projetos públicos.

Uma coisa que eu achei interessante e importante saber: o HEAD é tipo um apelido que o Git dá pra apontar pro último commit que teve. Então origin/head seria o ultimo commit que teve no origin.
___
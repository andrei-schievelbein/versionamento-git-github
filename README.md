### Introdução ao Git

**Git** é um sistema de controle de versão distribuído, criado por Linus Torvalds em 2005, que permite gerenciar mudanças no código-fonte ao longo do tempo.

### Principais Conceitos:

1. **Repositório (Repository):** Um diretório que contém todo o histórico de mudanças do seu projeto, incluindo commits, branches e tags.
2. **Commit:** Um snapshot do seu projeto em um determinado momento. Cada commit possui uma mensagem que descreve a mudança feita.
3. **Branch:** Um ponteiro móvel para commits. O `master` (ou `main`) é a branch principal, mas você pode criar outras branches para desenvolver novas features ou corrigir bugs.
4. **Merge:** Combina mudanças de diferentes branches.
5. **Clone:** Cria uma cópia local de um repositório remoto.
6. **Pull:** Atualiza seu repositório local com as mudanças do repositório remoto.
7. **Push:** Envia as mudanças do repositório local para o repositório remoto.

### Configurando o Git

1. **Instalação:**
    - Windows: Git for Windows
    - macOS: `brew install git`
    - Linux: `sudo apt-get install git`
2. **Configuração Inicial:**
    
    ```bash
    git config --global user.name "Seu Nome"
    git config --global user.email "seu.email@example.com"
    ```
    
3. **Configurando o nome da Branch Padrão:**
    
    ```
    $ git config --global init.defaultBranch main
    ```
    
    O comando `git config --list` no Git é utilizado para listar todas as configurações do Git que estão ativas no momento.
    
    `CRTL + L` Limpa o terminal
    

### Fluxo Básico de Trabalho com Git

1. **Criar um Novo Repositório:**
    
    ```bash
    git init nome-do-repositorio
    cd nome-do-repositorio
    ```
    
2. **Verificar conteúdo do arquivo config.**
    
    ```bash
    cd .git
    cat config
    [core]
            repositoryformatversion = 0
            filemode = false
            bare = false
            logallrefupdates = true
            symlinks = false
            ignorecase = true
    
    ```
    
3. **Adicionar Arquivos e Criar Commits:**
    
    ```bash
    touch README.md
    git add arquivo.txt
    git commit -m "Mensagem do commit"
    ```
    
4. **Verificar Status:**
    
    ```bash
    git status
    ```
    
5. **Verificar Histórico de Commits:**
    
    ```bash
    git log
    ```
6. **Modificar última mensagem de commit**
    ```
    git commit --amend -m "Mensagem do commit"
    ```
    

### Trabalhando com GitHub

**GitHub** é uma plataforma de hospedagem de código-fonte com controle de versão usando Git. Ele permite colaboração entre desenvolvedores e facilita o trabalho em equipe.

1. **Criar uma Conta no GitHub:** GitHub
2. **Criar um Novo Repositório no GitHub:**
    - Vá para seu perfil e clique em "New repository".
    - Nomeie o repositório e escolha se ele será público ou privado.
    - Clique em "Create repository".
3. **Conectar Repositório Local ao GitHub:**
    
    ```bash
    git remote add origin https://github.com/usuario/nome-do-repositorio.git
    git push -u origin main
    ```
    

### Fluxo de Trabalho Colaborativo

1. **Clonar Repositório:**
    
    ```bash
    git clone https://github.com/usuario/nome-do-repositorio.git nome-opcional
    cd nome-do-repositorio
    ```
    
    Clonar somente a branch feature-1
    
    ```bash
    git clone URL --branch feature-1 --single-branch
    ```
    
    Verificar repositório remoto conectado.
    
    ```bash
    git remote -v
    ```
    
2. **Criar e Trocar para uma Nova Branch:**
    
    ```bash
    git checkout -b nome-da-branch
    ```
    
3. **Fazer Alterações e Commitar:**
    
    ```bash
    git add .
    git commit -m "Descrição das alterações"
    ```
    
4. **Enviar Branch para o Repositório Remoto:**
    
    ```bash
    git push origin nome-da-branch
    ```
    
5. **Criar um Pull Request no GitHub:**
    - Vá para o repositório no GitHub.
    - Clique em "Compare & pull request" e preencha os detalhes.
    - Envie o pull request para revisão.

### Boas Práticas

1. **Commits Atômicos:** Faça commits pequenos e específicos para facilitar a revisão e o rastreamento de mudanças.
2. **Mensagens de Commit Descritivas:** Utilize mensagens claras e detalhadas.
3. **Branches para Features e Hotfixes:** Use branches para desenvolver novas funcionalidades e corrigir bugs sem afetar a branch principal.
4. **Revisões de Código:** Sempre revise o código por meio de pull requests antes de mesclar mudanças.

### Exemplos de Comandos Avançados

1. **:**
    
    ```bash
    git rebase master
    ```
    
2. **Cherry-Pick (Selecionar Commits Específicos):**
    
    ```bash
    git cherry-pick <commit-hash>
    ```
    
3. **Stash (Guardar Mudanças Temporariamente):**
    
    ```bash
    git stash
    git stash apply
    ```
    
4. **Reverter um Commit:**
    
    ```bash
    git revert <commit-hash>
    ```
    

### Recursos Adicionais

- Documentação Oficial do Git
- Guias do GitHub
- Pro Git Book

Com essas informações, você deve estar pronto para começar a usar Git e GitHub de maneira eficiente.
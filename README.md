# Versionamento Git e GitHub

✔ Principais comandos e boas práticas utilizando Git e GitHub

### Introdução ao Git

**Git** é um sistema de controle de versão distribuído, criado por Linus Torvalds em 2005, que permite gerenciar mudanças no código-fonte ao longo do tempo.

### Principais Conceitos

1. **Repositório (Repository):** Um diretório que contém todo o histórico de mudanças do seu projeto, incluindo commits, branches e tags.
2. **Commit:** Um snapshot do seu projeto em um determinado momento. Cada commit possui uma mensagem que descreve a mudança feita.
3. **Branch:** Um ponteiro móvel para commits. O `master` (ou `main`) é a branch principal, mas você pode criar outras branches para desenvolver novas features ou corrigir bugs.
4. **Merge:** Combina mudanças de diferentes branches.
5. **Clone:** Cria uma cópia local de um repositório remoto.
6. **Pull:** Atualiza seu repositório local com as mudanças do repositório remoto.
7. **Push:** Envia as mudanças do repositório local para o repositório remoto.
8. **Stash:** Guarda temporariamente mudanças não commitadas.

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
    
    ```bash
    git config --global init.defaultBranch main
    ```

4. **Listar todas as configurações do Git:**
    
    ```bash
    git config --list
    ```
    
    `CTRL + L` limpa o terminal.
    
### Fluxo Básico de Trabalho com Git

1. **Criar um Novo Repositório:**
    
    ```bash
    git init nome-do-repositorio
    cd nome-do-repositorio
    ```
    
2. **Adicionar Arquivos e Criar Commits:**
    
    ```bash
    touch README.md
    git add arquivo.txt
    git commit -m "Mensagem do commit"
    ```
    
3. **Verificar Status do Repositório:**
    
    ```bash
    git status
    ```
    
4. **Verificar Histórico de Commits:**
    
    ```bash
    git log
    ```
    
5. **Modificar Última Mensagem de Commit:**
    
    ```bash
    git commit --amend -m "Mensagem do commit"
    ```
    
6. **Mostrar Diferenças entre Arquivos:**
    
    ```bash
    git diff
    ```

### Convenções de Nomes

1. **Nomes de Repositórios:**
    - Use nomes descritivos e significativos.
    - Evite caracteres especiais e espaços; prefira hifens (-) para separar palavras.
    - Exemplos: `meu-projeto`, `aplicativo-web`, `sistema-de-vendas`.

2. **Nomes de Branches:**
    - Utilize um padrão consistente para facilitar a identificação.
    - Prefixos comuns incluem `feature/`, `bugfix/`, `hotfix/`, `release/`.
    - Use hifens (-) para separar palavras e descreva a finalidade da branch.
    - Exemplos: `feature/nova-funcionalidade`, `bugfix/corrigir-login`, `hotfix/ajuste-paginacao`.

### Trabalhando com Branches

1. **Mostrar Branch Atual:**
    
    ```bash
    git branch
    ```
    
2. **Criar e Trocar para uma Nova Branch:**
    
    ```bash
    git checkout -b nome-da-branch
    ```
    
3. **Mudar para uma Determinada Branch:**
    
    ```bash
    git checkout nome-da-branch
    ```
    
4. **Deletar uma Branch:**
    
    ```bash
    git branch -d nome-da-branch
    ```
    
5. **Verificar Branches com Detalhes:**
    
    ```bash
    git branch -v
    ```

### Integrando Mudanças

1. **Merge de Ramificações:**
    
    ```bash
    git merge nome-da-branch-que-voce-quer-mesclar
    ```
    
2. **Rebase:**
    
    ```bash
    git rebase master
    ```
    
3. **Cherry-Pick (Selecionar Commits Específicos):**
    
    ```bash
    git cherry-pick <commit-hash>
    ```
    
4. **Reverter um Commit:**
    
    ```bash
    git revert <commit-hash>
    ```

### Stash: Guardando Mudanças Temporariamente

1. **Guardar Mudanças Temporariamente:**
    
    ```bash
    git stash
    ```
    
2. **Listar Stashes:**
    
    ```bash
    git stash list
    ```
    
3. **Aplicar Stash:**
    
    ```bash
    git stash apply
    ```
    
4. **Aplicar e Remover Stash:**
    
    ```bash
    git stash pop
    ```

### Trabalhando com GitHub

**GitHub** é uma plataforma de hospedagem de código-fonte com controle de versão usando Git. Ele permite colaboração entre desenvolvedores e facilita o trabalho em equipe.

1. **Criar uma Conta no GitHub:** [GitHub](https://github.com)
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
    
    Clonar somente a branch específica:
    
    ```bash
    git clone URL --branch feature-1 --single-branch
    ```
    
2. **Verificar Repositório Remoto Conectado:**
    
    ```bash
    git remote -v
    ```
    
3. **Criar e Trocar para uma Nova Branch:**
    
    ```bash
    git checkout -b nome-da-branch
    ```
    
4. **Fazer Alterações e Commitar:**
    
    ```bash
    git add .
    git commit -m "Descrição das alterações"
    ```
    
5. **Enviar Branch para o Repositório Remoto:**
    
    ```bash
    git push origin nome-da-branch
    ```
    
6. **Criar um Pull Request no GitHub:**
    - Vá para o repositório no GitHub.
    - Clique em "Compare & pull request" e preencha os detalhes.
    - Envie o pull request para revisão.

### Atualizando o Repositório

1. **Pegar Alterações do Repositório Remoto:**
    
    ```bash
    git pull origin nome-da-branch
    ```
    
2. **Atualizar as Referências Remotas:**
    
    ```bash
    git fetch
    ```

3. **Comparar Diferenças entre Branches:**
    
    ```bash
    git diff main origin/main
    ```

### Boas Práticas

1. **Commits Atômicos:** Faça commits pequenos e específicos para facilitar a revisão e o rastreamento de mudanças.
2. **Mensagens de Commit Descritivas:** Utilize mensagens claras e detalhadas.
3. **Branches para Features e Hotfixes:** Use branches para desenvolver novas funcionalidades e corrigir bugs sem afetar a branch principal.
4. **Revisões de Código:** Sempre revise o código por meio de pull requests antes de mesclar mudanças.

### Exemplos de Comandos Avançados

1. **Rebase:**
    
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
    git stash pop
    ```
    
4. **Reverter um Commit:**
    
    ```bash
    git revert <commit-hash>
    ```

### Recursos Adicionais

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [Guias do GitHub](https://guides.github.com/)
- [Pro Git Book](https://git-scm.com/book/en/v2)
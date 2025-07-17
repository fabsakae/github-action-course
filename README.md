# github-action-course
Repositório contendo exemplos para o GitHub action course
### Exercício Prático 01 - Criando Nosso Primeiro Workflow do curso
* Descrição do Exercício: Neste exercício prático, nosso objetivo é criar nosso primeiro workflow.

## Instruções para o Exercício
* Crie um arquivo chamado `01-building-blocks.yaml` dentro da pasta `.github/workflows` na raiz do seu repositório.

* Nomeie o workflow como 01 - Building Blocks.

* Adicione os seguintes "triggers" (gatilhos) ao seu workflow:

`push`

`workflow_dispatch`

* Adicione dois "jobs" (tarefas) ao workflow:

`Primeiro job: echo-hello`

Deve rodar em ubuntu-latest.

Deve ter um único "step" (passo), chamado `Say hello`, que simplesmente imprime a mensagem `"Hello, World!"` na tela.

`Segundo job: echo-goodbye`

Também deve rodar em ubuntu-latest.

Deve ter dois steps:

*Primeiro step: Chamado Failed step, deve executar um script bash multi-linha que imprime "I will fail" na tela e sai com qualquer código diferente de zero (ex: exit 1).

*Segundo step: Chamado Say goodbye, deve simplesmente imprimir "Goodbye!" na tela.

**Observe o Comportamento:** Dedique um tempo para observar e inspecionar o que acontece quando um step falha durante a execução do workflow.

**Ajuste Final (Mude o Comportamento):** Como último passo, altere o primeiro step do segundo job para sair com um código zero (ex: exit 0). Você também pode ajustar o nome do step e a mensagem impressa para refletir o novo estado.

Observe como essa alteração impacta a execução do workflow.

**Finalização dos Triggers:** Altere os gatilhos do workflow para conter apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.

---

### Exercício Prático 02 - Usando Diferentes Eventos para Acionar Workflows
* Descrição do Exercício: Neste exercício prático, nosso objetivo é explorar as diferentes maneiras pelas quais podemos acionar workflows no GitHub Actions.

## Instruções para o Exercício:
* Crie um arquivo chamado `02-workflow-events.yaml` dentro da pasta `.github/`workflows na raiz do seu repositório.

* Nomeie o workflow como 02 - Workflow Events.

*Adicione o seguinte "trigger" (gatilho) ao seu workflow:

`push`

* Adicione um único "job" (tarefa) ao workflow:

O job, nomeado echo, deve rodar em `ubuntu-latest`.

Deve conter um único "step" (passo), nomeado Show the trigger, que imprime o tipo e o nome do evento que acionou o workflow.

* Commit e Push Inicial:

Faça o commit das alterações e envie o código (git push). Dedique um tempo para inspecionar a saída da execução do workflow.

* Adicione Mais Triggers:

Agora, adicione mais os seguintes gatilhos ao workflow:

`pull_request`

`schedule` (com uma expressão cron - cron expression)

`workflow_dispatch`

* Commit e Push das Novas Triggers:

Faça o commit das alterações e envie o código (git push). Dedique um tempo para inspecionar as diferentes formas como o workflow é acionado.

* Explore Gatilhos Adicionais:

Você pode criar um pull request no GitHub para ver como isso muda a saída da execução do workflow.

Experimente também acioná-lo pela interface do usuário (UI). Para fazer isso:

Clique na aba "Actions" (Ações) na página inicial do repositório.

Selecione o workflow nomeado 02 - Workflow Events no lado esquerdo da tela.

Clique no botão `"Run workflow"` (Executar workflow) no lado direito da tela, ao lado da mensagem `"This workflow has a workflow_dispatch event trigger."` (Este workflow tem um gatilho de evento workflow_dispatch.)

* Finalização dos Triggers:

Após explorar as diferentes formas de acionar um workflow, reduza a lista de gatilhos para deixar apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.

---

### Exercício Prático 03 - Trabalhando com Runners Windows e Ubuntu
Descrição do Exercício
Neste exercício prático, o objetivo é explorar diferentes possibilidades para configurar runners (executores) para os workflows (fluxos de trabalho).

## Instruções do Exercício
* Crie um arquivo chamado `03-workflow-runners.yaml` dentro da pasta `.github/`workflows na raiz do seu repositório.

* Nomeie o workflow como `03 - Workflow Runners`.

* Adicione os seguintes gatilhos (trigger) ao seu workflow inicialmente:

push

* Adicione dois jobs (tarefas) ao workflow:

O primeiro job, ubuntu-echo, deve ser executado em um runner ubuntu-latest e ter um único passo (step), chamado `Show OS`. Este passo executará um script bash de várias linhas que imprimirá `"This job is running on an Ubuntu runner."` (Este job está sendo executado em um runner Ubuntu.).

O segundo job, windows-echo, deve ser executado em um runner `windows-latest` e ter um único passo (step), chamado Show OS. Este passo executará um script bash de várias linhas que imprimirá `"This job is running on a Windows runner."` (Este job está sendo executado em um runner Windows.).

O terceiro job, mac-echo, deve ser executado no `macos-latest`. Terá um único passo (step) chamado `Show OS`. Este passo deve executar um script bash multi-linha que irá imprimir `"This job is running on a MacOS runner."`.

Altere os gatilhos do workflow de `push` para conter apenas `workflow_dispatch` para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.

---
### Exercício Prático 04 - Trabalhando com Ações Personalizadas de Terceiros
## Descrição do Exercício:

Neste exercício prático, nosso objetivo é explorar como podemos usar ações personalizadas de terceiros para realizar tarefas sem ter que defini-las do zero.

Para isso, utilizaremos uma aplicação React que será gerada com a ajuda da ferramenta create-react-app. Consulte a seção de dicas para o comando específico para gerar sua aplicação React. Aqui estão as instruções para o exercício:

Gerar uma Aplicação React:
Crie uma nova pasta chamada 04-using-actions na raiz do repositório.

Usando um terminal, navegue até este diretório (cd) e gere uma aplicação React dentro de um diretório react-app. Você pode criar o diretório manualmente ou deixar que a ferramenta create-react-app faça isso por você.

Assim que a configuração do React estiver concluída, você deverá ver uma mensagem de sucesso.

Dedique alguns momentos para inspecionar os arquivos e se familiarizar com a estrutura de pastas da aplicação.

Criar a Primeira Versão do Workflow:
Crie um arquivo chamado 04-using-actions.yaml dentro da pasta .github/workflows na raiz do seu repositório.

Nomeie o workflow como 04 - Using Actions.

Adicione os seguintes gatilhos (triggers) ao seu workflow:

push

Adicione um único job (tarefa) chamado build ao workflow. O job deve conter dois passos (steps):

O primeiro, nomeado Checkout Code, deve fazer o checkout do código do repositório para o diretório de trabalho atual.

O segundo, nomeado Printing Folders, deve simplesmente imprimir a estrutura de pastas após o comando de checkout. (Para rodar comandos shell (como ls, npm install, etc.), você deve usar a palavra-chave run:.)

Faça o commit das alterações e envie o código (push).

Dedique alguns momentos para inspecionar a saída da execução do workflow.

Estender o Workflow para Configurar o Node e Instalar as Dependências da Aplicação React:
Remova o passo Printing Folders.

Adicione um novo passo após o passo Checkout Code. Este novo passo deve ser nomeado Setup Node e configurar o Node usando a versão 20.x.

Adicione um novo passo após o passo Setup Node. Este novo passo deve ser nomeado Install Dependencies e instalar as dependências da nossa aplicação React executando o comando npm ci dentro da pasta da aplicação React. Você pode tanto navegar (cd) para o diretório antes de executar o comando npm ci, ou pode passar o diretório de trabalho adicionando a opção working-directory: 04-using-actions/react-app ao passo (como uma chave irmã de name e run).

Faça o commit das alterações e envie o código (push).

Dedique alguns momentos para inspecionar a saída da execução do workflow.

Estender o Workflow para Executar os Testes Automatizados da Aplicação React:
Adicione um novo passo após o passo Install Dependencies. Este novo passo deve ser nomeado Run Unit Tests e deve executar os testes automatizados rodando o comando npm run test dentro da pasta da aplicação React. Você pode tanto navegar (cd) para o diretório antes de executar o comando npm run test, ou pode passar o diretório de trabalho adicionando a opção working-directory: 04-using-actions/react-app ao passo (como uma chave irmã de name e run).

Faça o commit das alterações e envie o código (push).

Dedique alguns momentos para inspecionar a saída da execução do workflow.

Finalizando:
Altere os gatilhos do workflow para conter apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.

---

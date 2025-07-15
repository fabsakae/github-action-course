# github-action-course
Repositório contendo exemplos para o GitHub action course
Exercício Prático 01 - Criando Nosso Primeiro Workflow
Descrição do Exercício
Neste exercício prático, nosso objetivo é criar nosso primeiro workflow.

Instruções para o Exercício
Crie um arquivo chamado 01-building-blocks.yaml dentro da pasta .github/workflows na raiz do seu repositório.

Nomeie o workflow como 01 - Building Blocks.

Adicione os seguintes "triggers" (gatilhos) ao seu workflow:

push

workflow_dispatch

Adicione dois "jobs" (tarefas) ao workflow:

Primeiro job: echo-hello

Deve rodar em ubuntu-latest.

Deve ter um único "step" (passo), chamado Say hello, que simplesmente imprime a mensagem "Hello, World!" na tela.

Segundo job: echo-goodbye

Também deve rodar em ubuntu-latest.

Deve ter dois steps:

Primeiro step: Chamado Failed step, deve executar um script bash multi-linha que imprime "I will fail" na tela e sai com qualquer código diferente de zero (ex: exit 1).

Segundo step: Chamado Say goodbye, deve simplesmente imprimir "Goodbye!" na tela.

Observe o Comportamento:

Dedique um tempo para observar e inspecionar o que acontece quando um step falha durante a execução do workflow.

Ajuste Final (Mude o Comportamento):

Como último passo, altere o primeiro step do segundo job para sair com um código zero (ex: exit 0). Você também pode ajustar o nome do step e a mensagem impressa para refletir o novo estado.

Observe como essa alteração impacta a execução do workflow.

Finalização dos Triggers:

Altere os gatilhos do workflow para conter apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.

Exercício Prático 02 - Usando Diferentes Eventos para Acionar Workflows
Descrição do Exercício
Neste exercício prático, nosso objetivo é explorar as diferentes maneiras pelas quais podemos acionar workflows no GitHub Actions.

Instruções para o Exercício
Crie um arquivo chamado 02-workflow-events.yaml dentro da pasta .github/workflows na raiz do seu repositório.

Nomeie o workflow como 02 - Workflow Events.

Adicione o seguinte "trigger" (gatilho) ao seu workflow:

push

Adicione um único "job" (tarefa) ao workflow:

O job, nomeado echo, deve rodar em ubuntu-latest.

Deve conter um único "step" (passo), nomeado Show the trigger, que imprime o tipo e o nome do evento que acionou o workflow.

Commit e Push Inicial:

Faça o commit das alterações e envie o código (git push). Dedique um tempo para inspecionar a saída da execução do workflow.

Adicione Mais Triggers:

Agora, adicione mais os seguintes gatilhos ao workflow:

pull_request

schedule (com uma expressão cron - cron expression)

workflow_dispatch

Commit e Push das Novas Triggers:

Faça o commit das alterações e envie o código (git push). Dedique um tempo para inspecionar as diferentes formas como o workflow é acionado.

Explore Gatilhos Adicionais:

Você pode criar um pull request no GitHub para ver como isso muda a saída da execução do workflow.

Experimente também acioná-lo pela interface do usuário (UI). Para fazer isso:

Clique na aba "Actions" (Ações) na página inicial do repositório.

Selecione o workflow nomeado 02 - Workflow Events no lado esquerdo da tela.

Clique no botão "Run workflow" (Executar workflow) no lado direito da tela, ao lado da mensagem "This workflow has a workflow_dispatch event trigger." (Este workflow tem um gatilho de evento workflow_dispatch.)

Finalização dos Triggers:

Após explorar as diferentes formas de acionar um workflow, reduza a lista de gatilhos para deixar apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções do workflow.
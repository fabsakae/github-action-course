# github-action-course
Repositório contendo exemplos para o GitHub action course

Exercício Prático 01 - Criando Nosso Primeiro Workflow
Descrição do Exercício
Neste exercício prático, nosso objetivo é criar nosso primeiro workflow.
Aqui estão as instruções para o exercício:

Crie um arquivo chamado 01-building-blocks.yaml na pasta .github/workflows na raiz do seu repositório.

Nomeie o workflow como 01 - Building Blocks.

Adicione os seguintes gatilhos ao seu workflow:

push
workflow_dispatch


Adicione dois jobs ao workflow:

O primeiro job, echo-hello, deve ser executado em ubuntu-latest e ter um único passo, chamado Say hello, que simplesmente imprime a mensagem "Hello, World!" na tela.
O segundo job, echo-goodbye, também deve ser executado em ubuntu-latest e ter dois passos:
O primeiro passo, chamado Failed step, deve executar um script bash de várias linhas que imprime "I will fail" na tela e termina com qualquer código diferente de zero.
O segundo passo, chamado Say goodbye, deve simplesmente imprimir "Goodbye!" na tela.




Dedique algum tempo para experimentar e inspecionar o que acontece quando um passo falha durante a execução do workflow.

Como último passo, altere o primeiro passo do segundo job para terminar com um código zero. Você também pode ajustar o nome do passo e a mensagem impressa para corresponder ao novo estado.

Observe como isso impacta a execução do workflow.

Altere os gatilhos do workflow para conter apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções de workflow.


Exercício Prático 02 - Usando Diferentes Eventos para Acionar Workflows
Descrição do Exercício
Neste exercício prático, nosso objetivo é explorar as diferentes maneiras de acionar workflows no GitHub Actions.
Aqui estão as instruções para o exercício:

Crie um arquivo chamado 02-workflow-events.yaml na pasta .github/workflows na raiz do seu repositório.

Nomeie o workflow como 02 - Workflow Events.

Adicione o seguinte gatilho ao seu workflow:

push


Adicione um único job ao workflow:

O job, chamado echo, deve ser executado em ubuntu-latest e conter um único passo, chamado Show the trigger, que imprime o tipo do nome do evento que acionou o workflow.


Faça o commit das alterações e envie o código. Dedique algum tempo para inspecionar a saída da execução do workflow.

Agora, adicione mais gatilhos ao workflow:

pull_request
schedule (expressão cron)
workflow_dispatch


Faça o commit das alterações e envie o código. Dedique algum tempo para inspecionar as diferentes maneiras como o workflow é acionado.

Você pode criar um pull request no GitHub para ver como isso altera a saída da execução do workflow.

Experimente também acionar o workflow pela interface do usuário. Para fazer isso:

Clique na aba "Actions" na página inicial do repositório.
Selecione o workflow chamado 02 - Workflow Events no lado esquerdo da tela.
Clique no botão "Run workflow" no lado direito da tela, ao lado da mensagem "This workflow has a workflow_dispatch event trigger."


Após explorar as diferentes maneiras de acionar um workflow, reduza a lista de gatilhos para deixar apenas workflow_dispatch para evitar que este workflow seja executado a cada push e polua a lista de execuções de workflow.



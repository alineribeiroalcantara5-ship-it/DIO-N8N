# DIO- Santander 2026 - Automação com N8N

Repositório criado para entrega do projeto do curso Santander N8N na plataforma DIO . 

Contexto e Objetivos: 

O Tópico de um dos capitulos do curso Santander 2026 - Automação com N8N pela plataforma DIO , foi o notebook LM. 
Foi proposto um projeto de criação de um Notebook LM e o tema escolhido para a criação do Notebook foi o próprio assunto alvo do curso , ou seja, o N8N.
Utilizei como fonte o material disponibilizado no site do N8N , o N8N Academy. Também foi sugerido pelo NotebookLm outras fontes confiaveis e elas foram adicionadas ao caderno.
A escolha destas fontes garante assertividade e que apenas o conteúdo oficial seja disponibilizado ao pesquisar sobre o assunto.

# Curadoria de Fontes: 

Seguem as três fontes principias utilizadas no NotebookLm para a elaboração deste caderno:

https://dev.to/ciphernutz/what-are-n8n-nodes-triggers-and-workflows-a-beginners-guide-46hd#main-content
https://apps.learn.n8n.io/learner-dashboard/
https://docs.n8n.io/


# Engenharia de Prompts / testes de prompt :

No chat foi solicitado os conceitos fundamentais para criar fluxos de automação no n8n.
A resposta foi a seguinte :

"Com base nos tópicos dos cursos oficiais disponibilizados em suas fontes, os módulos e temas centrais para a criação e estruturação de fluxos no n8n incluem:
Primeiros Fluxos e Integrações (N8N101 / N8N102): Construção de automações essenciais e conexão com serviços externos por meio de APIs
.
Fluxos de Dados Complexos (Complex data flows): Organização e manipulação do fluxo de informações ao longo das etapas
.
Nós Técnicos Avancados (Advanced technical nodes): Uso de nós específicos para operações lógicas e técnicas complexas
.
Fixação e Edição de Dados de Saída (Pinning and editing output data): Edição e congelamento de dados para testes e desenvolvimento de fluxos
.
Subfluxos (Subworkflows): Modularização e reutilização de fluxos em partes menores
.
Tratamento de Erros (Error workflows): Criação de rotinas dedicadas para capturar e gerenciar falhas de execução
.
Manipulação de Arquivos (Handling files): Processamento de arquivos e anexos no fluxo de trabalho
.
As suas fontes listam a grade curricular e os módulos do n8n Academy e dos cursos avançados da comunidade
, mas não contêm as definições detalhadas ou tutoriais passo a passo de cada conceito (como funcionamento de triggers, sintaxe de expressões JSON ou credenciais)."

A IA solicitou uma pesquisa na web para inserir as informações do passo a passo de cada conceito, eu autorizei a pesquisa na web e esta seguiu DENTRO DA DOCUMENTAÇÃO OFICAL DO N8N , conforme o critério utilizado.

"Realizei a pesquisa na documentação oficial e em guias técnicos da comunidade sobre os conceitos fundamentais do n8n.
De acordo com a documentação oficial do n8n e guias do DEV Community, o n8n é uma ferramenta visual de automação de fluxos (low-code/no-code) estruturada em três pilares principais: Workflows (Fluxos), Triggers (Gatilhos) e Nodes (Nós), pelos quais as informações trafegam estruturadas em formato JSON.
Principais conceitos identificados:
Workflows (Fluxos): É o mapa visual completo da automação construído na tela (canvas), definindo a sequência lógica e a conexão entre diferentes aplicações ou rotinas.
Gatilhos (Triggers): São nós especiais que iniciam a execução automática do fluxo. Podem ser acionados por tempo/agendamento (Schedule/Cron), eventos externos (Webhooks) ou ações em serviços conectados (como a chegada de um e-mail ou nova linha em uma planilha).
Nós (Nodes) e Ações: São os blocos de construção de cada etapa do processo. Dividem-se em nós de aplicativo (integração com APIs como Gmail, Slack, Notion), nós de núcleo/lógica (manipulação de fluxo como IF, Switch, Loop) e nós de código (para executar JavaScript ou Python customizado).
Fluxo de Dados e Formato JSON: Os dados passados de um nó para o outro são sempre estruturados em JSON. O resultado do nó anterior torna-se a entrada disponível para os nós seguintes.
Expressões (Expressions): Sintaxe dinâmica (por exemplo, {{ $json.campo }}) usada para mapear e transformar dados de nós anteriores em tempo de execução.
Credenciais (Credentials): Sistema centralizado e seguro onde chaves de API, tokens OAuth e senhas são armazenados de forma criptografada para autenticação com serviços externos."


# Miniguia de Estudo :

Foi solicitada a criação de um guia de estudos com o seguinte prompt : 

"Se comporte como um especilista em n8n e crie um curso que deverá ser estrurado em capítulos de acordo com o tema para os niveis básico e avançado .
Estrure as fontes inseridas de forma didática , sempre no idioma Português brasileiro.  
Crie um glossário com os termos chave , tecnicos e dicas de acordo com o assunto tratado no capitulo .
Ao final do curso , crie um teste final de conhecimentos com dez perguntas com respotas nas opções A, B,C e D . O total minimo de acertos sao 7 perguntas, informe isso ao aluno. 
Ao final do teste exiba as respostas corretas e uma justificativa . "

O conteúdo do guia esta abaixo:

" Guia de Estudo: Domine o n8n – Do Básico ao Avançado

Este guia foi desenvolvido para fornecer uma compreensão profunda da arquitetura e funcionalidade do n8n, uma ferramenta de automação de fluxo de trabalho no-code/low-code. O conteúdo está estruturado para levar o estudante desde os conceitos iniciais até práticas avançadas de engenharia de fluxos.

Nível Básico: Fundamentos e Primeiros Passos

Capítulo 1: Introdução à Automação e ao n8n

O n8n é definido como um centro de comando de automação que conecta aplicativos, APIs e serviços sem a necessidade de escrever centenas de linhas de código. Diferente de outras ferramentas, ele se destaca por ser de código aberto (open-source), extensível e amigável ao desenvolvedor.

Principais Características:

* Hospedagem: Pode ser utilizado no n8n Cloud ou auto-hospedado via Docker (ex: docker run -p 5678:5678 n8nio/n8n).
* Segurança: No auto-hospitalmento, os dados permanecem nos servidores do usuário, e as credenciais são armazenadas de forma criptografada no banco de dados.
* Interface: Utiliza um sistema visual de "arrastar e soltar" em uma tela chamada canvas.

Capítulo 2: Blocos de Construção – Nós e Gatilhos

Um fluxo de trabalho (workflow) é uma série de nós conectados que realizam tarefas em sequência.

Tipos de Nós:

1. Gatilhos (Triggers): O ponto de partida. Iniciam o fluxo em resposta a eventos externos, agendamentos (Cron) ou ações manuais. São identificados por um ícone de raio.
2. Ações (Actions): Representam tarefas específicas, como enviar um e-mail ou interagir com uma API (ex: Gmail, Slack, Google Sheets).
3. Nós Principais (Core Nodes): Fornecem funcionalidades lógicas, agendamento ou chamadas de API genéricas (HTTP Request).

Capítulo 3: Fluxo de Dados e Expressões

No n8n, todos os dados trafegam entre os nós no formato JSON. A saída de um nó torna-se automaticamente a entrada do nó seguinte.

* Expressões: Permitem referenciar dados dinamicamente usando a sintaxe {{ $json.nome_do_campo }}.
* Manipulação de Data: É possível usar expressões para cálculos temporais, como {{ $today.minus(7, 'days') }} para buscar dados da última semana.

Glossário do Nível Básico

Termo	Definição	Dica Técnica
Workflow	Sequência de nós conectados que automatizam um processo.	Salve e ative o workflow para que ele rode 24/7.
Node (Nó)	Blocos individuais que realizam uma ação ou função.	Use o campo de busca para encontrar nós de apps específicos.
Trigger	Nó que inicia o workflow (ex: Schedule, Webhook).	O Schedule Trigger é ideal para relatórios diários.
JSON	Formato de dados padrão usado para comunicação entre nós.	Visualize a aba "OUTPUT" para entender a estrutura dos dados.
Credential	Informações privadas (API Keys, senhas) para autenticar apps.	Nunca compartilhe suas credenciais fora do ambiente seguro do n8n.

Nível Avançado: Lógica Complexa e Otimização

Capítulo 4: Lógica de Controle e Ramos

Fluxos avançados não são apenas lineares; eles exigem ramificações baseadas em condições.

* If Node: Verifica uma condição (ex: se o valor é maior que X) e divide o fluxo em caminhos "verdadeiro" e "falso".
* Switch Node: Permite múltiplas ramificações baseadas em diferentes critérios.
* Merge Node: Combina dados de múltiplos ramos para processamento unificado.

Capítulo 5: Sincronização e Fluxos Complexos

A sincronização bidirecional (ex: entre Notion e TickTick) exige design cuidadoso para evitar loops infinitos.

* Identificadores Únicos: Use campos como taskId para verificar se o dado já existe.
* Prevenção de Loops: Implemente verificações condicionais para garantir que uma atualização não dispare um novo ciclo de sincronização desnecessário.

Capítulo 6: Integração de IA e Subworkflows

O n8n permite a integração de Inteligência Artificial através do nó AI Agent.

* AI Agent: Conecta-se a modelos como OpenAI ou Claude. Pode ser configurado com "Memória" para lembrar o histórico da conversa e um "System Prompt" para definir o comportamento do agente.
* Subworkflows: Para manter a organização, fluxos complexos podem ser divididos. Um workflow principal pode chamar outros menores usando o nó Execute Workflow.

Capítulo 7: Debugging e Tratamento de Erros

* Histórico de Execução: Localizado na aba "Executions", permite ver onde um nó falhou (marcado em vermelho).
* Retry on Error: Configuração que permite ao nó tentar executar novamente (ex: 3 vezes) em caso de falha temporária da API.
* Pinning Data: Técnica para fixar dados de saída e testar nós subsequentes sem precisar re-executar todo o fluxo.

Glossário do Nível Avançado

Termo	Definição	Dica Técnica
Webhook	Gatilho que inicia o fluxo ao receber uma requisição HTTP externa.	Útil para receber notificações de formulários em tempo real.
Subworkflow	Um workflow independente chamado por outro workflow.	Use para reutilizar lógicas comuns em vários projetos.
AI Agent Node	Nó que integra LLMs (modelos de linguagem) ao fluxo.	Defina instruções claras no System Prompt para melhores resultados.
Binary Data	Tratamento de arquivos (imagens, PDFs) dentro do fluxo.	Verifique a capacidade de memória do servidor ao lidar com arquivos grandes.
Cluster Nodes	Grupo de nós (Root e Sub-nodes) que trabalham juntos.	Expanda a funcionalidade de um nó principal usando sub-nós específicos.

Teste Final de Conhecimentos

Instruções: Responda às 10 perguntas abaixo. Para ser aprovado, você deve acertar no mínimo 7 perguntas.

1. Qual é a função principal de um "Trigger Node" no n8n? A) Transformar dados JSON. B) Iniciar a execução de um workflow automaticamente. C) Armazenar credenciais de APIs externas. D) Conectar dois workflows diferentes.

2. Como o n8n protege as informações sensíveis de API e senhas? A) Através de criptografia no banco de dados com uma chave pessoal aleatória. B) Salvando-as em arquivos de texto simples na pasta do usuário. C) Enviando-as para o n8n Cloud para validação externa. D) Não há proteção, as chaves ficam visíveis no canvas.

3. Qual é o formato padrão de dados que trafega entre os nós? A) XML. B) CSV. C) JSON. D) HTML.

4. O que a expressão {{ $json.price }} faz em um nó de ação? A) Cria uma nova variável chamada price. B) Referencia dinamicamente o valor do campo "price" vindo do nó anterior. C) Exclui o campo price dos dados de saída. D) Multiplica o valor do campo price por dois.

5. Qual nó deve ser usado para criar dois caminhos diferentes (Verdadeiro/Falso) baseados em uma condição? A) Merge Node. B) Wait Node. C) If Node. D) HTTP Request Node.

6. No auto-hospedamento via Docker, qual a importância da flag -v? A) Aumentar a velocidade de processamento dos nós. B) Garantir a persistência dos dados e workflows após o container reiniciar. C) Habilitar a conexão com APIs de IA. D) Atualizar o n8n para a versão mais recente automaticamente.

7. O que caracteriza um "Subworkflow" no n8n? A) É um nó que apenas envia e-mails. B) É um workflow independente que pode ser chamado por outro através do nó "Execute Workflow". C) É a parte do fluxo que trata apenas de erros. D) É um nó que contém apenas códigos JavaScript.

8. Para que serve a funcionalidade "Retry on Error"? A) Para ignorar o erro e continuar o fluxo sem os dados. B) Para tentar executar o nó novamente em caso de falhas temporárias, como timeouts de API. C) Para deletar o nó que apresentou a falha. D) Para enviar um e-mail automático ao suporte do n8n.

9. Sobre o nó AI Agent, qual recurso permite que ele mantenha o contexto de uma conversa? A) System Prompt. B) Memory. C) JSON Payload. D) Webhook URL.

10. O que são "Cluster Nodes"? A) Nós que só funcionam em servidores de alta performance. B) Grupos de nós que trabalham juntos, consistindo em um nó raiz e sub-nós. C) Nós usados exclusivamente para bancos de dados SQL. D) Uma coleção de workflows desativados.

Gabarito e Justificativas

1. Resposta B. Justificativa: Gatilhos são os pontos de partida que reagem a eventos ou agendamentos.
2. Resposta A. Justificativa: O n8n utiliza uma chave de criptografia gerada automaticamente no primeiro uso para proteger as credenciais no banco de dados.
3. Resposta C. Justificativa: Toda a comunicação interna do n8n é baseada na estrutura de objetos JSON.
4. Resposta B. Justificativa: A sintaxe de chaves duplas e $json é o padrão para mapeamento dinâmico de dados.
5. Resposta C. Justificativa: O nó IF é a ferramenta fundamental de controle lógico para bifurcação de fluxos.
6. Resposta B. Justificativa: O volume (-v) mapeia uma pasta local ao container, evitando a perda de dados ao desligar o Docker.
7. Resposta B. Justificativa: Subworkflows promovem a modularidade e reutilização de lógica entre diferentes projetos.
8. Resposta B. Justificativa: Configurar tentativas de reexecução ajuda a lidar com instabilidades comuns em serviços de nuvem e APIs.
9. Resposta B. Justificativa: A "Memory" permite que o agente de IA acesse o histórico de interações anteriores na mesma sessão.
10. Resposta B. Justificativa: Cluster nodes utilizam uma estrutura de nó raiz estendido por sub-nós para funcionalidades específicas.
"


Para finalizar , também foi solicitado a criação de um Resumo em Áudio que pode ser acessado usando link do projeto:

https://notebook.google.com/notebook/c46fa4e3-88a6-42e9-ad53-35ee799e58f0







# 📋 Conceitos essenciais para um bom Engenheiro

Repositório criado com o objetivo de compartilhar conhecimentos e estudos relacionados à Engenharia de software como um todo. Espero que absorva novos conhecimentos, e faça bom uso dos conceitos abordados abaixo. São assuntos técnicos para aplicações modernas. Bora lá !!

## 12 Fatores

É uma espécie de “manifesto” com os 12 pontos que uma aplicação deveria seguir para ter sucesso nesse formato. Estes fatores não são uma verdade absoluta e tampouco devem ser seguidos cegamente, mas são um ótimo ponto de partida para a criação de projetos web modernos e que podem escalar mais facilmente para atender as demandas das empresas.
Segue abaixo o documento original criado pela Heroku, plataforma de cloud computing que revolucionou o desenvolvimento, ajudou a criar o movimento “devops” e que foi vendida por milhões de dólares para a Salesforce. Se tem algo que eles têm muita experiência é na criação e suporte de aplicativos SaaS (software-as-a-service), principalmente aplicativos web.

Saiba mais 💡

The Twelve-Factor App (traduzido):

https://12factor.net/pt_br/


## Event-Driven

Uma arquitetura orientada a eventos usa eventos para acionar e se comunicar entre serviços desacoplados e é comum em aplicativos modernos criados com microsserviços. Um evento é uma mudança de estado ou uma atualização.
As arquiteturas orientadas a eventos têm três componentes principais: produtores de eventos, roteadores de eventos e consumidores de eventos. Um produtor publica um evento no roteador, que filtra e envia os eventos aos consumidores. Os serviços do produtor e os serviços do consumidor são desacoplados, o que permite que sejam dimensionados, atualizados e implantados de forma independente.

Exemplo do fluxo do Event-Driven:
![image](https://user-images.githubusercontent.com/22088545/166073291-41334b11-d29a-48dc-b5df-3453ddef04c1.png)

Saiba mais 💡

O que é uma arquitetura orientada por eventos:

https://www.redhat.com/pt-br/topics/integration/what-is-event-driven-architecture

Escolhendo uma arquitetura orientada a eventos:

https://www.infoq.com/br/news/2017/09/selecting-event-architecture/

Events Hub: como e por quê uma Perspectiva Orientada a Eventos pode ajudar muito a sua empresa:

https://br.sensedia.com/post/events-hub-how-and-why-an-event-driven-perspective-can-greatly-help-your-company


### DLQ (Dead Letter Queue)

As filas de mensagens mortas são úteis para depurar sua aplicação ou sistema de mensagens, pois permitem que você isole mensagens não consumidas para determinar por que seu processamento não obteve êxito. Por exemplo, se um usuário fizer um pedido na web com um ID de produto específico, mas esse ID do produto for excluído, o código da loja da web falhará e exibirá um erro. Além disso, a mensagem com a solicitação do pedido poderá ser enviada para uma dead-letter queue.

Saiba mais 💡

DLQ + Kafka - Artigo da Uber Engineering:

https://imasters.com.br/desenvolvimento/construindo-reprocessamento-confiavel-e-dead-letter-queues-com-kafka

Lambda + DLQ (Exemplo da AWS, porém é possível em qualquer Cloud):

https://shre.ink/1hK


### Orquestração vs. Coreografia de serviços

A orquestração de serviço representa um único processo de negócios executável centralizado (o orquestrador) que coordena a interação entre diferentes serviços. O orquestrador é responsável por invocar e combinar os serviços.
O relacionamento entre todos os serviços participantes é descrito por um único terminal (ou seja, o serviço composto). A orquestração inclui o gerenciamento de transações entre serviços individuais. A orquestração emprega uma abordagem centralizada para a composição do serviço.

Coreografia de serviço é uma descrição global dos serviços participantes, definida pela troca de mensagens, regras de interação e acordos entre dois ou mais pontos de extremidade. A coreografia emprega uma abordagem descentralizada para a composição do serviço.
A coreografia descreve as interações entre vários serviços, onde a orquestração representa o controle da perspectiva de uma parte. Isso significa que uma coreografia difere de uma orquestração com relação a onde a lógica que controla as interações entre os serviços envolvidos deve residir.

| Orquestração de serviço | Coreografia de serviço |
| --- | --- |
| ![image](https://user-images.githubusercontent.com/22088545/167660064-25da6f9c-3767-4d62-b6b5-a1acb51d1772.png)s | ![image](https://user-images.githubusercontent.com/22088545/167660145-2402c710-37b9-4c1e-b44e-b032ff4ef5bf.png) |

Saiba mais 💡

Orquestração vs. Coreografia de serviços:

https://www.grupomult.com.br/orquestracao-vs-coreografia-de-servicos/

Entendendo Event Driven:

https://br.sensedia.com/post/understanding-event-driven-standards


## Microsserviço

Desenvolver um único aplicativo como um conjunto de pequenos serviços, cada um executando em seu próprio processo e se comunicando com mecanismos leves, geralmente uma API de recursos HTTP. Esses serviços são construídos em torno dos recursos de negócios e implantados de forma independente por máquinas de implantação totalmente automatizadas. Há um mínimo de gerenciamento centralizado desses serviços, que podem ser escritos em diferentes linguagens de programação e usar diferentes tecnologias de armazenamento de dados.

É assim que um monólito se pareceria. Um aplicativo para tudo:

![image](https://user-images.githubusercontent.com/22088545/168696771-61fe4e06-a226-41ec-95a4-5e8fdc2dd10b.png)

É assim que o mesmo aplicativo ficaria quando desenvolvido usando a Arquitetura de Microsserviços:

![image](https://user-images.githubusercontent.com/22088545/168696786-f336ba30-8791-4315-9fa2-f49708686436.png)

As arquiteturas de microsserviços envolvem vários componentes pequenos e bem projetados interagindo com as mensagens:

![image](https://user-images.githubusercontent.com/22088545/168696796-3ffe1431-031b-483e-bcdd-2a2be026e61a.png)

<br>

|  | Monolito | Microsserviço |
| --- | --- | --- |
| Vantagens | Mais simples de desenvolver | Altamente testável e manutenível
| | Simples de testar | Independência e agilidade
| | Simples de fazer o deploy para o servidor | Objetividade
| | Simples de escalar | Flexibilidade
| Desvantagens | Manutenção | Quando a arquitetura do sistema é feita, a divisão dos serviços tem que ser feita com muita atenção e cuidado
| | Alterações / Linha de código | Há replicação de código de resposta ou de infraestrutura
| | Linguagens de programação | Complexidade no gerenciamento da aplicação

<br>

Saiba mais 💡

Introdução a Microsserviços:

https://medium.com/introducao-a-arquitetura-de-microservicos/introdu%C3%A7%C3%A3o-a-microsservi%C3%A7os-25378269e6f9

Entenda as diferenças entre Arquitetura Monolítica e Microsserviços por meio de análises comparativas, vantagens e desvantagens:

https://www.zappts.com/blog/arquitetura-monolitica-e-microsservicos/


## Domain Driven Design

Domain Driven Design significa Projeto Orientado a Domínio. Podemos dizer que são padrões, um padrão é uma regra de três partes que expressa a relação entre um contexto (1), um problema (2) e uma solução (3).

Saiba mais 💡

DDD – Introdução a Domain Driven Design:

http://www.agileandart.com/2010/07/16/ddd-introducao-a-domain-driven-design/

Implementando o Domain-Driven Design para Arquitetura de Microsserviços:

https://medium.com/design-and-tech-co/implementing-domain-driven-design-for-microservice-architecture-26eb0333d72e


### Anti-Corruption Layer (ACL)

Em algum momento em nossa jornada nos deparamos com sistemas legados, e os mesmos possuem integração com os seus substitutos. Isso vai contra o design limpo, e com certeza gerará problemas em curto ou longo prazo. Os sistemas legados sofrem com protocolos, modelos de dados, schemas e/ou APIs obsoletos desatualizados. Para interagir com sistemas legados, novos aplicativos de pipeline podem precisar oferecer suporte a recursos legados que não se alinham às técnicas arquitetônicas modernas. É aí que entra o ACL, ele fará essa integração entre esses dois sistemas. Ele traduz solicitações entre o sistema legado e o novo, de modo que não há necessidade de mexer nas partes internas do novo sistema de maneira que possam prejudicar seu design mais recente ou causar problemas inesperados. Segue abaixo uma imagem para exemplificar o que foi dito acima:

![image](https://user-images.githubusercontent.com/22088545/171747692-9b72dd91-4a01-421f-84d8-24e886afa7fa.png)

Saiba mais 💡

Doc da Microsoft:

https://docs.microsoft.com/pt-br/azure/architecture/patterns/anti-corruption-layer

Anti-Corruption Layer: How to Keep Legacy Support from Breaking New Systems:

https://www.cloudbees.com/blog/anti-corruption-layer-how-keep-legacy-support-breaking-new-systems


## S.O.L.I.D

Basicamente o intuito do S.O.L.I.D são: construção de códigos mais limpos, separar responsabilidades, diminuir acoplamento, facilitar a refatoração e estimular o reaproveitamento do código. Segue abaixo o significado de cada letra, porém, como o conteúdo é bem extenso, aconselho fortemente à ler o artigo e assistir o vídeo que estão no Saiba mais.

- S — Single Responsiblity Principle (Princípio da responsabilidade única)
- O — Open-Closed Principle (Princípio Aberto-Fechado)
- L — Liskov Substitution Principle (Princípio da substituição de Liskov)
- I — Interface Segregation Principle (Princípio da Segregação da Interface)
- D — Dependency Inversion Principle (Princípio da inversão da dependência)

Saiba mais 💡

O que é SOLID:

https://medium.com/desenvolvendo-com-paixao/o-que-%C3%A9-solid-o-guia-completo-para-voc%C3%AA-entender-os-5-princ%C3%ADpios-da-poo-2b937b3fc530

SOLID fica FÁCIL com Essas Ilustrações:

https://www.youtube.com/watch?v=6SfrO3D4dHM


## Clean Arquitecture

A arquitetura limpa tem como principais finalidades ser independente de: frameworks, interface do usuário, banco de dados, agentes externos; e por final, ser facilmente testável. Resumindo, é um tipo de arquitetura de software amplamente independente.

![image](https://user-images.githubusercontent.com/22088545/172696015-d1000d74-4736-4146-bba0-212a64a6feec.png)

Na imagem acima, temos o desenho de como a Clean Architecture funciona. Note que as setas horizontais da imagem que representam as dependências entre as camadas vêm de “fora para dentro”, ou seja, a camada Framework “enxerga” somente a Interface Adapters, que por sua vez “enxerga” somente a User Cases, que finalmente “enxerga” apenas a Entites. Esta é a principal regra da Clean Architecture, e talvez sua única: o Princípio da Dependência.

As camadas internas não devem ter qualquer dependência das externas, nem indiretas, como nomes de variáveis, funções ou termos.

Provavelmente você terá mais abstrações nas camadas internas e mais implementações nas externas, utilizando injeção de dependência para fazer tudo funcionar.

Saiba mais 💡

Clean Architecture e suas premissas:

https://renicius-pagotto.medium.com/clean-architecture-e-suas-premissas-6beb933c72b1

O uso da Clean Architecture: Uma abordagem modular:

https://medium.com/@lopesvinicius1707/o-uso-da-clean-architeture-uma-abordagem-modular-b0905b59ab74


## Hexagonal Architecture (Port and Adapters)

Ports and Adapters ou também conhecido como Hexagonal Architecture, é uma arquitetura popular inventada por Alistair Cockburn em 2005.
É uma forma de organizar o código em camadas, cada qual com a sua responsabilidade, tendo como objetivo isolar totalmente a lógica da aplicação do mundo externo. Este isolamento é feito por meio de Portas e Adaptadores (daí o nome Ports and Adapters), onde as Portas são as interfaces que as camadas de baixo nível expõe, e Adaptadores as implementações para as interfaces em questão.

![image](https://user-images.githubusercontent.com/22088545/173692263-3b352bc0-c413-4d49-9a3b-744649d2578c.png)

Na figura acima é possível visualizar a lógica de negócio (Domínio) isolado de fatores externos, como bibliotecas de notificação por SMS e E-mail, banco de dados e ferramenta de busca, e utilizando diferentes formas de entrada de dados, como API (HTTP) e comandos de console (CLI). A forma como o domínio é acessado se dá por meio de Portas e Adaptadores.

| Adaptadores primários | Adaptadores secundários |
| --- | --- |
| ![image](https://user-images.githubusercontent.com/22088545/173692724-92109376-00d6-4618-ba68-6a6993727d70.png) | ![image](https://user-images.githubusercontent.com/22088545/173692734-763af0f3-975d-47bf-a33e-3177dd7ea3ba.png) |
| Os adaptadores primários ou de condução representam a interface do usuário. Isso pode ser nossos controladores de API, controladores da Web e visualizações. Eles são chamados de adaptadores de acionamento porque dirigem o aplicativo e iniciam ações no aplicativo principal. Esses adaptadores podem usar as portas de entrada (interfaces) fornecidas pelo aplicativo principal. Os controladores, então, dependem dessas interfaces da lógica de negócios principal. | Os adaptadores secundários ou orientados representam a conexão com seus bancos de dados de back-end, bibliotecas externas, APIs de correio, etc. Esses adaptadores reagem às ações iniciadas pelos adaptadores primários. Os adaptadores secundários são implementações da porta de saída. Que por sua vez dependem de interfaces dessas bibliotecas externas e ferramentas para transformá-las, de modo que o aplicativo principal possa utilizá-las sem estar acoplado a elas.

| Conclusão |
| --- |
| ![image](https://user-images.githubusercontent.com/22088545/173692743-9dc90428-8e3d-4509-873f-82e888ed0e6b.png) |
| O objetivo de Portas e Adaptadores é isolar a lógica de negócios da mecânica de entrega e ferramentas usadas pelo sistema. Para isso usamos Interfaces. Todas as dependências estão na direção do aplicativo principal. O núcleo em si não depende de nada. |

Criamos adaptadores no lado da interface do usuário de nosso aplicativo para usar nossas interfaces de aplicativos. E no lado da infraestrutura criamos adaptadores que implementam as interfaces de nossa aplicação.
Temos então um sistema completamente isolado de mudanças externas e de qualquer framework que você use. Claro que na realidade não será tão fácil mudar de framework, mas pelo menos não ficamos totalmente dependentes disso.

**Quando utilizar**

Qualquer aplicação pode ser arquitetada como hexagonal, porém devemos nos atentar se nossa aplicação está realmente precisando, se é factível tal migração ou implementação, nem sempre a melhor solução seja a adequada para determinados cenários. Arquitetura hexagonal traz bastante benefícios, em aplicações grandes com a divisão em camadas, em aplicações muito complexas com o encapsulamento da lógica, em aplicações com muita integração com a utilização de interfaces e serviços, tudo isso garante um aumento considerável na facilidade de manutenção e escalabilidade.

**Quando não utilizar**

A arquitetura hexagonal possui inúmeras vantagens, porém não são em todos os casos que realmente valerá a pena sua utilização.
Em sistemas muito pequenos ou que dificilmente irá gerar trabalho de manutenção/novas features talvez não seja tão interessante o custo-benefício de sua implementação, já que demanda um alto grau de esforço de desenvolvimento.
Como em todos os casos no nosso cotidiano, deve ser feita uma análise de viabilidade, já que podem haver formas mais eficazes de resolver o mesmo problema.

Saiba mais 💡

Arquitetura Hexagonal:
https://medium.com/dev-cave/arquitetura-hexagonal-4668a8ffac57

## Refatoring and Design Pattern

A refatoração é uma forma disciplinada de reestruturar o código quando pequenas mudanças são feitas nele para melhorar o design. Um aspecto importante de uma refatoração é que ela melhora o design sem mudar o comportamento do design; uma refatoração não adiciona nem remove funcionalidade.
Design Patterns ou padrões de projetos são soluções generalistas para problemas recorrentes durante o desenvolvimento de um software. Não se trata de um framework ou um código pronto, mas de uma definição de alto nível de como um problema comum pode ser solucionado.

Saiba mais 💡

Refatoração:
https://refactoring.guru/pt-br/refactoring

Design Pattern:
https://refactoring.guru/design-patterns


## Cloud Computing

Computação na nuvem, tem como principal objetivo a redução de custo de sua infraestrutura, mas oferece também muitos outros benefícios, como a flexibilização da estrutura, otimização de processos etc. Trago abaixo 7 itens que exemplificam as vantagens de se ter sua infraestrutura em Cloud Computing.

1. Elasticidade e escalabilidade

Na nuvem, a elasticidade significa a capacidade de um sistema em adicionar ou remover recursos de maneira autônoma. Podemos dizer que a elasticidade é a capacidade de escalar recursos tanto horizontalmente quanto verticalmente. Outra característica importante é que toda e qualquer alteração é feita em tempo real, de modo a não interferir no fluxo de trabalho.

2. Otimização de processos de TI

Imagine em um data center físico, qual o impacto de uma alteração como aumentar o número de processadores em uma máquina? Provavelmente seria preciso alocar recursos para trabalhar no final de semana, parar a máquina etc. Isso gera inúmeros transtornos ao negócio, além do gasto com horas extras dos colaboradores. Ao utilizar cloud computing, essa atividade pode ser feita em pouco tempo e sem nenhum impacto ao usuário. Dessa maneira, os colaboradores de TI podem ser alocados em outras atividades.

3. Provisionamento automático de recursos

É possível alocar recursos de processamento sob demanda. Isso quer dizer que, conforme a necessidade da aplicação durante o uso, o sistema redimensiona recursos automaticamente. Outra forma em que o provisionamento automático de recursos pode ser usado é na configuração de ambientes para instalação de softwares. Um exemplo é o preparo de uma área de desenvolvimento web em que seja preciso instalar servidor web, de aplicação e base de dados.

4. Monitoramento

Controlar o ambiente é extremamente importante, já que informações relevantes podem ser obtidas por meio da análise e controle das atividades de hardwares e softwares. Por isso, é fundamental definir métricas de monitoramento para os serviços. Assim, é possível acompanhar o consumo de todos os recursos e tomar decisões estratégicas de modo a antecipar eventuais problemas.

5. Conectividade e Alta disponibilidade

Poder acessar o ambiente a qualquer momento e de qualquer lugar proporciona um enorme benefício para a empresa, já que atualmente as pessoas trabalham em horários e lugares variados. Muitas empresas têm negócios 24/7 e precisam que o ambiente esteja disponível o tempo todo. Contudo, manter a alta disponibilidade em um data center físico requer um alto investimento. Isso porque alta disponibilidade significa manter redundância de todos os recursos de um data center. Por isso, a alternativa de manter o ambiente na nuvem é bem atrativa, já que ao contratar o serviço é possível escolher opções de alta disponibilidade, que contemplam o armazenamento em diferentes localidades.

6. Controle de acesso de usuários

Outra ferramenta muito importante para a segurança é o controle de acesso de usuários. Isso porque, por meio desse controle, é possível criar usuários com permissões adequadas ao tipo de tarefa que ele irá executar no ambiente.

7. Criptografia

Quando houver transferência de dados entre servidores, eles devem trafegar via SSL (Secure Sockets Layer). Isso porque esse protocolo garante a segurança na sua transmissão. Já os dados armazenados em nuvem utilizam padrões avançados de criptografia.

Saiba mais 💡

Cloud Computing (Computação em Nuvem):
https://www.youtube.com/watch?v=97l0Ahu2efE

O que é PaaS?
https://azure.microsoft.com/pt-br/overview/what-is-paas/

SaaS
https://www.youtube.com/watch?v=4Hw3FApvvhE


## Observability

Quando falamos neste tema, é importante termos claro quais são os 3 Pilares da Observabilidade.

<img src="https://user-images.githubusercontent.com/22088545/174402427-b7179c2d-53be-4ae1-8f59-e50f53337a29.png" width="450" height="400" />

1. Logs

Os logs são linhas de texto estruturadas e não estruturadas que um sistema produz quando determinados códigos são executados. Em geral, você pode pensar em um log como um registro de um evento que aconteceu em um aplicativo. Os logs ajudam a descobrir comportamentos imprevisíveis e emergentes exibidos por componentes da arquitetura de microsserviços. 
Os arquivos de log fornecem detalhes abrangentes do sistema, como uma falha e a hora específica em que a falha ocorreu. Ao analisar os logs, você pode solucionar problemas de seu código e identificar onde e por que o erro ocorreu. Os logs também são úteis para solucionar problemas de incidentes de segurança em balanceadores de carga, caches e bancos de dados.

2. Métricas

As métricas são uma representação numérica de dados que podem ser usadas para determinar o comportamento geral de um serviço ou componente ao longo do tempo. Elas são formadas por um conjunto de atributos (por exemplo, nome, valor, rótulo e carimbo de data/hora) que transmitem informações sobre SLAs, SLOs e SLIs. As métricas são um valor medido derivado do desempenho do sistema. Você pode reunir métricas sobre tempo de atividade do sistema, tempo de resposta, número de solicitações por segundo e quanta capacidade de processamento ou memória um aplicativo está usando, por exemplo. Normalmente, SREs e engenheiros de operações usam métricas para acionar alertas sempre que um valor do sistema ultrapassa um limite especificado.

3. Rastreamento

O rastreamento fornece contexto para os outros componentes da observabilidade. Por exemplo, você pode analisar um rastreamento para identificar as métricas mais valiosas com base no que está tentando realizar ou nos logs relevantes para o problema que está tentando solucionar.
O rastreamento é mais adequado para depurar e monitorar aplicativos complexos que disputam recursos (por exemplo, thread, disco ou rede) de maneira não trivial. O rastreamento fornece respostas rápidas para as seguintes perguntas em ambientes de software distribuído:
Quais serviços têm código ineficiente ou problemático que deve ser priorizado para otimização?
Como está a saúde e o desempenho dos serviços que compõem uma arquitetura distribuída?
Quais são os gargalos de desempenho que podem afetar a experiência geral do usuário final?

Saiba mais 💡

Observability : Como gerenciar sistemas complexos em produção
https://www.linkedin.com/pulse/observability-como-gerenciar-sistemas-complexos-em-1-coelho-de-sousa/

Observability : Metrics, Tracing e Logging - O Que, Onde e Porque dos incidentes
https://www.linkedin.com/pulse/observability-metrics-tracing-e-logging-o-que-onde-coelho-de-sousa/

SLI - SLO - SLA - Error Budget
https://harness.io/blog/srm/slo-error-budgets/

---
⌨️ com ❤️ por [Gabriel Mariusso](https://github.com/gaahmariusso) 😊

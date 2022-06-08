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

A arquitetura limpa tem como principais finalidades ser independente de frameworks, facilmente testável, independentemente da interface do usuário. Resumindo, é um tipo de arquitetura de software amplamente independente.

![image](https://user-images.githubusercontent.com/22088545/172696015-d1000d74-4736-4146-bba0-212a64a6feec.png)

Na imagem acima, temos o desenho de como a Clean Architecture funciona. Note que as setas horizontais da imagem que representam as dependências entre as camadas vêm de “fora para dentro”, ou seja, a camada Framework “enxerga” somente a Interface Adapters, que por sua vez “enxerga” somente a User Cases, que finalmente “enxerga” apenas a Entites. Esta é a principal regra da Clean Architecture, e talvez sua única: o Princípio da Dependência.

As camadas internas não devem ter qualquer dependência das externas, nem indiretas, como nomes de variáveis, funções ou termos.

Provavelmente você terá mais abstrações nas camadas internas e mais implementações nas externas, utilizando injeção de dependência para fazer tudo funcionar.

Saiba mais 💡

Clean Architecture e suas premissas:

https://renicius-pagotto.medium.com/clean-architecture-e-suas-premissas-6beb933c72b1

O uso da Clean Architecture: Uma abordagem modular:

https://medium.com/@lopesvinicius1707/o-uso-da-clean-architeture-uma-abordagem-modular-b0905b59ab74


## Hexagonal / Ports-and-Adapters

```
Hexagonal / Ports-and-Adapters
```

## Cloud Computing

```
Cloud Computing
```

---
⌨️ com ❤️ por [Gabriel Mariusso](https://github.com/gaahmariusso) 😊

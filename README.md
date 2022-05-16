# Engineering

Repositório criado com o objetivo de compartilhar conhecimentos e estudos relacionados à Engenharia como um todo.

## 🚀 Start

Espero que você embarque nesta nave, e faça bom uso dos conceitos abordados abaixo. São assuntos técnicos para aplicações modernas. Bora decolar !!

## 📋 Conceitos para um bom Engenheiro

### 12 Fatores

É uma espécie de “manifesto” com os 12 pontos que uma aplicação deveria seguir para ter sucesso nesse formato. Estes fatores não são uma verdade absoluta e tampouco devem ser seguidos cegamente, mas são um ótimo ponto de partida para a criação de projetos web modernos e que podem escalar mais facilmente para atender as demandas das empresas.
Segue abaixo o documento original criado pela Heroku, plataforma de cloud computing que revolucionou o desenvolvimento, ajudou a criar o movimento “devops” e que foi vendida por milhões de dólares para a Salesforce. Se tem algo que eles têm muita experiência é na criação e suporte de aplicativos SaaS (software-as-a-service), principalmente aplicativos web.

```
https://12factor.net/pt_br/
```

### Event-Driven

Uma arquitetura orientada a eventos usa eventos para acionar e se comunicar entre serviços desacoplados e é comum em aplicativos modernos criados com microsserviços. Um evento é uma mudança de estado ou uma atualização.
As arquiteturas orientadas a eventos têm três componentes principais: produtores de eventos, roteadores de eventos e consumidores de eventos. Um produtor publica um evento no roteador, que filtra e envia os eventos aos consumidores. Os serviços do produtor e os serviços do consumidor são desacoplados, o que permite que sejam dimensionados, atualizados e implantados de forma independente.

Exemplo do fluxo do Event-Driven:
![image](https://user-images.githubusercontent.com/22088545/166073291-41334b11-d29a-48dc-b5df-3453ddef04c1.png)

Segue abaixo alguns artigos para enriquecer o conhecimento do assunto:

O que é uma arquitetura orientada por eventos?
```
https://www.redhat.com/pt-br/topics/integration/what-is-event-driven-architecture
```
Escolhendo uma arquitetura orientada a eventos:
```
https://www.infoq.com/br/news/2017/09/selecting-event-architecture/
```
Events Hub: como e por quê uma Perspectiva Orientada a Eventos pode ajudar muito a sua empresa:
```
https://br.sensedia.com/post/events-hub-how-and-why-an-event-driven-perspective-can-greatly-help-your-company
```
#### DLQ (Dead Letter Queue)

As filas de mensagens mortas são úteis para depurar sua aplicação ou sistema de mensagens, pois permitem que você isole mensagens não consumidas para determinar por que seu processamento não obteve êxito. Por exemplo, se um usuário fizer um pedido na web com um ID de produto específico, mas esse ID do produto for excluído, o código da loja da web falhará e exibirá um erro. Além disso, a mensagem com a solicitação do pedido poderá ser enviada para uma dead-letter queue.

DLQ + Kafka - Artigo da Uber Engineering
```
https://imasters.com.br/desenvolvimento/construindo-reprocessamento-confiavel-e-dead-letter-queues-com-kafka
```
Lambda + DLQ (Exemplo da AWS, porém é possível em qualquer Cloud)
```
https://aws.amazon.com/pt/blogs/compute/robust-serverless-application-design-with-aws-lambda-dlq/#:~:text=Robust%20Serverless%20Application%20Design%20with%20AWS%20Lambda%20Dead%20Letter%20Queues,-by%20Bryan%20Liston&text=AWS%20Lambda%20is%20a%20serverless,handle%20exceptions%20and%20failures%20gracefully.
```
#### Orquestração vs. Coreografia de serviços

A orquestração de serviço representa um único processo de negócios executável centralizado (o orquestrador) que coordena a interação entre diferentes serviços. O orquestrador é responsável por invocar e combinar os serviços.
O relacionamento entre todos os serviços participantes é descrito por um único terminal (ou seja, o serviço composto). A orquestração inclui o gerenciamento de transações entre serviços individuais. A orquestração emprega uma abordagem centralizada para a composição do serviço.

Coreografia de serviço é uma descrição global dos serviços participantes, definida pela troca de mensagens, regras de interação e acordos entre dois ou mais pontos de extremidade. A coreografia emprega uma abordagem descentralizada para a composição do serviço.
A coreografia descreve as interações entre vários serviços, onde a orquestração representa o controle da perspectiva de uma parte. Isso significa que uma coreografia difere de uma orquestração com relação a onde a lógica que controla as interações entre os serviços envolvidos deve residir.

| Orquestração de serviço | Coreografia de serviço |
| --- | --- |
| ![image](https://user-images.githubusercontent.com/22088545/167660064-25da6f9c-3767-4d62-b6b5-a1acb51d1772.png)s | ![image](https://user-images.githubusercontent.com/22088545/167660145-2402c710-37b9-4c1e-b44e-b032ff4ef5bf.png) |

Orquestração vs. Coreografia de serviços
```
https://www.grupomult.com.br/orquestracao-vs-coreografia-de-servicos/
```
Entendendo Event Driven
```
https://br.sensedia.com/post/understanding-event-driven-standards
```

### Microsserviço

This is how a monolith would look like. One application for everything.
![image](https://user-images.githubusercontent.com/22088545/168696771-61fe4e06-a226-41ec-95a4-5e8fdc2dd10b.png)

This is how the same application would look like when developed using Microservices Architecture.
![image](https://user-images.githubusercontent.com/22088545/168696786-f336ba30-8791-4315-9fa2-f49708686436.png)

Microservice Architectures involve a number of small, well designed, components interacting with messages. 
![image](https://user-images.githubusercontent.com/22088545/168696796-3ffe1431-031b-483e-bcdd-2a2be026e61a.png)

Introdução a Microsserviços
```
https://medium.com/introducao-a-arquitetura-de-microservicos/introdu%C3%A7%C3%A3o-a-microsservi%C3%A7os-25378269e6f9
```

### Domain Driven Design

```
Domain Driven Design
```

### S.O.L.I.D

```
Solid
```

### Clean Arquitecture

```
Clean Arquitecture
```

### Hexagonal / Ports-and-Adapters

```
Hexagonal / Ports-and-Adapters
```

### Cloud Computing

```
Cloud Computing
```

---
⌨️ com ❤️ por [Gabriel Mariusso](https://github.com/gaahmariusso) 😊

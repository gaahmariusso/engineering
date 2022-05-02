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


### Microsserviço

```
Microsserviço
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

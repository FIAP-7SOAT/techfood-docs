# TechFood - Sistema de Autoatendimento para Restaurante FastFood

Este é um projeto do curso de Pós-graduação em Arquitetura de Software da FIAP compreende uma solução possível para um sistema de autoatendimento de restaurante do tipo fast-food, com quiosques ou terminais de autoatendimento, com o objetivo de otimizar o processo de pedidos, pagamento, preparação e entrega de comida..

Autores membros do Grupo:

- Geraldo Moratto Junior - RM356285
- Pedro Cantarelli - RM355410
- Vinicius Lopes - RM354901

## Índice

- [Requisitos](#requisitos)
- [Domain-Driven Development (DDD)](#domain-driven-development-ddd)
- [Arquitetura](#arquitetura)
- [Serviços Disponíveis](#serviços-disponíveis)

- [Postman Collection](#postman-collection)

## Requisitos

Em geral os clientes e administradores usarão o sistema, que dependerá de um serviço de pagamento externo.

No atual momento, os requisitos do sistema são:

- Gerenciamento de pedidos, com acompanhamento e pagamento.
- Gerenciamento de clientes
- Gerenciamento de produtos e categorias

Saiba mais sobre os requisitos de forma detalhada [aqui](https://github.com/FIAP-7SOAT/techfood-docs/blob/main/requirements.md)!

### Domain-Driven Development (DDD)

A abordagem utilizada para o desenvolvimento foi a DDD, com as seguintes saídas:

- [Glossário ubíquo](https://www.figma.com/board/JpMG7uY03GHnNY92hHxdb3/Lanchonete-de-Bairro?node-id=217-13086&t=TfMJyuLNDTmXck6Z-4)
- [Event storming](https://www.figma.com/board/JpMG7uY03GHnNY92hHxdb3/Lanchonete-de-Bairro?node-id=0-1&t=TfMJyuLNDTmXck6Z-0)
- Storytelling
- Mapa de Contexto
- [Modelagem de Microsserviços](https://www.figma.com/board/JpMG7uY03GHnNY92hHxdb3/Lanchonete-de-Bairro?node-id=299-2156&node-type=text&t=h5gsXNpOwHQ7cpOO-0)

## Arquitetura

O sistema expõe RESTful APIs para aplicações front-end, como terminais de autoatendimento para clientes e interfaces para administradores. Tem como dependência um provedor externo de pagamento, o MercadoPago.

Separamos a aplicação monolito em microsserviços, agora cada serviçoe é responsável por uma parte da aplicação. Os microsserviços permitem que um aplicativo grande seja separado em partes independentes e menores, com cada parte tendo sua própria responsabilidade. Arquitetura Hexagonal (Ports and Adapters) e Clean Architecture foram adotadas no projeto.

### Arquitetura Kubernetes

[Arquitetura Kubernetes](https://www.figma.com/board/JpMG7uY03GHnNY92hHxdb3/Lanchonete-de-Bairro?node-id=0-1&t=W1aQzvEzhq0IOrMn-0)
![Arquitetura Kubernetes](https://cdn.discordapp.com/attachments/1310749229756448779/1311866269581971466/image.png?ex=674a6a2b&is=674918ab&hm=ce4fffdc31a8924c02f80207b496483c82a47cb3a786699636593745c6e07dd7&)

### Video da Arquitetura Monolito

- [Funcionamento da apliação](https://www.youtube.com/watch?v=33iDsv87Nnc&ab_channel=PedroCantarelli).
- [Arquitetura do Projeto](https://www.youtube.com/watch?v=a7mExdMBwO4&ab_channel=PedroCantarelli)

## Serviços Disponíveis

O TechFood expõe os seguintes serviços para integração:

- **[Techfood Clientes](https://github.com/FIAP-7SOAT/techfood-clientes):** API para gerenciamento de clientes no sistema.
- **[Techfood Pedidos](https://github.com/FIAP-7SOAT/techfood-pedidos):** API para gerenciamento de pedidos no sistema.
- **[Techfood Produtos](https://github.com/FIAP-7SOAT/techfood-produtos):** API para gerenciamento de produtos no sistema.

![Modelagem Microsserviços](https://cdn.discordapp.com/attachments/1310749229756448779/1311877105700704256/image.png?ex=674a7443&is=674922c3&hm=1bbeff2bacdbdd94dfec228936809177484ef5799fe7d94e61d1585c5b47098e&)

### Funcionalidades Principais

- **Pedido Personalizado:** Os clientes podem criar pedidos personalizados, escolhendo entre uma variedade de itens, como lanches, acompanhamentos, bebidas e sobremesas.
- **Pagamento Integrado:** Integração com o Mercado Pago, permitindo que os clientes efetuem o pagamento de seus pedidos através de um QRCode.
- **Acompanhamento de Pedido:** Os clientes podem acompanhar o status de seus pedidos, desde o momento em que são recebidos até estarem prontos para retirada.
- **Gerenciamento Administrativo:** Os administradores têm acesso a um painel de controle para gerenciar clientes, produtos, categorias e pedidos em andamento.

### Postman Collections

Baixar o Postman ou o API Client de sua preferência e importar a collection:

- [Techfood Clientes](https://github.com/FIAP-7SOAT/techfood-docs/blob/main/Postman/TechFood%20Clientes%20Collection.postman_collection.json)
- [Techfood Pedidos](https://github.com/FIAP-7SOAT/techfood-docs/blob/main/Postman/TechFood%20Pedidos%20Collection.postman_collection.json)
- [Techfood Produtos](https://github.com/FIAP-7SOAT/techfood-docs/blob/main/Postman/TechFood%20Produtos%20Collection.postman_collection.json)

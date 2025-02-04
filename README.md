# EAD-MICROSERVICES

Este projeto implementa uma arquitetura de microsserviços para uma plataforma de Ensino a Distância (EAD). Ele utiliza fluxos síncronos e assíncronos para fornecer um sistema escalável e modular, permitindo o gerenciamento de usuários, cursos, notificações e pagamentos.

## Estrutura da Arquitetura
![Captura de tela 2025-01-13 111415](https://github.com/user-attachments/assets/c5294d0a-ddef-493e-9611-2cff4f99a7e6)

## Explicação do Diagrama

#### 1. Fluxo Síncrono:
O cliente interage com os microsserviços por meio do **API Gateway**, que se conecta diretamente ao **Authuser**, **Payment**, e outros microsserviços.

#### 2. Fluxo Assíncrono:
A comunicação entre **Course**, **Notification** e outros serviços ocorre por meio de mensagens publicadas no **RabbitMQ**.

#### Componentes Centrais:
- **Service Registry**: Gerencia o registro e a descoberta de microsserviços.
- **Config Server**: Centraliza e gerencia as configurações dos microsserviços.

## Estrutura dos Microsserviços

### 1. Authuser
- Gerencia a autenticação e autorização de usuários.
![Captura de tela 2025-01-13 122256](https://github.com/user-attachments/assets/49b85f64-bd68-4de9-bb35-030fa4253e1c)

### 2. Course
- Lida com o cadastro e gerenciamento de cursos.
![Captura de tela 2025-01-13 122724](https://github.com/user-attachments/assets/7f6b6c06-2303-4bce-8119-50ecd2da1ea5)

### 3. Payment
- Processa e gerencia pagamentos da plataforma.
![Captura de tela 2025-01-13 123216](https://github.com/user-attachments/assets/f62de49d-a322-4def-855c-f6c9256dad48)

### 4. Notification
- Responsável pelo envio e controle de notificações.
![Captura de tela 2025-01-13 123748](https://github.com/user-attachments/assets/345d5d7a-e2db-4f4c-ba76-858204023550)

### 5. API Gateway
- Roteia requisições para os microsserviços apropriados.

### 6. Config Server
- Centraliza e gerencia as configurações dos microsserviços.

### 7. ead-config-server-repo
- Repositório Git que armazena as configurações externas dos microsserviços.

### 8. Service Registry
- **Eureka Server** para registro e descoberta de microsserviços.

## Principais Tecnologias

- **Spring Boot**: Framework para construção de microsserviços.
- **Spring Cloud**: Suporte para padrões de microsserviços como **Service Discovery**, **API Gateway** e **Config Server**.
- **Spring Security**: Autenticação e autorização com **JWT**.
- **RabbitMQ**: Comunicação assíncrona entre serviços.
- **PostgreSQL**: Banco de dados relacional.
- **Resilience4j (Circuit Breaker)**: Resiliência em chamadas entre serviços.

## Configuração do Repositório do Config Server

Você precisa criar um repositório Git separado para gerenciar as configurações dos microsserviços. Siga os passos abaixo:

1. Crie um repositório no GitHub (ou qualquer serviço de hospedagem Git) com o nome **ead-config-server-repo**.
2. Clone o repositório e adicione seus arquivos de configuração.
3. Atualize o arquivo `application.yml` no serviço **Config Server** para apontar para o seu repositório. Exemplo:

![Captura de tela 2025-01-13 111943](https://github.com/user-attachments/assets/bc9e035d-1c69-459a-8b78-d4cbf65ffbea)

### Configuração do RabbitMQ

Certifique-se de que você possui uma chave própria configurada para o RabbitMQ. Atualize o arquivo `application.yml` com as credenciais do seu serviço AMQP e garanta que essa chave seja atualizada em todos os ambientes configurados no repositório **EAD Config Server Repo**.

## Tecnologias Usadas

- **Java**
- **Spring Boot**
- **Spring Cloud**
- **RabbitMQ**
- **PostgreSQL**
- **JWT (JSON Web Tokens)**

## Contribuições

Fique à vontade para fazer um fork deste repositório e enviar pull requests. Contribuições são bem-vindas!


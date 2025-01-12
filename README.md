
# EAD-MICROSERVICES

Este projeto implementa uma arquitetura de microsserviços para uma plataforma de ensino a distância (EAD). Ele utiliza fluxos síncronos e assíncronos para fornecer um sistema escalável e modular, permitindo o gerenciamento de usuários, cursos, notificações e pagamentos.




## Estrutura da Arquitetura
## Explicação do Diagrama

#### 1.Fluxo Síncrono:
O cliente interage com os microsserviços por meio do API Gateway, que se conecta ao Authuser, Payment, e outros microsserviços de forma direta.

#### 2.Fluxo Assíncrono:
A comunicação entre Course, Notification e outros serviços ocorre via mensagens publicadas no RabbitMQ.

#### 2.Componentes Centrais:

- Service Registry: Gerencia o registro e descoberta de microsserviços.
- Config Server: Centraliza as configurações.




## Estrutura dos Microsserviços

### 1. Authuser
- Gerencia autenticação e autorização de usuários.

### 2. Course
- Lida com o cadastro e gerenciamento de cursos.

### 3. Notification
- Responsável pelo envio e controle de notificações.

### 4. Service Registry
- Eureka Server para registro e descoberta de serviços.

### 5. API Gateway
- Roteia requisições para os serviços apropriados..

### 6. Config Server
- Centraliza e gerencia configurações dos microsserviços.

### 7. ead-config-server-repo
- Repositório Git que armazena as configurações externas dos microsserviços.

### 8. Payment
- Processa e gerencia pagamentos da plataforma.

## Configuração do Repositório do Config Server

#### Você precisa criar um repositório Git separado para gerenciar as configurações dos microsserviços. Siga os passos abaixo:

1. Crie um repositório no GitHub (ou qualquer serviço de hospedagem Git) com o nome ead-config-server-repo.

2. Clone o repositório e adicione seus arquivos de configuração.

3. Atualize o arquivo application.yml no serviço Config Server para apontar para o seu repositório. Exemplo:

### Exemplo:
spring:
  cloud:
    config:
      server:
        git:
          uri: https://github.com/seu-usuario/ead-config-server-repo
          default-label: main
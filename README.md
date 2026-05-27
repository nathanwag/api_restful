# api_restful
  
## Descrição do Trabalho 
As equipes deverão desenvolver uma API para um sistema de Gestão de tarefas Colaborativas, permitindo que usuários criem, editem, atribuam e concluam tarefas. A API deve seguir uma arquitetura bem definida (por exemplo, Arquitetura Hexagonal, Clean Architecture ou MVC), garantindo boas práticas de desacoplamento e modularização.    

## Requisitos Funcionais
A API deve expor os seguintes endpoints:

#### Usuários
- POST: /users → Criar um novo usuário
- GET: /users/{id} → Obter informações de um usuário específico
- PUT: /users/{id} → Atualizar informações do usuário
- DELETE: /users/{id} → Remover um usuário (soft delete recomendado)

#### Tarefas
- POST: /tasks → Criar uma nova tarefa
- GET: /tasks/{id} → Obter detalhes de uma tarefa
- GET: /tasks?assignedTo={userId} → Listar todas as tarefas atribuídas a um usuário
- PUT: /tasks/{id} → Atualizar informações da tarefa (título, descrição, status)
- DELETE: /tasks/{id} → Remover uma tarefa

#### Autenticação 
- POST: /auth/login → Login de usuários, retornando um token JWT para autenticação nas demais requisições
- POST: /auth/logout → Logout do usuário

## Requisitos Complementares 
- Integração com Calendários (Google Calendar, Outlook) 
    - Permitir que tarefas atribuídas com datas sejam sincronizadas com o calendário do usuário 
    - Exemplo: ao criar uma tarefa com data e hora, o sistema cria um evento no Google Calendar do usuário

- Webhooks para Integração com Discord 
    - Disparar notificações sempre que uma tarefa for criada, atribuída ou concluída 
    - Pode ser implementado de forma genérica: usuários configuram seus próprios webhooks 

- Comentários em Tarefas (Sub-recursos aninhados) 
    - Implementar /tasks/{id}/comments com suporte a:
        - Criação, leitura e exclusão de comentários
        - Associar comentários a usuários e timestamps

## Requisitos Não Funcionais   
- Implementar padrões arquiteturais claros (por exemplo, Arquitetura Hexagonal, MVC ou Clean Architecture) 
- Utilizar banco de dados relacional (MySQL, PostgreSQL) ou NoSQL (MongoDB), justificando a escolha 
- Implementar testes automatizados com cobertura mínima de 60% do código da API 
- Implementar logs e tratamento de erros adequados 
- Documentar a API utilizando Swagger/OpenAPI 
# support-tickets

### Sobre

API para gerenciar ticket de suporte técnico, permitindo criar um ticket solicitando suporte, atualizar as informações do ticket, listar os tickets podendo filtrar pelo status e atualizar o status de um ticket para fechado.

### Rotas

- _**Criar Ticket**_
    
    Cria um novo ticket de suporte.
    
    **Método:** POST
    
    **URL:** `/tickets`
    
    **Dados:**
    
    - `equipment` (string, obrigatório): Nome do equipamento (exemplo: computador)
    - `description` (string, obrigatório): Descrição do problema.
    - `user_name` (string, obrigatório): nome do usuário que está criando o ticket.
    ---
- _**Obter Tickets**_
    
    **Método:** GET
    
    **URL:** `/tickets`
    
    **Descrição:** Obtém uma lista de todos os tickets de suporte.
    
    **Parâmetros de Consulta (Query Parameters)**:
    
    - `status` (string, opcional): Filtra os tickets pelo status ("open" ou "closed").
    ---
- _**Atualizar Ticket**_
    
    **Método:** PUT
    
    **URL:** `/tickets/:id`
    
    **Descrição:** Atualiza as informações de um ticket específico.
    
    **Parâmetros de Rota:**
    
    - `id` (UUID, obrigatório): ID do ticket.
    
    **Parâmetros no Corpo (JSON):**
    
    - `equipment` (string, obrigatório): Nome do equipamento (exemplo: computador)
    - `description` (string, obrigatório): Descrição do problema.
    - `user_name` não altera.
---
- _**Fechar Ticket**_
    
    **Método:** PATCH
    
    **URL:** `/tickets/:id/status`
    
    **Descrição:** Atualiza as informações de um ticket específico.
    
    **Parâmetros de Rota:**
    
    - `id` (UUID, obrigatório): ID do ticket.
---
- _**Excluir Ticket**_
    
    **Método:** DELETE
    
    **URL:** `/tickets/:id`
    
    **Descrição:** Exclui um ticket específico pelo seu ID.
    
    **Parâmetros de Rota:**
    
    - `id` (UUID, obrigatório): ID do ticket.
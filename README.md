# **Desafio 01 - Conceitos do Node.js**

Nesse desafio, deverá ser criaado uma aplicação para treinar o que aprendeu até agora no Node.js!

O projeto neste desafio é uma API que realiza todo o CRUD de uma TODO list, onde será possível criar um usuário com `name` e `username`, bem como fazer o CRUD de *todos*.

## Rotas da aplicação

- **POST /users**: A rota deve receber `name` e `username` dentro do corpo da requisição para cadastrar um novo usuário;
- **GET /todos**: Rota que lista todos os *todos*;
- **POST /todos**: A rota deve receber `title` e `deadline` dentro do corpo da requisição, sendo `deadline` uma data no formato `yyyy-mm-dd`. Ao cadastrar um novo *todo*, ele deve ser armazenado dentro de um objeto no seguinte formato: `{ id: uuid(), title: 'Nome da tarefa', done: false, deadline: '2021-02-27T00:00:00.000Z', created_at: '2021-02-22T00:00:00.000Z' }`; **A data e hora `created_at` deve ser preenchida automaticamente pelo sistema e o `id` deve ser um uuid**;
- **PUT /todos/:id**: A rota deve alterar apenas o `title` e o `deadline` do *todo* que possua o `id` igual ao `id` presente nos parâmetros da rota;
- **PATCH /todos/:id/done**: A rota deve alterar o campo `done` para `true` para o *todo* que possua o `id` igual ao `id` presente nos parâmetros da rota;
- **DELETE /todos/:id**: A rota deve deletar o *todo* que possua o `id` igual ao `id` presente nos parâmetros da rota;

## Específicação dos testes

Para esse desafio temos os seguintes testes:

### Users

- **should be able to create a new user**: Para que esse teste passe, a aplicação deve permitir que um usuário seja criado, e retorne um json com o usuário criado;
- **should not be able to create a new user when username already exists**: Para que esse teste passe, a aplicação deve retornar um erro quando o username passado na requisição já existir no banco de dados;

### Todos

- **should be able to list all user's todo**: Para que esse teste passe, a aplicação deve permitir que sejam listados todos os *todos* de um usuário, e retorne um array contendo todos os *todos* do usuário;
- **should be able to create a new todo**: Para que esse teste passe, a aplicação deve permitir que um *todo* seja criado, e retorne um json com o *todo* criado;
- **should be able to update a todo**: Para que esse teste passe, a aplicação deve permitir que um *todo* seja atualizado, e retorne um json com o *todo* atualizado;
- **should not be able to update a non existing todo**: Para que esse teste passe, a aplicação deve retornar um erro quando o *todo* que se deseja atualizar não existir;
- **should be able to mark a todo as done**: Para que esse teste passe, a aplicação deve permitir que um *todo* seja marcado como feito, e retorne um json com o *todo* atualizado;
- **should not be able to mark a non existing todo as done**: Para que esse teste passe, a aplicação deve retornar um erro quando o *todo* que se deseja marcar como feito não existir;
- **should be able to delete a todo**: Para que esse teste passe, a aplicação deve permitir que um *todo* seja deletado, e retorne um status `204`;
- **should not be able to delete a non existing todo**: Para que esse teste passe, a aplicação deve retornar um erro quando o *todo* que se deseja deletar não existir.

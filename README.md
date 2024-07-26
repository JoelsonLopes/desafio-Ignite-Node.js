**Desafio Rockeseat para treinar temas abordados em aula sobre os fundamentos de NODE.JS
**
## Instalação

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
[Git](https://git-scm.com) e [Node.js](https://nodejs.org/en/). Além disso é bom ter um editor para trabalhar com o código como [VSCode](https://code.visualstudio.com/).

### 🎲 Rodando o Back End (servidor)

```bash
# Clone este repositório
$ git clone https://github.com/JoelsonLopes/desafio-Ignite-Node.js

# Acesse a pasta do projeto no terminal/cmd
$ cd desafio-ignite-node.js

# Instale as dependências
$ npm install

# Execute a aplicação em modo de desenvolvimento
$ npm run dev

# Para executar a criação das tasks por CSV execute
$ node --watch streams/import-csv.js

# O servidor iniciará na porta 3335 - acesse <http://localhost:3335>
```

## Tecnologias

[![My Skills](https://skillicons.dev/icons?i=nodejs,js)](https://skillicons.dev)


## Sobre o desafio

Nesse desafio você desenvolverá uma API para realizar o CRUD de suas *tasks* (tarefas).

A API deve conter as seguintes funcionalidades:

- Criação de uma task
- Listagem de todas as tasks
- Atualização de uma task pelo `id`
- Remover uma task pelo `id`
- Marcar pelo `id` uma task como completa
- E o verdadeiro desafio: Importação de tasks em massa por um arquivo CSV

### Rotas e regras de negócio

Antes das rotas, vamos entender qual a estrutura (propriedades) que uma task deve ter:

- `id` - Identificador único de cada task
- `title` - Título da task
- `description` - Descrição detalhada da task
- `completed_at` - Data de quando a task foi concluída. O valor inicial deve ser `null`
- `created_at` - Data de quando a task foi criada.
- `updated_at` - Deve ser sempre alterado para a data de quando a task foi atualizada.

Rotas:

- `POST - /tasks`
    
    Deve ser possível criar uma task no banco de dados, enviando os campos `title` e `description` por meio do `body` da requisição.
    
    Ao criar uma task, os campos: `id`, `created_at`, `updated_at` e `completed_at` devem ser preenchidos automaticamente, conforme a orientação das propriedades acima.
    
- `GET - /tasks`
    
    Deve ser possível listar todas as tasks salvas no banco de dados.
    
    Também deve ser possível realizar uma busca, filtrando as tasks pelo `title` e `description`
    
- `PUT - /tasks/:id`
    
    Deve ser possível atualizar uma task pelo `id`.
    
    No `body` da requisição, deve receber somente o `title` e/ou `description` para serem atualizados.
    
    Se for enviado somente o `title`, significa que o `description` não pode ser atualizado e vice-versa.
    
    Antes de realizar a atualização, deve ser feito uma validação se o `id` pertence a uma task salva no banco de dados.
    
- `DELETE - /tasks/:id`
    
    Deve ser possível remover uma task pelo `id`.
    
    Antes de realizar a remoção, deve ser feito uma validação se o `id` pertence a uma task salva no banco de dados.
    
- `PATCH - /tasks/:id/complete`
    
    Deve ser possível marcar a task como completa ou não. Isso significa que se a task estiver concluída, deve voltar ao seu estado “normal”.
    
    Antes da alteração, deve ser feito uma validação se o `id` pertence a uma task salva no banco de dados.

---

### "A jornada do aprendizado nunca termina. Continue sempre explorando, experimentando e evoluindo.🚀"

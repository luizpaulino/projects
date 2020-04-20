# Gerenciamento de repositórios

Projeto não faz persistência no banco de dados, os dados são armazenados em memória.

## Requisitos
- Node 12 ou mais recente
- Yarn 1

## Running do projeto:
- Acessar o diretório do projeto.
- Executar ``` yarn ``` para atualizar as dependências do projeto
- Executar ``` yarn dev ``` para rodar o servidor de API


## Rotas:
  - /repositories
    - POST -> Inclusão de um novo projeto, exemplo:
    ```json
    {
      "title": "Projeto react native",
      "url": "http: //github.com/...",
      "techs": [
        "JavaScript",
        "Android",
        "IOS"
      ]
    }
    ```
    - GET -> Lista todos os repositórios cadastrados, exemplo de resposta:
    ```json
    [
      {
        "id": "234a4b8d-0b3e-46de-beba-3bb5d3d3eb47",
        "title": "DesafioReactNative",
        "url": "http: //github.com/...",
        "techs": [
          "JavaScript",
          "Android",
          "IOS"
        ],
        "likes": 36
      }
    ]
    ```
  - /repositories/{ID}
    - DEL -> Exclui o repositório cujo ID foi passado como paramêtro da rota
    - PUT -> Altera qualquer informação do repositório, exceto o ID, exemplo de alteração da url do projeto:
    ```json
    {
      "title": "Projeto react native",
      "url": "https://github.com/luizpaulino/projects",
      "techs": [
        "JavaScript",
        "Android",
        "IOS"
      ]
    }
    ```
  - /repositories/{ID}/like
    - POST -> Permite curtir um projeto, retornando todas as informações do projeto com o novo total de likes, exemplo:
    ```json
    {
        "id": "234a4b8d-0b3e-46de-beba-3bb5d3d3eb47",
        "title": "DesafioReactNative",
        "url": "http: //github.com/...",
        "techs": [
          "JavaScript",
          "Android",
          "IOS"
        ],
        "likes": 37
      }
    ```


### To-do
- [X] Colocar o README do projeto bem documentado
- [ ] Colocar uma opção de README em inglês
- [ ] Implementar os testes unitários das funcionalidades atuais
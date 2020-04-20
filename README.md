#Gerenciamento de repositórios

Projeto não faz persistência no banco de dados, os dados são armazenados em memória.

Rotas:
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

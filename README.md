# API de Games
Esta API é ultilizada para...
## Endpoints
### GET /games
Esse e o endpoint é responsavel por retornar a linguagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Genshin Impact",
        "year": 2020,
        "price": 0
    },
    {
        "id": 65,
        "title": "Sea of Teaives",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Elsword",
        "year": 2012,
        "price": 0
    }
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token invalido, Token expirado.
Exemplo de resposta:
```
{
    "err": "Token Invalido"
}
```



### POST /auth
Esse e o endpoint é responsavel por fazer o processo de login.
#### Parametros
email: Email do usuario cadastrado no sistema.


password: Senha do usuario cadastrado no sistema, com aquele determinado email.

Exemplo:
```
{
    "email":"alesygabriel3@gmail.com",
    "password":"nodada50"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints accessados na API.
Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJhbGVzeWdhYnJpZWwzQGdtYWlsLmNvbSIsImlhdCI6MTY1NjQ0OTE3NywiZXhwIjoxNjU2NjIxOTc3fQ.sKQ-kIw48lizuHubqsN8-v9TjYW7JKm9eU-wZhbAcu0"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou email incorretos.
Exemplo de resposta:
```
    err: "Credenciais invalidas"
```

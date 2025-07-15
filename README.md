_# API de Games
Esta API é ultilizada para TAL e TAL...
## Endpoints
### GET /Games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
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
        "title": "Call of dut MW",
        "year": 2019,
        "price": 60
    },
    {
        "id": 75,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 1,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]

```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.
Exemplo de resposta:
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de loguin.
#### Parametros
email: E-mail do usúario cadastrado no sistema.

password: Senha do usúario cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "RcpEscobar9482@gmail.com",
    "password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJSY3BFc2NvYmFyOTQ4MkBnbWFpbC5jb20iLCJpYXQiOjE3NTI1OTIwMzcsImV4cCI6MTc1Mjc2NDgzN30.XJUSiQc0t1YEeXLZdcuD9zkX7vjchb0lmaRSr2bX5Lo"
}

```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorreto.
Exemplo de resposta:
```
({err: "Credenciais inválidas!"});
```

_

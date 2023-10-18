# API  de Games
Esta API é utilizada para tal (descrição)...

## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco.
#### Parametros
Nenhum.
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 2323,
        "title": "GTA",
        "price": "350",
        "year": "2003"
    },
    {
        "id": 2345,
        "title": "Minecraft",
        "price": "143",
        "year": "2012"
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido/expirado.

Exemplo de resposta: 
```
{
    "error": "Token inválido"
}
```

### POST /auth
Esse endpoint é responsável por efetuar o login do usuário.
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha atrelada ao email/conta do usuário.

Exemplo: 
```
{
  "email": "exemple@gmail.com",
  "password": "123h4g12jv34"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber um token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta:
```
    {
        "token": "kjeh456b3k4j56bl34kj56b3l4kj5"
    }
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Email ou senha inválido.

Exemplo de resposta: 
```
{
    "error": "Credenciais inválidas"
}
```


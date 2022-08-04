# LOVEPETSHOP API

Essa é uma api criada a partir do json-server LOVE PET SHOP API - um banco de dados para um e commerce de uma pe shop. <br>
A partir dos dados da fake API, é possivel criar um front-end com informações estaveis e de boa interagibilidade.

## Endpoints

A API traz ao todo 7 Endpoints, sendo 3 referente ao usuário, 2 a pet shop, e mais 2 para o cliente deixa o seu feedback sobre a loja!

a base url da api é: <a>https://lovepetshop.herokuapp.com</a>

## Rotas que não precisam de autenticação

## Cadastro

POST - baseurl/register <br/>
POST - baseurl/signup <br/>
POST - baseurl/users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

dados para registrar um novo usuario: <br>

```
{

    "email": "allankenzie@example.com",
    "password": "123456",
    "name": "Allan Kenzie",
    "age": 22

}
```

resposta da api: <br>

```
{
    "accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9eyJlbWFpbCI6Im5pY29sZUBnbWFpbC5jb20iLCJpYXQiOjE2NTk1NjA2NDcsImV4cCI6MTY1OTU2NDI0Nywic3ViIjoiMyJ9. Lpx1cdORQjtBiL8HG--h3_KLIh6O1c9qFewRRAbvCEg",
    "user": {
    "email": "allankenzie@example.com",
    "name": "Allan Kenzie",
    "age": 22,
    "id": 3
    }
}
```

### Possivel erro no cadastro

Os campos de email e password são campos obrigatórios para a requisição funcionar:

```
"email and password are required"
```

A senha não pode ser curta, tolerância de no minimo 4 caracteres.

```
"Password is too short"
```

Não é possivel criar um usuário com o mesmo email.

```
"Email already exists"
```

---

## Login

POST - baseurl/login <br/>
POST - baseurl/signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

dados para o usuario fazer o login: <br>

```
{
    "name": "allankenzie@example.com",<br>
    "password": "123456" <br>
}
```

resposta da api: <br>

```
{

  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im5pY29sZUBnbWFpbC5jb20iLCJpYXQiOjE2NTk1NjA2NDcsImV4cCI6MTY1OTU2NDI0Nywic3ViIjoiMyJ9.Lpx1cdORQjtBiL8HG--h3_KLIh6O1c9qFewRRAbvCEg",
  "user": {
    "email": "allankenzie@gmail.com",
    "name": "Allan Kenzie",
    "age": 22,
    "id": 3
    }
}
```

### Possiveis erros

Usuário que não está registrado no banco de dados. Possivelmente o usuário inseriu um email não existente

```
"Cannot find user"
```

Senha incorreta.

```
"Incorrect password""
```

---

## Products

GET - baseurl/products

Nesse endpoint você consegue consultar os produtos da loja. Onde terá as informações de cada produto da loja LOVEPET com o nome, categoria, a url da imagem do produto, e as informações de pagamento (preço normal, e o valor em parcelas)

Resposta da API:

```
[
  {
    "id": 1,
    "title": "Cama Viton -tecido suede",
    "category": "cama",
    "post": "https://images.tcdn.com.br/img/img_prod/1113036/cama_viton_tecido_suede_1_1_0177d8920ebfc98d55630b1f217f8cdc.jpg",
    "price": {
      "debit": 249.9,
      "credit": {
        "value": 79.97,
        "split": 3
      }
    }
  },
  {
    "id": 2,
    "title": "MINI COLAR BANDANA LOVE NATURE DA PETECCO",
    "category": "acessório",
    "post": "https://images.tcdn.com.br/img/img_prod/783690/mini_colar_bandana_love_nature_da_petecco_63_1_8240f225cf92b81ab52198a5cde36a2c.jpg",
    "price": {
      "debit": 19,
      "credit": {
        "value": 1.96,
        "split": 12
      }
    }
  },
  {
    "id": 3,
    "title": "GUIA PARA PET PRETA DA PETECCO",
    "category": "acessório",
    "post": "https://images.tcdn.com.br/img/img_prod/783690/guia_para_pet_preta_da_petecco_61_1_b82a0573eaef3212b2c531b7f4307b46.jpg",
    "price": {
      "debit": 53,
      "credit": {
        "value": 5.47,
        "split": 12
      }
    }
  },
  {
    "id": 4,
    "title": "Cama Zee.Bed Skull",
    "category": "cama",
    "post": "https://zeedog.vteximg.com.br/arquivos/cama-para-cachorros-zeebed-skull-zeedog-cachorro-pet-main-01.jpg",
    "price": {
      "debit": 499,
      "credit": {
        "value": 166.33,
        "split": 3
      }
    }
  },
  {
    "id": 5,
    "title": "TAPETE HIGIÊNICO ECOLÓGICO REUTILIZÁVEL LAVÁVEL DA PETECCO",
    "category": "higiênicos",
    "post": "https://images.tcdn.com.br/img/img_prod/783690/tapete_higienico_ecologico_reutilizavel_lavavel_g_da_petecco_9_1_7091c5dc18ecce6f4a65eae289bf9ae4.jpg",
    "price": {
      "debit": 89,
      "credit": {
        "value": 7.45,
        "split": 12
      }
    }
  },
  {
    "id": 6,
    "title": "Mordedor Ossinho Petz P - Cores Sortidas",
    "category": "Brinquedo  ",
    "post": "hhttps://static.petz.com.br/fotos/1608211837627.jpg",
    "price": {
      "debit": 27.49,
      "credit": {
        "value": 9.17,
        "split": 3
      }
    }
  }
]
```

---

## Rotas que precisam da autorização

As rotas que precisão de autorização são rotas onde o usuário precisa estar logado, tendo como referência o token gerado pos login que deve ser informado na header de requisição dess forma:

```
headers:{
    Authorization: `Bearer {token}`
}
```

## Feedbacks

POST - <strong>baseurl</strong>/feedbacks

Com essa rota é possivel o usuário postar um comentário sobre a loja.Além de uma avaliação de 1 a 5

```
{
  "comment": "site muito bom, recomendo demais",
  "rate": 4.8
}

```

Resposta da API:

```
{
  "comment": "site muito bom, recomendo demais",
  "rate": 4.8,
  "id": 3
}
```

GET - <strong>baseurl</strong>/feedbacks

Apenas usuários que estão logado conseguem ver todos os comentários.

```
[
  {
    "comment": "Gostei muito da pet shop online, traz uma grande praticidade em levar os produtos do meu pet até mim de maneira muito rapida, site muito bem confiavel!",
    "rate": 5,
    "id": 1
  },
  {
    "comment": "Loja muito boa, tem bastante produto de qualidade que posso comprar para meu pet, mas o atendimento é um pouco demorado",
    "rate": 4.5,
    "id": 2
  },
  {
    "comment": "site muito bom, recomendo demais",
    "rate": 4.8,
    "id": 3
  }
]
```

## Pets

POST - <strong>baseurl</strong>/pets

Nessa rota o usuário consegui registrar os dados do pet dele, com o nome do pet, o tipo do animal (cachorro,gato, roedor), idade,raça.

```
{
	"name": "Tom",
	"type": "gato",
	"age": 5,
	"breed": "Vira-lata",
	"userId": 2
}
```

<strong>!! IMPORTANTE</strong> é necessário a relação do id do usuário logado no objeto de registro do pet. "userId"

Resposta da API:

```
{
  "name": "Jerry",
  "type": "roedor",
  "age": 2,
  "breed": "hamster chines",
  "userId": 2,
  "id": 2
}
```

### Possiveis erros

No cadastro de um novo pet, deve-se relacionar o id do usuario no objeto, como no exemplo mostrado acima.

```
"Private resource creation: request body must have a reference to the owner id"
```

## User

GET - <strong>baseurl</strong>//users/2?\_embed=pets

Nessa requisição você precisa referenciar o id do usuário para fazer a consulta de todos os dados do usuário e dos seus pets registrados

Resposta da API:

```
{
  "email": "allankenzie@gmail.com",
  "password": "$2a$10$NDr9Tl4qs95l8AIgfpnAiuBLQmlQ15JbUS51jd4HdlEVHW.Ig2Tpm",
  "name": "Allan kenzie",
  "age": 22,
  "id": 3,
  "pets": [
    {
      "name": "timão",
      "type": "gato",
      "age": 2,
      "breed": "vira-lata",
      "userId": 3,
      "id": 3
    }
  ]
}
```

### Possiveis erros

Provavelmente no momento da requisição não referenciou o id do usuário logado

baseurl/users<strong>:ID</strong>?\_embed=pets

```
"Private resource access: entity must have a reference to the owner id"
```

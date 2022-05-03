# API REST - o verdadeiro início do backend

## API
É um conjunto de instruções que determina como se comunicar com a aplicação, em outras palavras: **é o servidor que temos criado nas aulas passadas**, quase todos os serevições WEB possuem API's

## Rest
> REST é um acrônimo para *'Representational State Transfer' (Transferencia de Estados Representacional)*

É um conjunto de restrições de aquitetura que podem ser usadas para a contrução de uma API


O rest organiza a forma de comunicação entre o cliente e o servidor, para que a requisição do cliente seja enviada de forma a qual o servidor compreenda a mesma de acordo com a forma de construção da API. 

## Organização de uma Rest API

### 1. Coleções de recursos
Os dados manipulados são os recursos e estes são organizados em coleções, **por exemplo**

Em um array de objetos, o array seria o recurso e o objeto seria o dado:

``` javascript
const array = [ // este array representa a coleção
    { id: 1, nome: "Maria" }, // cada um desses objetos é um recurso
    { id: 2, nome: "João" }, // cada um desses objetos é um recurso
    { id: 3, nome: "Luna" }, // cada um desses objetos é um recurso
]
```


##### este é um exemplo **ILUSTRATIVO**, não significa é a exata forma como uma API funciona

---

### 2. Identificador de recursos
cada recurso possui um identificador no qual cada um deste é **ÚNICO E IMUTÁVEL**

``` javascript
const array = [ 
    {
        RG: 1434564612, // NÃO PODEMOS ALTERAR O RG DE UMA PESSOA
        nome: "Maria", // O nome de uma pessoa pode ser alterado caso ela queira
        CEP: 29073571582 // uma pessoa pode alterar o CEP pois pode se mudar
    }
]
```

---

### 3. JSON - JavaScript no Backend
É uma notação em que utilizamos para representar os recursos


# JSON - JavaScript no Backend
> *JavaScript Object Notation - JSON* é uma forma de escrita baseada em objetos JS utilizada para transitar dados na WEB.

No curso iramos utilizar o JSON para criar nossas API's

O JSON é bastante semelhante ao objeto em JS, porém, uma das suas diferençãs é a de que devemos sempre declarar propriedades com **aspas duplas**
```json
{
    "rg": 1434564612,
    "nome": "Maria",
    "sobrenome": "Silva Santos",
    "endereco":{
        "rua": "Rua da paz",
        "numero": 743,
        "bairro": "Graça"
    }
}
```
##### o JSON **NÃO ACEITA** aspas simples

# Manipulação de Coleção de Recursos
Toda comunicação cliente servidor possui métodos que chamamos de verbos



## 1. GET

Este verbo é utilizado para fazer uma requisição ao servidor para listar os recursos contidos numa coleção - READ

exemplo: 
``` javascript
    app.get('/livros')
    app.get('/livros/3') // /livros/:id
```

## 2. POST
Este verbo é utilizado para cadastrar sempre um novo recurso à coleção - CREATE

``` javascript
    app.post('/livros')
    app.post('/livros/3')// /livros/:id
```


## 3. PUT
O put altera por completo um recurso numa coleção - UPDATE

``` javascript
    app.put('/livros')
    app.put('/livros/3')// /livros/:id
```

## 4. PATCH
É utilizado para alterar especificamente uma parte de um recurso

``` javascript
    app.patch('/livros')
    app.patch('/livros/3')// /livros/:id
```
## 5. DELETE
Como já esta descrito, este deleta o recurso de uma coleção - DELETE

``` javascript
    app.delete('/livros')
    app.delete('/livros/3')// /livros/:id
```

> Podemos utilizar o mesmo nome de rota para utilizar verbos diferentes sem causar conflitos à API


# Status code HTTP
Sabemos que para cada interação entre cliente e servidor temos uma *REQUISIÇÃO* e uma *RESPOSTA*

A cada resposta de requisição HTTP é atribuído um código para informar o *STATUS* da solicitação, podendo ser bem sucedido ou não.

estes códigos são compostos por 3 dígitos de números e, a cada centena, temos um tipo de resposta diferente.
## Principais famílias de códigos utilizados
200 - Código de sucesso
1. 200: `OK` -  Requisição bem sucedida
2. 201: `Created` - indica que algo foi criado de forma bem sucedida 
3. 204: `No Content` - requisição bem sucedida, porém sem conteúdo no corpo da resposta

400 - Erro do Cliente
1. 400: `Bad Request` - O servidor não entendeu a requisição por causa de  uma *sintaxe inválida*
2. 401: `Unauthorized` - O usuário não está autenticado
3. 403: `Forbidden` - O usuário não tem permissão para acessar este recurso
4. 404: `Not Found` - O servidor não pode encontrar o recurso solicitado

500 - Erro do Servidor
1. 500: `Internal Server Error` - O servidor encontrou uma situação em que não sabe lidar com o erro inesperado

> site que ajuda a entender status: https://httpstatusdogs.com/

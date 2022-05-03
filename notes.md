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
    {id: 1, nome: "Maria"}, // cada um desses objetos é um recurso
    {id: 2, nome: "João"}, // cada um desses objetos é um recurso
    {id: 3, nome: "Luna"}, // cada um desses objetos é um recurso
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

---

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
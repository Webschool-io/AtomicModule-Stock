# AtomicModule-Stock

  Módulo atômico para gerenciar as movimentações de produtos no estoque com Node.js

## Conceito

  Esse módulo deverá controlar as quantidades de produtos em estoque,
  esse módulo será chamado ao entrar(como num pedido de compras, por exemplo) ou sair(como na venda) algum produto do estoque para poder fazer então o devido ajuste no estoque.

## Funcionalidades

  - Adicionar quantidades de produtos no estoque (entrada)

  - Remover quantidades de produtos no estoque (baixa)

  - Busca da quantidade em estoque de um determinado produto

## Interface

  Aqui definimos a nomenclatura utilizada para cada funcionalidade, seus parâmetros e seu retorno:

### Adicionar quantidades de produtos no estoque (entrada)

      - nome: setInStock
      - parametros: {product}, qty
        - product: objeto do tipo produto
        - qty: quantidade (quantity), valor inteiro
      - retorno: Object
        - {   
                status: String
            ,   message: String
            ,   code: Number
            ,   idTransaction: Number
          }

### Remover quantidades de produtos no estoque (baixa)

      - nome: setOutStock
      - parametros: {product}, qty
        - product: objeto do tipo produto
        - qty: quantidade (quantity), valor inteiro
      - retorno: Object
          - {   
                  status: String
              ,   message: String
              ,   code: Number
              ,   idTransaction: Number
            }

### Busca da quantidade em estoque de um determinado produto
  - nome: getStock
  - parametros: {product}
    - product: objeto do tipo produto
  - retorno: Object
    - {   
            status: String
        ,   message: String
        ,   code: Number
        ,   idTransaction: Number
        ,   object: []
      }

## Tipos
Aqui definimos os tipos de objetos usados nesse módulo

### stockType

  - type: object
  - schema:
  - {
        product: {} //objeto productType
      , qtde: Number //int
      , qtdMinima: Number //int, default 10% da qtde
    }


**Aqui será adicionado futuramente o TYPE de produto que as funções irão receber**
### productType

  type: object
  schema:
  {}

## Todo retorno de função será um objeto
###Objeto de retorno para functions SET
  - {   
        status: String
      , message: String
      , code: Number
      , idTransaction: Number
    }

  - status: Status com mensagens padronizadas tipo: "success", "error" (ainda não definidas)
  - message: Mensagem de retorno
  - code:  códigos padrões à serem ainda definidos
  - idTransaction: id da tentativa


###Objeto de retorno para functions GET
  - {   
            status: String
        ,   message: String
        ,   code: Number
        ,   idTransaction: Number
        ,   object: []
    }

  - status: Status com mensagens padronizadas tipo: "success", "error" (ainda não definidas)
  - message: Mensagem de retorno
  - code:  códigos padrões à serem ainda definidos
  - idTransaction: id da tentativa
  - object é array contendo os valores solicitados na função

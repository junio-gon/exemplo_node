# EXEMPLO DE APLICAÇÃO COM NODE TS

**OBS:**
* Desenvolvi o ITENS como nova tabela para ficar mais fácil quando posteriormente for criada a entedidade associativa para relacionamento n/n;

* Não houve tempo hábil para implementação de testes automátizados;

* Para desenvolvimento do exemplo foi utilizado o banco SQLITE (./src/database/database.sqlite) devido a facilidade de se criar um banco na própria aplicação.

* Não usei SKU como chave primária para poder fazer o update inclusive do SKU; 

* Para o exemplo foi Utilizado ORM;

***executar as migrations:***
yarn typeorm migration:run

***rodar o programa:***
yarn dev

## CLIENTE

**insert**:
http://localhost:3333/clientes
*POST*:
>	{
>        "nome": "Junio Santos",
>        "email": "junio@junio.com",
>        "cpf": "333.333.333-33",
>	    "cep": "33.333-333",
>	    "frete": 50.00,
>	    "valor": "a"
>    }

**delete**:
*DELETE/PARAMS*
http://localhost:3333/clientes/4

**show all**:
*GET*
http://localhost:3333/clientes

**show 1**:
*GET/PARAMS*
http://localhost:3333/clientes/1

**update**
http://localhost:3333/clientes
*PUT*:
>	{
>        "id" : 1,    
>        "nome": "Paulo Paulada",
>        "email": "paulo@paulada.com",
>        "cpf": "111.111.111-11",
>	    "cep": "11.111-111",
>	    "frete": 150.00,
>	    "valor": 1000.00
>    }

## ITENS

**insert**:
http://localhost:3333/itens
*POST*:
>   {
>       "sku": "tv43-abc4",
>       "descricao": "tv 43",
>       "valor": 1500.00,
>       "quantidade": 1,
>       "cliente_id": 2
>   }

**delete**:
*delete/PARAMS*
http://localhost:3333/itens/2

**show all**:
*GET*
http://localhost:3333/itens

**show 1**:
*GET/PARAMS*
http://localhost:3333/itens/2

**update**
http://localhost:3333/itens
*PUT*
>   {
>       "id" : 1,
>       "sku": "tv43-abc4",
>       "descricao": "tv 43",
>       "valor": 1500.00,
>       "quantidade": 1,
>       "cliente_id": 2
>   }

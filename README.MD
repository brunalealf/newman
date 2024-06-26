# Test de API

Este é o projeto de Testes de API automatizado.

##  Requisitos
 * Postman - v11.0.5
 * Newman - v6.1.2
 * NodeJS - v21.7.3

## Como executar a aplicação 

Na raiz do projeto, através de seu Prompt de Commando/Terminal/Console execute o comando 

```bash
newman run '.\Test South.postman_collection.json'
```
## Reports
O report da execução do teste fica diretamente no retorno de execução do terminal.

## Casos de Testes
A cobertura dos testes foi definida conforme abaixo:
- Retorno do status code 201 para sucesso;
- Campos obrigatórios;
- URL inválida;
- Inserção de novos campos;
- Quebra de contrato - sem json informado;

## Criar um usuário

`https://reqres.in/api/users`

Este endpoint é responsável por inserir um novo usuário.

Existem os seguintes atributos a serem informados, com suas respectivas regras:

| Atributo | Obrigatório? | Regra |
|----------|--------------|-------|
| name| não | texto informando o nome da pessoa |
| job | não | texto informando o profissão da pessoa |


* Um usuário cadastrado com sucesso retorna o HTTP Status 201, os dados inseridos como retorno, o número do ID e a data da criação
* Um usuário cadastrado sem json informado retorna o HTTP Status 201 com o ID informado e a data de criação
* Um usuário cadastrado com a URL inválida retorna o HTTP Status 201, os dados inseridos como retorno, o número do ID e a data da criação

## Conclusão

Com base na API que foi desenvolvida os testes automatizados, podemos notar que é uma API que não possui regras definidas como:
* Não possui campos obrigatórios
* Permite adicionar qualquer atributo nos campos 
* Permite inclusão de novos campos
* Permite que os campos sejam strings ou números inteiros
* Mesmo não informando um json na requisição, o retorno do status code é 201
* Permite salvar um usuário com a URL inválida, no caso deveria retornar um status code 404 e esta retornando status code 201.



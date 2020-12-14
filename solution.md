# Solução do Trabalho Individual


[![pipeline status](https://gitlab.com/Vitor.Leal/Trabalho-Individual-2020-1/badges/master/pipeline.svg)](https://gitlab.com/Vitor.Leal/Trabalho-Individual-2020-1/-/commits/master)
[![Maintainability](https://api.codeclimate.com/v1/badges/5cba253b2451bbc9f28f/maintainability)](https://codeclimate.com/github/vitorl-s/Trabalho-Individual-2020-1/maintainability)

Aluno: Vitor Leal dos Santos

Matrícula: 16/0148375

## Conteinerização

A **divisão** do projeto consistiu-se em **3 containers (frontend, backend e database)**, listados no arquivo `docker-compose.yml` localizado na raiz do projeto, havendo somente um arquivo
.env na pasta `/docker` para a finalidade de configuração do database.

Os containers da api e database foram inseridos em uma network, para facilitar a comunicação entre os containers, através de variáveis de ambiente definidas no arquivo
`/docker/db_config.env`. Além disso, foi utilizado o volume db para armazenar o banco de dados.

### Executando o projeto

Para executar toda a stack do projeto devemos ter tanto o [Docker](https://docs.docker.com/engine/install/) como o [Docker-compose](https://docs.docker.com/compose/install/) 
instalados e configurados corretamente, e então na raiz do projeto executar:

```
docker-compose up
```

Após a finalização do comando, as aplicações estarão rodando nas seguintes urls:

- Frontend : `http://localhost:8080/`
- Backend : `http://localhost:3000/`

Para a execução de testes nos ambientes dockerizados acima devemos executar no frontend:
```
docker-compose run frontend yarn install && yarn run test:unit
```

Já no backend, devemos executar:
```
docker-compose run api bundle exec rails test
```


#  Teste-Fake-REST-API

---

## Objetivo
Garantir a integridade, estrutura e regras de negócio da API de listagem de atividades, validando que os dados retornados estejam corretos e consistentes.

---

## Ferramentas utilizadas
- Postman – Execução de testes de API
- JavaScript – Scripts de validação no Postman
- GitHub – Versionamento e organização do portfólio
- NodeJS
- Newman

---  
## API usada
[Fake REST API](https://fakerestapi.azurewebsites.net/index.html)

---

## Passo a Passo para uso no postman
1. Abrir Postman
2. Importar ambiente e coleção
3. Executar todos os requests
4. Conferir resultados nos testes

## Passo a Passo para uso no newman
1. Abrir Terminal
2. Executar o comando: newman run '.\Validação API.postman_collection .json' -e '.\Base URL.postman_environment.json' -r htmlextra --reporter-htmlextra-export report.html
3. Abrir o arquivo result.html no navegador

---

## Validações Implementadas
- Validação de Resposta
- Status code deve ser 200
- Tempo de resposta menor que 500ms
- Retorno deve ser um array não vazio

---

## Validação de Estrutura

Validação do objeto da resposta se o mesmo esta no formato de array, conforme estrutura abaixo:

```json
[
  {
    "id": 0,
    "title": "string",
    "dueDate": "2026-03-24T18:25:26.949Z",
    "completed": true
  }
]

```

---

## Tipos de dados

Valida

| Campo     | Tipo esperado |
|-----------|---------------|
| id        |    number     |
| title     |    string     |
| dueDate   |    string     |
| completed |    boolean    |

---

## Regras de negócio
- title não pode ficar vazio
- id precisa ser positivo
- dueDate tem que ser uma data válida
- completed deve ser boolean

## Testes realizados
- Validação do status code e tempo de resposta
- Validação da estrutura e tipos dos campos
- Validação das regras de negócio
 
---

Todos os testes foram executados no Postman e passaram com sucesso, garantindo que a API atende às expectativas do negócio.

![Resultado dos testes](result.png)

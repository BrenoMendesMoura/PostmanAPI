# 🛠️ Projeto de Teste de API - Postman

Este projeto contém testes automatizados para a API **X** utilizando **Postman** e **Newman**. O objetivo é validar os endpoints da API e garantir que funcionem conforme esperado.

## 📌 Tecnologias Utilizadas
- [Postman](https://www.postman.com/) - Plataforma para testes de API  
- [Newman](https://www.npmjs.com/package/newman) - Executor de testes do Postman via linha de comando  
- [JSON Schema Validation](https://json-schema.org/) - Para validação de respostas da API  

## 🚀 Como Executar os Testes
### 1️⃣ Clonar o repositório:

```sh
git clone https://github.com/BeatrizCamposPortifolio/PostmanAPI
cd PostmanAPI
```

2️⃣ Instalar o Newman (caso ainda não tenha):
```sh
npm install -g newman
```

3️⃣ Executar os testes:
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json
```

4️⃣ Gerar um relatório HTML dos testes (opcional):
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json -r html --reporter-html-export reports/relatorio.html
```


## 📂 Estrutura do Projeto

### 📁 projeto-teste-api

 ┣ 📂 collections       # Coleções de testes do Postman
 
 ┣ 📂 reports           # Relatórios gerados pelo Newman
 
 ┣ 📜 README.md         # Documentação do projeto

 
<hr>

# Documentação do Teste no Postman
### Fizemos 4 requisições, sem nenhuma falha. Utilizamos javascript no Collection Runnet, a ideia era automatizar o processo de teste de API

![image](https://github.com/user-attachments/assets/df62ac97-6a9d-413f-b3d5-e8cc00266961)


## Utilizamos os seguintes endpoints: GET, POST, PUT e Delete
![image](https://github.com/user-attachments/assets/a530c908-0e18-4d01-910e-5c1874b803d1)




### Descrevendo o que foi feito e mostrando cada execução

GET
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains user data", function () {
    pm.expect(pm.response.json().data).to.be.an('array');
});
```
![image](https://github.com/user-attachments/assets/dd0d2923-cf6c-4a01-94e9-26fb56c5a31f)

<hr>


POST
```javascript
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Response has ID", function () {
    pm.expect(pm.response.json()).to.have.property("id");
});
```
![image](https://github.com/user-attachments/assets/c23a4e0f-4c58-44c8-b5d7-f4794fb2014f)



PUT
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains updated job title", function () {
    pm.expect(pm.response.json().job).to.eql("QA Senior");
});
```
![image](https://github.com/user-attachments/assets/3964b87c-bb42-4901-a02e-18f9c353cd19)



DELETE
```javascript
exec: [
    pm.test("Status code is 204", function () {
        pm.response.to.have.status(204);
    });
]
```
![image](https://github.com/user-attachments/assets/97e3246d-2212-41d3-a0a2-3116f38924ac)


<hr>

## 📄 Licença
Este projeto é de código aberto e está disponível sob a licença MIT.

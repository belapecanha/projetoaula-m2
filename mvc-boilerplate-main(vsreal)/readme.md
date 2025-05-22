# Boilerplate MVC em Node.js com PostgreSQL

Este projeto é um boilerplate básico para uma aplicação Node.js seguindo o padrão MVC (Model-View-Controller), utilizando PostgreSQL como banco de dados.

## Requisitos

- Node.js (versão X.X.X)
- PostgreSQL (versão X.X.X)

## Instalação

1. **Clonar o repositório:**

```bash
   git clone https://github.com/seu-usuario/seu-projeto.git
   cd seu-projeto
```

2. **Instalar as dependências:**
    
```bash
npm install
```
    
3. **Configurar o arquivo `.env`:**
    
Renomeie o arquivo `.env.example` para `.env` e configure as variáveis de ambiente necessárias, como as configurações do banco de dados PostgreSQL.
    

Configuração do Banco de Dados
------------------------------

1. **Criar banco de dados:**
    
    Crie um banco de dados PostgreSQL com o nome especificado no seu arquivo `.env`.
    
2. **Executar o script SQL de inicialização:**
    
```bash
npm run init-db
```
    
Isso criará a tabela `users` no seu banco de dados PostgreSQL com UUID como chave primária e inserirá alguns registros de exemplo.
    

Funcionalidades
---------------

* **Padrão MVC:** Estrutura organizada em Model, View e Controller.
* **PostgreSQL:** Banco de dados relacional utilizado para persistência dos dados.
* **UUID:** Utilização de UUID como chave primária na tabela `users`.
* **Scripts com `nodemon`:** Utilização do `nodemon` para reiniciar automaticamente o servidor após alterações no código.
* **Testes:** Inclui estrutura básica para testes automatizados.

Scripts Disponíveis
-------------------

* `npm start`: Inicia o servidor Node.js.
* `npm run dev`: Inicia o servidor com `nodemon`, reiniciando automaticamente após alterações no código.
* `npm run test`: Executa os testes automatizados.
* `npm run test:coverage`: Executa os testes e gera um relatório de cobertura de código.

Estrutura de Diretórios
-----------------------

* **`config/`**: Configurações do banco de dados e outras configurações do projeto.
* **`controllers/`**: Controladores da aplicação (lógica de negócio).
* **`models/`**: Modelos da aplicação (definições de dados e interações com o banco de dados).
* **`routes/`**: Rotas da aplicação.
* **`tests/`**: Testes automatizados.
* **`views/`**: Views da aplicação (se aplicável).

Contribuição
------------

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

Licença
-------

Este projeto está licenciado sob a Licença MIT.

Este README.md fornece uma visão geral clara do boilerplate, incluindo instruções de instalação, configuração do banco de dados, funcionalidades principais, scripts disponíveis, estrutura de diretórios, como contribuir e informações de licença. Certifique-se de personalizar as seções com detalhes específicos do seu projeto conforme necessário.

# Respostas aula 6
1. Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto. Como o Model, o Controller e a View interagem entre si?
No projeto, a arquitetura MVC serve pra deixar tudo separado e organizado. O Model é responsável pelos dados, ele acessa o banco, faz as consultas, salva, edita e deleta. O Controller é como se fosse o intermediário: ele recebe as requisições, chama o Model quando precisa de dados e decide o que vai ser mostrado. A View é a parte visual, o que o usuário vê, geralmente feita com HTML e EJS, e ela recebe as informações que o Controller manda. Os três trabalham juntos assim: o usuário faz uma ação na View, isso chama uma função do Controller, que pega ou envia dados pro Model, e depois atualiza a View com o que for necessário. Um exemplo prático disso é o funcionamento do cadastro de alunos, primeiro o usuário vai ver onde adicionar outro aluno no view, logo depois ele pode apertar em um botão onde o controller receberá a informação e mandará para o model as alterações a serem feitas, model, por sua vez, irá editar no banco e o fluxo reguirá pela cadeia até que o novo usuário aparece na tela, novamente no view. 

2. Como ocorre o envio e o recebimento de dados no formato JSON neste projeto? Cite uma rota que responde em JSON e explique seu funcionamento.
O envio e recebimento de dados em JSON acontece quando usamos as rotas da API. Um exemplo de rota que responde em JSON é a GET /alunos, que busca e retorna todos os alunos. Quando essa rota é chamada, o Controller vai no banco de dados, pega os alunos daquele curso e devolve um array com os dados no formato JSON. 

3. Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador? Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js?
Usar HTML básico com formulários e tabelas é  útil principalmente em projetos Node.js que são mais simples ou são focados em CRUD. Os formulários servem pra enviar dados de forma fácil e direta, sem depender de frameworks pesados e as tabelas ajudam a organizar visualmente os dados pra quem está usando, como listar tarefas, usuários, entre outros, com tudo claro e bem dividido. Isso economiza tempo no desenvolvimento, facilita os testes e funciona bem com os templates do EJS, além de ser ótimo pra protótipos ou sistemas internos.
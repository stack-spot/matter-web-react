A stack **matter-web-react** provê templates e plugins para a inicialização e desenvolvimento de projetos React web. A mesma vem preparada para desenvolvimento de aplicações microfrontend utilizando module federation do Webpack. Para atingir o objetivo de provê inicialização rápida de projetos microfrontend a stack **matter-web-react** possui 2 templates principais: o **web-react-app-template** que cria uma aplicação React que pode ser utilizada sozinha ou acoplada a um ambiente microfrontend e o template **web-react-appshell-template** que cria uma aplicação React shell que pode renderizar outras aplicações geradas pelo pelo template **matter-web-react**.

### Visão Geral

O template **web-react-appshell-template** cria um projeto React pronto para desenvolvimento de aplicações microfrontend. O template utiliza o module federation do Webpack para servir como uma aplicação shell, deste modo o template **web-react-appshell-template** é ideal para se iniciar um projeto microfrontend que servirá como aplicação que engloba todas as outras aplicações nexte contexto.
o template é preparado para escrita e execução de testes unitários utilizando **Jest** com **testing-library**, possui configurado o eslint e o prettier para garantir a padronização de escrita de código entre os desenvolvedores e já possui a dependência do **react-router-dom** como sistema de rotas.

### Pré-requisitos

Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).

- Yarn ou NPM

### Inputs

Os inputs necessários para utilizar o template são:

| **Campo**    | **Valor**  | **Descrição**     |
| :----------- | :--------- | :---------------- |
| Project Name | ex.: MyApp | Nome da aplicação |

## Execução do projeto criado

Após criar o projeto, acesse o diretório **app** e execute um dos seguintes comandos:

```bash
    yarn
```

```bash
    npm install
```

Após instalar as dependências do projeto, execute um dos seguintes comandos para executar o projeto:

```bash
    yarn start
```

```bash
    npm start
```

Após executar o projeto, abra o browser em `http://localhost:8005`

Para realizar a execução dos testes unitários. Execute um dos seguintes comandos:

```bash
yarn test
```

```bash
npm run test
```

## Conectando um microfrontend

Com uma aplicação shell criada, é possível criar e conectar outras aplicações microfrontend na mesma. Para isso, crie uma aplicação React utilizando o template **web-react-app-template**(siga o caso de uso Criar aplicação React) e siga os seguintes passos:

- Na pasta do projeto shell acesse o arquivo `app/src/App.tsx`
- Remova a linha 38 do arquivo e descomente as linhas 26 - 36
- Atualize as propriedades `path` e `scope` onde `path` é a rota que irá renderizar microfrontend e o `scope` é o nome do microfrontend que deseja carregar ao navegar para essa rota. O nome da aplicação é o inputproject_name que foi preenchido para criar o microfrontend com o template **web-react-app-template**
- Atualize a url para apontar para o endereço e porta que o seu microfrontend está sendo exposto
- Execute ambos os projetos(shell e microfrontend)
- Acesse o projeto shell no browser e clique no link que navega para a rota(cadastrada em path) para ver a conexão de ambos os projetos em um ambiente microfrontend. O template shell base adiciona um link no menu lateral para cada microfrontend cadastrado no array de RemoteModule

O objeto **RemoteModule** que é utilizado para conectar e configurar o microfrontend no shell possui as seguintes propriedades:

```bash
remote = {
      id: Identificador unico para o módulo remoto
      name: nome a sua escolha do modulo remoto na sua aplicação shell
      url: local onde o seu módulo remoto está sendo exposto
      scope: nome da aplicação que está sendo exposta(você pode achar esse nome no arquivo webpack.config.js no plugin ModuleFederationPlugin)
      module: conteúdo sendo exposto(você pode achar esse nome no arquivo webpack.config.js in ModuleFederationPlugin )
      path: caminho na sua aplicação que irá renderizar o módulo remoto
      icon: caminho para o ícone dessa aplicação
    }
```

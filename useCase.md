A stack **matter-web-react** provê templates e plugins para a inicialização e desenvolvimento de projetos React web. A mesma vem preparada para desenvolvimento de aplicações microfrontend utilizando module federation do Webpack. Para atingir o objetivo de provê inicialização rápida de projetos microfrontend a stack **matter-web-react** possui 2 templates principais: o **web-react-app** que cria uma aplicação React que pode ser utilizada sozinha ou acoplada a um ambiente microfrontend e o template **web-react-appshell** que cria uma aplicação React shell que pode renderizar outras aplicações geradas pelo pelo template **matter-web-react**.

### Visão Geral

O template **web-react-app** cria um projeto React 17 pronto para desenvolvimento de aplicações web. O template é instalado com a biblioteca de estilização **styled-components** e é preparado para ser conectado a um shell microfrontend que utiliza module federation. Este projeto e pronto para escrita e execução de testes unitários por meio das bibliotecas Jest e Testing Library. Por fim o projeto possui configurado o eslint e o prettier para garantir a padronização de escrita de código entre os desenvolvedores.

### Pré-requisitos

Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).

- Yarn ou NPM

### Inputs

Os inputs necessários para utilizar o template são:

| **Campo**    | **Valor**     | **Descrição**              |
| :----------- | :------------ | :------------------------- |
| Project Name | ex.: MyApp    | Nome da aplicação          |
| Add Routing  | true ou false | Adicionar react-router-dom |

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

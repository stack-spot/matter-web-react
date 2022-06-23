A Stack **matter-web-react** provê Templates e Plugins para a inicialização e desenvolvimento de projetos React web. A mesma vem preparada para desenvolvimento de aplicações microfrontend utilizando module federation do Webpack. Para atingir o objetivo de prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** oferece dois Templates principais: 

- O **web-react-app** cria uma aplicação React que pode ser utilizada sozinha ou acoplada a um ambiente microfrontend.
- O **web-react-appshell** cria uma aplicação React shell que pode renderizar outras aplicações geradas pelo Template **matter-web-react**.

### Visão Geral

O Template **web-react-app** cria um projeto React 17 pronto para desenvolvimento de aplicações web. O Template é instalado com a biblioteca de estilização **styled-components** e é preparado para ser conectado a um shell microfrontend que utiliza module federation. Este projeto é pronto para escrita e execução de testes unitários por meio das bibliotecas **Jest** e **Testing Library**. Por fim o projeto possui o **eslint** e o **prettier** configurados para garantir a padronização de escrita de código entre os desenvolvedores.

### Pré-requisitos

Para utilizar esse Template você precisa utilizar o `STK CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).

- Yarn ou NPM

### Inputs

Os inputs necessários para utilizar o Template são:

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

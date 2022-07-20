A Stack **matter-web-react** provê Templates e Plugins para a inicialização e o desenvolvimento de projetos **React Web**. 

A Stack vem preparada para o desenvolvimento de aplicações **`microfrontend`**, utilizando o **`module federation`** do **Webpack**. 

Para atingir o objetivo de prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** disponibiliza dois Templates principais:

1. O **web-react-app**, que cria uma aplicação **React** para ser utilizada sozinha ou conectada a um ambiente microfrontend;

2. O template **web-react-appshell**, que cria uma aplicação **React shell** que pode renderizar outras aplicações geradas pelo template **matter-web-react**.  

### **Visão Geral**

O template **web-react-app** cria um projeto **React 17** pronto para o desenvolvimento de aplicações web. O template é instalado com a biblioteca de estilização **styled-components** e é preparado para ser conectado a um **`shell microfrontend`** que utiliza **`module federation`**. 

Este projeto é preparado para a escrita e execução de testes unitários por meio das bibliotecas **Jest** e **Testing Library**. O projeto também tem o **`eslint`** e o **`prettier`** já configurados para garantir a padronização de escrita de código entre os desenvolvedores.

### Pré-requisitos
Para utilizar este Template, é preciso ter instalado na sua máquina os itens abaixo:  

- Ter o [**STK CLI**](https://stackspot.com.br/) baixado;  
- Yarn ou NPM

### Inputs

Os inputs necessários para utilizar o template são:

| **Campo**    | **Valor**     | **Descrição**              |
| :----------- | :------------ | :------------------------- |
| Project Name | ex.: MyApp    | Nome da aplicação          |
| Add Routing  | true ou false | Adicionar react-router-dom |

## Execução do projeto criado

1. Depois de criar o projeto, acesse o diretório **app** e execute um dos comandos abaixo:  

```bash
    yarn
```

```bash
    npm install
```

2. Após instalar as dependências do projeto, execute um dos comandos para executar o projeto:  

```bash
    yarn start
```

```bash
    npm start
```

3. Depois de executar o projeto, abra o browser em `http://localhost:8005`

4. Para realizar a execução dos testes unitários, execute um dos comandos abaixo:  

```bash
yarn test
```

```bash
npm run test
```

A Stack **`matter-web-react`** provê Templates e Plugins para a inicialização e o desenvolvimento de projetos **React Web**. 

A Stack já vem preparada para o desenvolvimento de aplicações **`microfrontend`**, utilizando o **`module federation`** do **Webpack**. 

Para atingir o objetivo de prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** disponibiliza dois Templates principais:

1. O **web-react-app**, que cria uma aplicação **React** para ser utilizada sozinha ou conectada a um ambiente microfrontend;

2. O template **web-react-appshell**, que cria uma aplicação **React shell** que pode renderizar outras aplicações geradas pelo template **matter-web-react**.

### **Visão Geral**  

O Template **web-react-appshell** cria um projeto React para o desenvolvimento de aplicações microfrontend.  

O **web-react-appshell** utiliza o `module federation` do **Webpack** para servir como uma aplicação `shell`. Assim, o Template **web-react-appshell** se torna ideal para começar um projeto microfrontend que servirá como aplicação que engloba todas as outras aplicações neste contexto.

Além disso, o Template é preparado para a escrita e execução de testes unitários utilizando **Jest** com **testing-library**. 

Ele também tem configurado o `eslint` e o `prettier` para garantir a padronização de escrita de código entre os desenvolvedores e já possui a dependência do **react-router-dom** como sistema de rotas.

### **Pré-requisitos**  
Para utilizar este Template, é preciso ter instalado na sua máquina os itens abaixo:  

- Ter o [**STK CLI**](https://stackspot.com.br/) baixado;  
- Yarn ou NPM

### Inputs

O input necessário para utilizar o Template é:

| **Campo**    | **Valor**  | **Descrição**     |
| :----------- | :--------- | :---------------- |
| Project Name | ex.: MyApp | Nome da aplicação |

## Execução do projeto criado

1. Depois de criar o projeto, acesse o diretório **app** e execute um dos comandos abaixo:  

```bash
    yarn
```

```bash
    npm install
```

2. Após instalar as dependências do projeto, execute um dos seguintes comandos para executar o projeto:

```bash
    yarn start
```

```bash
    npm start
```

3. Depois de executar o projeto, abra o browser em `http://localhost:8005`

4. Para executar os testes unitários, execute um dos seguintes comandos:  

```bash
yarn test
```

```bash
npm run test
```

## Conectando um microfrontend

Com uma aplicação `shell` criada, é possível criar e conectar outras aplicações microfrontend dela. 

Para isso, crie uma aplicação React utilizando o template **web-react-app**(veja o caso de uso **Criar aplicação React**) e siga os passos abaixo:

1. Na pasta do projeto shell acesse o arquivo `app/src/App.tsx`;
2. Remova a linha 38 do arquivo e descomente as linhas **26 - 36**;  
3. Atualize as propriedades `path` e `scope` onde `path` é a rota que irá renderizar microfrontend e o `scope` é o nome do microfrontend que deseja carregar ao navegar para essa rota. O nome da aplicação é o `inputproject_name` que foi preenchido para criar o microfrontend com o template **web-react-app**;  
4. Atualize a URL para apontar para o endereço e porta que o seu microfrontend está sendo exposto;  
5. Execute ambos os projetos(shell e microfrontend)
6. Acesse o projeto shell no browser e clique no link que navega para a rota (cadastrada em path) para ver a conexão de ambos os projetos em um ambiente microfrontend. O template shell base adicionará um link no menu lateral para cada microfrontend cadastrado no array de **`RemoteModule`**.

O objeto **RemoteModule** que é utilizado para conectar e configurar o microfrontend no shell possui as propriedades abaixo:  

```bash
remote = {
      id: Identificador único para o módulo remoto
      name: nome a sua escolha do módulo remoto na sua aplicação shell
      url: local onde o seu módulo remoto está sendo exposto
      scope: nome da aplicação que está sendo exposta(você pode achar esse nome no arquivo webpack.config.js no plugin ModuleFederationPlugin)
      module: conteúdo sendo exposto(você pode achar esse nome no arquivo webpack.config.js in ModuleFederationPlugin )
      path: caminho na sua aplicação que irá renderizar o módulo remoto
      icon: caminho para o ícone dessa aplicação
    }
```

A Stack **matter-web-react** provê Templates e Plugins para a inicialização e desenvolvimento de projetos React web. A mesma vem preparada para desenvolvimento de aplicações microfrontend utilizando module federation do Webpack. Para atingir o objetivo de prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** oferece dois Templates principais: 

- O **web-react-app** cria uma aplicação React que pode ser utilizada sozinha ou acoplada a um ambiente microfrontend. 
- O **web-react-appshell** cria uma aplicação React shell que pode renderizar outras aplicações geradas pelo Template **matter-web-react**.

### Visão Geral

O Template **web-react-appshell** cria um projeto React pronto para desenvolvimento de aplicações microfrontend. O Template utiliza o module federation do Webpack para servir como uma aplicação shell, deste modo o Template **web-react-appshell** é ideal para se iniciar um projeto microfrontend que servirá como aplicação que engloba todas as outras aplicações nexte contexto.

O Template é preparado para escrita e execução de testes unitários utilizando **Jest** com **testing-library**, possui o **eslint** e o **prettier** configurados para garantir a padronização de escrita de código entre os desenvolvedores e já possui a dependência do **react-router-dom** como sistema de rotas.

### Pré-requisitos

Para utilizar esse Template você precisa utilizar o `STK CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).

- Yarn ou NPM

### Inputs

Os inputs necessários para utilizar o Template são:

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

Com uma aplicação shell criada, é possível criar e conectar outras aplicações microfrontend na mesma. Para isso, crie uma aplicação React utilizando o Template **web-react-app** (siga o caso de uso **Criar aplicação React**) e siga os seguintes passos:

- Na pasta do projeto shell acesse o arquivo `app/src/App.tsx`
- Remova a linha 38 do arquivo e descomente as linhas 26 - 36
- Atualize as propriedades `path` e `scope` onde `path` é a rota que irá renderizar microfrontend, e o `scope` é o nome do microfrontend que deseja carregar ao navegar para essa rota. O nome da aplicação é o `inputproject_name` que foi preenchido para criar o microfrontend com o Template **web-react-app**
- Atualize a URL para apontar para o endereço e porta que o seu microfrontend está sendo exposto
- Execute ambos os projetos (shell e microfrontend).
- Acesse o projeto shell no browser e clique no link que navega para a rota (cadastrada em path) para ver a conexão de ambos os projetos em um ambiente microfrontend. O Template shell base adiciona um link no menu lateral para cada microfrontend cadastrado no array de RemoteModule

O objeto **`RemoteModule`** utilizado para conectar e configurar o microfrontend no shell possui as seguintes propriedades:

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

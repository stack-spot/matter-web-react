Para criar uma aplicação React, junto com a infraestrutura necessária para se fazer o deploy dela, a Stack **`matter-web-react`** disponibilzia o Plugin **`deploy-aws`**. 

Este Plugin cria uma pasta infra no projeto com uma aplicação **CDK** que, ao ser executada, cria os recursos necessários na **AWS** para fazer o deploy de uma aplicação React. 

O Plugin **`deploy-aws`** também cria uma pasta **`.github`**, com arquivos **GitHub Actions** para fazer o `build` e o `deploy` da aplicação na AWS.

### **Pré-requisitos**  
Para utilizar este Template, é preciso ter instalado na sua máquina os itens abaixo:  

- Ter o [**STK CLI**](https://stackspot.com.br/) baixado;  
- [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable) ou [npm](https://nodejs.org/en/)
- Uma conta **AWS**;
- O **Secrets** da AWS nas [variáveis de ambiente](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html#envvars-set);  
- Um **GitHub Identity Provider** na sua conta AWS; **role IAM** com acesso ao S3 e uma **`trust relationship`** com o **Identity Provider**. [Confira um exemplo aqui](https://github.com/aws-actions/configure-aws-credentials#sample-iam-role-cloudformation-template)
- **`arn`** da role IAM configurada como **`secret`* no GitHub do projeto com o nome **`PIPELINE_RELEASE_ROLE`**. 

### **Execução do projeto criado**  

1. Depois de criar o projeto com o **`stackfile`**, acesse o diretório **app** e execute um dos comandos abaixo:  

```bash
    yarn
```

```bash
    npm install
```

2. Após instalar as dependências do projeto, execute um dos comandos abaixo para executar o projeto:  

```bash
    yarn start
```

```bash
    npm start
```

3. Depois de executar o projeto, abra o browser em `http://localhost:8005`

Para executar os testes unitários, execute um dos comandos abaixo:  

```bash
yarn test
```

```bash
npm run test
```

### **Criação da infraestrutura na AWS**  

1. Após criar o projeto, crie um diretório chamado **stages** no mesmo nível dos diretórios **app** e **infra**.
2. Ainda neste diretório, crie um arquivo com o nome no padrão **`<stage_name>.json`**. É recomendado criar com o mesmo nome do ambiente e conta AWS em que o recurso e o deploy da aplicação serão criados. Exemplos: `qa`, `staging`, `production`, etc. Neste mesmo arquivo preencha com as seguintes informações:  

```bash
  {
  "cloud": {
      "account": {
          "id": "<aws_account_id>",
          "region": "<aws-region>"
      }
    }
  }
```

> Você pode criar vários arquivos para criar a infra em diferentes ambientes.

3. Com o arquivo de `stages` criado, dentro do diretório do projeto crie os recursos na sua conta AWS com o seguinte comando:

```bash
stk deploy <stage_name>
```

4. Faça o `commit` e dê o `push` do seu código para o GitHub. 

5. Depois de fazer o `merge` de suas alterações, gere uma release no GitHub com o formato **`<stage_name>-v0.0.0`**.

A Action de release será executada no GitHub e se não houver erros com testes, build ou de qualidade no código, o deploy será feito no ambiente criado.

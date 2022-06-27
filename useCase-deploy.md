Caso deseje criar uma aplicação React juntamente da infra necessária para se fazer o deploy da mesma, use o Plugin **deploy-aws** fornecido na Stack **matter-web-react**. Esse Plugin cria uma pasta infra no projeto com uma Aplicação CDK que, ao ser executada, cria os recursos necessários na AWS para fazer o deploy de uma aplicação React. O Plugin também cria uma pasta .github com arquivos github actions para fazer o build e o deploy da Aplicação na AWS.

### Pré-requisitos

Para utilizar esse Template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).

- [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable) ou [npm](https://nodejs.org/en/)
- Uma conta AWS
- Secrets da AWS nas [variáveis de ambiente](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html#envvars-set)
- Um github Identity Provider na sua conta AWS e uma role IAM com acesso ao S3 e uma trust relationship com o Identity provider.([Exemplo](https://github.com/aws-actions/configure-aws-credentials#sample-iam-role-cloudformation-template))
- arn da role IAM configurada como secret no github to projeto com o noome `PIPELINE_RELEASE_ROLE`

## Execução do projeto criado

Após criar o projeto com o Stackfile, acesse o diretório **app** e execute um dos seguintes comandos:

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

## Criação da infra na AWS

Após criar o projeto, crie um diretório chamado **stages** no mesmo nível dos diretórios **app** e **infra**, neste diretório crie um arquivo com o nome no padrão `<stage_name>.json`(recomendado com o nome do ambiente e conta aws que será feita a criação do recurso e o deploy da Aplicação. Exemplos: qa, staging, production, etc).
Neste arquivo preencha com as seguintes informações:

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

**NOTA:** Você pode criar vários arquivos para criar a infra em diferentes ambientes.

Com o arquivo de stages criado, no diretório do projeto, crie os recursos na sua conta AWS com o seguinte comando:

```bash
stk deploy <stage_name>
```

Faça o commit e dê o push do seu código para o github. Após fazer o merge de suas alterações, gere uma release no github com o formato `<stage_name>-v0.0.0`.
A action de release será executada no github e se não houver erros com testes, build ou de qualidade no código o deploy será feito no ambiente criado.

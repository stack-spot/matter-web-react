A Stack **matter-web-react** provê Templates e Plugins para a inicialização e o desenvolvimento de projetos **React Web**. 

A Stack vem preparada para o desenvolvimento de aplicações **`microfrontend`**, utilizando o **`module federation`** do **Webpack**. 

Para atingir o objetivo de prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** disponibiliza dois Templates principais:

1. O **web-react-app**, que cria uma aplicação **React** para ser utilizada sozinha ou conectada a um ambiente microfrontend;

2. O template **web-react-appshell**, que cria uma aplicação **React shell** que pode renderizar outras aplicações geradas pelo template **matter-web-react**.  

Ambos Templates **web-react-app** e **web-react-appshell** são aplicações React com a biblioteca de componentes **styled-components** e com o sistema de **`routing react-router-dom`**. 

Os dois Templates já vêm preparados para executar testes unitários utilizando a biblioteca de testes **testing-library**. Além disso, eles possuem o **`eslint`** e o **`prettier`** já configurados para garantir o padrão de escrita de código entre os desenvolvedores.

A Stack **matter-web-react** possui dois Plugins que podem ser aplicados a ambos os Templates citados anteriormente:

1. O Plugin **`beagle`** adiciona ao projeto a dependência e o `boilerplate` necessário da biblioteca para **Server Driven UI** [Beagle](https://usebeagle.io);  

2. Já o Plugin **`deploy-aws`** adiciona ao projeto a capacidade de criar recursos **AWS** e **Github Actions** para implatanção nestes recursos.

A Stack **matter-web-react** provê Templates e Plugins para a inicialização e desenvolvimento de projetos React Web. A mesma vem preparada para desenvolvimento de aplicações microfrontend utilizando module federation do Webpack. Para prover a inicialização rápida de projetos microfrontend, a Stack **matter-web-react** oferece dois Templates principais: 

- O **web-react-app** cria uma aplicação React para ser utilizada sozinha, ou conectada a um ambiente microfrontend.
- O **web-react-appshell** cria uma aplicação React shell que pode renderizar outras aplicações geradas pelo Template **matter-web-react**.

Os Templates **web-react-app** e **web-react-appshell** são aplicações React com a biblioteca de componentes **styled-components** e com o sistema de routing react-router-dom. Ambas já vêm preparadas para execução de testes unitários utilizando a biblioteca de testes **testing-library**. Ambas possuem o **eslint** e o **prettier** configurados para garantir o padrão de escrita de código entre os desenvolvedores.

A Stack possui dois Plugins que podem ser aplicados a ambos os Templates citados anteriormente. O Plugin **beagle** adiciona ao projeto a dependência e o boilerplate necessários da biblioteca para server driven UI [Beagle](https://usebeagle.io). Já o Plugin **deploy-aws** adiciona ao projeto a capacidade de criação de recursos AWS e Github actions para implatanção nesses recursos.

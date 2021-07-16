# my-electron-app

Scaffold the project
Aplicativos Electron seguem a mesma estrutura geral que outros projetos Node.js. Comece criando uma pasta e inicializando um pacote npm.

mkdir my-electron-app && cd my-electron-app
npm init
Copiar
O comando interativo init solicitará que você defina alguns campos em sua configuração. Existem algumas regras a seguir para os propósitos deste tutorial:

entry point deve ser main.js.
author e description podem ser de qualquer valor, mas são necessários para o pacote do aplicativos.
Seu arquivo package.json deve ser parecido com isto:

{
  "name": "my-electron-app",
  "version": "1.0.0",
  "description": "Hello World!",
  "main": "main.js",
  "author": "Jane Doe",
  "license": "MIT"
}
Copiar
Em seguida, instale o pacote electron nas devDependencies do seu aplicativo.

$ npm install --save-dev electron
Copiar
Nota: Se você estiver encontrando algum problema com a instalação do Electron, por favor consulte o guia de Instalação avançada.

Finalmente, você deve ser capaz de executar o Electron. No campo scripts de sua package.json config, adicione um comando start assim:

{
  "scripts": {
    "start": "electron ."
  }
}
Copiar
Este comando start permitirá que você abra seu aplicativo em modo de desenvolvimento.

npm start
Copiar
Nota: Este script diz ao Electron para ser executado na pasta raiz do seu projeto. Neste estágio, o seu aplicativo lançará imediatamente um erro informando que ele não consegue encontrar um aplicativo para executar.

Execute o processo principal
O ponto de entrada de qualquer aplicação Electron é o script main. Este script controla o processo principal, que é executado em um ambiente Node.js completo e é responsável por controlar o ciclo de vida de seu aplicativo, exibindo interfaces nativas, realizando todas as operações necessárias e gerenciando os processos de renderização (mais sobre isso mais tarde).

During execution, Electron will look for this script in the main field of the app's package.json config, which you should have configured during the app scaffolding step.

Para inicializar o script main, crie um arquivo vazio com o nome main.js na pasta raíz do seu projeto.

Nota: Se você executar o script start novamente neste ponto, sua aplicação não irá lançar qualquer erro! Entretanto, ela não fará nada, visto que não adicionamos nenhum código no arquivo main.js.

Crie uma página web
Antes de criarmos uma janela para a nossa aplicação, precisamos criar o conteúdo que será carregado dentro dela. No Electron, cada janela exibe um conteúdo web, que pode ser carregado de um arquivo HTML local ou de um URL remoto.

Para este tutorial, você fará a página html primeiro. Crie um arquivo index.html na pasta raíz do seu projeto:

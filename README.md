Dicas de como configurar um workspace do Cloud9 para desenvolvimento Java com o Maven e o GitHub para as aulas de Tarcisio Rocha (Prof. do DCOMP/UFS)

# Criação de uma conta no GitHub

* Usando o seu email "@dcomp.ufs.br", crie uma conta gratuita em https://github.com/  

# Convite do Prof. Tarcisio para participar de time no Cloud9

* Certifique-se de que você recebeu um convite pelo seu email "@dcomp.ufs.br" para integrar o time no Cloud9 chamado "DCOMP/UFS - Prof. Tarcisio Rocha". Aceite o convite do e-mail e crie a sua nova conta no Cloud9 a partir deste convite escolhendo o perfil "Student/Coursework" durante o processo e use um nome de usuário que inclua o seu nome e sobrenome.

* Caso não tenha recebido o convite, solicite ao prof. Tarcisio

# Criar workspace Cloud9 no time  

* Na sua conta do Cloud9 (https://c9.io/), vá à seção "Your team subscriptions" e clique clique no nome do time "DCOMP/UFS - Prof. Tarcisio Rocha" listado.

* Crie um novo workspace dentro do contexto do time selecionado. Para tanto, clique no símbolo "+" no menu superior da tela.  Dê um nome ao workspace (ex: "sd-dcomp-ufs"). Escolha o time "DCOMP/UFS - Prof. Tarcisio Rocha". Marque o workspace como "Private". Escolha o template "Blank". Clique "Create workspace". Aguarde a criação e o carregamento do seu workspace.

# Configurando o workspace para desenvolvimento Java

* No terminal Linux do workspace execute os dois comandos:

    sudo apt-get update
    
    sudo apt-get install default-jdk

O primeiro dispara uma atualização da base de pacotes do Linux e o segundo instala o Java Development Kit default.

* Teste para ver se o compilador java foi instalado com o comando:

    javac -version
  
  Esse comando deve exibir a versão do compilador.
  
# Configurando o Maven no workspace  

* No terminal linux execute os seguintes comandos:

  # Atualizar base de pacotes
    sudo apt-get update
  # Remover versão 2 do Maven
    sudo apt-get remove maven2
  # Instalar nova versão do Maven
    sudo apt-get install maven
  # Criar a variável MAVEN_OPTS
    export MAVEN_OPTS="-Xmx256m"

  









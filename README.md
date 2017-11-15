Dicas de como configurar um workspace do Cloud9 para desenvolvimento Java com o Maven e o GitHub para as aulas no DCOMP/UFS do Prof. Tarcisio Rocha.

# 1. Criação de uma conta no GitHub

* Usando o seu email "@dcomp.ufs.br", crie uma conta gratuita em https://github.com/  

# 2. Convite do Prof. Tarcisio para participar de time no Cloud9

* Certifique-se de que você recebeu um convite pelo seu email "@dcomp.ufs.br" para integrar o time no Cloud9 chamado "DCOMP/UFS - Prof. Tarcisio Rocha". Aceite o convite do e-mail e crie a sua nova conta no Cloud9 a partir deste convite escolhendo o perfil "Student/Coursework". Durante o processo e use um nome de usuário que inclua o seu nome e sobrenome para facilitar a identificação futura. (Caso não tenha recebido o convite, solicite ao professor.)

# 3. Criar workspace Cloud9 no time  

* Na sua conta do Cloud9 (https://c9.io/), vá à seção "Your team subscriptions" e selecione o nome do time "DCOMP/UFS - Prof. Tarcisio Rocha" listado.

* Crie um novo workspace dentro do contexto do time selecionado. Para tanto, clique no símbolo "+" no menu superior da tela.  Dê um nome ao workspace (ex: "sd-dcomp-ufs"). Escolha o time "DCOMP/UFS - Prof. Tarcisio Rocha". Marque o workspace como "Private". Escolha o template "Blank". Clique "Create workspace". Aguarde a criação e o carregamento do seu workspace.

# 4. Configurando o workspace para desenvolvimento Java

* No terminal Linux do workspace execute os dois comandos:

    	sudo apt-get update
       	sudo apt-get install default-jdk

O primeiro dispara uma atualização da base de pacotes do Linux e o segundo instala o Java Development Kit default.

* Teste para ver se o compilador java foi instalado com o comando:

    	javac -version
  
  Esse comando deve exibir a versão do compilador.
  
# 5. Configurando o Maven no workspace  

* No terminal linux execute os seguintes comandos:

  # Atualizar base de pacotes
    	sudo apt-get update
  # Remover versão 2 do Maven
    	sudo apt-get remove maven2
  # Instalar nova versão do Maven
    	sudo apt-get install maven
  # Criar a variável MAVEN_OPTS
    	export MAVEN_OPTS="-Xmx256m"

# 6. Criação do Diretório de Projetos da Disciplina no Cloud9

* Dentro do diretório "/home/ubuntu/workspace", crie um novo diretório para os projetos da disciplina. É nesse diretório que ficarão os projetos/exemplos trabalhados durante a disciplina. Exemplo:
 
   	cd /home/ubuntu/workspace
   	mkdir sistemas-distribuidos
    
Com os passos anteriores, temos o workspace do Cloud9 já configurado para o desesenvolvimento Java + Maven. Não será necessário instalar o git, pois ele já vem instalado por default no Cloud9. 

Os próximos passos dizem respeito a um teste básico de uso desse ambiente configurado, envolvendo a criação de um novo projeto Java/Maven no Cloud9 com integração com um novo repositório correspondente no GitHub.  

# 7. 

# Link ExemploTCP

https://classroom.github.com/a/N0HarabO








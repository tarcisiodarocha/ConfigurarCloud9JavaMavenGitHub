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

* No diretório "/home/ubuntu/workspace", crie um novo diretório para os projetos da disciplina. É nesse diretório que ficarão os projetos/exemplos trabalhados durante a disciplina. Exemplo:
 
        cd /home/ubuntu/workspace
        mkdir sistemas-distribuidos
    
Com os passos anteriores, temos o workspace do Cloud9 já configurado para o desesenvolvimento Java + Maven. Não será necessário instalar o git, pois ele já vem instalado por default no Cloud9. 

Os próximos passos dizem respeito a um teste básico de uso desse ambiente configurado, envolvendo a criação de um novo projeto Java/Maven no Cloud9 com integração com um novo repositório correspondente no GitHub.  

# 7. Criação de um Novo Projeto Maven no Cloud9

* Entre no diretório de projetos da disciplina. Exemplo:

        cd /home/ubuntu/workspace/sistemas-distribuídos

* A partir desse diretorio, crie um novo projeto Maven usando o seguinte comando (Na prática o parâmetro -DgroupId indicará o pacote Java que o Maven criará inicialmente para o projeto, nesse caso o pacote será "br.ufs.dcomp.MeuProjetoTeste". O parâmetro -DartifactId indica o nome do projeto, no caso "MeuProjetoTeste"):

        mvn -B archetype:generate \
                -DarchetypeGroupId=org.apache.maven.archetypes \
                -DgroupId=br.ufs.dcomp.MeuProjeto \
                -DartifactId=MeuProjetoTeste

Observe que depois da execução desse comando, o Maven cria uma pasta para o projeto chamada MeuProjetoTeste que contém a segunte estrutura interna:

        MeuProjetoTeste
        |-- pom.xml
        `-- src
            |-- main
            |   `-- java
            |       `-- br
            |           `-- ufs
            |               `-- dcomp
            |                   `-- MeuProjeto
            |                       `-- App.java
            `-- test
                `-- java
                    `-- br
                        `-- ufs
                            `-- dcomp
                                `-- MeuProjeto
                                    `-- AppTest.java

O arquivo "pom.xml" gerado possui as informações acerca do projeto necessárias ao Maven incluindo a lista de dependências do mesmo. A pasta "src/main/java" possui a estrutura de diretórios do pacote Java criado (br.ufs.dcomp.MeuProjeto). O arquivo "App.java" consiste em uma aplicação "Hello world" criada pelo Maven que pode ser usada como ponto de partida para o desenvolvimento do projeto. O diretório "src/test/java" possui a aplicação de testes de unidade gerada pelo Maven.

# 8. Renomeação Temporária do Diretório do Projeto

* Para que não hava confilto de diretórios nas próximas etapas, renomeie o diretório do projeto de "MeuProjetoTeste" para "MeuProjetoTesteTemp" com o segunte comando:

        mv MeuProjetoTeste/ MeuProjetoTesteTemp

# 9. Criação de um Novo Repositório para o "MeuProjetoTeste" no GitHub

* Na sua conta do GitHub, crie um novo repositório chamado "MeuProjetoTeste" (em "Your profile" >> "Repositories"). Marque-o como "Private", escolha a opção "Initialize this repository with a README" e crie o repositório. 

* Depois de criado copie o link de clonagem do mesmo (selecione o botão "Clone" e copie o link https). Ex: https://github.com/tarcisiodarocha/MeuProjetoTeste.git

# 10. Clonagem do Repositório GitHub no Cloud9

* A partir do diretório de projetos da disciplina no Cloud9 (ex: "/home/ubuntu/workspace/sistemas-distribuidos/"), clone o repositório do projeto usando como parâmetro o link copiado na etapa anterior: 
        
        git clone <link-do-repositorio-no-github>

Exemplo: git clone https://github.com/tarcisiodarocha/MeuProjetoTeste.git

Como parte do processo de clonagem, será criada um diretório com o nome do repositório ("MeuProjetoTeste") com um arquivo texto "README.md". 

# 11. Mover Conteúdo do Diretório "MeuProjetoTesteTemp" (gerado pelo Maven) para o Diretório "MeuProjetoTeste" 

*  A partir do diretório de projetos da disciplina (ex: "/home/ubuntu/workspace/sistemas-distribuidos/") execute o seguinte comando:

        mv MeuProjetoTesteTemp/* MeuProjetoTeste/
        
* Depois disso, remova o diretório "MeuProjetoTesteTemp" que agora estará vazio.       

        rmdir MeuProjetoTesteTemp
        
Realizadas essas etapas, teremos o projeto Maven gerado já integrado com o repositório que foi clonado do GitHub. Nas próximas etapas serção descritos o processo de compilação do projeto Maven local e a submissão (push) do mesmo para o repositório remoto no GitHub.

# 12. Compilação do Projeto com o Maven

* Entre no diretório do projeto. Exemplo:

        cd /home/ubuntu/workspace/sistemas-distribuidos/MeuProjetoTeste

* A partir daí, compile o projeto com o Maven

        mvn compile
        
Como resultado do processo de compilação, teremos o diretório "target/classes" que conterá a estrutura de diretórios do pacote com os ".class" do projeto.

# 13. Execução do App de "Hello world" do Projeto

* A partir do diretório do projeto, execute o App com o seguinte comando:

        java -cp target/classes br.ufs.dcomp.MeuProjeto.App
        
Deve ser exibida a mensagem "Hello Word!"

# 14. Commit e Push da Primeira Versão do Projeto

* A partir do diretório do projeto, execute o App com os seguintes comandos:

   # Adicionar os novos arquivos/diretórios inseridos anteriormente no projeto git
        
        git add .
        
   # Realizar o primeiro commit do projeto no repositório local
   
        git commit -m "meu primeiro commit no repositório"
        
   # Realizar o push do repositório local para o repositório remoto do GitHub
   
        git push
        
Nesse último comando deve ser fornecido o email usuário e a senha correspondente de sua conta do GitHub. Depois disso, verifique as atualizações no seu repositório GitHub via browser.

# Configurando SonarQube para scannear projetos Java

# INSTALANDO SONARQUBE 

## 1. Download e configuração do SONARQUBE Server (COMMUNITY EDITION 6.7.5):  https://www.sonarqube.org/downloads/
   
   ### Faça o download o arquivo COMMUNITY EDITION 6.7.5 para o diretório C:\Users\SeuUsuario\sonar\ (Para evitar problemas de permissão)
   
   ### Configure o servidor no arquivo "C:\Users\SeuUsuario\sonar\sonarqube-6.7.5\conf\sonar.properties" descomentando as linhas abaixo(Remova #):
     - sonar.web.host=localhost (Host)
	   - sonar.web.port=9000 (Porta)
	   - sonar.ce.javaOpts=-Xmx512m -Xms128m -XX:+HeapDumpOnOutOfMemoryError (Memória)
   
   ### Configure o arquivo JDK no arquivo "C:\Users\SeuUsuario\sonar\sonarqube-6.7.5\conf\wrapper.conf" conforme a linha abaixo:
        wrapper.java.command=C:/Desenvolvimento/programas/jdk1.8.0_65/bin/javaw.exe
   
   ### Execute o Sonar Server
       De dentro do diretório "C:\Users\SeuUsuario\sonar\sonarqube-6.7.5\bin\windows-x86-64" abra o prompt de comando 
	   e execute o arquivo StartSonar.bat   
 
   
## 2. Download SCANNER (Windows 64 bit): https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner
  
    
	### Configurar variável de ambiente
	    - Incluir no path o caminho: ;C:\Users\F520127\sonar\sonar-scanner-3.2.0.1227-windows\bin
    
	### Criar projeto que será referenciado no sonarQube	
	    - Dentro do projeto a ser monitorado, crie o arquivo "sonar-project.properties" com as configurações abaixo:
		  
          # Identificação do projeto
          sonar.projectKey=sinbc-portalbanking
          sonar.projectVersion=1.0
          sonar.projectName=sinbc-portalbanking

          # Informações de configuração
          sonar.sources=.
          sonar.language=java
          sonar.sourceEncoding=UTF-8
          sonar.language=java
          sonar.java.binaries=./target/classes
			
	### Execute o scanner para o projeto
        - Dentro do projeto a ser monitorado, onde foi criado o arquivo "sonar-project.properties", abra o prompt de comando
          e digite $sonar-scanner
		  
	

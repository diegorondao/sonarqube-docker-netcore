<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="https://github.com/user-attachments/assets/93b9793f-6010-4820-b29f-67d62538b94e" alt="Logo" width="720" height="240">
  </a>
  <h3 align="center">SonarQube + Docker + .NET Coree</h3>
  <p align="center">
    🚀 Análise de código com SonarQube + Docker + .NET Core em ambiente local
    <br />
    <br />
  </p>
  <p> Escrever código de qualidade é fundamental no ciclo de vida do desenvolvimento de software. Existem algumas ferramentas que nos auxiliam a escrever um código mais limpo. O SonarQube é uma dessas ferramentas e oferece uma versão gratuita para a comunidade. Ele realiza diversas análises, como a detecção de bugs, code smells, cobertura de testes, vulnerabilidades e duplicações de código.
  </p>
</div>

## Instale o SonarQube no Docker
Para executar o projeto em seu ambiente local, basta clonar ou realizar o download do projeto em sua maquina local.

```sh
git clone https://github.com/diegorondao/sonarqube-docker-netcore.git
```

Acessar o diretório do projeto

```sh
cd sonarqube-docker-netcore
```
Você deve ter o Docker Desktop instalado e logado. Execute este comando no prompt de comando.
```
docker-compose up 
```
Docker Compose finalizado, SonarQube e PostgreSQL estão funcionando

![image](https://github.com/user-attachments/assets/e48753d0-1de2-4f2b-bc9f-c69dd5e76eb2)

Abra o seu navegador no endereço http://localhost:9999
![image](https://github.com/user-attachments/assets/a2525b10-84bd-4752-8cca-7ff6942ae2d2)
    
    Login: admin
    Password: bitnami

Forneça o nome e a chave para o projeto.

![image](https://github.com/user-attachments/assets/ae0859cb-d0e7-4eaa-ab0f-401c6e5f5b0d)

Forneça um nome para o token e pressione o botão "Gerar".
![image](https://github.com/user-attachments/assets/8eff12e8-ef98-4bfb-a920-523536716638)

Selecione ".NET" como o tipo de compilação e ".NET Core" como a ferramenta de compilação.
![image](https://github.com/user-attachments/assets/6041e199-d4d8-4845-9eaa-8498995eefec)

### Install the SonarScanner .NET Core Global Tool
```
dotnet tool install --global dotnet-sonarscanner 
``` 

### Executar análise em seu projeto
Vá para a pasta raiz da solução de projeto do .NET Core e abra um prompt de comando a partir dela. Agora podemos executar os comandos fornecidos na página, um por um no prompt de comando.
```
dotnet sonarscanner begin /k:"Projeto-Demo" /d:sonar.host.url="http://localhost:9999"  /d:sonar.token="sqp_54a94e04c72d802d284f2babb6d02ad2e7144670" 
``` 
```
dotnet build 
``` 
```
dotnet sonarscanner end /d:sonar.token="sqp_54a94e04c72d802d284f2babb6d02ad2e7144670"
``` 
### Overview
Assim que os últimos comandos forem concluídos, a página será atualizada automaticamente com o relatório.

![image](https://github.com/user-attachments/assets/4accc881-7ff6-4b5b-9b9b-7c06b8d50c98)

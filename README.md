# aula04-docker

# Aula prática - Docker e GitHub Codespaces 
## 1. Identificação Nome do aluno:
-- André de Abreu Rocha

## 2. Docker no Codespaces Versão do Docker utilizada: ... 

Docker version 29.3.0-1, build 5927d80c76b3ce5cf782be818922966e8a0d87a3

## 3. Contêiner Nginx Descreva em 2 ou 3 linhas o que aconteceu ao executar o Nginx. 

Através do Ngnix foi efetuado o download de um imagem que ficou disponível 
no ambiente do Docker, depois disso foi criado e executado um Contêiner
que "se conecta com o Nginx" usando volumes.

## 4. Imagem personalizada Informe o nome/tag da imagem criada e o resultado de docker run --rm aula-docker:1.0. 

Olá! Esta imagem Docker foi criada na aula de Integração e Entrega Contínua.

## 5. Docker Compose Registre o resultado de docker compose ps e confirme o acesso ao phpMyAdmin. 

NAME              IMAGE               COMMAND                  SERVICE      CREATED         STATUS         PORTS
aula-mysql        mysql:8.4           "docker-entrypoint.s…"   mysql        7 seconds ago   Up 6 seconds   0.0.0.0:3306->3306/tcp, [::]:3306->3306/tcp, 33060/tcp
aula-phpmyadmin   phpmyadmin:latest   "/docker-entrypoint.…"   phpmyadmin   6 seconds ago   Up 6 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp

## 6. Persistência Explique por que o registro da tabela mensagem continuou existindo depois de docker compose down e docker compose up -d. 

Por conta que não foi utilizado o comando [docker compose down -v], manténdo assim o histórico de recriação e destruição de contêiners.

## 7. Evidências Inclua as evidências solicitadas pelo professor, como capturas de tela ou saídas curtas do terminal.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. Qual é a diferença entre uma imagem Docker e um contêiner?

A imagen Docker apenas é um modelo que guarda o código de forma estática, enquanto a contêiner é uma instância em execução da imagem.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-

2. O que significa o mapeamento de portas 8080:80?

8080 (esquerda)-> a porta (host) da máquina fisíca que está rodando a aplicação.
80 (direita)-> a porta que está direcionada dentro da contêiner.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-

3. Qual é a função do Dockerfile neste exercício?

Ele cria o diretório de trabalho, copia o hello.txt para imagem e define o comando 
quando o contêiner for iniciar. 

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-

4. Por que o serviço phpMyAdmin consegue acessar o MySQL usando PMA_HOST: mysql?

Pela conexão entre ele e os contêiners pelo nome do arquivo.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-

5. Qual é a função do volume mysql-data?

Ele mantém os dados intactos do MYSQL separadamente dos ciclos de vida dos contêiners. 

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-

6. O que aconteceria com os dados se o ambiente fosse encerrado com docker compose down -v?

Ele apagaria os dados armazenados e os volumes associados ao ambiente támbem. 
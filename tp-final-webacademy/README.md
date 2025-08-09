# Trabalho Final - Web Academy Containers
Este projeto contém a aplicação de listagem de livros do Web Academy, configurada para rodar em um ambiente Docker.

## Pré-requisitos
Para executar este projeto, você precisará ter instalado em sua máquina:
- Docker
- Docker Compose

# Como Configurar e Executar
Siga os passos abaixo para colocar a aplicação no ar.

1. Clone o Repositório
Bash

git clone <https://github.com/tedyprist/Web-Academy---T5.git>
cd <WACAD012-Conteineres/tp-final-webacademy>
2. Configure as Variáveis de Ambiente do Backend
A aplicação backend precisa se conectar ao banco de dados. Para isso, é necessário criar um arquivo de configuração.

Navegue até a pasta backend:

Bash

cd backend
Crie um arquivo chamado .env e adicione o seguinte conteúdo:

Snippet de código

#Configurações do Banco de Dados
DB_HOST=db
DB_USER=root
DB_PASSWORD=root
DB_DATABASE=weba_books

#Porta da aplicação
PORT=4444
Volte para a raiz do projeto:

Bash

cd ..
3. Inicie os Contêineres
Com tudo configurado, utilize o Docker Compose para construir as imagens e iniciar os contêineres. Execute o comando abaixo na raiz do projeto:

Bash

docker-compose up --build
O processo pode levar alguns minutos na primeira execução, pois o Docker irá baixar as imagens base e construir as aplicações.

Acessando a Aplicação
Após a conclusão do comando docker-compose up, os serviços estarão disponíveis nos seguintes endereços:

### Aplicação Frontend (Listagem de Livros):

URL: http://localhost:8000

### Backend (API Node.js)
Porta: 4444

URL: http://localhost:4444

### PHPMyAdmin (Gerenciador do Banco de Dados):

URL: http://localhost:8080

Servidor: db

Usuário: root

Senha: root

# Verificação dos Volumes
Para verificar a persistência dos dados, você pode parar os contêineres (Ctrl + C no terminal onde o compose está rodando, e depois docker-compose down) e iniciá-los novamente. Os dados do banco de dados e os logs do backend deverão ser mantidos.

Volume do Banco de Dados: mysql_data

Volume de Logs do Backend: log_volume
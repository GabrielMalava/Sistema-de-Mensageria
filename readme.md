Sistema de Mensageria com RabbitMQ
Este projeto exemplifica a criação de um sistema de mensageria simples utilizando RabbitMQ. A aplicação inclui um componente produtor, que envia mensagens para uma fila, e um componente consumidor, que lê e processa essas mensagens.

Tecnologias
RabbitMQ: Sistema de mensageria que permite comunicação assíncrona entre diferentes serviços.
Node.js: Ambiente de execução para JavaScript no backend.
Express: Framework para construção de APIs no Node.js.
amqplib: Biblioteca de integração com RabbitMQ.
Principais Funcionalidades
Produtor de Mensagens: Publica mensagens na fila tasks.
Consumidor de Mensagens: Processa as mensagens enviadas para a fila.
Servidor HTTP com Express: Permite enviar mensagens para o RabbitMQ via requisições HTTP.
Requisitos de Configuração
Docker em execução.
Node.js e npm instalados no sistema.
Configurando o Ambiente
1. Inicializando o RabbitMQ
Para iniciar uma instância do RabbitMQ usando Docker, execute o seguinte comando:

bash
Copiar código
docker run -d --hostname my-rabbit --name some-rabbit -p 5672:5672 -p 15672:15672 rabbitmq:3-management
O painel de controle do RabbitMQ pode ser acessado em http://localhost:15672 (usuário: guest, senha: guest).

2. Clonando o Projeto
Para obter o código, faça o clone deste repositório em sua máquina:

bash
Copiar código
git clone https://github.com/Pedrogom7/rabbitmq_mensageria.git
cd rabbitmq_mensageria
3. Instalando as Dependências
Execute o comando abaixo para instalar as dependências necessárias:

bash
Copiar código
npm install
Executando a Aplicação
1. Executando o Consumidor
Em um terminal, inicie o processo do consumidor:

bash
Copiar código
node consumer.js
2. Iniciando o Servidor
Abra outro terminal e execute o servidor Express:

bash
Copiar código
node server.js
3. Enviando Mensagens para a Fila
Para enviar mensagens à fila tasks, faça uma requisição POST para http://localhost:3000/send. Você pode usar ferramentas como Postman ou Insomnia, ou um comando curl:

bash
Copiar código
curl -X POST http://localhost:3000/send -H "Content-Type: application/json" -d '{"message": "Olá, Mundo!"}'
Conceitos Básicos de Mensageria
Filas: Estruturas de dados que mantêm as mensagens até que sejam processadas pelo consumidor.
Produtor: Componente que cria e envia mensagens para uma fila específica.
Consumidor: Componente que lê e processa mensagens da fila.
RabbitMQ: Ferramenta de mensageria que facilita a comunicação entre serviços através de filas e roteamento de mensagens.
Contribuindo
Contribuições são bem-vindas! Sinta-se à vontade para fazer um fork do projeto, realizar suas modificações e enviar um pull request.

Licença
Este projeto está sob a Licença MIT. Confira o arquivo LICENSE para mais informações.


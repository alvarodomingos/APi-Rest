Golden Raspberry Awards
Descrição do Projeto
API RESTful para gerenciar a lista de indicados e vencedores da categoria Pior Filme do Golden Raspberry Awards.
Para executar o projeto, será necessário instalar os seguintes programas:
JDK 17: Necessário para executar o projeto Java

Maven 3.5.3: Necessário para realizar o build do projeto Java

IDE(Eclipse/Intellij): Para desenvolvimento do projeto

Para iniciar o desenvolvimento, é necessário clonar o projeto do GitHub num diretório de sua preferência:
cd "diretorio de sua preferencia"

git clone https://github.com/alvarodomingos/goldenraspberryawards

Para construir o projeto com o Maven, executar os comando abaixo:
mvn clean install
Para rodar os testes, utilize o comando abaixo:
mvn test
Executando a aplicação
Você pode executar a aplicação por linha de comando conforme abaixo ou pela sua IDE preferida:
mvn exec:java -Dexec.mainClass="com.goldenraspberryawards.GoldenraspberryawardsApplication"
Quando a aplicação estive startada esse será o seu PATH: http://localhost:8080.

A aplicação utiliza um banco de dados em memoria (H2) que é carregado a partir de um arquivo csv que esta na raiz do projeto contendo uma lista de produções.

Podemos acessar ao console do banco através do seguindo endereço:

PATH + /h2-console
Obs - Você pode alterar essa caminho dentro do arquivo "application.yml" que fica na pasta resource da aplicação.

image

Preencha os campos conforme dados abaixo e clique em conectar.

JDBC URL: jdbc:h2:mem:testdb

USER NAME: sa

Obs - Você pode alterar essas configurações dentro do arquivo "application.yml" que fica na pasta resource da aplicação.

Segue a lista de ENDPOINTs da aplicação:
ENDPOINT - Consultar Ganhadores Por Produtor
URL: PATH + /producers

METHOD: GET

RESPONSE: { "min": [ { "producer": "string", "interval": number, "previousWin": number, "followingWin": number } ], "max": [ { "producer": "string", "interval": number, "previousWin": number, "followingWin": number } ] }

ENDPOINT - Consultar Ganhadores Por Estudio
URL: PATH + /studios

METHOD: GET

RESPONSE: { "min": [ { "producer": "string", "interval": number, "previousWin": number, "followingWin": number } ], "max": [ { "producer": "string", "interval": number, "previousWin": number, "followingWin": number } ] }

ENDPOINT - Consultar Produções
URL: PATH + /movies

METHOD: GET

RESPONSE: [ { "year" : number, "title": "string", "studios": "string", "producers": "string", "winner": "string" } ]

ENDPOINT - Consulta Produção
URL: PATH + /movies/{id}

PARAM: "id" (Long)

METHOD - GET

RESPONSE: { "year" : number, "title": "string", "studios": "string", "producers": "string", "winner": "string" }

ENDPOINT - Cadastrar Produção
URL: PATH + /movies

METHOD: POST

BODY: { "year" : number, "title": "string", "studios": "string", "producers": "string", "winner": "string" }

RESPONSE: ""

ENDPOINT - Excluir Produção
URL: PATH + /movies/{id}

PARAM: "ID" (Long)

METHOD - DEL

RESPONSE: ""

ENDPOINT - Atualizar Produção
URL: PATH + /movies/{id}

PARAM: "ID" (Long)

METHOD - PUT

BODY: { "year" : number, "title": "string", "studios": "string", "producers": "string", "winner": "string" }

RESPONSE: ""

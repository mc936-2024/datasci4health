## Instalação
A _pipeline_ principal do projeto foi construída para rodar no [Google Colab](https://colab.google/), portanto, basta fazer o upload notebook no Drive e abrir.

Também é possível executar localmente, com alguns ajustes na interação com arquivos. Para isso, é necessário remover a biblioteca que monta a partição (```from colab import drive```), a chamada do mount (```drive.mount("/content/drive")```) e ajustar o caminho dos arquivos com prefixo em `/content/drive` para o seu sistema local.

## Ambiente
Dois arquivos são necessários para a execução da pipeline: `genes.csv` e `neo4j.env`. O primeiro é o arquivo que contém o transcriptôma das amostras de LLA, e o segundo é um arquivo no formato [dotenv](https://www.dotenv.org/docs/security/env) que contém as variáveis necessárias para se conectar em uma instância do banco de dados Neo4J (`NEO4J_URI`, `NEO4J_USERNAME` e `NEO4J_PASSWORD`).

## Execução
Para executar a pipeline, basta rodar as células do notebook `main.ipynb`. O notebook está dividido em duas seções principais: a análise dos genes e a criação do grafo.

Na primeira seção, temos majoritariamente o uso de `scikit-learn` para clusterização dos genes e `matplotlib` para visualização dos resultados. Na segunda seção, temos a criação do grafo no Neo4J, onde é feita a conexão com o banco de dados, a criação dos nós e arestas e a adição de propriedades de acordo com os resultados obtidos na primeira seção.

Ao executar o começo da segunda seção, o notebook dará a opção de um _hard reset_, que apaga todos os nós e arestas do banco de dados. Caso não seja necessário, basta responder com `n` e o notebook continuará a execução normalmente.
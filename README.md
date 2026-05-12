# Apache Spark com MinIO e SQL Server

> Trabalho de Pesquisa 2 - Arquitetura de Dados | SATC

## Participantes

- Nathan Frasetto
- Rafael Pagnan
- Ryan Candeu

## Sobre o Projeto

Este projeto implementa um pipeline de dados completo utilizando Apache Spark, MinIO e SQL Server 2022:

- Extracao: dados extraidos do SQL Server salvos como CSV no MinIO (landing-zone)
- Landing Zone: arquivos CSV armazenados no MinIO
- Bronze Layer: dados convertidos para Delta Lake no MinIO (bronze)
- DML: operacoes de INSERT, UPDATE e DELETE nas tabelas Delta

## Arquitetura

SQL Server 2022 --> MinIO (landing-zone/CSVs) --> MinIO (bronze/Delta Tables)

## Estrutura do Projeto

spark-minio-sqlserver/
- pipeline.ipynb
- docker-compose.yml
- jars/
- docs/
- mkdocs.yml
- pyproject.toml
- README.md

## Pre-requisitos

- Docker
- Java 17
- Python 3.11
- Poetry

## Como Rodar

1. Clone o repositorio
git clone https://github.com/Ra-man/spark-minio-sqlserver.git

2. Suba os containers
docker compose up -d

3. Instale as dependencias
poetry install
eval $(poetry env activate)

4. Baixe os JARs
mkdir -p jars
wget -P jars https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.4/hadoop-aws-3.3.4.jar
wget -P jars https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.262/aws-java-sdk-bundle-1.12.262.jar

5. Crie os buckets no MinIO
Acesse http://localhost:9001 (minioadmin/minioadmin) e crie: landing-zone e bronze

6. Inicie o Jupyter
jupyter lab --no-browser

7. Execute o notebook pipeline.ipynb

## Servicos Docker

- SQL Server 2022: porta 1433 (sa/Senha@1234)
- MinIO API: porta 9000 (minioadmin/minioadmin)
- MinIO Console: porta 9001 (minioadmin/minioadmin)

## Documentacao

https://Ra-man.github.io/spark-minio-sqlserver/

## Referencias

- https://spark.apache.org/docs/latest/
- https://docs.delta.io/
- https://min.io/docs/
- https://github.com/jlsilva01/spark-delta-minio-sqlserver

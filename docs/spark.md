# Apache Spark

## O que e?

Apache Spark e um motor de processamento distribuido open-source que processa dados em memoria.

## Papel no Projeto

- Le os CSVs do MinIO (landing-zone)
- Converte para Delta Lake (bronze)
- Executa operacoes DML nas tabelas Delta

## Configuracao com MinIO

Usamos o protocolo S3A para conectar ao MinIO como se fosse um Amazon S3 local.

## JARs necessarios

- hadoop-aws-3.3.4.jar
- aws-java-sdk-bundle-1.12.262.jar

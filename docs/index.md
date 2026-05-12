# Apache Spark com MinIO e SQL Server

## Contextualizacao

Este projeto implementa um pipeline de dados completo seguindo a arquitetura Data Lakehouse.

## Fluxo do Pipeline

1. Extracao dos dados do SQL Server 2022
2. Armazenamento como CSV no MinIO bucket landing-zone
3. Leitura dos CSVs e conversao para Delta Lake no bucket bronze
4. Operacoes DML nas tabelas Delta

## Tecnologias

| Tecnologia | Versao |
|---|---|
| Python | 3.11 |
| Apache Spark | 3.5.1 |
| Delta Lake | 3.2.0 |
| SQL Server | 2022 Dev |
| MinIO | latest |

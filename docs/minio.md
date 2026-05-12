# MinIO

## O que e?

MinIO e um sistema de armazenamento de objetos open-source compativel com a API S3 da Amazon.

## Buckets do Projeto

| Bucket | Conteudo | Camada |
|---|---|---|
| landing-zone | CSVs extraidos do SQL Server | Landing Zone |
| bronze | Tabelas Delta Lake | Bronze Layer |

## Como Acessar

Console web: http://localhost:9001
Usuario: minioadmin
Senha: minioadmin

## Diferenca entre Camadas

A landing-zone recebe dados brutos em CSV. O bronze armazena dados processados em Delta Lake com ACID e Time Travel.

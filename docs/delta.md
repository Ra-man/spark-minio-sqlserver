# Delta Lake

## O que e?

Delta Lake adiciona transacoes ACID ao Data Lake. Desenvolvido pela Databricks.

## Operacoes DML

### INSERT

    spark.sql("INSERT INTO delta.`s3a://bronze/pedidos` VALUES (4, 1, 2, 3, 450.00, 'pendente', '2024-02-01')")

### UPDATE

    dt = DeltaTable.forPath(spark, 's3a://bronze/pedidos')
    dt.update(condition='id_pedido = 1', set={'status': "'entregue'"})

### DELETE

    dt.delete('id_pedido = 4')

## Time Travel

    dt.history().select('version', 'timestamp', 'operation').show()

## Tabelas Gerenciadas vs Nao Gerenciadas

| Tipo | Descricao |
|---|---|
| Gerenciada | Spark controla dados e metadados. Ao dropar, dados sao deletados |
| Nao Gerenciada | Spark controla apenas metadados. Dados permanecem no storage |

Neste projeto usamos tabelas NAO GERENCIADAS pois os dados ficam no MinIO.

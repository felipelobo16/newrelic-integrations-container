# New Relic Integrations

## MSSQL Data + Custom Queries.


1) Alterar os dados:

- ./Dockerfile: ```NRIA_LICENSE_KEY```

- ./integrations/mssql.yaml: ```HOSTNAME``` , ```USERNAME``` e ```PASSWORD``` com dados do banco.

- ./integrations/custom/custom-queries.yaml: Com as Queries custom que deseja executar.


2) Build and Run:

- Buildar e Rodar o container na mesma rede que o banco MSSQL se encontra.


3) Tabelas na New Relic.

- Ira aparecer as tabelas: ```MssqlDatabaseSample``` , ```MssqlInstanceSample``` , ```MssqlWaitSample``` e ```MssqlCustomQuerySample```

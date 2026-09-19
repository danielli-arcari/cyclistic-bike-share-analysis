# Dados do projeto

Este projeto utiliza 12 meses de dados públicos de viagens da Divvy, correspondentes ao período de setembro de 2025 a agosto de 2026.

Os arquivos originais foram mantidos neste diretório, organizados por mês.

## Base preparada para o Power BI

Após a etapa de limpeza e preparação dos dados, foi gerado o arquivo:

`BaseDadosDivvy_LimpaParaPowerBI.csv`

Essa versão foi utilizada na construção do dashboard no Power BI.

Durante essa etapa, foram removidas as seguintes colunas:

- `start_station_name`
- `start_station_id`
- `end_station_name`
- `end_station_id`
- `start_lat`
- `start_lng`
- `end_lat`
- `end_lng`

Essas variáveis continham informações relacionadas às estações e à localização geográfica das viagens.

Como a pergunta de negócio deste estudo de caso está concentrada na comparação entre usuários `member` e `casual`, essas informações não eram necessárias para responder ao problema proposto nem para construir as visualizações utilizadas na análise final.

A remoção dessas colunas também contribuiu para reduzir o tamanho da base utilizada no Power BI, sem perda de informações relevantes para os objetivos desta análise.

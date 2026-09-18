# Cyclistic Bike-Share Analysis

Estudo de caso desenvolvido como parte do **Google Data Analytics Professional Certificate**, oferecido pelo Google por meio da Coursera.

O projeto reproduz um cenário de trabalho para uma analista de dados júnior e segue as seis etapas do processo de análise apresentadas no curso: **Perguntar, Preparar, Processar, Analisar, Compartilhar e Agir**.

## Sobre o curso

- **Google Data Analytics Professional Certificate:**  
  https://www.coursera.org/professional-certificates/google-data-analytics

- **Google Data Analytics Capstone: Complete a Case Study:**  
  https://www.coursera.org/learn/google-data-analytics-capstone

O estudo Cyclistic é um dos estudos de caso propostos no projeto final do certificado, com o objetivo de aplicar o processo completo de análise de dados e produzir um material que possa ser apresentado em portfólio.

---

## Contexto do case

A **Cyclistic** é uma empresa fictícia de compartilhamento de bicicletas em Chicago.

No cenário apresentado pelo Google, a diretora de marketing acredita que o crescimento futuro da empresa depende do aumento do número de **assinaturas anuais**. Para apoiar essa estratégia, a equipe de análise precisa compreender como dois grupos utilizam o serviço:

- **casual:** usuários que compram passes avulsos ou diários;
- **member:** usuários com assinatura anual.

O estudo de caso apresenta três perguntas de negócio:

1. Como os assinantes anuais e os usuários casuais utilizam as bicicletas da Cyclistic de maneiras diferentes?
2. Por que os usuários casuais comprariam uma assinatura anual?
3. Como a Cyclistic pode usar mídias digitais para influenciar usuários casuais a se tornarem assinantes?

Neste projeto, a pergunta atribuída à análise foi:

> **Como os assinantes anuais e os usuários casuais utilizam as bicicletas da Cyclistic de maneiras diferentes?**

A proposta é transformar os dados históricos de viagens em informações que possam apoiar futuras decisões de marketing voltadas à conversão de usuários casuais em assinantes anuais.

---

## Resumo das instruções do estudo de caso

O material do case orienta a construção do projeto em seis etapas.

### 1. Perguntar

Definir claramente o problema de negócio, compreender quem são as partes interessadas e estabelecer a pergunta que a análise deverá responder.

**Entrega esperada:** declaração clara da tarefa de negócio.

### 2. Preparar

Obter os dados históricos de viagens, compreender como os arquivos estão organizados e avaliar aspectos como integridade, credibilidade, privacidade, licenciamento e limitações dos dados.

**Entrega esperada:** descrição das fontes de dados utilizadas.

### 3. Processar

Verificar erros e inconsistências, escolher as ferramentas de trabalho, limpar e transformar os dados e documentar as alterações realizadas.

**Entrega esperada:** documentação da limpeza e da manipulação dos dados.

### 4. Analisar

Organizar os dados, realizar cálculos, criar estatísticas descritivas e procurar tendências e relações capazes de responder à pergunta de negócio.

O roteiro sugere análises como:

- duração média das viagens;
- duração máxima;
- dia da semana;
- comparação entre usuários `member` e `casual`;
- número de viagens por dia da semana;
- consolidação dos 12 meses em uma visão anual.

**Entrega esperada:** resumo da análise.

### 5. Compartilhar

Criar visualizações claras, profissionais e adequadas ao público executivo, destacando os padrões mais relevantes encontrados durante a análise.

**Entrega esperada:** visualizações de apoio e principais descobertas.

### 6. Agir

Transformar as descobertas em recomendações de negócio e disponibilizar o estudo de caso no portfólio.

**Entrega esperada:** três recomendações baseadas nos dados.

---

## Fontes e arquivos do projeto

### Dados originais

Os dados utilizados no estudo são dados públicos de viagens da **Divvy**, utilizados pelo Google como base para representar a empresa fictícia Cyclistic.

**Fonte oficial indicada nas instruções do case:**

https://divvy-tripdata.s3.amazonaws.com/index.html

No projeto foram utilizados **12 arquivos mensais**, cobrindo o período de **setembro de 2025 a agosto de 2026**.

A base bruta consolidada possuía aproximadamente **6,1 milhões de registros**.

### PDF com as instruções do case

https://drive.google.com/file/d/1u_7951LuTewBW-5TVi7LggP8d_GWFzyb/view?usp=sharing

### Base tratada completa — `cyclistic_limpo.csv`

https://drive.google.com/file/d/13gkQdLmNL2fyKYKT0Ty7U5z3SaLbyza_/view?usp=sharing

### Projeto Power BI

https://drive.google.com/file/d/1Ddb5DukxWc_TXkhesHI3NAJtzMzuP6BL/view?usp=sharing

Os arquivos maiores foram disponibilizados por URL em vez de serem armazenados diretamente no GitHub, evitando manter arquivos de centenas de megabytes ou gigabytes dentro do repositório.

---

## Estrutura dos dados originais

Os arquivos originais continham as seguintes colunas:

| Coluna | Descrição |
|---|---|
| `ride_id` | Identificador único da viagem |
| `rideable_type` | Tipo de bicicleta |
| `started_at` | Data e horário de início |
| `ended_at` | Data e horário de término |
| `start_station_name` | Nome da estação inicial |
| `start_station_id` | ID da estação inicial |
| `end_station_name` | Nome da estação final |
| `end_station_id` | ID da estação final |
| `start_lat` | Latitude inicial |
| `start_lng` | Longitude inicial |
| `end_lat` | Latitude final |
| `end_lng` | Longitude final |
| `member_casual` | Categoria do usuário: `member` ou `casual` |

---

## Preparação e limpeza dos dados

Os 12 arquivos mensais foram consolidados em uma única base.

Durante a preparação foram realizadas verificações de:

- estrutura e tipos de dados;
- datas de início e término;
- duplicidade de `ride_id`;
- valores ausentes;
- consistência das categorias de usuários;
- duração das viagens.

Após a validação:

- registros com datas inválidas foram retirados;
- registros duplicados por `ride_id` foram removidos;
- valores ausentes ligados a estações e coordenadas foram mantidos quando não impediam a análise principal, pois o objetivo deste projeto não dependia de localização;
- foram criadas variáveis derivadas para apoiar a análise temporal.

A base tratada final ficou com **6.115.918 viagens válidas e únicas**.

---

## Variáveis criadas

Foram adicionadas variáveis analíticas derivadas dos campos de data e hora:

| Variável | Finalidade |
|---|---|
| `ride_length_min` | Duração da viagem em minutos |
| `day_of_week` | Dia da semana em que a viagem começou |
| `month` | Mês da viagem |
| `hour` | Hora de início da viagem |

Essas variáveis permitem comparar o comportamento dos usuários ao longo da semana, dos meses e em relação à duração das viagens.

---

## Arquivo reduzido para Power BI

Além da base tratada completa, foi preparado um arquivo voltado especificamente para a etapa de visualização no Power BI.

O objetivo foi evitar carregar no dashboard informações que não seriam utilizadas para responder à pergunta de negócio.

No recorte analítico, foram dispensados campos ligados à identificação física das estações e à geolocalização:

- `start_station_name`
- `start_station_id`
- `end_station_name`
- `end_station_id`
- `start_lat`
- `start_lng`
- `end_lat`
- `end_lng`

O campo `rideable_type` também não foi necessário nas visualizações finais deste estudo, pois a análise apresentada no dashboard foi direcionada à comparação entre **usuários casuais e assinantes**, e não ao tipo de bicicleta utilizado.

Os campos de data e hora foram usados para gerar as variáveis analíticas `ride_length_min`, `day_of_week`, `month` e `hour`.

Essa redução diminuiu o volume do arquivo levado ao Power BI sem alterar as informações necessárias para responder à pergunta do case.

---

## Análises realizadas

A análise foi estruturada para comparar os padrões de utilização entre `member` e `casual`.

Foram explorados principalmente:

- quantidade de viagens por categoria de usuário;
- duração média das viagens;
- quantidade de viagens por dia da semana;
- duração média por dia da semana;
- evolução mensal do número de viagens;
- diferenças de comportamento entre usuários casuais e assinantes.

As visualizações foram construídas no **Power BI** com foco direto na pergunta:

> **Como usuários casuais e assinantes anuais utilizam as bicicletas de maneiras diferentes?**

---

## Dashboard

O dashboard foi organizado para permitir a comparação entre `member` e `casual`, apresentando indicadores e gráficos sobre:

- volume de viagens;
- duração média;
- comportamento por dia da semana;
- comportamento ao longo dos meses.

O tipo de bicicleta não foi utilizado como dimensão da análise final.

---

## Ferramentas utilizadas

- **Python / Pandas**
- **Jupyter / Google Colab**
- **Pentaho Data Integration**
- **Power BI**
- **Git / GitHub**

---

## Fluxo do projeto

```text
Dados públicos da Divvy
        ↓
12 arquivos CSV mensais
        ↓
Consolidação e validação
        ↓
Limpeza e criação de variáveis
        ↓
cyclistic_limpo.csv
        ↓
Recorte analítico para BI
        ↓
Power BI
        ↓
Dashboard e recomendações
```

---

## Objetivo de portfólio

Este projeto foi desenvolvido com finalidade acadêmica e de portfólio, aplicando conceitos estudados no **Google Data Analytics Professional Certificate** em um conjunto de dados com mais de seis milhões de registros.

O trabalho demonstra etapas de:

- compreensão de uma pergunta de negócio;
- preparação e limpeza de dados;
- transformação de variáveis;
- análise exploratória;
- criação de métricas;
- visualização em Power BI;
- comunicação dos resultados.

---

## Referências

**Google Data Analytics Professional Certificate — Coursera**  
https://www.coursera.org/professional-certificates/google-data-analytics

**Google Data Analytics Capstone: Complete a Case Study — Coursera**  
https://www.coursera.org/learn/google-data-analytics-capstone

**Dados públicos Divvy / Cyclistic**  
https://divvy-tripdata.s3.amazonaws.com/index.html

**Instruções do estudo de caso**  
https://drive.google.com/file/d/1u_7951LuTewBW-5TVi7LggP8d_GWFzyb/view?usp=sharing

**Base tratada completa**  
https://drive.google.com/file/d/13gkQdLmNL2fyKYKT0Ty7U5z3SaLbyza_/view?usp=sharing

**Projeto Power BI**  
https://drive.google.com/file/d/1Ddb5DukxWc_TXkhesHI3NAJtzMzuP6BL/view?usp=sharing

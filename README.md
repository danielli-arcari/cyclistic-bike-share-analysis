# Análise de Compartilhamento de Bicicletas para Ciclistas

## Sobre o projeto

Este projeto foi desenvolvido como estudo de caso do **Google Data Analytics Professional Certificate**.

O cenário proposto envolve a **Cyclistic**, empresa fictícia baseada nos dados públicos da Divvy, sistema de compartilhamento de bicicletas de Chicago.

O objetivo da análise é compreender as diferenças de comportamento entre dois grupos de usuários:

- `member`: assinantes anuais;
- `casual`: usuários casuais.

A análise busca responder à seguinte pergunta de negócio:

> **Como assinantes anuais e usuários casuais utilizam as bicicletas de maneiras diferentes?**

A partir dessas diferenças, o estudo propõe recomendações que podem apoiar estratégias de conversão de usuários casuais em assinantes anuais.

---

## Período analisado

Foram utilizados **12 meses de dados**, correspondentes ao período de:

**setembro de 2025 a agosto de 2026**

Os arquivos originais foram mantidos separadamente no repositório para preservar a origem dos dados utilizados na análise.

---

## Fonte dos dados

Os dados são disponibilizados publicamente pela **Divvy** para utilização em análises e estudos.

No repositório, os arquivos originais estão organizados na pasta:

```text
data/
```

---

## Cada mês foi armazenado separadamente:

202509
202510
202511
202512
202601
202602
202603
202604
202605
202606
202607
202608

---

## Ferramentas utilizadas:

Python
Pandas
Google Colab
Power BI
GitHub

---

## Etapas do projeto

### 1. Coleta dos dados

Foram utilizados 12 arquivos CSV mensais contendo registros de viagens realizadas no sistema Divvy.

### 2. Consolidação

Os arquivos foram importados e consolidados em uma única base para análise.

### 3. Exploração e validação

Durante a análise exploratória foram verificadas:

estrutura das tabelas
tipos de dados
valores nulos
registros duplicados
consistência das datas
duração das viagens
distribuição das viagens por tipo de usuário

### 4. Criação de variáveis analíticas

Foram utilizadas variáveis derivadas para permitir comparações entre os grupos, incluindo informações relacionadas a:

duração da viagem
dia da semana
mês
horário
tipo de usuário

---

## Preparação da base para o Power BI

Para construção do dashboard foi criada uma versão específica da base:

data/BaseDadosDivvy_LimpaParaPowerBI.csv

Essa base foi preparada a partir da base consolidada e teve algumas colunas removidas:

start_station_name
start_station_id
end_station_name
end_station_id
start_lat
start_lng
end_lat
end_lng

Essas variáveis estavam relacionadas às estações e à localização geográfica das viagens.

Como a pergunta de negócio deste estudo está concentrada na comparação de comportamento entre usuários member e casual, essas informações não eram necessárias para responder ao problema proposto.

A remoção dessas colunas também contribuiu para reduzir o tamanho da base utilizada no Power BI sem eliminar informações relevantes para as análises realizadas.

---

## Análise em Python

A etapa de exploração, tratamento e validação dos dados foi realizada em Python com Pandas, utilizando Google Colab.

O notebook está disponível em:

cadernos/Analise_Divvy.ipynb

---

## Dashboard em Power BI

Após a preparação da base, foi desenvolvido um dashboard no Power BI para facilitar a comparação entre os usuários member e casual.

O arquivo completo está disponível em:

Power BI/Projeto_Divvy.pbix

---

## Métricas e visualizações

As principais visualizações foram desenvolvidas para responder à pergunta de negócio proposta.

Entre as análises realizadas estão:

quantidade total de viagens
quantidade de viagens por tipo de usuário
duração média das viagens
comportamento por dia da semana
comportamento por horário
comportamento por mês
comparação entre usuários casuais e membros

Essas métricas permitem observar diferenças de frequência, duração e padrão de utilização do serviço.

---

## Principais resultados

A análise mostrou diferenças claras entre os dois grupos de usuários.

### Volume de viagens

Os membros realizam maior quantidade de viagens ao longo do período analisado.

Os dados indicam aproximadamente:

3,96 milhões de viagens de membros
2,16 milhões de viagens de usuários casuais

### Duração das viagens

Apesar de realizarem menos viagens, os usuários casuais apresentam viagens mais longas em média.

A duração média encontrada foi aproximadamente:

20,7 minutos para usuários casuais
12,4 minutos para membros

### Comportamento ao longo da semana

Os membros apresentam maior concentração de viagens durante os dias úteis.

Os usuários casuais apresentam aumento relativo de utilização nos finais de semana.

### Comportamento por horário

Os membros apresentam padrões de utilização mais concentrados em horários associados a deslocamentos recorrentes.

Os usuários casuais apresentam maior presença em períodos relacionados a atividades de lazer.

### Sazonalidade

A utilização do serviço aumenta durante os meses mais quentes.

Esse crescimento é particularmente visível entre os usuários casuais.

### Memória de cálculo

As principais métricas foram obtidas a partir de regras de negócio simples aplicadas à base consolidada.

#### Quantidade de viagens

Cada registro representa uma viagem.

A quantidade total foi obtida pela contagem dos registros válidos da base.

#### Quantidade de viagens por tipo de usuário

Os registros foram agrupados pela variável:
member_casual

permitindo comparar os grupos:

member
casual

#### Duração da viagem

A duração foi calculada pela diferença entre:

ended_at - started_at

O resultado foi convertido para minutos para facilitar a interpretação.

#### Duração média

A média foi calculada separadamente para cada tipo de usuário.

#### Dia da semana

O dia da semana foi derivado da data de início da viagem.

#### Horário

O horário foi extraído do campo de início da viagem.

#### Mês

O mês foi obtido a partir da data de início da viagem e utilizado para análise de sazonalidade.

---

## Principais insights

Os dados mostram dois padrões distintos de utilização.

### Membros

Os assinantes apresentam comportamento mais frequente e recorrente.

O padrão observado sugere maior utilização associada a deslocamentos cotidianos.

### Usuários casuais

Os usuários casuais realizam menos viagens, porém permanecem mais tempo utilizando as bicicletas.

Também apresentam maior participação relativa nos finais de semana e nos períodos de maior sazonalidade.

Essas diferenças sugerem que parte desse público pode representar uma oportunidade de conversão para planos de assinatura.

---

## Recomendações

### 1. Campanhas em períodos de maior uso casual

Direcionar campanhas para períodos nos quais a participação dos usuários casuais é maior, especialmente finais de semana e meses mais quentes.

### 2. Demonstrar vantagens da assinatura

Criar comunicações mostrando as vantagens financeiras e práticas da assinatura anual para usuários com comportamento recorrente.

### 3. Segmentar usuários casuais frequentes

Usuários casuais que utilizam o serviço repetidamente podem apresentar maior potencial de conversão.

---

## Apresentação do case

Uma apresentação resumindo o problema de negócio, métricas, memória de cálculo, fontes, análises, limitações e próximos passos está disponível em:

apresentação/Apresentacao_Case_Divvy.pdf

---

## Case original

O enunciado original do estudo está disponível na pasta:

case/

---

##Estrutura do repositório:

```
cyclistic-bike-share-analysis/
│
├── case/
│   └── Case Study 1_ How does a bike-share navigate speedy success.pdf
│
├── cadernos/
│   └── Analise_Divvy.ipynb
│
├── data/
│   ├── 202509/
│   ├── 202510/
│   ├── 202511/
│   ├── 202512/
│   ├── 202601/
│   ├── 202602/
│   ├── 202603/
│   ├── 202604/
│   ├── 202605/
│   ├── 202606/
│   ├── 202607/
│   ├── 202608/
│   ├── BaseDadosDivvy_LimpaParaPowerBI.csv
│   └── README.md
│
├── Power BI/
│   └── Projeto_Divvy.pbix
│
├── imagens/
│   └── gráficos do projeto
│
├── apresentação/
│   └── Apresentacao_Case_Divvy.pdf
│
├── .gitattributes
├── .gitignore
└── README.md
```
---

## O que pode ser melhorado

Algumas evoluções possíveis para este projeto incluem:

aprofundar a análise geográfica
explorar estações de origem e destino
analisar trajetos mais frequentes
criar segmentações adicionais entre usuários casuais
comparar diferentes anos
construir modelos de previsão de demanda
publicar o dashboard em ambiente online
automatizar a atualização dos dados
Próximos passos

Como evolução futura, o projeto pode incorporar análises de localização, sazonalidade mais detalhada e comportamento por estação.

Também seria possível criar um pipeline automatizado de atualização dos dados e integrar novas competências de engenharia de dados ao fluxo do projeto.

---

## Conclusão

A análise mostrou que membros e usuários casuais apresentam comportamentos diferentes na utilização do serviço.

Os membros utilizam o sistema de maneira mais frequente e recorrente, enquanto os usuários casuais apresentam viagens mais longas e maior participação em períodos associados ao lazer.

Essas diferenças ajudam a identificar oportunidades para campanhas mais direcionadas e podem apoiar estratégias de conversão de usuários casuais em assinantes anuais.

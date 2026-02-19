# Case Study: Cyclic
Estudo de caso de Análise de Dados (Capstone Google Data Analytics)

#### Autor: Lucas Martin Toth
#### Data: 17/02/2026
#### [Dashboard Tableau](https://public.tableau.com/views/CyclistAnualMembersvs_CasualUsersBehavior/Painel1?:language=pt-BR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
#

_O estudo de caso segue o processo de análise de dados em 6 passos:_

### ❓ 1. Pergunte
### 💻 2. Prepare
### 🛠 3. Processe
### 📊 4. Analise
### 📋 5. Compartilhe
### 🧗‍♀️ 6. Atue

## Cenário
Sou um analista de dados júnior trabalhando na equipe de análise de marketing da Cyclistic, uma empresa de compartilhamento de bicicletas em Chicago. A diretora de marketing acredita que o sucesso futuro da empresa depende de maximizar o número de assinaturas anuais. Portanto, minha equipe deseja entender como usuários casuais e membros anuais utilizam as bicicletas da Cyclistic de forma diferente. Com base nesses insights, a equipe desenvolverá uma nova estratégia de marketing para converter usuários casuais em membros anuais. No entanto, primeiro os executivos da Cyclistic devem aprovar nossas recomendações, portanto elas precisam ser sustentadas por insights de dados convincentes e visualizações de dados profissionais.

## ❓ 1. Pergunte
💡 **BUSINESS TASK: A tarefa de negócio é analisar como os membros anuais e os usuários casuais utilizam as bicicletas da Cyclistic de forma diferente, a fim de identificar padrões de comportamento que distingam esses dois segmentos de clientes.**

Principais Stakeholders: Os principais stakeholders envolvidos nesta tarefa de negócio incluem:

• Lily Moreno: Diretora de Marketing, responsável por desenvolver estratégias para converter usuários casuais em membros anuais.

• Equipe de Marketing Analytics da Cyclistic: responsável por analisar os dados e fornecer insights acionáveis.

• Equipe Executiva da Cyclistic: responsável por aprovar e investir em estratégias de marketing baseadas em dados.

## 💻 2. Prepare
Os dados utilizados nesta análise consistem em dados históricos de viagens de bicicletas da Cyclistic, disponibilizados publicamente pela Motivate International Inc. Esses dados incluem registros detalhados de viagens realizadas por usuários ao longo do último trimestre de 2025.

Os datasets são arquivos no formato CSV, com cada arquivo representando um mês de dados de viagens. Cada registro contém informações relevantes sobre o uso das bicicletas, incluindo:

•	Tipo de usuário (member ou casual)

•	Data e horário de início da viagem (started_at)

•	Data e horário de término da viagem (ended_at)

•	Tipo de bicicleta (rideable_type)

•	Estação de início (start_station_name)

•	Estação de término (end_station_name)

•	Coordenadas geográficas de início e término (latitude e longitude)

Esses dados estão armazenados localmente no ambiente de análise e foram organizados em uma estrutura de pastas para facilitar o acesso, manipulação e análise.

## 🛠 3. Processe
#### 1. Padronização de colunas e tipos de dados
#### 2. Combinação dos arquivos mensais
Os 2 arquivos CSV foram importados e combinados em um único dataframe consolidado utilizando pd.concat().
Isso permitiu analisar todo o período como um único dataset.
#### 3. Conversão de tipos de dados para data
As colunas started_at e ended_at foram convertidas para o formato datetime, permitindo cálculos precisos de duração e análise temporal.
#### 4. Criação da variável de duração da viagem
Foi criada uma nova coluna chamada ride_length, representando a duração da viagem em minutos
#### 5. Remoção de registros inválidos
Foram removidos registros com:
•	Duração menor ou igual a zero
•	Viagens de manutenção
#### 6. Criação de variáveis temporais adicionais
Foram criadas colunas auxiliares para facilitar a análise de padrões de uso:
•	Dia da semana, mês, ano, data 
#### 7. Remoção de duplicatas
#
Todo o processo de limpeza foi documentado e executado em Python, garantindo transparência, reprodutibilidade e confiabilidade.
O dataset final limpo foi exportado para uso na fase de análise.

## 📊 4. Analise
#### Organização e formatação dos dados

Após o processo de limpeza, os dados foram organizados em um dataframe estruturado contendo apenas registros válidos e relevantes. As seguintes variáveis foram utilizadas para análise:

•	member_casual — tipo de usuário (member ou casual)

•	average_duration — duração média das viagens em minutos

•	day_of_week — dia da semana da viagem

•	number_of_rides — número de viagens

Essas variáveis permitiram comparar diretamente os padrões de uso entre membros e usuários casuais.

Os dados foram agregados utilizando funções de agrupamento (groupby) no Python pandas para calcular médias, contagens e identificar padrões comportamentais.
#
#### Cálculos realizados
As seguintes métricas foram calculadas:

•	Número total de viagens por tipo de usuário

•	Duração média das viagens por tipo de usuário

•	Número de viagens por dia da semana

Essas métricas permitem identificar diferenças claras no comportamento dos usuários.
#
#### Tendências e relacionamentos identificados
A análise revelou várias diferenças importantes entre membros anuais e usuários casuais.

#### 1. Usuários casuais têm viagens mais longas em média
Usuários casuais apresentaram uma duração média de viagem significativamente maior do que membros anuais.

Isso sugere que usuários casuais utilizam as bicicletas principalmente para lazer, enquanto membros utilizam para deslocamentos mais curtos e frequentes.
#### 2. Membros utilizam as bicicletas com maior frequência durante dias úteis
Membros apresentaram maior volume de viagens durante dias úteis (segunda a sexta-feira), especialmente em horários típicos de deslocamento.

Isso indica que membros utilizam as bicicletas como meio de transporte diário, possivelmente para ir ao trabalho ou estudo.

#### 3. Usuários casuais utilizam mais as bicicletas durante fins de semana
Usuários casuais apresentaram maior volume de uso durante sábados e domingos.
Isso reforça a hipótese de que usuários casuais utilizam o serviço principalmente para lazer e recreação.
#
#### Insights importantes e descobertas inesperadas
Uma descoberta importante foi a diferença clara no propósito de uso entre os dois grupos:
•	Membros utilizam o serviço como meio de transporte regular
•	Usuários casuais utilizam o serviço principalmente para lazer
Essa diferença comportamental representa uma oportunidade estratégica para conversão.
#
#### Como esses insights ajudam a responder à pergunta de negócio:
“Como membros anuais e usuários casuais utilizam as bicicletas da Cyclistic de forma diferente?”

Os resultados mostram que:

•	Membros usam as bicicletas com mais frequência e regularidade

•	Usuários casuais fazem viagens mais longas, mas menos frequentes

•	Usuários casuais usam mais nos fins de semana

•	Membros usam mais durante dias úteis

•	Membros usam mais como meio de transporte diário

•	Usuários casuais usam mais como lazer

Esses insights indicam que usuários casuais podem ser convertidos em membros se perceberem valor em usar o serviço com maior frequência.

## 📋 5. Compartilhe
#### [Dashboard Tableau](https://public.tableau.com/views/CyclistAnualMembersvs_CasualUsersBehavior/Painel1?:language=pt-BR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 🧗‍♀️ 6. Atue
### Top 3 recomendações baseadas na análise
#### 1. Criar campanhas de marketing direcionadas a usuários casuais que utilizam o serviço com frequência
•	Usuários casuais que já utilizam o serviço regularmente são os candidatos mais prováveis à conversão. A Cyclistic pode usar campanhas digitais personalizadas, destacando os benefícios financeiros e a conveniência da assinatura anual em comparação com o pagamento por viagem.

•	Essas campanhas podem ser veiculadas por meio de e-mail marketing, notificações no aplicativo e anúncios digitais.

#### 2. Promover a assinatura anual como uma opção mais econômica para usuários recreativos
•	Como usuários casuais realizam viagens mais longas e frequentes durante fins de semana, a Cyclistic pode demonstrar claramente a economia gerada pela assinatura anual.

•	Por exemplo, a empresa pode mostrar comparações como:

- “Você poderia economizar X% com uma assinatura anual”

- “Usuários como você economizam em média $X por mês ao se tornarem membros”

•	Isso ajuda a transformar usuários recreativos em usuários recorrentes.

#### 3. Oferecer incentivos para conversão durante períodos de alto uso casual
•	Como o uso casual é maior durante fins de semana, a Cyclistic pode oferecer incentivos nesses períodos, como:

•	Testes gratuitos de assinatura anual por tempo limitado

•	Descontos promocionais na assinatura anual

•	Ofertas exclusivas para usuários casuais frequentes

•	Isso aproveita o momento em que o usuário já está engajado com o serviço, aumentando a probabilidade de conversão.

### Próximos passos recomendados

•	Para expandir esta análise, a Cyclistic poderia coletar dados adicionais, como:

- Frequência individual de uso por usuário

- Localização geográfica dos usuários

- Dados de campanhas de marketing anteriores

- Dados de conversão de usuários

•	Isso permitiria estratégias ainda mais direcionadas e eficazes.

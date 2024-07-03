# Projeto de scraping de dados via requests

## Situação
Imagine a seguinte situação:

É preciso informar ao cliente da consultoria política sobre o Presidente do Banco Central, Roberto Campos Neto, utilizando dados.

Para isso, são necessários os dados da agenda do Presidente do Banco Central desde 28 de fevereiro de 2023 até 28 de junho de 2024.

As informações devem ser apresentadas em uma tabela organizada e de fácil entendimento.

## Bibliotecas Utilizadas
- *requests*: lib para execução de requisições http com endpoints arbitrários
- *pandas*: lib para manipulação de matrizes (dataframes) e exibição ou exportação dos seus dados
- *re*: lib para utilização do regex na normalização de strings
- *html*: lib para manipulação de conteúdo html
- *time*: lib para manipulação de dados temporais e utilização de temporizadores

## Fluxograma
- Utilização da lib requests para fazer um http get à api do Banco Central, onde são obtidos dados da agenda do presidente da instituição
- Após a aquisição dos dados por meio de sucessivas chamadas à api, é feita a limpeza dos dados colhidos, normalizando os textos e formatando adequadamente com quebras de linha
- Normalizados os textos descritivos sobre a agenda do presidente, armazenamos esses dados em diferentes dataframes
  - Cada dataframe é responsável por um mês do prazo estipulado, onde cada coluna é um dia desse mês e as linhas são os diferentes eventos do dia
- Após gerados os dataframes, eles são então exportados para o formato do excel (.xlsx)

## Ideias anteriormente pensadas
- Utilização de BeatifulSoup: não é possível devido ao fato do site das agendas do Banco Central não utilizar state em URL
- Utilização de Selenium: devido à quantidade grande de dados, o script com essa lib teria muito pouco desempenho

  

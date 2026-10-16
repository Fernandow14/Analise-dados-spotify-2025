
# Análise Exploratória de Dados do Spotify

Projeto desenvolvido no Google Colab com Python, Pandas e Matplotlib para analisar o desempenho de músicas e artistas a partir de dados de reproduções.

## 🎯 Objetivo

Identificar músicas e artistas de destaque na base, comparando reproduções acumuladas, reproduções diárias, quantidade de registros e média de reproduções por artista.

## 🛠️ Tecnologias utilizadas

- Python
- Pandas
- Matplotlib
- Google Colab

## 🗃️ Base de dados

O arquivo `most_streamed_spotify_2025.csv` contém **730 registros e 10 colunas** e está disponível na pasta [`data`](./data/).

As informações incluem:

- Nome da música e do artista.
- Reproduções acumuladas.
- Reproduções diárias.
- Posições nos rankings acumulado e diário.
- Quantidade de artistas e indicador de colaboração.
- Relação percentual entre reproduções diárias e acumuladas.
- Posição no Top 10 do Spotify Wrapped, quando informada.

Apesar da referência a 2025 no nome do arquivo, a base não apresenta datas de coleta ou lançamento. Portanto, não foi possível confirmar o período abrangido pelas reproduções.

## ❓ Perguntas respondidas

1. Quais são as 10 músicas com mais reproduções acumuladas?
2. Quais são as 10 músicas com mais reproduções diárias?
3. Quais músicas aparecem nos dois Top 10?
4. Quais artistas somam mais reproduções acumuladas?
5. Quais artistas possuem mais registros na base?
6. Quanto os 10 maiores registros representam do total de reproduções acumuladas?
7. Entre os artistas com pelo menos 3 registros, quais possuem a maior média de reproduções acumuladas por registro?

## 🔎 Etapas do projeto

### 📥 1. Carregamento e organização

- Leitura do arquivo CSV com Pandas.
- Tradução dos nomes das colunas para português.
- Inspeção da estrutura e dos tipos de dados.

### 🧹 2. Verificação da qualidade

- Contagem de valores ausentes.
- Verificação de linhas completamente duplicadas.
- Investigação de combinações repetidas de música e artista.
- Definição dos critérios de preservação dos registros.

### 📊 3. Análise exploratória

- Cálculo de estatísticas descritivas.
- Construção dos rankings acumulado e diário.
- Cruzamento dos Top 10.
- Agrupamento de reproduções por artista.
- Contagem de registros por artista.
- Cálculo de participação percentual e médias.

### 📝 4. Apresentação

- Construção de gráficos de barras horizontais.
- Interpretação dos resultados.
- Registro da conclusão e das limitações no notebook.

## 🏆 Principais resultados

| Indicador | Resultado |
|---|---|
| Música com mais reproduções acumuladas | “Ordinary”, de Alex Warren: aproximadamente 1,95 bilhão |
| Música com mais reproduções diárias | “Man I Need”, de Olivia Dean: 3.075.070 |
| Músicas presentes nos dois Top 10 | 4 músicas, equivalentes a 40% das posições de cada ranking |
| Artista com maior total acumulado na base | Bad Bunny: aproximadamente 11,25 bilhões |
| Artista com mais registros | Bad Bunny: 15 registros |
| Participação dos 10 maiores registros nas reproduções acumuladas | 8,39% |
| Maior média por registro entre artistas com pelo menos 3 registros | HUNTR/X: aproximadamente 879,9 milhões |

## 🔗 Músicas presentes nos dois rankings

- “DtMF” — Bad Bunny.
- “BAILE INoLVIDABLE” — Bad Bunny.
- “The Fate of Ophelia” — Taylor Swift.
- “Man I Need” — Olivia Dean.

## 📐 Critérios de análise

### 🔁 Registros repetidos

Não foram encontradas linhas completamente duplicadas.

Foram identificadas quatro combinações de música e artista com duas ocorrências cada, totalizando oito linhas com valores diferentes de reproduções.

Essas ocorrências foram preservadas, pois a base não possui identificadores de faixa ou informações de versão suficientes para confirmar se são duplicidades.

Por esse motivo, as contagens são apresentadas como **quantidade de registros**, sem garantia de músicas únicas.

### 🔍 Valores ausentes

A coluna `Top 10 rank`, referente ao Wrapped, possui apenas três valores preenchidos e 727 ausentes.

Ela foi mantida sem preenchimento artificial e ficou fora das análises principais.

### 🧮 Média por artista

A média foi calculada dividindo a soma das reproduções acumuladas pela quantidade de registros de cada artista.

Foram considerados somente artistas com pelo menos três registros. Esse mínimo foi um critério definido para o projeto.

### 📊 Participação do Top 10

O percentual foi calculado pela fórmula:

**Participação do Top 10 = (reproduções acumuladas do Top 10 ÷ reproduções acumuladas da base) × 100**

Esse indicador mede participação nas reproduções. Já os 40% de sobreposição entre rankings medem a proporção de músicas em comum em cada Top 10.

## ⚠️ Limitações

- A ausência de datas impede análises de crescimento, evolução mensal e sazonalidade.
- As repetições preservadas podem afetar somas, médias e percentuais.
- A coluna colaboração apresenta possíveis inconsistências e não foi utilizado nas análises principais.
- Reproduções não representam ouvintes únicos nem necessariamente escolhas diretas dos usuários.
- A base contém registros com mais de 100 milhões de reproduções acumuladas e não representa todo o catálogo do Spotify.
- Os totais por artista correspondem somente aos registros disponíveis na base.

## 💡 Conclusão

A análise mostrou que o destaque depende do indicador escolhido. “Ordinary” liderou as reproduções acumuladas, enquanto “Man I Need” apresentou o maior volume diário informado.

Bad Bunny liderou tanto o total acumulado por artista quanto a quantidade de registros. HUNTR/X apresentou a maior média por registro entre os artistas que atenderam ao mínimo de três registros.

Os resultados demonstram a importância de combinar totais, quantidades, médias e percentuais para interpretar os dados, respeitando as limitações da fonte.

## 📚 Aprendizados

Durante o projeto, foram praticados:

- Leitura e exploração de arquivos CSV.
- Renomeação e seleção de colunas.
- Identificação de valores ausentes e repetições.
- Estatística descritiva.
- Agrupamentos com `groupby()`.
- Agregações com `sum()`, `size()` e `mean()`.
- Cruzamento de tabelas com `merge()`.
- Seleção de maiores valores com `nlargest()`.
- Cálculo de percentuais.
- Visualização com Matplotlib.
- Documentação e interpretação de resultados.

## 👤 Autor

**Fernando Dias**
  
LinkedIn: [Fernando Dias](https://www.linkedin.com/in/fernandodias-viana/)

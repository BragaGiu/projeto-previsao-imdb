# Projeto IMDb

Este repositório reúne uma análise completa sobre os fatores que impactam o sucesso de um filme e a construção de um modelo preditivo para estimar sua avaliação no IMDb.

O projeto nasceu de um desafio prático e combina análise exploratória de dados (EDA), modelagem de machine learning e interpretação de métricas de desempenho.

### Descrição dos arquivos

- **README.md**: documento de apresentação do projeto.
- **requirements.txt**: lista de bibliotecas necessárias para rodar o projeto de forma reprodutível.  
- **notebooks/LH_CD_GIULLIABRAGA.ipynb**: notebook principal, contendo a análise exploratória (EDA), a modelagem preditiva e as respostas às perguntas do desafio.  
- **reports/LH_CD_GIULLIABRAGA.pdf**: relatório em PDF exportado do notebook.
- **models/model.pkl**: modelo final treinado (XGBoost Regressor), salvo em formato pickle para reutilização sem necessidade de re-treino.  
- **data/desafio_indicium_imdb.csv**: dataset original fornecido no desafio.  
- **data/movies_metadata.csv**: informações complementares coletadas e integradas ao dataset principal.  
- **data/the_oscars_awards.csv**: dataset com dados sobre premiações no Oscar, usado para enriquecer a análise.  

## Análise Exploratória

A análise inicial permitiu identificar padrões relevantes nas variáveis. Entre os resultados, destacam-se:

- Filmes indicados e/ou ganhadores do Oscar, tendem a arrecadar mais do que filmes que não concorreram.
- Filmes dos gêneros Animation, Family, e Action tendem a gerar faturamentos mais altos.
- Filmes lançados em anos mais recentes tendem a ter, em média, um desempenho financeiro maior.
- A coluna de descrições (Overview) é capaz de inferir o gênero do filme de maneira parcial, dependendo do gênero e da quantidade dados disponíveis para análise.

## Modelagem

O problema foi tratado como regressão supervisionada, pois a variável alvo (IMDB_Rating) é contínua.
Foram testados diferentes modelos, como Regressão Linear Múltipla e Random Forest. O melhor desempenho foi obtido com o XGBoost Regressor.

## Previsões em Prática

O modelo foi testado com o exemplo fornecido no desafio: The Shawshank Redemption. A previsão resultou em uma nota 9.0. O modelo final foi salvo em arquivo `.pkl`, permitindo sua reutilização sem necessidade de re-treino.

## Como usar

1. Crie um ambiente virtual.  
2. Instale as dependências com:  
   ``pip install -r requirements.txt
3. Abra o notebook em notebooks/ para explorar a análise.
4. Caso queira testar previsões, carregue o arquivo salvo em models/model.pkl e utilize a função de predição com as variáveis do filme desejado.

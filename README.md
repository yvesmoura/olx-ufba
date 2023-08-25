
![code](https://img.shields.io/static/v1?label=python&message=3.8&color=blue)





<p align="center">
  <img src="reports/figures/olx-ufba.png" width="1000" title="img-principal">
</p>


# Apartment Price Prediction


1.  [Contexto do Problema](Contexto-do-Problema)
2.  [O Problema](O-Problema)
3.  [Entendimento do Problema](Entendimento-do-Problema)
4.  [Dados](Descrição-de-Dados)
5.  [Planejamento da Solução](Planejamento-da-Solução)
6.  [Hipóteses Principais](Hipóteses-Principais)
7.  [Algoritmos ML](Algoritmos-de-Machine-Learning-Aplicados)
8.  [Performace Modelos](Performace-dos-Modelos-de-Machine-Learning)
9.  [Resultados](Resultados)
10. [Entrega da Solução](#Entrega-da-Solucao)



# Contexto do Problema

O objetivo é desenvolver um modelo de machine learning que seja capaz de estimar com precisão o valor de um apartamento com base em várias variáveis ou características relevantes. Será extremamente útil para compradores, vendedores, corretores imobiliários e investidores, pois ajuda a tomar decisões informadas sobre transações imobiliárias.

este projeto visa explorar os anúncios de imóveis disponíveis no OLX. Ao extrair e analisar esses dados, será possível identificar tendências de preços, características populares e padrões de imovel

# O Problema

Você foi contratado como um Consultor de Ciência de Dados para criar um modelo de alta precisão para prever valores de apartamentos feitas através de dispositivos móveis.

Ao final da sua consultoria, você precisa entregar ao CEO um modelo em produção, ou seja, os clientes enviarão Características do apartamento via  dispositivos móveis para que o seu modelo estime um valor do imóvel




# Entendimento do Problema

**Motivação:** Reduzir a incerteza e a complexidade que muitas vezes envolvem o processo de compra ou aluguel de imóveis.

**Causa Raiz do Problema:** Falta de acesso a estimativas precisas e confiáveis de valor de imóveis

**Tipo de Problema:** Prever valor do apartamento.

**Potênciais Métodos:** Regressão.

**Entrega da Solução:** WebApp contendo a predição no huggingface.

# Descrição de Dados

O Dataset usado para este projeto possui 10 mil linhas e 26 colunas. Os dados contém:

| Atributo            | Significado                                                                     |
|---------------------|---------------------------------------------------------------------------------|
| bathrooms           | Número de banheiros no imóvel.                                                  |
| condominio          | Valor do condomínio do imóvel.                                                  |
| garage_spaces       | Número de vagas de garagem no imóvel.                                           |
| price               | Valor da transação em moeda local.                                              |
| rooms               | Número de quartos no imóvel.                                                    |
| size                | Tamanho do imóvel.                                                              |
| zipcode             | Código postal da localização do imóvel.                                         |
| re_types            | Tipo de imóvel (residencial/comercial).                                         |
| re_rent_full_price  | Preço total de aluguel do imóvel.                                               |
| condominio_fechado  | Indica se o imóvel está localizado em um condomínio fechado (Sim/Não).           |
| elevador            | Indica se o imóvel possui elevador (Sim/Não).                                   |
| permitido_animais   | Indica se animais de estimação são permitidos no imóvel (Sim/Não).               |
| piscina             | Indica se o imóvel possui piscina (Sim/Não).                                     |
| portaria            | Indica se o imóvel possui portaria (Sim/Não).                                    |
| portao_eletronico   | Indica se o imóvel possui portão eletrônico (Sim/Não).                           |
| salao_de_festas     | Indica se o imóvel possui salão de festas (Sim/Não).                             |
| seguranca24_h       | Indica se o imóvel possui segurança 24 horas (Sim/Não).                          |
| academia            | Indica se o imóvel possui academia (Sim/Não).                                    |
| area_murada.1       | Indicação não clara - talvez seja área murada?                                   |
| ar_condicionado     | Indica se o imóvel possui ar condicionado (Sim/Não).                             |
| armarios_na_cozinha | Indica se o imóvel possui armários na cozinha (Sim/Não).                          |
| armarios_no_quarto  | Indica se o imóvel possui armários no quarto (Sim/Não).                           |
| churrasqueira       | Indica se o imóvel possui churrasqueira (Sim/Não).                                |
| mobiliado           | Indica se o imóvel é mobiliado (Sim/Não).                                         |
| quarto_de_servico   | Indica se o imóvel possui quarto de serviço (Sim/Não).                            |
| varanda             | Indica se o imóvel possui varanda (Sim/Não).                                      |
| area_de_servico     | Indica se o imóvel possui área de serviço (Sim/Não).                              |

# Planejamento da Solução

**1. Descrever os Dados:**

- Carregar os dados e entender as variáveis disponíveis e verificar possíveis valores faltantes e inconsistências.
- Realizar uma estatística descritiva para entender as características dos dados.

**2. Levantar Hipóteses:**

- Criar Hipóteses sobre as características e o comportamento.
- Realizar uma Feature Engineering para criar novas variáveis.

**3. Filtrar Dados:**

- Filtrar linhas e colunas de acordo com as restrições de negócio e com as premissas assumidas.

**4. Realizar Análise Exploratória de Dados:**

- Validar ou refutar as hipóteses através dos dados.
- Identificar correlação entre variáveis e a variável resposta.
- Obter insights.

**5. Preparar os dados**

- Fazer o reescalonamento das variáveis e aplicar Encoding.

**6. Selecionar as melhores Features**

- Usar o algoritmo Boruta para selecionar as features mais importantes e low variance.

**7. Modelagem de Machine Leaning**

- Treinar, aplicar cross validation nos algoritmos e validar a partir de métricas apropriadas.

**8. Ajustar os Hiperparametros**

- Encontrar a melhor combinação de parametros para o modelo final usando a técnica de Optuna.

**9. Traduzir e Interpretar o erro**

- Transformar a performace de Machine Leaning para resultado de Negócio, respondendo as perguntas de negócio feitas.

**10. Deploy do Modelo em Produção**

- Deixar o modelo acessível utilizando huggingface via webApp.

## 💻 Machine Learning Modeling & Evaluation

 * Cross Validation
 
  *Performance on 5 K-Fold CV.*

|   Model Name     |   MAE TRAIN            |   MAE TEST            |   MAPE TRAIN           |   MAPE TEST            |   RMSE TRAIN           |   RMSE TEST            |
|------------------|------------------------|-----------------------|------------------------|------------------------|------------------------|------------------------|
| VotingRegressor  | 47684.34 +/- 246.64    | 60954.08 +/- 1216.24  | 0.14 +/- 0.00          | 0.18 +/- 0.00          | 61554.88 +/- 265.29    | 81205.50 +/- 1700.72   |
| XGBRegressor     | 81185.86 +/- 549.65    | 82370.33 +/- 1719.77  | 0.23 +/- 0.00          | 0.24 +/- 0.01          | 103319.89 +/- 685.40   | 104784.58 +/- 2059.22  |

# Algoritmos de Machine Learning Aplicados

Os modelos treinados foram:
- Random Forest
- XGB

O modelo com performance mais alta e custo benefício escolhido para resolver o problema de Prever valor do apartamento foi o **XGB**, mesmo o VotingRegressor tendo a maior performance a diferença entre o treino e o teste é grande e pode ter overfitting.

# Entrega da Solução


[olx-ufba](https://huggingface.co/spaces/yvesmoura/olx-ufba)

# Melhorias

* Conseguir mais dados para treinar o modelo. pois estamos utilizando apenas 10 mil linhas
* Exploração mais profunda: Ao realizar a Análise Exploratória de Dados (EDA)
* Testar diferentes algoritmos
* Feature Engineering
* Monitoramento do modelo em produção 

# Stack utilizada

**Back-end:** Python,Docker

**Design** Figma

**IDE** Visual Code, Jupyter Notebook

**Bancos de Dados** MongoDB

**Ferramentas de Visualização** PowerBI

**Agendamento de Tarefas** Airflow

**Web Scraping e Automação** Selenium e BeautifulSoup

**Comunicação e Colaboração** Git

**Deploy** Huggingface


## 🔗 References

1. Data Science Process Alliance - [What is CRISP-DM](https://www.datascience-pm.com/crisp-dm-2/)
2. Olx  - [Anúncio de apartamentos](https://www.olx.com.br/imoveis/venda/apartamentos/estado-ba/grande-salvador/salvador)
3. Bulldogjob - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


<br>

Se você tiver alguma outra sugestão ou dúvida, não hesite em entrar em contato comigo através do [LinkedIn](https://www.linkedin.com/in/yves-moura-99b231187/).

<br>

## ✍🏽 Author

- [@ylmoura](https://github.com/ylmoura)


[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yves-moura-99b231187/) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yvesluan016@gmail.com) [![kaggle](https://img.shields.io/badge/Kaggle-3776AB?style=for-the-badge&logo=Kaggle&logoColor=white)](https://www.kaggle.com/yvesmoura)

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

***

## 💪 How to contribute

1. Fork the project.
2. Create a new branch with your changes: `git checkout -b my-feature`
3. Save your changes and create a commit message telling you what you did: `git commit -m" feature: My new feature "`
4. Submit your changes: `git push origin my-feature`


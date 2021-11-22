 # Chrun Prediction

Our goal in this project is to provide a prediction in order to prevent future clients to leave the company. 
To achieve this intention we'll use some machine learning algorithms to anticipate the probability of the customer to leave after that well use the Gain curve
to drawn our scenarios 

The result of our project is this scenario.

![Captura de tela de 2021-11-22 09-52-00](https://user-images.githubusercontent.com/46419374/142865055-0fd66d46-168e-4c9c-be3b-5b883ea8c541.png)

**The project is located in the following link:** https://github.com/denisshiki/churn_prediction/blob/main/churn.ipynb
___
### Business Context:

Topbank is a company that offer bank a diverse type of services to other countries of europe, starting for business loans, insurance, wealth management and so on.

The major product of the company is the bank account, using this service the client can deposit it's salary, make loans, see the balance etc. and this bank account has a limit of 12 months if that limit expires he has to renovate the contract in order to use the company services.

___
### Business Question:

You belong to the data science team and your job is to prevent the customers to leave the company, but before solve the problem you have to ask those tree questions.

- __Motivation:__ What is the motivation of this problem, so we ask to our superiors about who made this problem and what the context, different from other problems, in this project the motivation is more simple and easy to understand. 

- __Root Case:__ After understanding the motivation of the problem that we'll try to understand this root case, so we talk to other people of the company and discover that the income of the company is decreasing and one of the main case is because the clients are leaving the company.
 
- __Deploy:__ Understanding the root case, we'll negotiate about the product that we'll deploy, because it's our first CRISP cycle we'll deploy only a result and in our next cycles we'll deliver a better data product.

___
### Ciclo CRISP

Like other projects in this we'll use the CRIP method, for further explanation see the link below: <br>
https://www.ibm.com/docs/en/spss-modeler/SaaS?topic=dm-crisp-help-overview

The goal of this method is to repeat the cycle until the project is finished, each cycle is composed by end to end projects and delivered the data product according to what we promissed, and each cycle has follow this schema below:

![Captura de tela de 2021-10-22 16-08-23](https://user-images.githubusercontent.com/46419374/138510162-7bf05413-c5ad-495f-94bd-aebbfb8fc897.png)

- **Business Understanding:** This stage we define talk to other teams in order to identify the problem and the solution that we'll deploy.
 
- **Data mining:** In this moment we'll search for the data that will help us in this project, in this exercise we'll use the data provided by the Kaggle platform.
 
- **Data Cleaning:** In this stage we'll clean the data removing the NaN values and we'll verify the type of our data, descriptive statistics and columns renaming.

- **Data Exploration:** We'll make and business hipothesis in order to give us scalable insights for the company this will help us too se the data in other perspective and give more ideas about future projects.

- **Data Modelling:** This we'll make the transformation, reescaling and outliers verification in some variables, tendo este o intuito de tratar os dados para os algoritmos de "Machine Learning". 

- **Machine Learning Algorithms:** We'll apply some machine learning algorithms and metrics in order to evaluate wich is the best.

- **Machine Learning Evaluation:** After select our model we will evaluat how is our income scenarios, this is an important step bacause it will determined if we'll follow our project or no.
 
___
### Data:

The data were extrated from the kaggle platform in the link below: 
https://www.kaggle.com/c/rossmann-store-sales

Contendo os seguintes atributos:

|***Atributo*** | ***Descrição*** |
| -------- | --------- |
|**RowNumber**| Number of the column.|
|**CustomerID**| Id of the client |
|**Surname**| Client surname |
|**CreditScore**|The core credit of the client |
|**Geography**| The country that he/she lives |
|**Gender**| The client gender |
|**Age**| The client age |
|**Tenure**| the time o tipos de lojas, sendo estas a, b, c, d |
|**Assortment**| Indica a variedade de produtos por levels, sendo esses: a = básico, b = extra, c = extendido |
|**CompetitionDistance**|distância em metros com a loja competidora próxima |
|**CompetitionOpenSince[Month/Year]**| Indica o o ano e mês aproximado que o competidor mais próximo abrir a loja |
|**Promo**| Indica se a loja abriu uma promoção naquele dia | 
|**Promo2**| Indica se a loja continuou a Promo: 0 = Loja não está participando, 1 = Loja está participando |
|**Promo2Since[Year/Week]**| Descreve o ano e semana que a loja participou da promo2 |
|**PromoInterval**| Descreve os meses consecutivos que a loja participou da promoção.| 

___
### Business Premisse:

Antes de analisarmos os dados teremos que conhecer do negócio que estamos lidando, para isso podemos tanto conversar com outras equipes da empresa, realizando uma reunião com estas no intuito de tirar dúvidas e gerar "insights" ou então podemos estudar o negócio e gerar essas dúvidas e ideias nós mesmos. Como atualmente não temos contato com outras áreas iremos optar por pesquisar sobre o negócio e então retirar nossos "insights".

Uma das formas de gerar insights para o negócio é realizando um "mapa mental" como na imagem abaixo

![Captura de tela de 2021-10-22 14-59-40](https://user-images.githubusercontent.com/46419374/138501756-a4d9bb5f-9932-42ea-a9bb-9b62173ac194.png)

Esse aspecto será importante pois é a partir do levantamento desse mapa mental que iremos validar as hipóteses de negócios presente na etapa de análise exploratória dos dados. 

___
## Planejamento da solução:

Com o problema de negócio e o produto de entrega definido, iremos agora partir para a parte de execução: 
___
### Descrição dos Dados:

Nesta iremos realizar uma análise descritiva dos dados, executando as seguintes etapas:

 - Renomear os algumas colunas dos dados
 - Verificação da dimensão dos dados
 - Verificação dos tipos de dados
 - Alteração dos valores "NaN"
 - Estaísticas descritivas   
___
### Feature Engeneering:

Nesta realizaremos o levantamento de hipóteses ocorridas durante a montagem do mapa mental na etapa de premissa do negócio, outro aspecto que realizaremos é a "feature engeneering" que é a criação de variáveis que serão utilizadas na etapa de "Análise Exploratória".
___
### Filtragem de Variáveis:

Nesta filtraremos algumas variáveis, selecionand os dados com os seguintes atributos:
 - Vendas maiores que 0.
 - Lojas abertas. 
 - Eliminação da coluna "open" e "promo_interval".
___
### Análise Exploratória dos dados:

Esta geralmente é parte em que mais dedicamos tempo sendo que nesta etapa é a que faremos a validação ou não das hipóteses de negócios levantadas anteriormente na etapa de premissa dos negócios, sendo estas:  

  - __Análise Univariada:__ Nesta analisamos cada variável sozinha sem nenhuma relação com outras variáveis, observando como estas se comportam ou como se distribuem no gráfico.

  - __Análise Bivariada:__ Nesta etapa é a que verificamos as hipóteses de negócios, sendo que nesta iremos relacionar a variável de vendas com outras variáveis e verificar se existe uma correlação entre ambas ou não, trazendo essas correlações insights que possam ser acionáveis para os outros times.  

 | __Hipótese__ | __Resultado__ | __Tradução para negócio__ |
 | ------------ | ------------ | ------------ |
 | __H1__ - Loja com maior sortimento (diferentes tipos) tem mais vendas? | Falsa | Supondo que a versão extra é a que contém mais tipos de sortimentos, esta afirmação é falsa, pois o sortimento extra representa uma soma de vendas menor que as com menores variedades. |
 | __H2__ - Lojas com competidores mais próximos, deveriam vender menos? | Falsa | Lojas com competidores próximos vendem mais do que com competidores distantes. |
 | __H3__ - Lojas com concorrentes a mais tempo vendem mais? | Falsa | Há um crescimento das vendas quando ocorre uma abertura de um concorrente próximo e com o tempo as vendas tendem a cair com a prensença de competidores. |
 | __H4__ - Lojas com promoções ativas a mais tempo tendem a vender mais? | Falsa | Quanto mais tempo a promoção ativa menor é o valor de venda. |
 | __H5__ - Loja que tem promoções vendem mais? | Falsa | Lojas que não contém promoções tem uma quantidade média de vendas ligeiramente maior que as lojas com promoções, assim como veremos que a distribuição média de vendas de produtos entre lojas que realizaram a promoção não é distante das lojas que não realizaram esta. |
 | __H6__ - Loja com promoções consecutivas vender mais? | Falsa | Lojas que participam de uma promoção consecutiva contém uma soma de faturamento não muito discrepante das lojas que não participaram das promoções.|
 | __H7__ - Lojas deveriam vender mais no fim de semana do que durante a semana? | Falsa | O que ocorre é uma diminuição na soma de vendas com o passar da semana, sendo que no domingo (dia 7) ocorre uma diminuição brusca das vendas.|
 | __H8__ - Lojas vendem mais nos feriados? | Falsa | Não vemos nenhuma diferença significativa na média de vendas havendo um feriado ou não.|
 | __H9__ - Lojas vendem mais com o passar dos anos? | Falsa | Houve uma diminuição da soma de vendas durante os anos. |
 | __H10__ - Lojas abertas durante o natal, deveriam vender mais? | Falsa | Podemos ver que a média de vendas durante o natal é menor que outros feriados. |
 | __H11__ - Lojas vendem mais antes do dia 10 de cada mês? | Falsa | Não vemos nenhuma indicação de que ocorre um aumento da soma de vendas antes do dia 10, o que vemos é um aumento de vendas depois do dia 10. |
 | __H12__ - Lojas vendem mais durante o segundo semestre do ano? | Falsa | Vemos que há uma tendência de queda da soma de vendas a partir do mês 7 e não de subida como esperávamos. |

  - __Análise Multivariada:__ Nesta realizamos a relação entre diversas variáveis, nos gerando uma panorama geral de como estas se relacionam.

Ao realizarmos os testes de hipóteses, selecionamos algumas variáveis que consideramos relevantes e das quais explicam em grande parte o comportamento do negócio, essa seleção se dá mais de maneira emppírica, sendo necessária a experiência sobre o negócio a ser resolvido.
___
### Preparação dos Dados:

Após realizar o selecionamento de váriáveis em seguida iremos realizar o tratamento dos dados, nesta transformamos todas as variáveis categóricas em numéricas assim como colocaremos algumas variáveis numéricas em uma faixa de valores pré estabelecida, resultando nas seguintes etapas:
  - __Normalização:__ Verificamos se a variável de interesse (sales) tem um comportamento normal.
  - __Rescalonamento:__ Reescalonamento as variáveis numéricas eliminando nesta a presença de outliers e transformando os dados numéricos em uma faixa de valores entre 0 e 1.
  - __Transformação:__ Nesta iremos transformar os dados cíclicos (Mês, dia, semana, semana_ano) em valores numéricos.
  - __Encoding:__ Tranformação dos dados categóricos em numéricos.
___
### Seleção de Variáveis:
Feita a preparação dos dados para os algoritmos de "Machine Learning" iremos agora selecionar as variáveis (colunas) que iremos inserir em nossos algoritmos. Nesse primeiro ciclo do CRISP, iremos aplicar o algoritmo BORUTA para a seleção das variáveis que serão utilizadas no modelo de "Machine Learning". 

**Observação:** Como este é o primeiro ciclo do CRISP iremos inicialmente pegar o resultado do algoritmo BORUTA e aplicar nos modelos, sendo que nos proximos ciclos iremos fazer uma melhor seleção das variáveis de acordo com o negócio.
___
### Modelos Machine Learning:

Nesta iremos finalmente aplicar os algoritmos de Machine Learning, utilizando como "output" as métricas MAE, MAPE e RMSE no link:
https://towardsdatascience.com/forecast-kpi-rmse-mae-mape-bias-cdc5703d242d

Outro método que utilizaremos durante o treino de nossos modelos é o "cross validation", descrito no link:
https://scikit-learn.org/stable/modules/cross_validation.html

Sendo que neste projetos utilizamos 5 modelos, sendo esses:
  - **Modelos Lineares:**
  
      - **Média:** Este modelo nos gera uma média das métricas utilizadas, sendo este um modelo base para comparar o desempenho dos outros.
      - **Linear Regression Cross Validation** 
      - **Linear Regression Lasso Cross Validation**
     
  - **Modelos Não Lineares**
      - **Random Forest Cross Validation**
      - **XBoost Regressor Cross Validation**
  
Poderíamos treinar mais modelos, mas como temos o intuito de fazer a primeira entrega desse ciclo o mais rápido possível, resolvemos treinar o nosso modelo somente com esses cinco algoritmos e então escolhemos qual teve o melhor desempenho, considerando tanto o tempo levado como o consumo de memória. Com isso consideramos o modelo XGBoost mais adequado.

___
### Seleção de Hiperparâmetros:
Após a seleção dos modelo de Machile Learning á ser seguido, iremos agora selecionar os hiperparâmetros desse algoritmos, sendo estes variáveis que o algoritmo precisa como "input" para que este possa nos gerar um resultado desejado. Esta etapa é mais uma correção fina do modelo, caso o modelo tenha uma performance muito ruim, é necessário voltar para o problema de negócio e selecionar as variáveis mais adequadas. 

___
### Interpretação do Erro e Resposta para a pergunta de Negócio:
Após treinar e prever o modelo, nessa etapa iremos finalmente responder a pergunta do negócio e gerar um resultado financeiro que podemos alcançar caso a empresa deseje seguir com o nosso modelo. Resultando este na tabela abaixo citada anteriormente:

| __Melhor Cenário__ | __Pior Cenário__ | __Previsão__ |
| ----------------- | ----------------- | ----------------- | 
| R$ 288.554.280,06 | R$ 286.397.838,89 | R$ 287.476.064,00 |

Outra coisa que realizamos é o quão bem o algoritmo previsto performou comparado as variáveis existentes, gerando o gráfico abaixo:
![Captura de tela de 2021-10-23 12-16-53](https://user-images.githubusercontent.com/46419374/138562112-7fdc1ef2-6ac9-4539-ac00-872d6788259c.png)
Vimos que ainda é necessário uma melhor seleção de variáveis para se ter uma melhor performance nos modelos, sendo este algo que faremos no pŕoximo ciclo do CRISP.
___
##  Conclusão:

O projeto tem como princípio responder a questão de negócio assim gerar um projeto de ciência de dos "End-to-End" utilizando o método CRISP como guia, nele geramos e validamos algumas hipóteses de negócios, preparamos os dados para os algoritmos de "Machine Learning" e por fim aplicamos alguns algoritmos selecionados e verificamos quais os financeiros gerados pelo modelo escolhido, lembrando que iremos passar mais vezes por esse ciclo com o intuito de melhorar o modelo para trazer melhores resultados para a empresa.

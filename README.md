 # Chrun Prediction

Our goal in this project is to provide a prediction in order to prevent future clients to leave the company. 
To achieve this intention we'll use some machine learning algorithms to anticipate the probability of the customer to leave after that well use the Gain curve
to drawn our scenarios 

The result of our project is this scenario.

| __Best Scenario__ | __Real Scenario__ | __Worst Scenario__ |
| ----------------- | ----------------- | ----------------- | 
| R$ 288.554.280,06 | R$ 286.397.838,89 | R$ 287.476.064,00 |

**The project is located in the following link:** https://github.com/denisshiki/churn_prediction/blob/main/churn.ipynb
___
### 🏢 Business Context:

A Houssman Store é uma plataforma digital que tem como modelo de negócio e a venda de produtos diversos, sendo que para melhorar o seu faturamentos, eles começaram a utilizam a tecnologia no intuito de gerar dados, tendo este dois objetivos; analisar as melhores oportunidades de negócios, aumento do faturamento a partir destes.

O objetivo do case é fornecer um modelo de previsão da venda de produtos, dando este suporte para as futuras decisões da empresa, podendo esta acatar ou não as previsões feitas por esse modelo, assim como verificar se este condiz com a realidade das vendas caso a empresa resolva seguir com este modelo.

___
### 👨‍💼 Questão do negócio:

Como você é um dos poucos integrantes da equipe de ciência de dados da empresa, em um belo dia os gerentes começaram a te ligar pedindo uma previsão de vendas nas próximas seis semanas, antes de iniciar executando imadiatamente a tarefa que lhe foi cabida, você primeiro conversou com os gerentes, percorrendo os três passos abaixo:

- __Motivação:__ qual foi a motivação que os gerentes tiveram para realizar essa requisição. Durante a conversa com estes percebemos que a motivação foi o pedido feito pelo CEO da empresa.

- __Causa Raiz:__ Entendido a motivação iremos na causa raiz, ou seja, iremos conversar com o CEO e verificar o porque este realizou esta requisição, ao entrarmos em contato com este, vimos que ele realizou esse pedido pois gostaria de utilizar o lucro gerado para reformar as lojas preexistentes.
 
- __Formato da Solução:__ Entendido a causa raiz com o CEO, iremos agora combinar o formato de entrega com ele, como no mundo nos negócios tudo é negociável, dissemos  que para ter uma velocidade maior, iremos entregar nesse primeiro ciclo uma tabela contendo o faturamento total previsto com o pior e melhor cenário, para assim ele ter uma idéia do quanto de dinheiro irá chegar na empresa para então realizar a decisão de reformar ou não as lojas ou em quais lojas reformar.
___
### Ciclo CRISP

Um método que utilizaremos tanto neste como em outros projetos de portfólio é o método CRISP (Cross Industry Standard Process for Data Mining,)presente no link abaixo: <br>
https://www.ibm.com/docs/en/spss-modeler/SaaS?topic=dm-crisp-help-overview

O objetivo desse método é passar pela mesma tarefa várias vezes, tendo cada ciclo "end to end", nos dando esse ciclo uma velocidade de entrega assim como o mapeamento de possíveis problemas a serem ocorridos futuramente, sendo que o ciclo que montamos nesse projeto tem o seguinte desenho esquemático:

![Captura de tela de 2021-10-22 16-08-23](https://user-images.githubusercontent.com/46419374/138510162-7bf05413-c5ad-495f-94bd-aebbfb8fc897.png)

**Observação:** Apesar do ciclo ser o mesmo é bom lembrar que a manipulação dos dados depende do tipo de problema que queremos resolver, portanto é recomendado entender os dados antes de fazer qualquer alteração.

- **Questão e Entendimento do Negócio:** Nessas etapas como dito anteriormente realizaremos uma conversa com as outras equipes para identificar a fonte do problema e definimos o formato da solução.
 
- **Coleta de Dados:** Neste realizaremos ou uma busca do banco de dados da empresa ou então buscaremos dados fora destas, sendo que nesse projeto os dados foram fornecidos pela plataforma "Kaggle".
 
- **Limpeza dos Dados:** Realizaremos um preenchimento dos dados faltantes, assim como verificaremos os tipos de dados, estatísticas descritivas e renomeação de colunas.

- **Exploração dos Dados:** Essa é uma das etapas em que realizaremos o levantamento das hipóteses no intuito de gerar "insights" que sejam escaláveis para a empresa, outro aspecto que iremos realizar é a criação de variáveis e verificação de hipóteses.

- **Modelagem dos Dados:** Nesta realizaremos a rescalonação, transformação e eliminação "outliers" em algumas variáveis, tendo este o intuito de tratar os dados para os algoritmos de "Machine Learning". 

- **Algoritmo de Machine Learning:** Nesta aplicaremos alguns algoritmos utilizando o método "Cross Validation".

- **Avaliação de Algoritmos:** Neste analisamos a performance dos algoritmos e então verificamos qual o seu resultado monetário.
 
___
### 📚 Dados:

Os dados foram extraídos da plataforma "Kaggle", usando o link abaixo:

https://www.kaggle.com/c/rossmann-store-sales

Contendo os seguintes atributos:

|***Atributo*** | ***Descrição*** |
| -------- | --------- |
|**Id**| Identificação que representa a dupla (data, loja).|
|**Store**| Identificação da loja |
|**Sales**| vendas da loja naquele dia |
|**Customers**|Número de clientes no dia |
|**Open**| Indicador se a loja está aberta ou fechada: 0 = fechada, 1 = aberta |
|**StateHoliday**| Indicador da presença de feriados, sendo estes. a = ferados públicos, b = Páscoa, c = Natal, 0 = Nenhum |
|**SchoolHoliday**| Indica se há ou não a presença de feriados escolares: 0 = não, 1 = sim. |
|**StoreType**| diferentes tipos de lojas, sendo estas a, b, c, d |
|**Assortment**| Indica a variedade de produtos por levels, sendo esses: a = básico, b = extra, c = extendido |
|**CompetitionDistance**|distância em metros com a loja competidora próxima |
|**CompetitionOpenSince[Month/Year]**| Indica o o ano e mês aproximado que o competidor mais próximo abrir a loja |
|**Promo**| Indica se a loja abriu uma promoção naquele dia | 
|**Promo2**| Indica se a loja continuou a Promo: 0 = Loja não está participando, 1 = Loja está participando |
|**Promo2Since[Year/Week]**| Descreve o ano e semana que a loja participou da promo2 |
|**PromoInterval**| Descreve os meses consecutivos que a loja participou da promoção.| 

___
### 💼 Premissas do negócio:

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

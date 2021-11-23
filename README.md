 # Churn Prediction

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
### CRISP Cicle

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


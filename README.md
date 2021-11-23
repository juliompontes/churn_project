# Entendendo o churn em clientes de serviços bancários

## Análise exploratória de dados para entender o que leva os clientes a cancelarem os serviços prestados por um banco e aplicação de modelos de Machine Learning para "prever" potenciais casos de churn

### Visão geral do projeto

O projeto tem como base o dataset "Predicting Churn for Bank Customers" - disponível [nesse link](https://www.kaggle.com/kmalit/bank-customer-churn-prediction/data) - que traz dados sobre clientes de uma instituição bancária hipotética. O dataset contém dados de 10 mil clentes e 14 variáveis (atributos) para análise, incluindo a variável-alvo ("Exited").

Após o contato inicial com o dataset - em que não foi verificada a necessidade de grandes limpezas, o que é bem raro -, foi realizada uma análise exploratória dos dados (AED). A AED nada mais é do que a aplicação de uma série de métodos e análises estatísticas para conhecer as variáveis e entender melhor como elas se relacionam uma com as outras. A partir da AED, pode ser observado, por exemplo:
* **trata-se de um dataset desbalanceado em relação à variável-alvo (informação fundamental para a aplicação dos modelos de Machine Learning)**;
* **existe algo próximo de um perfil do cliente que opta pelo churn** - *clientes localizados na Alemanha, do gênero feminino, que não são membros ativos do banco, com acesso a apenas 1 produto, com idades mais avançadas e com score de crédito baixo* -; e
* **outras variáveis pouco ou nada interferem na decisão do cliente em cancelar o relacionamento com o banco**.

Após o registro das informações acima e muitas outras geradas através da AED, passou-se para a etapa de modelagem. Após a adequação das variáveis (categóricas e quantitativas) e a divisão do dataset em fatias de treino e teste, foram experimentados 3 modelos de Machine Learning para lidar com esse problema de classificação - **Regressão Logística, Random Forest e Extreme Gradient Boosting Classifier**. Cada um desses 3 modelos foi aplicado e tunado (escolha dos parâmetros que entregam o melhor resultado). Após o tuning dos modelos, foram analisadas diversas métricas - **resultados das previsões (visualizadas na matriz de confusão), acurácia, precisão, recall, curva ROC** - para escolher o modelo que entrega o melhor resultado.

Principalmente pelos melhores resultados nas métricas de *recall* e *curva ROC* o modelo **Extreme Gradient Boosting Classifier** sobressaiu e foi escolhido como modelo a ser aplicado para resolver o problema. Assim foi possível aplicar o modelo ao dataset de teste e gerar um novo dataset com o ID de cada cliente associado à probabilidade desse cliente dar churn (probabilidade essa gerada pelo modelo Extreme Gradient Boosting Classifier).

Essa é uma possível utilização da **Análise Exploratória de Dados** e de **Machine Learning** para o benefício de um negócio real. Nesse sentido, o banco poderia se beneficiar de uma menor taxa de churn, consequentemente uma maior taxa retenção de clientes, o que poderia levar ao aumento do faturamento, à melhoria da imagem do banco, à manutenção da carteira de clientes e assim por diante.

### Como esse projeto pode ser aplicado para resolver um problema?

Tendo em mente que o problema em questão era como o banco poderia melhorar a sua taxa de retenção de clientes, através da redução do churn, o projeto gerou 3 resultados concretos:
1. entendimento profundo sobre as características dos clientes que deram churn, obtido através da análise exploratória;
2. modelo de machine learning feito sob medida para usar as variáveis disponibilizadas pelo dataset e prever se um cliente está próximo de dar churn ou não;
3. novo dataset com a probabilidade de churn associada a cada cliente do banco.

Nesse projeto foi possível observar que 42% dos clientes que deram churn de fato estão classificados com probabilidades acima de 60% de risco de churn. Em um cenário com novos dados, clientes nessa faixa de risco poderiam ser alvos de alguma ação de retenção, como, por exemplo a oferta de algum outro produto ou o convite para se tornarem membros ativos do banco (ambas características associadas a um menor risco de churn). Dessa forma, trabalharia-se em prol da retenção dos clientes do banco com ações mais direcionadas.

Uma forma de comprovar a importância desse trabalho seria, por exemplo, medir as taxas de churn antes e depois das ações de retenção aplicadas a partir da realização do estudo.

### Tecnologias

- [x] Python - bibliotecas **Pandas** e **Numpy** para trabalhar com os dados; **MatPlotLib**, **Seaborn** e **Plotly** para visualização dos dados; e **Scikit-learn**, **SciPy** e **XGBoost** para a aplicação do modelo de Machine Learning e a análise das métricas de resultados.
- [x] Jupyter Notebook

### No que você deve ficar de olho :eyes:

* :bulb: Análise exploratória de dados gerando vários **insights** sobre os clientes do banco e identificando um perfil dentre aqueles que deram churn
* :mechanical_arm: Aplicação e **tuning automatizado** dos 3 modelos de ML escolhidos
* :mortar_board: Interpretação das **métricas de avaliação do desempenho** dos modelos de ML
* :chart_with_upwards_trend: Entrega: **novo dataset com probabilidade de churn de cada cliente** do dataset de teste


### Por que realizar esse projeto?

O desafio do projeto que despertou minha vontade de realizá-lo é o de conseguir **explicitar a relação das variáveis do dataset com a variável-alvo (churn)**. Com a experiência de trabalho em empresas que possuo, percebi que muitas vezes é difícil deixar claro para os gestores como dados podem ser utilizados para tomar decisões. Uma das formas de fazer isso é mostrar, com tabelas, gráficos e outras visualizações, como uma ou mais características se relacionam com a categoria alvo, em termos de quantitativos. E nem sempre é simples mostrar essas relações, dada o grande número de possibilidades e outros fatores. Mas uma boa análise exploratória dos dados é capaz de iluminar algumas dessas relações entre as variáveis.

Além disso, era fundamental gerar um resultado concreto a partir das análises e da aplicação dos modelos de Machine Learning. Esse objetivo foi alcançado com a **criação do dataset com a probabilidade de churn associada a cada cliente** do dataset de treino. Isso mostra ser possível reproduzir o modelo para novos clientes e realizar ações de retenção tendo como base os clientes apontados com as maiores probabilidades de churn. 


Regressão Linear Manual e Gradient Descent. 

A ideia é usar as formulas matematicas de ambos métodos em vez de bibliotecas prontas.


Passos para Execução

1. Regressão Linear Manual
Geração de Dados:

Eu criei um conjunto de dados sintéticos com 1000 amostras, onde a variável dependente Y é uma função linear de X com um pouco de ruído adicionado.

O modelo é 𝑌 = 12.467 + 5.3 ⋅ 𝑋 + 𝜖, onde ϵ é o ruido.

Adição de Termo de Interceptação:

Também adicionei uma coluna de 1 à matriz de entrada X usando a função add_dummy_feature() da sklearn.

Cálculo dos Parâmetros:
Utilizei a fórmula da regressão linear 

𝜃=(𝑋^(𝑇) @ 𝑋)^(−1)𝑋^(𝑇)𝑌 

para calcular os parâmetros θ.

Predição e Visualização:

Fiz a predição para um novo conjunto de dados e então visualizei os resultados, incluindo o erro quadrático médio (MSE) usando a formula 

mse = (1/n)(y - X𝜃)^2

Resultado:

O modelo gerado tem uma boa aproximação dos coeficientes reais e o resultado do MSE foi de 1.01.

LinearRegression:

Treinamento com LinearRegression:

Usei o modelo LinearRegression da sklearn para comparar com os meus modelos.
Treinei o modelo com o mesmo conjunto de dados e obtive um MSE de 1.0467249181812295, com interceptação de 12.45155644 e coeficiente de 5.33025007.

2. Gradient Descent
   
Inicialização:

Similar à abordagem anterior, criei os dados e adicionei o termo de interceptação.

Cálculo via Gradient Descent:

Inicializei aleatoriamente os parâmetros θ e utilizei o algoritmo de Gradient Descent para reducir a função de custo (MSE).

Coloquei a taxa de aprendizado η = 0.01 e o número de iterações (épocas) foi colocado em 1000.

Resultado:

Após 1000 épocas, os parâmetros θ se aproximaram muito bem dos valores reais:

Interceptação: 12.43

Coeficiente: 5.29


Stochastic Gradient Descent (SGD) Manual

Implementação Manual do SGD:

Para a implementação manual do Stochastic Gradient Descent, inicialmente, coloquei os parâmetros θ como aleatorio.

A cada iteração, peguei um valor aleatório de X e Y, calculei o gradiente da função de custo para essa amostra, e atualizei os parâmetros θ.

Resultado:

Após o treinamento, os parâmetros θ se aproximaram dos valores reais:

Interceptação: 12.44

Coeficiente: 5.29


Mini-Batch Gradient Descent:

Também usei o Mini-Batch Gradient Descent.

Dividi os dados em mini-batches e, para cada mini-batch, calculei o gradiente da função de custo e atualizei os parâmetros θ.
Coloquei o tamanho de cada mini-batch para 50.

Resultado:

Após o treinamento com Mini-Batch Gradient Descent, os parâmetros θ convergiram para:

Interceptação: 12.43

Coeficiente: 5.29

SGDRegressor

Treinamento com SGDRegressor:

Usei o modelo SGDRegressor da sklearn para comparar com os meus modelos.
Treinei o modelo com o mesmo conjunto de dados e obtive uma precisão de 99%, com interceptação de 12.43 e coeficiente de 5.28.

Uso de partial_fit():

Durante o treinamento com o SGDRegressor, decidi usar o método partial_fit() para entender como funcionava e realizar o treinamento de forma incremental.
Este modelo obteve uma precisão de 99%.

Conclusões

Parece que as funções da bibliteca sklearn e os modelos feitos de forma manual chegaram a resultados próximos de si mesmos e dos reais.

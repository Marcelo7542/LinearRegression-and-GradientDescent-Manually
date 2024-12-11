English description below


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






Manual Linear Regression and Gradient Descent

The idea is to use the mathematical formulas for both methods instead of relying on pre-built libraries.

Steps for Execution


Manual Linear Regression

Data Generation: 

I created a synthetic dataset with 1000 samples, where the dependent variable Y is a linear function of X with some added noise. The model is 
𝑌 = 12.467 + 5.3 ⋅ 𝑋 + 𝜖, where ϵ is the noise.

Adding Intercept Term:

I also added a column of 1s to the input matrix X using the add_dummy_feature() function from sklearn.

Parameter Calculation: 

I used the linear regression formula 

𝜃=(𝑋^(𝑇) @ 𝑋)^(−1)𝑋^(𝑇)𝑌 

to calculate the parameters θ.

Prediction and Visualization: 

I made predictions for a new dataset and then visualized the results, including the Mean Squared Error (MSE) using the formula:

mse = (1/n)(y - X𝜃)^2
 
Result: 

The generated model closely approximates the real coefficients, and the resulting MSE was 1.01.

LinearRegression:

Training with LinearRegression: 

I used the LinearRegression model from sklearn to compare it with my manual models. I trained the model with the same dataset and obtained an MSE of 1.0467249181812295, with an intercept of 12.45155644 and a coefficient of 5.33025007.

Gradient Descent

Initialization: 

Similar to the previous approach, I created the data and added the intercept term.

Calculation via Gradient Descent: 

I randomly initialized the parameters θ and used the Gradient Descent algorithm to minimize the cost function (MSE). I set the learning rate 
η=0.01 and the number of iterations (epochs) to 1000.

Result: 

After 1000 epochs, the parameters 
θ closely approximated the real values:

Intercept: 12.43

Coefficient: 5.29

Stochastic Gradient Descent (SGD) Manual

Manual SGD Implementation: 

For the manual implementation of Stochastic Gradient Descent, I initially set the parameters θ randomly. For each iteration, I picked a random value of X and Y, computed the gradient of the cost function for that sample, and updated the parameters θ.

Result: 

After training, the parameters θ approximated the real values:

Intercept: 12.44

Coefficient: 5.29

Mini-Batch Gradient Descent:

I also used Mini-Batch Gradient Descent. I divided the data into mini-batches and, for each mini-batch, calculated the gradient of the cost function and updated the parameters 
θ. I set the mini-batch size to 50.

Result: 

After training with Mini-Batch Gradient Descent, the parameters 
θ converged to:

Intercept: 12.43

Coefficient: 5.29

SGDRegressor

Training with SGDRegressor: 

I used the SGDRegressor model from sklearn to compare with my models. I trained the model with the same dataset and obtained an accuracy of 99%, with an intercept of 12.43 and a coefficient of 5.28.

Use of partial_fit(): 

During training with SGDRegressor, I decided to use the partial_fit() method to understand how it worked and perform incremental training. This model achieved an accuracy of 99%.

Conclusions: 

It seems that the functions from the sklearn library and the manually created models yielded results that were close to each other and the real values.

Previsão de Preço

Este README descreve o processo de criação de um modelo de ML utilizando a ferramenta no-code Amazon SageMaker Canvas, utilizando o dataset Housing encontrado na pasta datasets deste repositório.

 Análise do Dataset e Construção do Modelo

Antes de iniciar a criação do modelo, foi realizada uma análise preliminar do dataset. Durante essa análise, verificou-se que não havia valores ausentes, que o tipo de modelo mais adequado seria o Numeric model type e que havia muitas variáveis categóricas binárias.

Para construir o modelo, a métrica escolhida para prever os coeficientes foi o MSE (Mean Squared Error). O dataset foi dividido em conjuntos de treinamento (80%) e validação (20%). O algoritmo de treinamento foi gerenciado pelo Amazon SageMaker Canvas, e a coluna alvo selecionada foi `price`.

 Análise dos Resultados do Modelo

Inicialmente, ao observar as métricas RMSE e MSE, pode-se ter a impressão de que o modelo teve um desempenho insatisfatório, pois os valores foram, respectivamente, 1.013.091,25 e 1.026.353.856.512,00. No entanto, isso se deve ao fato de que os valores da variável alvo (price) são bastante elevados.

Como o objetivo deste projeto era testar a capacidade do Amazon SageMaker Canvas, nenhum dado foi normalizado ou padronizado previamente. Entretanto, mesmo sem realizar esses processos, podemos obter uma melhor compreensão do desempenho do modelo ao observar a métrica R-squared, que apresentou um valor significativo de 70,641%. Isso significa que as features do modelo conseguem explicar pelo menos 70% da variação no preço, sendo a coluna `area` a mais influente, conforme mostra a imagem abaixo:

Previsões

Utilizando a ferramenta de single prediction, podemos confirmar que a coluna `area` é realmente a que mais impacta a variação do preço.

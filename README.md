# DataScience-POA-Traffic-accident
Se trata de uma análise de números de acidentes no trânsito de Porto Alegre de acordo com os anos, desde 2018. E uma previsão do numero de acidentes de 2023 utilizando a biblioteca statsmodels do Python.

# ARIMA (AutoRegressive Integrated Moving Average):

O ARIMA é um modelo estatístico amplamente utilizado para analisar e prever séries temporais, que são conjuntos de dados coletados ou observados ao longo do tempo, com pontos de dados em intervalos regulares. O modelo ARIMA é composto por três componentes principais:

- AR (AutoRegressive): Esta é a primeira parte do modelo e leva em consideração a dependência das observações em períodos anteriores. Em outras palavras, o termo AR modela a relação entre um ponto de dados e os pontos de dados anteriores. A ordem do termo AR (geralmente denotada como "p") indica quantos períodos anteriores são considerados na previsão. Um termo AR de ordem 1 (p=1) significa que apenas o valor imediatamente anterior é considerado.

- I (Integrated): Esta parte do modelo envolve a diferenciação dos dados para torná-los estacionários. Estacionariedade significa que as propriedades estatísticas da série temporal, como média e variância, são constantes ao longo do tempo. Se os dados não forem estacionários, a diferenciação é usada para torná-los estacionários. A ordem do termo I (geralmente denotada como "d") indica quantas vezes a diferenciação foi aplicada. Um termo de diferenciação de ordem 1 (d=1) significa que os valores originais foram diferenciados uma vez.

- MA (Moving Average): Esta é a terceira parte do modelo e leva em consideração a média móvel dos erros anteriores na série temporal. A ordem do termo MA (geralmente denotada como "q") indica quantos erros anteriores são considerados na previsão. Um termo MA de ordem 1 (q=1) significa que apenas o erro imediatamente anterior é considerado.

O modelo ARIMA é uma combinação dessas três partes e é especificado como (p, d, q). Para encontrar os melhores valores de p, d e q, os dados históricos são analisados e diferentes modelos ARIMA são ajustados. O objetivo é escolher o modelo que fornece a melhor previsão com base em métricas de desempenho, como o erro quadrático médio (MSE) ou o erro absoluto médio (MAE).

# Intervalo de Confiança:

Um intervalo de confiança é uma medida estatística que fornece um intervalo de valores em torno de uma estimativa, como a média ou a previsão, dentro do qual é razoável esperar que o valor real esteja com um certo grau de confiança. O intervalo de confiança expressa a incerteza associada a uma estimativa.

O intervalo de confiança é frequentemente expresso com um nível de confiança, que representa a probabilidade de que o intervalo contenha o valor real. O nível de confiança é geralmente especificado em termos de porcentagem, como 95% de confiança.

Por exemplo, se uma previsão tiver um intervalo de confiança de 95% para um valor de 100, isso significa que, com 95% de confiança, acreditamos que o valor real estará dentro desse intervalo. No entanto, há uma chance de 5% de que o valor real esteja fora desse intervalo.

O intervalo de confiança é útil porque reconhece que estimativas estatísticas, como médias ou previsões, não são valores exatos, mas sim estimativas com alguma incerteza. Um intervalo de confiança ajuda a quantificar essa incerteza e fornece uma faixa plausível para o valor real. É uma ferramenta importante na avaliação da precisão das estimativas em análises estatísticas e previsões.

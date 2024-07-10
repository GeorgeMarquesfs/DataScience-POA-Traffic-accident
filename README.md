# DataScience-POA-Traffic-accident
Se trata de uma análise de números de acidentes no trânsito de Porto Alegre de acordo com os anos, desde 2018. E uma previsão do numero de acidentes de 2023 utilizando a biblioteca statsmodels do Python.

# ARIMA (AutoRegressive Integrated Moving Average):

O ARIMA é um modelo estatístico amplamente utilizado para analisar e prever séries temporais, que são conjuntos de dados coletados ou observados ao longo do tempo, com pontos de dados em intervalos regulares. O modelo ARIMA é composto por três componentes principais:

* AR (AutoRegressive): Esta é a primeira parte do modelo e leva em consideração a dependência das observações em períodos anteriores. Em outras palavras, o termo AR modela a relação entre um ponto de dados e os pontos de dados anteriores. A ordem do termo AR (geralmente denotada como "p") indica quantos períodos anteriores são considerados na previsão. Um termo AR de ordem 1 (p=1) significa que apenas o valor imediatamente anterior é considerado.

* I (Integrated): Esta parte do modelo envolve a diferenciação dos dados para torná-los estacionários. Estacionariedade significa que as propriedades estatísticas da série temporal, como média e variância, são constantes ao longo do tempo. Se os dados não forem estacionários, a diferenciação é usada para torná-los estacionários. A ordem do termo I (geralmente denotada como "d") indica quantas vezes a diferenciação foi aplicada. Um termo de diferenciação de ordem 1 (d=1) significa que os valores originais foram diferenciados uma vez.

* MA (Moving Average): Esta é a terceira parte do modelo e leva em consideração a média móvel dos erros anteriores na série temporal. A ordem do termo MA (geralmente denotada como "q") indica quantos erros anteriores são considerados na previsão. Um termo MA de ordem 1 (q=1) significa que apenas o erro imediatamente anterior é considerado.

O modelo ARIMA é uma combinação dessas três partes e é especificado como (p, d, q). Para encontrar os melhores valores de p, d e q, os dados históricos são analisados e diferentes modelos ARIMA são ajustados. O objetivo é escolher o modelo que fornece a melhor previsão com base em métricas de desempenho, como o erro quadrático médio (MSE) ou o erro absoluto médio (MAE).

# Intervalo de Confiança:

* Um intervalo de confiança é uma medida estatística que fornece um intervalo de valores em torno de uma estimativa, como a média ou a previsão, dentro do qual é razoável esperar que o valor real esteja com um certo grau de confiança. O intervalo de confiança expressa a incerteza associada a uma estimativa.

* O intervalo de confiança é frequentemente expresso com um nível de confiança, que representa a probabilidade de que o intervalo contenha o valor real. O nível de confiança é geralmente especificado em termos de porcentagem, como 95% de confiança.

* Por exemplo, se uma previsão tiver um intervalo de confiança de 95% para um valor de 100, isso significa que, com 95% de confiança, acreditamos que o valor real estará dentro desse intervalo. No entanto, há uma chance de 5% de que o valor real esteja fora desse intervalo.

* O intervalo de confiança é útil porque reconhece que estimativas estatísticas, como médias ou previsões, não são valores exatos, mas sim estimativas com alguma incerteza. Um intervalo de confiança ajuda a quantificar essa incerteza e fornece uma faixa plausível para o valor real. É uma ferramenta importante na avaliação da precisão das estimativas em análises estatísticas e previsões.
  
# insights e Resultados

**Análise de Locais Críticos**
* Como a ideia da pesquisa é avaliar os locais de acidentes da cidade, foi utilizado as colunas de “longitude” e “latitude” do Dataset. Antes de qualquer análise, foi feito a limpeza dos dados e a retirada de valores nulos que se encontravam em algumas linhas das respectivas colunas.

Após a limpeza, foi realizada a primeira visualização, utilizando mapa de calor, onde as regiões que possuem mais acidentes terão uma cor mais escura em relação as outras. O código Python utilizou a biblioteca HeatMap do folium.

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/faef5673-b774-49b3-bfad-6dbb8a086500)

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/c8d36d8a-4f42-40f3-a344-7a2d4980409b)

Com essa visualização, já se pode perceber as regiões com a cor mais escura, identificando os locais onde ocorrem mais acidentes de trânsito. A partir disso, foi realizado uma refatoração no código para dividir as regiões em Clusters, mostrando o número de acidentes em cada local.

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/bec6505a-48da-4304-96d8-444f54aa510f)

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/c8d32c2f-2a61-49a0-a930-b9788c93087f)

A partir dessa visualização, observa-se o alto número de acidentes na região marcada, exatamente por essa região se encontrar mais ao centro da cidade, onde os acidentes de trânsito são mais recorrentes. Ao clicar na região marcada, se tem mais detalhes da região, como mostra a figura abaixo:

# Número de Acidentes por Ano

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/87e35e67-d87b-4785-9e47-2ae4ed407033)

Percebe-se que o número de 2020 possui um número bem menor de acidentes, justamente por esse ano ter tido a pandemia do COVID-19, onde as pessoas ficaram mais em casa por conta do Lockdown. E, a partir do ano de 2020, existe uma tendência positiva, pois as coisas começam a voltar ao normal e as pessoas tendem a saírem mais com os seus veículos.


**Previsão de Acidentes em 2023 utilizando o modelo ARIMA**

![image](https://github.com/GeorgeMarquesfs/DataScience-POA-Traffic-accident/assets/102534476/33d25a09-89a6-46e7-8cbc-1f69b22d6cbd)


# Conclusão

* A análise de locais críticos revelou insights importantes sobre as áreas onde a maioria dos acidentes ocorrem. Essas informações são cruciais para a formulação de políticas de segurança no trânsito e a implementação de medidas preventivas em locais de alto risco.

* A previsão de acidentes para 2023, embora baseada em um método estatístico, fornece uma estimativa valiosa que pode apoiar o planejamento de recursos, a resposta a emergências e a conscientização pública. No entanto, é importante reconhecer que qualquer previsão está sujeita a incertezas e limitações inerentes. O modelo ARIMA fornece uma previsão com um intervalo de confiança, que indica a faixa de valores possíveis, levando em consideração a incerteza estatística.

* Portanto, embora a previsão seja uma ferramenta útil para o planejamento e a tomada de decisões, ela deve ser interpretada com cautela. Outros fatores, como mudanças nas condições de tráfego, políticas de segurança no trânsito e eventos imprevisíveis, também podem influenciar o número de acidentes.

Em resumo, este estudo fornece informações valiosas sobre a segurança no trânsito na cidade de Porto Alegre, destacando locais críticos e oferecendo uma previsão estatística para o ano de 2023. A combinação de análise de dados e modelos estatísticos ajuda a orientar esforços para reduzir a incidência de acidentes de trânsito e melhorar a segurança nas estradas.















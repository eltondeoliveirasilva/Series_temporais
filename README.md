# Series_temporais

Conceitos Básicos

Antes de falarmos sobre os modelos de previsão, precisamos entender alguns conceitos fundamentais sobre séries temporais:

Tendência

A tendência representa a direção para onde a série temporal está indo ao longo do tempo. Ela pode ser:


Crescente: a série apresenta uma tendência de alta. Por exemplo, as ações de uma empresa após receber um grande investimento.

Decrescente: a série apresenta uma tendência de queda. Por exemplo, a temperatura média ao longo dos anos devido às mudanças climáticas.

Estável: a série não apresenta aumento ou diminuição significativos. Ela se mantém próxima de uma média.


Identificar corretamente a tendência é essencial para fazer boas previsões.

Sazonalidade

A sazonalidade representa padrões cíclicos e repetitivos na série temporal. Por exemplo:


Vendas no varejo são maiores em datas comemorativas como Natal, Dia das Mães etc.

Consumo de energia aumenta no verão devido ao uso intensivo de ar condicionado.

Incidência de gripe tem picos no inverno.


Esses padrões que se repetem em determinados períodos são chamados de sazonalidades. Identificá-los ajuda a fazer previsões mais precisas.

Média Móvel

A média móvel é a média de uma série temporal em uma janela específica de tempo. Ela suaviza a série, facilitando a visualização de tendências e padrões.

Por exemplo, a média móvel de 5 dias considera a média dos últimos 5 valores. À medida que a série temporal avança, a janela de 5 dias vai se movendo, daí o nome "móvel".

As médias móveis são muito utilizadas para identificar tendências em séries temporais. Valores abaixo da média móvel indicam possíveis quedas, enquanto valores acima indicam altas.

Modelos de Previsão

Agora que entendemos os conceitos básicos, vamos conhecer os principais modelos para prever séries temporais em Python:

ARIMA

O ARIMA (Auto Regressive Integrated Moving Average) é um dos algoritmos mais populares para prever séries temporais. Ele considera os dados históricos para fazer estimativas sobre o futuro.

O ARIMA é composto por 3 parâmetros principais:


AR(p): Auto Regressão. Usa regressão linear nos valores passados da série temporal. O parâmetro p determina o número de lags (valores passados) a serem usados.

I(d): Integração. Remove tendências e sazonalidades, tornando a série temporal estacionária. O parâmetro d determina o grau de diferença na série.

MA(q): Média Móvel. Usa uma combinação linear de erros recentes na previsão para tentar melhorá-la. O parâmetro q determina o número de termos de erro.


O ARIMA aprende com os erros das previsões passadas para tentar melhorar suas estimativas futuras. Isso o torna muito poderoso para séries temporais.

SARIMA

O SARIMA é uma extensão do ARIMA que suporta sazonalidade. Ele adiciona 3 parâmetros sazonais:


S: Frequência da sazonalidade (por exemplo, 12 para sazonalidade mensal)

P: Auto regressão sazonal

Q: Média móvel sazonal


Assim como o ARIMA, o SARIMA utiliza regressão linear e médias móveis, mas também modela os padrões cíclicos e sazonais dos dados.

SARIMAX

O SARIMAX é outra variação do SARIMA que suporta o uso de variáveis exógenas, ou seja, variáveis externas que não fazem parte da série temporal mas que afetam seus valores.

Por exemplo, em uma previsão de vendas, informações sobre promoções e campanhas de marketing podem melhorar a acurácia das estimativas. O SARIMAX consegue incorporar essas variáveis no modelo de previsão.

Machine Learning

Além dos modelos estatísticos como ARIMA e SARIMA, também é possível aplicar algoritmos de machine learning em séries temporais, como redes neurais (RNN, LSTM etc).

As principais diferenças em relação aos modelos estatísticos são:


Maior flexibilidade, sem a necessidade de ajustes manuais nos parâmetros
Menor interpretabilidade do funcionamento interno
Dificuldade de fazer previsões muito longas no futuro

De modo geral, os modelos estatísticos ainda apresentam melhor performance e praticidade para a maioria dos casos de uso de séries temporais. Mas vale explorar diferentes abordagens.

Etapas de um Modelo de Previsão

Agora que conhecemos os principais algoritmos, vamos entender as etapas para construir um modelo de previsão de séries temporais:

1. Coletar e preparar os dados


Reunir observações históricas da série temporal
Tratar valores faltantes e outliers
Separar dados em treino e teste

2. Analisar a série temporal


Identificar tendência, sazonalidade e outras características
Calcular médias móveis
Verificar se a série é estacionária

3. Treinar modelos candidatos


Treinar vários modelos ARIMA, SARIMA, SARIMAX etc
Testar diferentes combinações de parâmetros (p, d, q)
Também treinar modelos de machine learning

4. Avaliar o desempenho no conjunto de teste


Verificar métricas como MAPE, RMSE em dados nunca vistos antes
Escolher o melhor modelo com base nas métricas

5. Fazer previsões para o futuro


Utilizar o modelo final treinado para estimar valores futuros
Monitorar o desempenho e re-treinar se necessário

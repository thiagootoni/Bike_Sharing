# Bike_Sharing
Modelo de Predição de demanda de sistema de compartilhamento de bicicletas em Washington D.C.

Modelo apresentado como projeto final para o Nanodegree Machine Learning, da Udacity.

Sistema de Previsão de Demanda de Aluguel de Bicicleta em Washington D.C.

Histórico do assunto:

Os sistemas de compartilhamento de bicicletas são um meio de alugar bicicletas em que o processo de obtenção de associação, locação e devolução de bicicletas é automatizado por meio de uma rede de quiosques em toda a cidade. Usando esses sistemas, 
as pessoas podem alugar uma bicicleta em um local e devolvê-la a um local diferente conforme necessário. Atualmente, existem mais de 500 programas de compartilhamento de bicicletas em todo o mundo.
Os dados gerados por esses sistemas os tornam atraentes, porque a duração da viagem, o local da partida, a localização da chegada e o tempo decorrido são explicitamente registrados. Os sistemas de compartilhamento de bicicletas, portanto, funcionam como uma rede de 
sensores, que pode ser usada para estudar mobilidade em uma cidade. Nesta análise temos os padrões históricos de uso somados de dados meteorológicos, a fim de prever a demanda de aluguel de bicicletas no programa Bikeshare em Washington, D.C.

Descrição do problema: 

Como dito acima, atualmente, existem cerca de 500 programas de compartilhamento de bicicletas em todo o mundo, compostos por mais de 
500 mil bicicletas. Hoje, existe um grande interesse nesses sistemas devido ao seu importante papel no trânsito, questões ambientais, 
de saúde e de alternativa à locomoção, principalmente em grandes Cidades.
A Análise pode ser útil em diversas frentes; quando pensamos no serviço de aluguel de bicicletas, pensamos em disponibilidade das 
mesmas, e por muitas vezes temos bicicletas com problemas mecânicos e/ou estações de aluguel com sistema inoperante. A manutenção 
preventiva nesses casos é de extrema importância para a qualidade do serviço prestado. Com uma boa projeção de demanda de uso, 
a empresa fornecedora dos serviços, poderia saber qual o melhor momento para retirar um número X de biciletas das ruas sem prejudicar 
o serviço ou realizar manutenção nos pontos de aluguel, tirando do ar momentaneamente alguns deles em horários mais propíceos, que não 
prejudiquem os horários grande demanda.
Além disto, é uma forma interessante para acompanhar o fluxo de uso do sistema, poder fazer o balanço entre o real x previsto, 
pode auxiliar em ações de marketing e comunicação para estímulo do uso do sistema ou se o uso estiver superando a previsão, implementar 
pontos e planos de expansão do sistema.

Conjuntos de dados e entradas:

Para esta análise, irei utilizar o conjunto de dados "Bike Sharing Demand - Forecast use of a city bikeshare system", um banco de dados 
com finalidade de prever a demanda de aluguel de bicicletas na cidade de "Washington D.C - USA". Este conjunto foi utilizado numa 
competição do Kaggle e o mesmo está disponível para download em:

https://www.kaggle.com/c/bike-sharing-demand 

ou pode ser encontrado com algumas modificações no repositório da UCI Machine learning https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset
A nossa análise será em cima do conjunto de dados do arquivo "Train.csv". Este conjunto tem 10886 informações de aluguel de biciletas, 
ao longo de 2 anos de medição, onde cada linha representa a soma das bicicletas alugadas em uma determinada hora, de um dia, mês e ano 
específico, dadas as condições climáticas daquele ponto de tempo.

As variáveis podem ser descritas como:

datetime : dia + hora season : 1 = inverno, 2 = primavera, 3 = verão, 4 = outono 
holiday : se o dia é considerado um feriado 
workingday: se o dia não é nem um fim de semana nem feriado 
weather:  1: Limpo, Poucas nuvens, Pouco nublado, Pouco nublado  
          2: Névoa + Nublado, Névoa + nuvens quebradas, Névoa + Algumas nuvens, Névoa  
          3: Nevões fracos, Chuva fraca + Trovoada + Nuvens dispersas, Chuva fraca + Nuvens d ispersas  
          4: Chuva forte + "Paletas" de Gelo + Trovoada + Névoa, Neve + Nevoeiro
temp : temperatura em Celsius 
atemp : Sensação Térmica 
humidity : umidade relativa 
windspeed : velocidade do vento 
casual : número de locações de usuários não registradas iniciadas 
registered: número de locações de usuários registrados iniciadas 
count : número de aluguéis totais

A variável alvo é "count" que representa a quantidade total de aluguéis das bicicletas para o dia e hora indicados.

A particularidade deste conjuto de dados, é que o mesmo representa os dias de 01 a 19 dos meses que estão disponíveis. 
É a versão exposta do conjunto de dados de treinamento da competição Kaggle. Irei utilizar esta base para avaliar a precisão de 
meu regressor.


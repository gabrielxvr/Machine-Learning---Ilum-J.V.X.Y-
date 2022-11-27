# Machine-Learning---Ilum-R.W.Q.Y-

## Aprendizado de Máquina aplicado à previsão de resultados do Brasileirão

<img src="https://user-images.githubusercontent.com/107067724/184998620-beb7c37b-20d5-4ec9-843a-a624387f682e.png" style="width:320px;height:200px;">

### Futebol é estatística?
Esse é um repositório relativo ao desenvolvimento do projeto realizado pelo grupo J.V.X.Y na disciplina Aprendizado de Máquinas, na Ilum Escola de Ciências. Nele, será estudada a relação de alguns atributos ao resultado de partidas na seria A do Brasileirão, para que, assim, seja possível a previsão desses resultados.

##### 

<img src= "https://user-images.githubusercontent.com/107067724/185000434-94e58d5a-f494-41c2-bcc8-69aee78a1213.gif" style="width:320px;height:200px;">

### Como fazer a melhor simulação?
Para realizar simulações a respeito dos jogos foram usados alguns atributos, disponíveis nos bancos de dados do brasileirão. Informações como a colocação de cada time no campeonato ou o número de torcedores presentes no estádio podem ser indicativos de um resultado positivo ou negativo. Selecionar dados significativos é muito importante e fez parte do pre-tratamento realizado.

### Dados trabalhados
De maneira geral, nós utilizamos uma tabela de dados relativos a jogos da série A do Brasileirão, entre os anos de 2003 e 2020.

<img src= "https://user-images.githubusercontent.com/107067724/203422699-021d084f-7534-4f51-bf45-bb4ef222a22e.png" style="width:640px;height:400px;">


### Tratamento de dados
O tratamento de dados foi realizado usando o Python, por meio do JupyterLab, especialmente utilizando a biblioteca scikit-learn. Além disso, foram usadas algumas bibliotecas, como o pandas, o matplotlib e o seaborn. O código feito está disponível nesse repositório no documento "Código Utilizado.pynb". Para utilizá-los é necessário fazer o download da tabela "dados brasileirao.xlsx".

### Alguns resultados obtidos de forma exploratória
Em um primeiro momento, é interessante analisar algumas relações de dependência envolvendo as partidas de futebol. Para isso, faremos uso de gráficos, relacionando algum atributo desejado à média de gols.

<img src= "https://user-images.githubusercontent.com/107067724/203429334-adbf659a-ad6c-45b3-ab0f-b4dd77ea9a07.png" style="width:320px;height:200px;">

Podemos perceber, a partir do gráfico acima que, estatisticamente, o número de torcedores presentes no estádio não influencia de maneira significativa a quantidade de gols do mandante.

<img src= "https://user-images.githubusercontent.com/107067724/203430340-b26adddf-3cd8-4763-beec-105f07197e4d.png" style="width:320px;height:200px;">

De maneira diferente ao que foi apresentado no primeiro gráfico, no gráfico acima, podemos perceber que o valor do elenco titular mandante influencia positivamente a quantidade de gols marcados pelo mandante.

<img src= "https://user-images.githubusercontent.com/107067724/203430848-3a2a9f44-90d8-4f1a-8381-19f4e0857223.png" style="width:320px;height:200px;">

Quando nos referimos à colocação do time mandante, essa informação também se mostra importante para a predição do número de gols do time mandante.

<img src= "https://user-images.githubusercontent.com/107067724/203431038-3a4a5447-95e2-4f68-adbb-9f6647c86789.png" style="width:320px;height:200px;">

De forma complementar ao segundo gráfico, o valor da equipe titular mandante influencia negativamente a média de gols marcados pela equipe visitante.

<img src= "https://user-images.githubusercontent.com/107067724/203429941-868b1c97-4560-4ee2-ad5e-4c15368b5830.png" style="width:320px;height:200px;">

De forma semelhante ao obtido anteriormente, a colocação do time mandante parece influenciar no número de gols marcados, em média, pelo time visitante.

<img src= "https://user-images.githubusercontent.com/107067724/203431171-6b5642a8-978b-431b-8a43-0fc232ce8031.png" style="width:320px;height:200px;">

<img src= "https://user-images.githubusercontent.com/107067724/203431289-8126d2f1-c304-4036-95bb-626d87313272.png" style="width:320px;height:200px;">

<img src= "https://user-images.githubusercontent.com/107067724/203431378-75cace32-ab85-43b3-831c-e069d6a19c92.png" style="width:320px;height:200px;">

As frequências de cada atributo analisado pela faixa desses atributos nos permitem compreender algumas dispersões nos gráficos anteriores. Por exemplo, a quantidade de dados contendo uma quantidade de torcedores no estádio maior que 60 mil é muito pequena, isso permite compreender a grande dispersão do primeiro gráfico quando a quantidade de torcedores é maior que 60 mil.

## Modelagem
Após a análise exploratória dos dados indicar possíveis correlações dos atributos análisados com o resultado da partida, foi possível, então, criar alguns modelos que possibilitaram a previsão de resultados. Sendo que, estes, serão apresentados a seguir. Em uma primeira abordagem, nosso objetivo era simplificar os dados com que estávamos trabalhando, para tal, disassociamos esses dados aos clubes aos quais eles se referiam, em seguida, nós optamos por trabalhar apenas com os dados que poderiam ser estabelicidos anteriormente ao início do jogo, excluindo, dessa forma, features como o número de chutes ao gol ou o número de escanteios. Dessa forma, nós trabalhamos com um dataset contendo 4921 linhas, em que nós tínhamos sete features para realizar a previsão. Essa abordagem está apresentada em "Códigos de aprendizado e teste" -> "Código Utilizado.ipynb" e pautará os próximos tópicos.

## Divisão do Database em Treino e Teste
A divisão do Database em treino e teste é um passo fundamental para qualquer modelagem e consiste em, basicamente, separar a quantidade de objetos que serão utilizados para treinar o código e aqueles que servirão de medida para saber o quão boa está a previsão. No nosso caso, por exemplo, a primeira modelagem foi realizada com 90% dos objetos utilizados no treino e 10% utilizados no teste. No entanto, após o desenvolvimento do código, em um ponto, notou-se mais vantajoso utilizar a proporção de 70% para treino e 30% para teste.

## Modelo Baseline
O modelo baseline serve de padrão para descobrir o quão eficiente estão os outros modelos. Nesse caso, foi utilizado o DummyRegressor, método esse que calcula a média e prevê os valores a partir apenas da média. Os resultados obtidos, para a média de gols do mandante foi de 1.5049 gols, enquanto o erro médio foi de 1.1665 gols.

## Regressão Linear
Diferentemente do DummyRegressor, na regressão linear, a previsão é baseada em um modelo linear, o qual pode trabalhar com a proporcionalidade em relação a algumas features. Condição essa que permite uma melhor predição. Nesse caso, o erro médio registrado foi de 1.1010 gols.

## k-vizinhos
Ainda na regressão linear, é possível trabalhar com um hiperparâmetro, chamado k-vizinhos. Esse hiperparâmetro faz com que a predição seja baseada de maneira mais contundente pelos k-vizinhos do alvo, sendo que k será um número natural determinado anteriormente ao treino.

## Árvore de Decisões
A árvore de decisões é um método de previsão que permite constituir uma série de perguntas e passos a fim de predizer a condição final do alvo. Para isso, o código treina uma série de perguntas e consequências para cada resposta, sendo que os testes serão submetidos a esse processo. Para o alvo de gols do mandante, o erro médio obtido, sem a inclusão de hiperparâmetros, foi de 1.6809 gols.

## Árvore de Decisões com Hiperparâmetros
Alguns hiperparâmetros, como a quantidade de folhas, podem ser adicionados ao modelo de árvore de decisões com o objetivo de diminuir o erro médio. Objetivo esse bem sucedido, pois, ao definirmos o número de folhas como 6 e o número de profundidade como 3 nós obtivemos o erro médio de 1.121 gols.

<img src= "https://user-images.githubusercontent.com/107067724/203431565-272b9381-4cfa-4429-9453-d2aad05ce42e.png" style="width:600px;height:400px;">

## Floresta Aleatória
Na verdade é a ideia de floresta aleatória é bem parecidada com a de árvore de decisões, mas ampliada. Nesse caso, o erro médio obtido foi de  1.1285 gols. No entanto, após a inserção de alguns hiperparâmtros, o erro médio passou para 1.11 gols.

## Algumas consideração
Até o determinado momento, considerando o alvo numérico "gols do mandante" a melhor previsão foi realizada a partir da Regressão Linear.

## Classificação
O método de classificação é uma forma de previsão baseada no agrupamento de resultados semelhantes, a fim de estabelecer esse mesmo resultado para os valores de teste. Acontece que, a classificação é utilizada, em especial, para targets não numéricos. Portanto, surgiu a hipótese de trabalhar, no nosso problema, não mais com a previsão do número de gols do mandante, mas sim com o resultado do mandante, sendo que as três opções seriam vitória, derrota ou empate. Para tal, nós fizemos um código que criou uma coluna de resultado do mandante a partir do número de gols marcados e sofridos, para que, dessa forma, fosse possível o treinamento e o sequente teste.

## k-vizinhos
A ideia de k-vizinhos, quando utilizada na classificação ocorre de maneira parecida. Sendo que, nesse caso, os vizinhos interfeririam no agrupamento realizado.

## Arvore de Decisões com Hiperparâmetros
A arvore de decisões também possui a mesma dinâmica de perguntas e argumentos lógicos para determinar a previsão, sendo que, somado aos hiperparâmetros determinados, foi possível obter, finalmente, um accuracy de pouco mais de 50%.

## Algumas conclusões
A partir dos resultados obtidos, mencionados anteriormente, foi possível obter, no modo de classificação, um accuracy, ou precisão, de mais de pouco mais de 50%. Isso significa que, em média, a cada dois jogos, o modelo é capaz de responder corretamente um dos resultados, sendo que as opções possíveis são vitória, derrota ou empate do mandante. Isso faz com que o modelo possua a capacidade de prever relativamente bem alguns resultados, especialmente quando pensamos em um número grande de jogos. Portanto, podemos fazer a seguinte constatação lógica: Se em um site de apostas on-line o resultado obtido pelo modelo estiver correspondendo a um multiplicador maior que 2, ou seja, a cada 1 real investido o valor de retorno caso se acerte o resultado é maior que 2 reais (algo bastante comum), então, torna-se vantajoso investir nessa partida, pois, como constatado, a chance de acerto do código é mais de 50%, isso faz com que, se pensarmos em centenas ou milhares de apostas em que o resultado apontado pelo modelo possui um multiplicador maior que 2 é, estatisticamente, bem provável o lucro.

## Conclusões precipitadas...

"o mundo é um moinho" - Cartola

Sim! O mundo é um moinho que triturou nossos sonhos mesquinhos de ganhar dinheiro com apostas esportivas. Depois de analisar os resultados que o nosso código havia apresentado, nós notamos um comportamento estranho, o nosso modelo sim acertava o resultado de 50% dos jogos, MAS, ele acertava pois previa a vitória para o mandante em TODAS as vezes. Nesse momento, nós descobrimos que existe uma "lei empírica do futebol", que vai ser referida aqui como "distribuição real", em que o time mandante ganha em 50%, empata em 25% e perde em 25% das ocasiões, ou seja, até mesmo alguém que nunca assistiu futebol antes na vida, se soubesse dessa tendência, conseguiria acertar o resultado de 50% dos jogos simplesmente apostando no mandante. Podemos chamar esse fenômeno, então, de "A barreira dos 50%"! Nesse momento, nosso baseline deixa de ser o DummyRegressor ou a ilusão de que haveria 33,333...% de chance em adivinhar aleatoriamente o resultado e passa a ser o "novo óbvio": A barreira dos 50%!

Até então, todos os nossos resultados tidos como "bons" estavam, na verdade, convergindo para a barreira dos 50%, o modelo da árvore de decisões havia sido o único a ter uma distribuição real e uma precisão de 42%, o que ainda estava abaixo do esperado. Seria esse o fim do nosso sonho? Estaríamos nós esse tempo todo em busca do inexistente pote de ouro ao fim do arco-íris?

## Uma luz no fim do tunel

"Não me diga que a canção está perdida" - Raul Seixas

Havia uma luz no fim do tunel! Após refletir sobre o nosso problema, chegamos a uma conclusão também óbvia. O nosso código, assim como uma pessoa que nunca assistiu a uma partida de futebol, poderia acertar 50% dos jogos, tudo bem! Mas para qualquer um desses passar a acertar mais que 50% dos resultados, seria necessário ir além do óbvio, pois prever a vitória do mandante sempre estaria condenado a nunca passar da barreira dos 50%. Ou seja, um modelo mais robusto, para acertar mais que 50% passaria, necessariamente, a prever derrotas e empates do mandante. Dessa forma, a nossa missão deixa de ser manter de qualquer forma uma distribuição real para ampliar nosso modelo de forma que necessariamente ele atinja a distribuição real, passando, dessa forma, também, da barreira dos 50%.

A nossa primeira abordagem, então, foi mudar absurdamente alguns hiperparâmetros do nosso "melhor" modelo até então, a floresta aleatória. No entanto, nós percebemos que essa mudança não foi efetiva, o que acontecia é que, ao aumentar os hiperparâmetros, tanto a precisão quanto a distribuição dos resultados se aproxima muito do modelo sem a modificação dos hiperparâmetros, até o ponto em que nós não tínhamos mais capacidade de processamento para aumentar os hiperparâmetros. Como já era esperado, essa não foi uma abordagem muito inteligente! :(

Nós precisaríamos, agora, partir para outra forma de resolver o nosso problema. Então, resolvemos dar vários passos para trás e voltar ao nosso dataset original. Nesse momento, nós tínhamos 7030 jogos, 37 features, algumas fristrações no caminho e uma missão a ser cumprida.

## Uma possível solução

Vale retornar ao início da nossa primeira abordagem em que nós definimos, arbitrariamente, que todos os dados que aconteceram durante o jogo, como chutes a gol, escanteios, etc, seriam considerados como lixo e excluídos do nosso dataframe. O que nós não levamos em conta é que esses dados eram, na verdade, muito valiosos para a nossa análise. Seria essa nova abordagem a solução para os nossos problemas?

"Quem não arrisca, não petisca" - Ditado popular

Essa resposta só seria respondida se tentássemos. Portanto, foi traçada a seguinte estratégia: Dados como chutes ao gol realizados na partida não podem ser utilizados para prever uma partida que nem começou, porém eles dizem muito a respeito do time que está jogando, como, por exemplo, se esse time é mais ofensivo ou defensivo, entre outras características. Dessa forma, precisariamos de utilizar esses dados de maneira em que seria possível obtê-los antes do início da partida, mas como?

## Aplicação da nova abordagem

A nossa abordagem, então, foi não mais trabalhar com os dados de chutes a gol ou escanteios, e sim trabalhar com tendências. Ou seja, baseado nos últimos jogos de cada time, nós encontraríamos qual é a tendência de gols, chutes a gol, faltas ou defesas de cada, dessa forma, seria possível estimar esses valores anteriormente ao início da partida. Mas como implementar isso na prática?

A solução foi, a partir do dataframe inicial, retirar todas as linhas que possuíssem dados faltantes. Nossa ideia era não mais trabalhar com várias linhas, mas sim com várias Features. Após isso, foi definida uma função de tendência, que, a partir dos últimos quatro valores, encontra uma tendência, de maneira que os valores mais recentes contribuem mais para essa tendência. Em seguida, nós criamos uma função, em cada linha, irá identificar os times mandante e visistante, encontrar os dados a respeito de seus últimos quatro jogos, calcular a tendência de cada um deles e adicioná-la à coluna "tendência de ..." criada anterioemente. Dessa forma, adicionamos diversas novas Features ao nosso dataframe e poderíamos, em seguida, excluir as Features que não seriam possíveis de determinar sem, no entanto, perder a informação contida nelas. Dessa forma, nós tínhamos em mãos um dataframe contendo 666 linhas e 25 Features. Ou seja, perdemos um número considerável de linhas, mas ganhamos quase o quadruplo de Features. Seria possível, então, começar a testar alguns modelos mais simples.

## Divisão do Database em Treino e Teste

A divisão entre treino e teste ocorreu de maneira bem parecida com o que foi realizado na primeira abordagem, separando 10% dos dados para teste e 90% para treino.

## Modelo Baseline

"Valeu a pena, ê ê" - O Rappa

O Modelo Baseline para prever o número de gols do mandante teve, a partir da inserção dessas novas Features, um RMSE de 1.021 gols, ou seja, para a previsão do número de gols do mandante, o DummyRegressor apresentou um RMSE menor que todos os outros modelos testados na primeira abordagem! Esse resultado é incrível!

## Regressão Linear

A regressão linear também seguiu a mesma tendência do DummyRegressor, possuindo um RMSE de, também, 1.021 gols, porém, sendo um pouco menor que o modelo baseline, porém, esses poderiam ser considerados estatisticamente iguais.



## Agradecimentos Especiais

A equipe agradece imensuravelmente aos professores Daniel Cassar e James de Almeida, responsáveis por ministrar a disciplina de "Aprendizado de Máquina" na Ilum Escola de Ciência. Além disso, agradecemos a todos os envolvidos na produção de conhecimento da Ilum Escola de Ciência. Ademais, agradecemos a nosso parceiro Gustavo Matos, que nos ajudou em partes do código, revisando e propondo algumas abordagens.

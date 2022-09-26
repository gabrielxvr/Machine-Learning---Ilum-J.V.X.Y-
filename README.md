# Machine-Learning---Ilum-R.W.Q.Y-

## Aprendizado de Máquina aplicado à previsão de resultados do Brasileirão

<img src="https://user-images.githubusercontent.com/107067724/184998620-beb7c37b-20d5-4ec9-843a-a624387f682e.png" style="width:320px;height:200px;">

### Futebol é estatística?
Esse é um repositório relativo ao desenvolvimento do projeto realizado pelo grupo J.V.X.Y na disciplina Aprendizado de Máquinas, na Ilum Escola de Ciências. Nele, será estudada a relação de alguns atributos ao resultado de partidas na seria A do Brasileirão, para que, assim, seja possível a previsão desses resultados.

##### 

<img src= "https://user-images.githubusercontent.com/107067724/185000434-94e58d5a-f494-41c2-bcc8-69aee78a1213.gif" style="width:320px;height:200px;">

### Como fazer a melhor simulação?
Para realizar simulações a respeito dos jogos foram usados alguns atributos, disponíveis nos bancos de dados do brasileirão. Informações como a colocação de cada time no campeonato ou o número de torcedores presentes no estádio podem ser indicativos de um resultado positivo ou negativo. Selecionar dados significativos é muito importante e fez parte do pre-tratamento realizado.

### Tratamento de dados
O tratamento de dados foi realizado usando o Python, por meio do JupyterLab, especialmente utilizando a biblioteca scikit-learn. Além disso, foram usadas algumas bibliotecas, como o pandas, o matplotlib e o seaborn. O código feito está disponível nesse repositório no documento "Código Utilizado.pynb". Para utilizá-los é necessário fazer o download da tabela "dados brasileirao.xlsx".

### Alguns resultados obtidos de forma exploratória
Em um primeiro momento, é interessante analisar algumas relações de dependência envolvendo as partidas de futebol. Para isso, faremos uso de gráficos, relacionando algum atributo desejado à média de gols.

<img src= "Gols e Público Médio.png" style="width:320px;height:200px;">
Podemos perceber, a partir do gráfico acima que, estatisticamente, o número de torcedores presentes no estádio não influencia de maneira significativa a quantidade de gols do mandante.
<img src= "Gols e Valor do Elenco.png" style="width:320px;height:200px;">
De maneira diferente ao que foi apresentado no primeiro gráfico, no gráfico acima, podemos perceber que o valor do elenco titular mandante influencia positivamente a quantidade de gols marcados pelo mandante.
<img src= "Gols e Colocação do Mandante.png" style="width:320px;height:200px;">
Quando nos referimos à colocação do time mandante, essa informação também se mostra importante para a predição do número de gols do time mandante.
<img src= "Gols do Visitante e Valor do Elenco Mandante.png" style="width:320px;height:200px;">
De forma complementar ao segundo gráfico, o valor da equipe titular mandante influencia negativamente a média de gols marcados pela equipe visitante.
<img src= "Gols do Visitante e Colocação do Mandante.png" style="width:320px;height:200px;">
De forma semelhante ao obtido anteriormente, a colocação do time mandante parece influenciar no número de gols marcados, em média, pelo time visitante.
<img src= "Frequência de Valor da Equipe Mandante.png" style="width:320px;height:200px;">
<img src= "Frequência de Público.png" style="width:320px;height:200px;">
<img src= "Frequência da Colocação.png" style="width:320px;height:200px;">
As frequências de cada atributo analisado pela faixa desses atributos nos permitem compreender algumas dispersões nos gráficos anteriores. Por exemplo, a quantidade de dados contendo uma quantidade de torcedores no estádio maior que 60 mil é muito pequena, isso permite compreender a grande dispersão do primeiro gráfico quando a quantidade de torcedores é maior que 60 mil.

## Modelagem
Após a análise exploratória dos dados indicar possíveis correlações dos atributos análisados com o resultado da partida, foi necessário, então, ...

## Árvore de decisão criada no Bloco 2

<img src= "árvorefut.png" style="width:600px;height:400px;">

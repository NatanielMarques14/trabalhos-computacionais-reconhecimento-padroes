# Trabalhos Computacionais de Reconhecimento de Padrões (TI0097)

Este repositório reúne os dois trabalhos computacionais da disciplina, feitos com a base de dados Wall Following Robot Navigation, que registra leituras de sensores de um robô que navega seguindo paredes e precisa decidir para onde se mover.

## TC1: Análise dos dados e classificação

Este trabalho tem duas partes.

Na primeira parte é feita uma análise descritiva da base com 4 sensores. São mostradas quantas classes existem e quantas amostras cada uma tem, calculadas a média, a variância, a assimetria e a curtose de cada sensor por classe, e construídos histogramas para ver como os valores de cada sensor se distribuem. Também é feito um gráfico com todos os pares de sensores e a matriz de correlação entre eles, para entender se os sensores carregam informação parecida ou não.

Na segunda parte o problema é reduzido a 3 classes de movimento, e quatro classificadores são implementados e comparados: o vizinho mais próximo com diferentes formas de medir distância, a distância mínima ao centróide, uma versão dessa distância mais resistente a valores fora do padrão, e um classificador baseado em correlação. Cada classificador é testado 100 vezes, variando também a proporção de dados usada para treino e para teste, e são reunidas estatísticas de acerto, tempo de execução e matrizes de confusão, além de uma comparação de desempenho por classe.

## TC2: Matriz de covariância

Este trabalho olha mais de perto para a matriz de covariância, que é a peça usada por vários classificadores estatísticos para descrever como os sensores variam juntos.

Primeiro, quatro formas diferentes de calcular essa matriz são implementadas e comparadas entre si e com a função pronta do numpy, para confirmar que todas chegam no mesmo resultado. Depois, o tempo de execução de cada uma dessas formas é medido e comparado, já que fazer esse cálculo de um jeito mais eficiente importa quando ele precisa ser repetido muitas vezes. Em seguida, a matriz de covariância é calculada separadamente para cada classe e é verificado se essas matrizes podem ser invertidas, o que é necessário para alguns classificadores funcionarem. Por fim, nos casos em que a matriz fica mal condicionada, é aplicada uma pequena correção antes de invertê la, e o resultado dessa correção é comentado.

## Base de dados

Os arquivos de dados usados são baixados automaticamente pelos próprios notebooks a partir de um release no GitHub, então não é necessário baixar nada manualmente antes de rodar o código.

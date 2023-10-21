# Castelos
Projeto Castelos Cheat Code para o calculo de todos os tiros

## Geogebra
o arquivo .ggb é para ser aberto no geogebra, feito no geogebra classic com adição de Javascript embutido para os cálculos dos tiros

esse arquivo possibilita ver toda a trajetória dos tiros e local exato de chegada, imitando o programa real usado para avaliar os tiros no trabalho.

- apresenta lag ao calcular os tiros levando em média 10-15s para terminar o processo, já que o geogebra tenta desenhar cada uma das possibilidades de tiros que existe de uma vez, mas tao rápido que nao se dá para ver as mudanças. nao sei como concertar isso

### Funcionamento

ao carregar o programa é possivel mover o rolamento do "seu castelo" e "castelo inimigo" no canto superior direito da tela, ao colocar os castelos em que quer adiquirir a resposta é possivel mover os rolamentos de "v0" para velocidade inicial e "o" para ângulo e ver quais valores acertam os tiros
porem para maior precisão e velocidade se pode clicar no botao de "calcular" para que o programa calcule todos os tiros possiveis e salve apenas os que acertam (é normal travar a tela e lagar um pouco o computador ao clicar)
após os calculos tiverem sido terminados aparecerá "(Cálculos Concluídos)" na caixa de texto do lado esquerdo e voce poderá escolher um dos 3 botões para mostrar os resultados.
- Botão superior "Mostrar Valores (Otimizado)" que te mostrará a melhor combinação de 5 ou mais tiros com no mínimo de 10 garus de diferença entre sí e filtrados para a menor distância do centro da linha de diâmetro do castelo inimigo e com uma altura de chegada no castelo inimigo de 5 ou mais se possível.
- Botão do meio "Mostrar Valores (Não Otimizado)" apenas irá te mostrar a maior combinação de tiros com 10 graus de diferença entre sí, escolhendo o primeiro tiro que acertar dos proximos 10 graus, fazendo com que muitos deles sejam na borda do castelo inimigo, mas sempre fogo
- Botão inferior "Mostrar Valores (Total)" mostra todos os valores de tiro que ão fogo e acertam o castelo inimigo

Após ver os valores por meio de um desses 3 botões é possivel clicar no botao de "RunTest" para mostrar cada uma das combinaçoes de tiros provenientes do ultimo botão de "Mostrar Valores" que foi pressionado (exceto o Total), cada vez que clicar nesse botão ele passará os valores do próximo tiro da lista em loop e o botão "RunTest(Total)" é a mesma coisa só que para todos os tiros que são fogo sem filtro nenhum.
- ao passar para o proximo teste  de tiro em qualquer botão o programa irá salvar o tiro que passar, nao importando se for o mesmo, porém isso nao afeta a qualidade dos cálculos nem os resultados, nem as listas de tiros providas. apenas impossibilida de chegar ao fim dos testes de "RunTest(Total)"

também é possivel clicar no botão "Copiar Valores" para copiar os tiros do ultimo botão pressionado em formato para se usar no Excel ou Sheets em formato de "velocidade inicial"+"ângulo" de cada tiro em série.

## HTML

um dos problemas do geogebra é que por ele possibilitar visualizar o gráfico em tempo real, entre outras coisas isso o torna extremamente ineficiente em termos de velocidade para se calcular os tiros, e já que foi provado que eles acertarão o alvo graficamente pelo geogebra, foi copiado a mesma lógica para uma pagina em html/javascript para calcular os tiros com muito mais velocidade. chegando até em **2 MILISSEGUNDOS** (ou menos) para se calcular todos os 8.811 tiros, em comparação com a media de 12 segundos do geogebra para o mesmo, já que nao é necessário calcular todos os pontos da função para desenha-la apenas se torna necessário saber dois pontos da função por tiro para determinar se ele acerta ou não com 100% de precisão.
porém para se conseguir filtrar os valores dos tiros para os melhores em precisão são necessários cálculos adicionais, para se saber com uma precisao de 2 casas decimais (mesma usada normalmente pelo geogebra) aonde o tiro atinge o castelo inimigo para se calcular a distância do centro, mesmo assim o programa consegue chegar a velocidade de apenas 160 milissegundos para se calcular a melhor combinação de todos os tiros de todos os castelos contra todos os castelos, 8.811 tiros por cada uma das 90 combinações de castelos totalizando 792.990 tiros ao todo com uma velocidade média de aproximadamente 1.7ms/tiro

TL;DR: esse programa apresenta as mesmas respostas do geogebra em velocidades record só que sem visualização gráfica 

### Funcionamento

Após escoler o "SEU CASTELO" e o "CASTELO INIMIGO" é possivel:
- verificar o fogo de qualquer combinação de velocidade inicial e ângulo
- calcular todos os tiros que acertam
- calcular os melhores desses tiros
- calcular os melhores tiros de todos os castelos contra todos os castelos

"si vis pacem, para bellum" - batmão

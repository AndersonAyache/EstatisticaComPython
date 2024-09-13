# Estatística com Python
<p style="text-align:justify">A estatística é uma área da matemática frequentemente vista como complexa e até controversa, mas é essencial no mundo moderno. Afinal, quem hoje em dia não ouviu falar do ChatGPT ou de inteligência artificial? Esses novos modelos de linguagem computacional são construídos com base em modelos estatísticos amplamente estudados e testados. Além disso, empresas utilizam a estatística para tomar decisões, como em pesquisas de mercado ou análises de vendas de determinados produtos. Outros exemplo são as pesquisas eleitorais, realizadas antes de cada eleição, e o Censo, conduzido nos países para entender o comportamento de sua população. Todos esses exemplos destacam a importância da estatística no cenário atual.</p>


## Então, por onde começar?
<p style="text-align:justify">A primeira coisa a se entender na estatística é que existe uma ordem a se seguida para uma estudo estatístico, o primeiro passo é fazer o planejamento do estudo, isso requer escolher as perguntas certas a serem feitas ao publico alvo do estudo. Como nosso objetivo e entender o uso do Python para a área de estatística, vamos usar um estudo já pronto estatístico já pronto, o de "Gorjetas" este conjunto tem sua primeira publicação documentando no livro "Practical Data Analysis: Case Studies in Business Statistics" de Bryant, P. G. e Smith, M (1995). Este conjunto é muito famoso para quem estuda ciência de dados, ele trás a informação de 224 gorjetas recebidas por um garçom muito dedicado.</p>
<p style="text-align:justify">Os dados podem ser encontrados no site do <a herf="https://www.kaggle.com/datasets/jsphyg/tipping">Kaggle - A Waiter's Tips</a>, aqui podemos encontra o DataFrame, uma formula de representação dos dados na formula tabular.

## Visualizando os dados
Para visualizar os dados, uma das formulas mais fácil e fazendo o uso de uma biblioteca excelente do Python para isso o <a href="https://pandas.pydata.org/">Panda</a>.

> Instalando a biblioteca
>```python
>pip install pandas
>```

Toda vez que precisarmos fazer o uso de alguma das bibliotecas do Python além de fazer sua instalação é preciso importa ela no arquivo em que se está trabalhando.


~~~python
import pandas as pd
~~~

<p style="text-align:justify">Apos a importação da biblioteca é preciso importas os dados, sendo assim, criei uma pasta <code>/dados</code>, onde salvei os dados baixados do <a herf="https://www.kaggle.com/datasets/jsphyg/tipping">Kaggle</a>. Os dados vem compactados, em forma de zip, apos a descompactação é possível ver que agora existe um arquivo com o formato tipo <code>.csv</code>, do qual o nome é <i>Comma-separated values</i>, que significa nada mais que, valores separados por virgulas, ou seja, são planilhas do qual os valores cada um deles são separados por virgulas e linhas.</p>

![pasta de dados](/image/pasta_dados.png)

<p style="text-align:justify">O arquivo <code>tips.csv</code>(gorjetas) e o arquivo que está contido o estudo estatístico feito, sendo assim para que possamos visualizarmos é preciso primeiro atribuir-lo a uma variável de ambiente do Python, que iremos chamar de <code>gorjeta</code>.</p>

<p align="center">
    <img width="460" height="250" src="image\criando_gorjetas.png">
</p>

## População ou Amostra

<p style="text-align:justify">Um ponto de partida importante é entender o que significam <b>População Estatística</b> e <b>Amostra Estatística</b>.</p>
<ul>
<li><p style="text-align:justify"><b>População Estatística</b>: é o conjunto completo de elementos. Por exemplo, quando uma pesquisa estatística é feita com uma turma de colégio, e todos os integrantes da turma respondem à pesquisa, ou quando é feita com todos os seus familiares que moram com você.</p></li>
<li><p style="text-align:justify"><b>Amostra Estatística</b>: já a Amostra Estatística é utilizada quando não é possível entrevistar toda a população, pois isso demandaria muito tempo e custos elevados. Portanto, são selecionados indivíduos específicos, com base em critérios, para responder à pesquisa, e os resultados apresentados refletem uma tendência para toda a população. Isso é muito comum em pesquisas eleitorais, onde, em vez de perguntar a toda a população, seleciona-se um grupo representativo, cujas respostas indicam tendências para o restante da população. Outro exemplo claro é quando uma empresa quer lançar um novo produto e realiza uma pesquisa de mercado. Como não é viável entrevistar todos os consumidores, uma amostra é selecionada para verificar se o produto será bem aceito.</p></li>
</ul>
<p style="text-align:justify">A utilização de amostras tem vantagens, como a redução de custos e tempo, mas também traz alguns desafios. Por exemplo, se a amostra não for bem representativa da população, os resultados podem não refletir com precisão o comportamento do grupo maior. Isso torna a escolha dos critérios de seleção uma etapa crucial,e abordaremos mais a frente.</p>

<p style="text-align:justify">Um ponto a se observar é a amplitude amostral, que é calculada pela subtração do menor valor da amostra do maior valor.</p>

> ## Exemplo
> Em uma turma de 40 alunos, foram selecionados 10 alunos com as seguintes idades: 
> $$ \lparen 12, 12, 13, 15, 17, 19, 19, 25, 31, 46 \rparen$$ 
> Facilmente se observa que o menor valor é 12 e o maior é 46, sendo assim, a amplitude das idades do grupo selecionado é: 
> $$46−12=34$$
> Sendo assim a amplitude da amostra é de 34 anos. <br>
> <br>

## Variáveis estatísticas
<p style="text-align:justify">Um dos pontos mais importante na estatística é a parte da coleta de dados, uma pesquisa estatística tem que ser muito bem elaborada para que se possa atender o objetivo desejado, sendo assim as perguntas que devem ser feitas devem ser muito bem elaboradas, pois cada pergunta tera um valor na pesquisa e está sera atribuída a um campo na nossa pesquisa, este campo se chama variável, esta variável pode ser um o nome do entrevistado, a idade, ou gênero, renda salário, se gosta de um tipo de produto ou não, ou seja, tudo que for perguntando pode se tornar um tipo de variável.</p>

### Tipos de variáveis
$$\begin{matrix}
 & & &  & \text{discretas} \\
 & & & \nearrow & \\
 &  & \text{Quantitativa}\\
 & & & \searrow & \\
 & & &  & \text{contínuas} \\
 & \nearrow & \\
\text{Variável} \\
 & & &  & \text{nominais} \\
 & & & \nearrow & \\
 & \searrow & \\
 &  & \text{Qualitativa} \\
 & & & \searrow & \\
 & & &  & \text{ordinais} \\
\end{matrix}$$




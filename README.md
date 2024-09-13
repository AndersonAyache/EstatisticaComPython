# Estatística com Python
<p style="text-align:justify">
A estatística é uma área da matemática frequentemente vista como complexa e até controversa, mas é essencial no mundo moderno. Afinal, quem hoje em dia não ouviu falar do ChatGPT ou de inteligência artificial? Esses novos modelos de linguagem computacional são construídos com base em modelos estatísticos amplamente estudados e testados. Além disso, empresas utilizam a estatística para tomar decisões, como em pesquisas de mercado ou análises de vendas de determinados produtos. Outros exemplo são as pesquisas eleitorais, realizadas antes de cada eleição, e o Censo, conduzido nos países para entender o comportamento de sua população. Todos esses exemplos destacam a importância da estatística no cenário atual.
</p>


## Então, por onde começar?

<p style="text-align:justify">
A primeira coisa a se entender na estatística é que existe uma ordem a se seguida para uma estudo estatístico, o primeiro passo é fazer o planejamento do estudo, isso requer escolher as perguntas certas a serem feitas ao publico alvo do estudo. Como nosso objetivo e entender o uso do Python para a área de estatística, vamos usar um estudo já pronto estatístico já pronto, o de "Gorjetas" este conjunto tem sua primeira publicação documentando no livro "Practical Data Analysis: Case Studies in Business Statistics" de Bryant, P. G. e Smith, M (1995). Este conjunto é muito famoso para quem estuda ciência de dados, ele trás a informação de 224 gorjetas recebidas por um garçom muito dedicado.
</p>

<p style="text-align:justify">
Os dados podem ser encontrados no site do <a herf="https://www.kaggle.com/datasets/jsphyg/tipping">Kaggle - A Waiter's Tips</a>, aqui podemos encontra o DataFrame, uma formula de representação dos dados na formula tabular.
</p>

## Visualizando os dados
<p style="text-align:justify">
Para visualizar os dados, uma das formulas mais fácil e fazendo o uso de uma biblioteca excelente do Python para isso o <a href="https://pandas.pydata.org/">Panda</a>.
</p>

> Instalando a biblioteca
>```python
>pip install pandas
>```

Toda vez que precisarmos fazer o uso de alguma das bibliotecas do Python além de fazer sua instalação é preciso importa ela no arquivo em que se está trabalhando.


~~~python
import pandas as pd
~~~

<p style="text-align:justify">
Apos a importação da biblioteca é preciso importas os dados, sendo assim, criei uma pasta <code>/dados</code>, onde salvei os dados baixados do <a herf="https://www.kaggle.com/datasets/jsphyg/tipping">Kaggle</a>. Os dados vem compactados, em forma de zip, apos a descompactação é possível ver que agora existe um arquivo com o formato tipo <code>.csv</code>, do qual o nome é <i>Comma-separated values</i>, que significa nada mais que, valores separados por virgulas, ou seja, são planilhas do qual os valores cada um deles são separados por virgulas e linhas.
</p>

![pasta de dados](/image/pasta_dados.png)

<p style="text-align:justify">
O arquivo <code>tips.csv</code>(gorjetas) e o arquivo que está contido o estudo estatístico feito, sendo assim para que possamos visualizarmos é preciso primeiro atribuir-lo a uma variável de ambiente do Python, que iremos chamar de <code>gorjeta</code>.
</p>

<p align="center">
    <img width="460" height="250" src="image\criando_gorjetas.png">
</p>

<p style="text-align:justify">
Nesta tabela podemos ver as 244 vezes que este garçom anotou as informações de suas gorjetas, um ponto a se observar que o Python começa sempre sua contagem sempre no zero, por isso que o ultimo número é 243, ou seja,
</p>

$$243+1\text{ (o número na posição zero)} = 244 \text{ entradas}$$ 

<p style="text-align:justify">
Um ponto a se ressaltar aqui é, este garçom não entrevistou todas as pessoas que frequentam restaurante, então isso significa que ele só tem a estatística destas pessoas? Bem na verdade não existe um conceito na estatística que trabalha justamente sobre isso. 
</p>

## População ou Amostra
<p style="text-align:justify">
Como vimos este garçom entrevistou somente 244 pessoas, mas é possível ter uma noção de um todo? É a reposta é sim. Mas para isso primeiro precisamos entender o que é 
uma <b>População Estatística</b> e uma <b>Amostra Estatística</b>.
</p>
<ul>
    <li>
        <p style="text-align:justify">
            <b>População Estatística</b>: é o conjunto completo de elementos. Por exemplo, quando uma pesquisa estatística é feita com uma turma de colégio, e todos os integrantes da turma respondem à pesquisa, ou quando é feita com todos os seus familiares que moram com você. Para o caso do nosso exemplo o garçom só teria feito a pesquisa dele com toda a população estatística se ele tivesse entrevistado todos as pessoas que frequentam restaurantes, o que para o caso dele seria quase que impossível.
        </p>
    </li>
    <li>
        <p style="text-align:justify">
            <b>Amostra Estatística</b>:a Amostra Estatística é utilizada quando não é possível entrevistar toda a população, pois isso demandaria muito tempo e custos elevados, o que melhor se encaixa no nosso exemplo, afinal o garçom só conseguiu colegar as informações dos clientes que ele atendeu no restaurante que ele trabalha. Nestes casos, são selecionados indivíduos específicos, com base em critérios para que os resultados apresentados refletem uma tendência para toda a população. As amostras estatísticas também pode ser vistas em pesquisas eleitorais, pesquisas de mercado, quando uma empresa quer lançar um novo produto ou verificar a aceitação de seus produtos. Então toda vez que não for viável entrevistar todos os consumidores é preciso selecionar uma amostra da população, e se os critérios de seleção forem bem específicos, então esta amostra ira representar, com certas aproximações o comportamento de toda a população.
        </p>
    </li>
</ul>

## Variáveis estatísticas
<p style="text-align:justify">
Como podemos ver cada coluna representa uma informação extraída pelo garçom, tirando a primeira coluna que é chamada de ID, um identificador, todas as demais colunas tem um proposito, o nome disso em estatística é <code>variável</code>. Existe dois tipos de variáveis:
</p>


<table style="margin: 0px auto;">
    <caption>
        Variáveis estatísticas 
    </caption>
    <tr>
        <th>Tipos de Variáveis</th>
        <th>Subtipos de Variáveis</th>
        <th>Descrição</th>
        <th>Exemplos</th>
    </tr>
    <tr>
        <td rowspan="2">Qualitativa</td>
        <td>Nominal</td>
        <td>Não permite ordenação.</td>
        <td>Cor dos olhos, local de nascimento, gênero, etc... </td>
    </tr>
    <tr>
        <td>Ordinal</td>
        <td>Quando permite ordenação.</td>
        <td>Classe social, grau de escolaridade, etc... </td>
    </tr>
    <tr>
    <tr>
    <td rowspan="2">Quantitativa</td>
        <td>Continua</td>
        <td>Quando á variável admite número com virgula, ou seja, pertence a um intervalo de números reais.</td>
        <td>Altura, peso, idade, etc... </td>
    </tr>
    <tr>
        <td>Discreta</td>
        <td>Quando á variável é enumerável, quando é possível contar.</td>
        <td>Quantidade de clientes, quantidade de pedidos, Quantidade de filhos,etc... </td>
    </tr>
    <tr>
</table>

<br>
<p style="text-align:justify">A utilização de amostras tem vantagens, como a redução de custos e tempo, mas também traz alguns desafios. Por exemplo, se a amostra não for bem representativa da população, os resultados podem não refletir com precisão o comportamento do grupo maior. Isso torna a escolha dos critérios de seleção uma etapa crucial,e abordaremos mais a frente.</p>

<p style="text-align:justify">Um ponto a se observar é a amplitude amostral, que é calculada pela subtração do menor valor da amostra do maior valor.</p>

> ## Exemplo
> Em uma turma de 40 alunos, foram selecionados 10 alunos com as seguintes idades: 
> $$ \lparen 12, 12, 13, 15, 17, 19, 19, 25, 31, 46 \rparen$$ 
> Facilmente se observa que o menor valor é 12 e o maior é 46, sendo assim, a amplitude das idades do grupo selecionado é: 
> $$46−12=34$$
> Sendo assim a amplitude da amostra é de 34 anos. <br>
> <br>

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




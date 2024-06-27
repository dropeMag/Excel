<h1>Vendas de Supermercado</h1>
<h2>Descrição</h2>
Aqui tratei e analisei dados sobre o primeiro semestre de venda de um supermercado. </br>
Tomei a liberdade de traduzir e adaptar os dados. </br> </br>

Link para os dados originais: kaggle.com/datasets/aungpyaeap/supermarket-sales


</br>
<h2>Alterações Realizadas</h2>

1. Converti a data do inglês para o português:

```
=DIVIDIRTEXTO(Tabela_supermarket_sales___Sheet1[@Data]; "/")
=U2 & "/" & T2 & "/" & V2
```

2. Removi a coluna `gross margin percentage`.

3. Mantive a tabela com todos os dados brutos, mas também dividi cópias em subseções:

![Divisão em setores](https://github.com/dropeMag/Excel/assets/107576199/06a1b63a-14eb-45de-97fa-e133c80fafea)

4. Criei uma coluna `mês` para separar o número do mês da coluna data, para facilitar nos cálculos.

5. Os dados brutos possuiam problemas com seu formato monetário, foi preciso tratá-los para ficar no formato desejado. Um exemplo foi a coluna `cogs`. Como algumas linhas possuiam duas casas decimais e outras possuiam três casas decimais, usei os seguintes códigos para efetuar o tratamento:
```
=ESQUERDA(Tabela_supermarket_sales___Sheet1[@cogs];2) & "," & SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2)) = 2; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2); SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2)) = 1; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2) & "0"; SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2)) = 0; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-2) & "00")))
```
```
=ESQUERDA(Tabela_supermarket_sales___Sheet1[@cogs];3) & "," & SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3)) = 2; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3); SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3)) = 1; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3) & "0"; SE(NÚM.CARACT(DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3)) = 0; DIREITA(Tabela_supermarket_sales___Sheet1[@cogs];NÚM.CARACT(Tabela_supermarket_sales___Sheet1[@cogs])-3) & "00")))
```

6. Assim como no Power BI contamos com as medidas para nos auxiliar em cálculos, no Excel criei a tabela `Tb_Calculos`, que serve para fazer cálculos matemáticos, cujos resultados foram usados no desenvolvimento de gráficos:
![Tabela de Cálculos](https://github.com/dropeMag/Excel/assets/107576199/eea1e56a-13f9-464b-a8a4-da5f959bbe59)


</br>
<h3>Dados Antes e Depois do Tratamento</h3>

![Dados Brutos](https://github.com/dropeMag/Excel/assets/107576199/6d42e1a6-2ce9-4446-8d2c-6754b898e7ed)

![Dados Tratados](https://github.com/dropeMag/Excel/assets/107576199/94bc1ad7-171a-437d-a9cd-bc8332dba421)


</br>
<h3>Preview de Alguns Gráficos</h3>

![Dashboards 2](https://github.com/dropeMag/Excel/assets/107576199/cd52e731-11a5-4cfc-ba59-52f2873075b1)

![Dashboards 1](https://github.com/dropeMag/Excel/assets/107576199/efc0a131-d644-424d-ba54-fc49d690a63c)

<h4>Color Palette</h4>

`#FBF7F5`

`#283D3B`

`#197278`

`#772E25`

`#C44536`

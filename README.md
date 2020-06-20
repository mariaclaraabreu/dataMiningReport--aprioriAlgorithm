# Mineração de dados com o algoritmo Apriori na base Traffic Accident Severety

<h3>1. A base de dados - Traffic Accident Severety</h3> 

<p>A base de dados selecionada para realização deste trabalho foi a Traffic Accident Severity que consiste em um conjunto de dados sobre acidentes de trânsito.
Os dados são classificados pelos 14 atributos listados abaixo:</p>
<ul>
  <li>Unnamed: 0 (Sem nome: 0);</li>
  <li>Strassenklasse (Classe Rua);</li>
  <li>Unfalldatum (Data do Acidente);</li>
  <li>Alter (Idade);</li>
  <li>Unfallklasse (Classe Acidente);</li>
  <li>Lichtverhältnisse (Condições de Iluminação);</li>
  <li>Verletzte Personen (Pessoas Feridas);</li>
  <li>Anzahl Fahrzeuge (Número de Veículos);</li>
  <li>Bodenbeschaffenheit (Qualidade de Solo);</li>
  <li>Geschlecht (Sexo);</li>
  <li>Zeit (Tempo);</li>
  <li>Fahrzeugtyp (Tipo de Veículo);</li>
  <li>Wetterlage (Tempo);</li>
  <li>Monat (Mês).</li>
</ul>

<h3>2. O algoritmo e a ferramenta utilizada </h3>
<p>O algoritmo escolhido foi o Apriori pelo fato de com ele ser possível realizar Mineração de Regras de Associação. 
Esse algoritmo consegue trabalhar com um número grande de atributos, gerando 
várias alternativas combinatórias entre eles, realizando buscas sucessivas em toda 
a base de dados e mantendo um ótimo desempenho em termos de tempo de processamento. </p>
<p>A mineração foi feita na ferramenta Weka 3.8, escolhida por sua facilidade de uso e boa disponibilidade de recursos.</p>

<h3>3. Mineração e análise </h3>
<p>Ao todo, foram analisadas 15221 instâncias e durante a fase de pré-processamento dos dados, 
foi realizada a conversão dos atributos para nominal utilizando o método NumericToNominal, como 
demonstra a imagem abaixo</p></br>

![001](https://user-images.githubusercontent.com/44175992/85191058-d6afbf00-b293-11ea-9395-490cfebf028b.jpg)
</br>

<p>Na Figura abaixo, podem ser visualizados os gráficos de todos os atributos contidos na base de dados utilizada.</p>

![002](https://user-images.githubusercontent.com/44175992/85191060-d7e0ec00-b293-11ea-980a-51273f5bed84.jpg)
</br>


<p>Como resultados gerais, foi obtido como suporte mínimo 0.45 para 6849 instâncias analisadas, uma métrica de confiança de 99% e o algoritmo rodou por 11 vezes, como é mostrado abaixo (resultado dado pelo weka): </p>

```

Minimum support: 0.45 (6849 instances)
Minimum metric <confidence>: 0.9
Number of cycles performed: 11


```

<p>Como resultado dessa mineração, foram obtidas dez regras (mostradas na figura abaixo). Estas regras foram interpretadas e podem ser visualizadas na tabela após a imagem abaixo.</p>

![003](https://user-images.githubusercontent.com/44175992/85191061-d8798280-b293-11ea-93fb-c52ba0b3e23c.jpg)
</br>

<table>
  <tr>
    <td>ID</td>
    <td>Regra</td>
    <td>Interpretação</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Lichtverhältnisse=Tageslicht: Strassenbeleuchtung vorhanden Bodenbeschaffenheit=trocken 8381 ==>Wetterlage=Gut 8260 <conf:(0.99)> lift:(1.13) lev:(0.06) [975] conv:(8.99) </td>
    <td>Com nível de confiança de 99%, se 8381 dos acidentes que ocorreram durante o dia, cuja iluminação era disponível e também ocorreram em um solo seco, então em 8260 desses casos as condições climáticas eram consideradas boas.</td>
  </tr>

  <tr>
    <td>2</td>
    <td>Unfallschwere=1 Lichtverhältnisse=Tageslicht: Strassenbeleuchtung vorhanden Bodenbeschaffenheit=trocken 7482
==> Wetterlage=Gut 7370
<conf:(0.99)> lift:(1.13) lev:(0.06) [867]
conv:(8.67)</td>
    <td>Com nível de confiança de 99%, se 7482 dos acidentes foram de gravidade 1, ocorreram durante o dia, cuja iluminação era disponível, e o solo era seco, então as condições climáticas naquele dia eram consideradas boas para 7370 desses casos.</td>
  </tr>
  
  <tr>
    <td>3</td>
    <td>Bodenbeschaffenheit=trocken 11298
==> Wetterlage=Gut 11128
<conf:(0.98)> lift:(1.13) lev:(0.09) [1308] conv:(8.65)
    </td>
    <td>Com nível de confiança de 98%, se 11298 dos acidentes ocorreram em locais de solo seco, então 11128 destes foram em condições climáticas consideradas boas.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Bodenbeschaffenheit=trocken Fahrzeugtyp=Auto 7464 ==>
Wetterlage=Gut 7351	<conf:(0.98)> lift:(1.13) lev:(0.06) [863] conv:(8.57)</td>
    <td>Com nível de confiança de 98%, se 7464 dos acidentes ocorreram em um local de solo seco e por um carro, então em 7351 desses casos as condições climáticas eram consideradas boas.</td>
  </tr>
  
  <tr>
    <td>5</td>
    <td>Anzahl Fahrzeuge=2 Bodenbeschaffenheit=trocken 6999
==> Wetterlage=Gut 6891
<conf:(0.98)> lift:(1.13) lev:(0.05) [807]
conv:(8.4)</td>
    <td>Com nível de confiança de 98%, se 6999 dos acidentes envolveram dois veículos e ocorreram em um tipo de solo seco, então em 6891 destes casos as condições climáticas eram consideradas boas.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Unfallschwere=1 Bodenbeschaffenheit=trocken 10005
==> Wetterlage=Gut 9849
<conf:(0.98)> lift:(1.13) lev:(0.08) [1153] conv:(8.34)</td>
    <td>Com nível de confiança de 98%, se 10005 dos acidentes possuíram gravidade 1 e ocorreram em solo seco, então as condições climáticas do local eram consideradas boas em 9849 destes casos.</td>
  </tr>
  
  <tr>
    <td>7</td>
    <td>Anzahl Fahrzeuge=2 9268 ==> Unfallschwere=1 8504	<conf:(0.92)> lift:(1.03) lev:(0.02) [286] conv:(1.37)</td>
    <td>Com nível de confiança de 98%, se 9268 dos acidentes ocorreram com dois veículos ao mesmo tempo, então a gravidade destes foi considerada nível 1 em 8504 dos casos.</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Anzahl Fahrzeuge=2 Wetterlage=Gut 8071 ==> Unfallschwere=1 7384
<conf:(0.91)> lift:(1.03) lev:(0.01) [228]
conv:(1.33)</td>
    <td>Com nível de confiança de 91%, se 8071 dos acidentes ocorreram com dois veículos ao mesmo tempo e as condições climáticas do local eram consideradas boas, então em 7384 dos casos a gravidade do acidente foi considerada nível 1.</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Fahrzeugtyp=Auto 10376 ==>
Unfallschwere=1 9463	<conf:(0.91)> lift:(1.03) lev:(0.02) [263] conv:(1.29)</td>
    <td>Com nível de confiança de 91%, se 10376 dos acidentes envolveram o veículo carro, então a gravidade do acidente foi considerada de nível 1 em 9463 desses casos.</td>
  </tr>
  <tr>
    <td>10</td>
    <td>Fahrzeugtyp=Auto Wetterlage=Gut 8890 ==> Unfallschwere=1 8086
<conf:(0.91)> lift:(1.03) lev:(0.01) [204]
conv:(1.25)</td>
    <td>Com nível de confiança de 91%, se 8890 dos acidentes ocorreram com carro e as condições climáticas eram boas, então a gravidade de 8086 dos casos pode ser considerada de nível 1.</td>
  </tr>
  
</table>
  









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
demonstra a imagem abaixo</p>





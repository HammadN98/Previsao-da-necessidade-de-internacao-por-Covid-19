
![covid-19-4908692_1280](https://user-images.githubusercontent.com/56181068/155827749-3d2d4542-9084-4cff-a57c-8c82f160b95b.jpg)



<h1 align="center"> Prevendo a necessidade de internação por covid-19 no Hospital Sírio-Libanês </h1>



O projeto tem como necessidade fazer a predição dos pacientes que chegam ao hospital se será necessario a internação, além de que a necessiade é prever com certa rapideza. Se em um primeiro contato é possivel determinar ou não a internção.


## Ordem notebooks
 1. Analises Exploratorias.
 2. Modelos, Testes e conclusão.


## Dados :game_die:

Os dados foram disponibilizados em kaggle.com/Sírio-Libanes/covid19


## Analíse Exploratória
Foi feita uma analise inicial com graficos, com a inteção de conhecer melhor os dados e também a vinda de insghtis. Onde foram plotados varios graficos com finalidade de:
  * Grafico 1: Primeiro contado com os dados
  * Grafico 2: Separar por grupos de doenças
  * Grafico 3: Separar por idade
  * Grafico 4: Separar por grupo de Não Risco X Risco
  * Grafico 5: Seprar por sexo
 
## Tratamentos :hammer_and_wrench:
Os dados foram tratados de maneira a se adequarem melhor para a modelagem. Para isso:

&emsp;&emsp;* Valores faltantes foram preenchidos.

&emsp;&emsp;* Os pacientes que foram internados já da primeira janela foram removidos, como é pedido no enunciado do projeto.

&emsp;&emsp;* As janelas temporais foram reduzidas a apenas uma, afinal se busca uma intervenção já na primeira janela. 

&emsp;&emsp;* Com base em suas altas correlações colunas foram excluídas para não terem grande influência no modelo.


## Modelos :brain: 
Foram feitos modelos de Árvore de Decisão, Regressão Logística e de Floresta de Decisão, os quais foram refinados conforme necessário.
 
 
## Resultados :dart:
Dos 3 modelos usados, apenas 2 performaram bem, sendo eles o de Regressão Logística e de Floresta de Decisão. A média de F1-Score dos dois foi relativamente parecida, 82 para a Regressão e 80 para a Floresta de Decisão. Porém o desempate veio pela matriz de confusão onde usando os Falsos Negativos, os quais seriam pacientes que precisam de internação porém foram marcados como sem necessidade de internação este sendo o pior erro possível, já que a falta de internação poderia custar a vida de pacientes. Então por essa métrica a Regressão Logística foi escolhida!!


## Conclusões :balance_scale:
Os objetivos do projeto foram concluídos com sucesso, foi possível determinar a internação em uma primeira visita, tal qual previsão possuiu uma assertividade de 80%, o que é um valor alto. O modelo de Regressão Logística, foi escolhido com os seguintes critérios: maior precisão(F1-Score) e também pelos resultados da matriz de confusão. Que considerando nosso problema "Saber se o paciente precisa ser internado ou não", o pior problema seria mandar um paciente que precisa ser internado para casa, como o resultado desse modelo teve o menor número de Falsos Negativos foi o escolhido. E também sendo ele o com maior número de verdadeiros positivos. Apesar de ser o com o menor valor de Curva Auc. Porém não do modo que eu estava esperando, que seria com um modelo usando a floresta de Decisão, devido à sua maior complexidade de um simples regressão, talvez tenha faltado habilidade da hora de otimizar os parâmetros da floresta e fazer um modelo melhor, ou talvez o simples tenha de fato resolvido o problema de uma maneira satisfatória.


### Trabalhos futuros
Vejo como um trabalho futuro uma melhor seleção de parâmetros nos modelos, e ainda tentar mais uma vez fazer uma floresta que resolva o problema. Além de usar outros modelos de classificação. Além da criação de um pipeline para deixar tudo mais fácil quando se for mexer no notebook.


### Referências 
kaggle.com/Sírio-Libanes/covid19

https://scikit-learn.org/stable/

https://pandas.pydata.org

As aulas do bootcamp e os códigos disponibilizados, bem como os materiais extras.








![covid-19-4908692_1280](https://user-images.githubusercontent.com/56181068/155827749-3d2d4542-9084-4cff-a57c-8c82f160b95b.jpg)



<h1 align="center"> Projeto_final </h1>

## Prevendo a necessidade de internação por covid-19 no Hospital Sírio-Libanês

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
Os dados foram tratado de maneira a se adquarem melhor para a modelagem.
 Para isso:
    * Valores faltatens foram preenchidos.
    * Os pacientes que foram internados já da primeira janela foram removidos, como é pedido no enunciado do projeto.
    * As janelas temporais foram reduidas a apenas uma, afinal se busca uma intervenção já na primeira janela.
    * Com base em suas altas correlações colunas foram excluidas para nao terem grande influencia no modelo.

## Modelos :brain: 
Foram feitos modelo de Arvore de Decisão, Regressão Logistica e de Floresta de Decissão, os quais foram refinados conforme necessario.
 
## Resultados :dart:
Dos 3 modelos usados, apenas 2 performaram bem, sendo eles o de Regressão Logistica e de Floresta de Decissão.
A metrica de F1-Score dos dois foi relativamente parecidas, 82 para a Regressão e 80 para a Floresta de Decissão. Pórem o desempate veio pela matrix de confusão aonde usando os Falsos Negativos, os quais seriam pacientes que precisam de internação porém forma marcados como sem necessiade de internação  este sendo o pior erro possivel, já que a falta de internação poderia custar a vida de pacientes. Então por ess metrica a Regressão Logistica foi escolhida!!


## Conclusões :balance_scale:

Os objetivos do projeto foram concluidos com sucesso, foi possivel determinar a internação em uma primeira visita, tal qual previsão possuiu uma acertividade de 80%, o que é um valor alto.
O modelo de Regressão Logistica, foi escolhido com os seguintes criterios, maior precisão(F1-Score) e também pelas resultados da matrix de confusão. Que considerando nosso problema "Saber se o paciente precisa ser internado ou não", o pior problema seria mandar um paciente que precisa ser internado para casa, como o resultado desse modelo teve o menor numero de Falsos Negativos foi o escolhido. E tambem sendo ele o com maior numero de verdadeiros positivos. Apesar de ser o com o menor valor de Curva Auc.
Pórem não do modo que eu estava esperando, que seria com um modelo usando a floresta  de Decissão, devido s sua maior complexidade de um simples regressão, talvez tenha faltado habiidade da hora de otimizar os parametros da floresta e fazer um modelo melhor, ou talvez o simples tenha de fato resolvido o problema de uma maneira satisfatoria.

### Trabalhos futuros
Vejo como um trabalho futuro uma melhor seleção de paremetros nos modelos, e ainda tentar mais uma vez fazer uma floresta que resolva o problema. Além de usar outros modelos de classificação. Além da criação de um pipeline para deixar tudo mais facil quando se for mexer no notebook.


### Referencias 
kaggle.com/Sírio-Libanes/covid19

https://scikit-learn.org/stable/

https://pandas.pydata.org

As aulas do bootcamp e os codigos disponibilizados, bem como os materiais extras.







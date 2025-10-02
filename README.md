# **SVM Diabetes**  
#   
# **Desempenho de Técnicas de Machine Learning na Previsão de**  
# **Resultados Clínicos.**  
  
Nosso trabalho é sobre a aplicação de Machine Learning na previsão de resultados clínicos, usando o SVM que é um algoritmo de aprendizado de máquina e o nosso estudo de caso foi a precisão do uso destes modelos na detecção de **diabetes.**  
  
A diabetes é uma doença desafiadora então quanto mais cedo é feita a detecção melhor. Nosso objetivo não é substituir o médico, mas criar uma ferramenta de apoio: um modelo de IA que seja capaz de analisar dados clínicos de um paciente e prever com alta confiança se ele tem ou não a condição.  
  
Para a nossa análise utilizamos 2 modelos, **KFold 10** e **StratifiedShuffleSplit **porém antes de rodar os modelos foi necessário tratar os dados, este que é um passo muito importante na analise de dados. A primeira questão foi tratar os **zeros problemáticos**, foi observado em dados como **Glicose**, **Pressão Arterial** e **IMC** várias linhas com valores zerados, a nossa escolha foi substituir estes zeros pela média da coluna. Como o modelo precisam que os dados estejam na mesma escala usamos o **StandardScaler** para padronizar os dados.  
  
Dados pré-processados é hora de rodar o modelo, e como dito anteriormente usamos 2 validações diferentes para comparação, uma sendo a **KFold 10** que divide os dados em 10 partes, sendo ela treinando o modelo em 9 partes e testando em 1 parte, repetindo o processo 10 vezes. Como resultado a melhor configuração usou o **Kernel RBF **e foi obtida uma **acurácia de 76,56%** e um **desvio padrão de 4,86%**. Para a validação usando o **StratifiedShuffleSplit** o modelo usou 70% dos dados para treino e 30% para testes, a **melhor kernel** foi o **linear** e obtivemos uma **acurácia média de 75,76%** com um **desvio padrão** de **2,33%.**  
  
Por mais que a acurácia usando o KFold tenha sido maior o desvio padrão usando o StratifiedShuffleSplit foi melhor o que significa que a performance do modelo foi mais estável e confiável independente de qual a amostra de análise.  
  
O problema é que tivemos um recall de 47% o que significa que o modelo teve muito falsos negativos em relação aos diabéticos.  
  
A conclusão é que usando um Kernel RBF ele demonstrou uma acurácia melhor porém com um desvio padrão maior (o que não é tão bom) mas ele teve um recall bom para os não diabéticos e um recall melhor para diabéticos em relação ao StratifiedShuffleSplit que sim, teve uma estabilidade melhor porém muitos falsos negativos o que é ruim por si só mas é agravante quando estamos falando de dados de saúde.  

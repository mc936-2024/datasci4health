# Resumo
A Leucemia Linfoide Aguda (LLA) é uma neoplasia agressiva e heterogênea que afeta células precursoras de linfócitos, ocorrendo quando há o sequestro das células de seu ciclo normal de diferenciação, alterando vias de proliferação e apoptose e gerando o quadro da doença. Por se tratar de uma doença heterogênea onde casos de recaída tem um prognóstico ruim, os pacientes podem se beneficiar de abordagens baseadas na medicina de precisão, promovendo estratégias terapêuticas pensadas segundo as características moleculares do paciente, buscando o tratamento adequado para evitar recaídas e o desenvolvimento de resistência aos medicamentos.

Desta forma, buscamos criar um modelo baseado em dados de transcriptômica organizados em uma rede com o objetivo de identificar os grupos de genes mais afetados de um paciente segundo a expressão gênica e qual droga age de forma mais eficiente na rede do paciente. Esta abordagem permite maior liberdade para explorar possibilidades de tratamento ainda in sílico, tornando mais eficiente os esforços in vitro e in vivo, tentando diminuir custos e promover o desenvolvimento de alternativas terapêuticas para os pacientes.

# Introdução
A leucemia linfoide aguda (LLA) é uma neoplasia de precursores imaturos de células linfoides e é subdividida em LLA derivada de precursores de células B (LLA-B) e de precursores T (LLA-T) (Lejman et al., 2021), sendo a malignidade mais comum na infância. Atualmente, a taxa de sobrevivência da LLA pediátrica aproxima-se de 90% (Hunger et al., 2015), todavia, cerca de 3% das LLA pediatricas são resistentes (refratárias) ao tratamento de indução da remissão e entre 15 e 20% levam à reincidência (recaída) da doença, casos em que a taxa de sobrevida geral é de 50% (Annesley et al., 2015).  
Diferente de outras doenças hematológicas em que o uso de uma única droga contribuiu para o aperfeiçoamento do tratamento, como no caso de mieloma múltiplo (MM) (Jayaweera et al., 2021), o tratamento de LLA é constituído pelo emprego de várias drogas em diferentes combinações ao longo do tratamento quimioterápico, as quais visam à indução, à consolidação e à manutenção da remissão da doença (Lee et al., 2017). Ainda assim, o desenvolvimento de resistência, adquirida por diversos mecanismos celulares, é comum em casos de LLA (Borst, 1991). A LLA, como o câncer em geral, caracteriza-se por apresentar anormalidades genéticas, como aneuploidias, rearranjos cromossômicos e diversas mutações gênicas, associadas a diferentes respostas terapêuticas e ao risco de recaída da doença (Inaba et al., 2020).  

# Características genéticas da LLA pediátrica derivada de linfócitos B

É amplamente estabelecido que anormalidades cromossômicas e genéticas contribuem significativamente para a diferenciação e proliferação patológica de precursores linfoides na LLA-B, e que algumas dessas anormaliades genéticas contribuem para a estratificação dos pacientes em grupos de risco e tratamento (Lejman et al., 2022). Algumas alterações cromossômicas (como hipodiploidia ou alta hiperdiploidia), rearranjos cromossômicos (como, por exemplo, “_BCR-ABL1_”) e outras alterações genéticas (como mutações e amplificações ou deleções no gene PAX5, por exemplo), tem sido usadas como biomarcadores genéticos para a classificação das LLA.  
Alguma dessas anormalidades genéticas, como a t(12;21)(ETV6/RUNX1), estão associadas a maior quimiosensibilidade e prognóstico favorável (Ramakers-Van Woerden et al., 2000; Whitehead et al., 2001), enquanto outras, como a t(9;22)(BCR/ABL1) ou rearranjos do gene MLL, estão associadas a maior resistência _in vitro_ (Pieters et al., 1993; Ramakers-van Woerden et al., 2002) e a falha terapêutica (Aricò et al., 2000; Pui et al., 2002). A LLA hipodiplóide, subgrupo associado a prognóstico ruim (Pui et al., 2003), apresenta comumente mutações de ativação das vias Ras e PI3K, mas que parecem ser sensíveis a inibidores de PI3K (Holmfeldt et al., 2013). A LLA “ph-like” ou “BCR-ABL1-like”, em 13% dos casos apresenta rearranjos envolvendo os genes ABL1, ABL2, CSF1R e PDGFRB, e por isso são sensíveis ao tratamento com imatinib/dasatinib (Roberts et al., 2014). Deleções intersticiais do gene IKZF1, evento frequentemente encontrado nas LLA de Alto Risco e associado a pior prognóstico (Mullighan et al., 2009), contribui para maior resistência _ex vivo_ da LLA aos corticoides, como também na resposta clínica avaliada após 7 dias de tratamento com prednisolona e também foi demonstrado que a perda de IKZF1 diminui significativamente a resposta transcricional desencadeada pelos corticoides (Marke et al., 2016). Estes achados indicam que a resistência às drogas na LLA, como no câncer em geral, tem um componente genético importante, de cujo entendimento depende a definição de novos alvos terapêuticos.  
Pacientes que recaem da doença são classificados em diferentes grupos de risco de acordo com quatro variáveis: tempo entre diagnóstico e recaída, local da recaída, imunofenótipo da LLA e Doença Residual Minima (DRM) ao final da terapia de re-indução da remissão. A maioria das recaídas ocorre durante o tratamento ou até 2 anos após término do tratamento (que dura de 2 a 3 anos dependendo do protocolo utilizado). Considerado que as recaídas da LLA ocorrem mais frequentemente na parcela de pacientes de Alto Risco, para os quais o tratamento quimioterápico já alcançou o seu limite em intensidade e toxicidade, a solução do problema não está mais no simples ajuste de dose ou combinação dos quimioterápicos, mas na descoberta dos mecanismos de resistência e adoção de novos fármacos capazes de suplantá-los.

# Perguntas da Pesquisa
Considerando a importância de desenvolver novas estratégias para LLA, buscando o melhor tratamento para cada subtipo de forma a evitar o desenvolvimento de leucemias resistentes ou de recaídas, nosso projeto buscou responder às seguintes perguntas:

1. As vias moleculares alteradas na LLA se organizam em clusters?
2. Esses clusters são alvos potenciais para as classes de fármacos disponíveis que iremos triar in silico?

Desta forma, poderemos buscar interações entre fármacos e os padrões de transcrição da LLA que podem vir a basear novas ideias de tratamento.

# Metodologia

## Base de dados e evolução

| **Base de dados** | **Endereço na Web** | **Resumo descritivo** |
| --- | --- | --- |
| St. Jude Cloud Genomics Platform | <https://platform.stjude.cloud/> | Base de dados de tumores pediátricos do hospital St. Jude |
| Hospital Boldrini | Não há dados disponíveis online | Base de dados de fármacos usados no tratamento de diferentes subtipos de LLA |

## Dados de expressão e filtragem de genes

Os dados de expressão foram obtidos a partir do St. Jude Cloud Genomic Platform, onde estão disponíveis arquivos de RNA-seq de diferentes amostras de subtipos de LLA. Esses arquivos foram utilizados para se fazer a contagem dos valores de expressão em TPM, metodologia caracterizada pela maior facilidade em se comparar os níveis de expressão gênica entre diferentes grupos. Assim, gerou-se uma tabela com aproximadamente 55 mil genes, e seus valores de expressão para 280 amostras.

Esta tabela de expressão foi filtrada a partir de seus genes, em que selecionamos os 5 mil genes com maiores valores de MAD (Mean Absolute Deviation). Nesta seleção estão inseridos os genes que caracterizam clinicamente os diferentes subtipos de LLA como, por exemplo, os genes BCR e ABL1, mutados no subtipo BCR-ABL1.

## Seleção de Fármacos e identificação dos genes alvos

Os fármacos foram selecionados a partir da lista do Centro de Pesquisa Boldrini, a qual inclui medicamentos já usados pela clínica no tratamento da LLA, como também fármacos em teste clínico com uso potencial para a doença. De um total de 61 fármacos, 57 foram selecionados por terem como alvo uma proteína codificada por um gene. Fármacos que não tinham genes como alvo, os quais, por exemplo, agiam diretamente no DNA ou nos sítios do ribossomo, foram desconsiderados.

O gene alvo dos 57 fármacos foram identificados usando o banco de dados [DrugBank](https://go.drugbank.com/) onde foi possível obter a lista de genes alvos. Para garantir que nossa triagem obtivesse resultados significativos, foram desconsiderados genes alvos que estavam baseados em referências bibliográficas. A partir dessas informações, foi construído um arquivo.tsv que foi utilizado para a construção do grafo e das interações entre drogas e genes.

## Modelo Lógico

**![](/project3-final/assets/images/image1.png)**
<p align="center">Figura 1 - Modelo lógico dos grafos criados</p></br>

No modelo lógico do grafo, há a relação de interação entre proteínas. Drogas podem ser inibidoras ou antagonistas com relação às proteínas ou seus genes respectivos. A expressão dos genes e proteínas é definida pelo subtipo de alteração molecular, com as proteínas e genes mais expressos em um subtipo específico tendo uma relação de associação a ele. Note que os subtipos têm como atributo o prognóstico, que varia entre bom, intermediário e ruim.

## Integração das bases
Os dados de transcriptoma forneceram uma lista de genes mais heterogêneos em cada subtipo de LLA-B. Enquanto a lista de fármacos possibilitou a identificação de genes alvos. Ambos os dados foram integrados na forma de um grafo seguindo nosso modelo lógico (Figura 1), assim os genes coletados se transformaram em nós do nosso grafo.

## Análises Realizadas

### Procura pelos genes associados aos subtipos

Realizamos 3 tipos de análises para encontrar os genes associados aos subtipos de LLA, todas envolvendo o treinamento de uma Random Forest e a extração das *features* (genes) mais importantes. Na primeira análise, treinamos o modelo para classificar os subtipos, obtendo os 20 genes mais importantes para a classificação geral. Na segunda análise, repetimos esse processo com o prognóstico, dessa vez obtendo os genes que diferenciavam um prognóstico bom de um prognóstico ruim. Por fim, na terceira análise, treinamos o modelo para classificar um subtipo de LLA em relação a todos os outros, obtendo os 5 genes que diferenciavam aquele subtipo do resto.

Em todas as análises, filtramos o *dataset* original para conter apenas os 20 genes resultantes daquela análise (sendo que no terceiro caso, foram 5 genes para cada subtipo). A partir daí, criamos um clustermap para visualizar a expressão desses genes em cada amostra, e assim identificar padrões de expressão que pudessem ser associados a um subtipo ou prognóstico específico.

O clustermap foi feito com a biblioteca `seaborn` do Python, e a distância os genes e as amostras foi calculada com a distância de Ward, utilizando a métrica Euclidiana.

Os resultados apresentados estarão em uma escala de verde a vermelho, onde o verde representa uma expressão menor que a média, e o vermelho uma expressão maior que a média. A escala vai de -4 a 4 desvio padrões da média. É importante lembrar que nenhuma amostra é de uma pessoa saudável, logo esse desvio padrão é em relação a amostras de LLA, ou seja, um gene que está sendo menoss expresso não necessariamente é anormal, pois pode ser um gene que a média é mais elevada nos outros subtipos de LLA.

### Criação do grafo

O grafo foi criado incluindo os seguintes dados e relações:

- Proteínas/genes pertencentes às vias moleculares JAK/STAT, RTK-RAS e PI3K, e a relação entre elas
- Proteínas/genes que estão na lista dos 5000 genes com maiores valores de MAD, e a interação entre elas
- Proteínas/genes que interagem com as proteínas vindas da expressão gênica dos genes encontrados como mais importantes para a definição do subtipo, segundo a análise one-vs-all
- 17 drogas que interagem com algum dos 1000 genes com maiores valores de MAD, e as interações de inibição e antagonismo
- Genes encontrados como mais importantes para a definição do subtipo, segundo a análise one-vs-all, estão associados ao subtipo respectivo.

Note que, para todas as relações entre os genes/proteínas obtidas pelo String DB, foi considerada a sub-rede física, considerando apenas fontes de interação de experimentos e databases, com pontuação de interação maior que 0,4.

A partir desses dados, consegue-se criar o grafo. Nas imagens a seguir, os nós de cor laranja representam os subtipos, as arestas de cor laranja representam a interação de associação gene/subtipo. Os nós de cor azul representam as drogas, as arestas azuis são as relações de inibição droga-gene, as arestas verdes representam relações de antagonismo droga-gene. Os nós de cor roxa, de tamanho menor, são os genes, e as arestas finas cinzas representam as interações entre eles.

![](/project3-final/assets/images/image2.png)
<p align="center">Figura 2: Grafo completo.</p>

Pela quantidade de genes mostradas no grafo completo ser maior que 5000, a imagem se torna difícil de se analisar. Por isso, foi feito um recorte considerando somente os genes diretamente ligados à drogas e subtipos, além dos genes que pertencem aos caminhos mais curtos (desconsiderando orientação das arestas) entre drogas e subtipos. A análise dos caminhos mais curtos e das distâncias é feita na seção de resultados e discussão.

![](/project3-final/assets/images/image3.png)

<p align="center">Figura 3: grafo considerando subtipos, drogas, genes ligados diretamente às drogas e subtipos, e genes que pertencem ao caminho mínimo entre cada combinação droga-subtipo</p>

# Evolução do Projeto

Nosso projeto sofreu evoluções principalmente em relação ao tamanho do dataset analisado. Em um primeiro momento, acreditamos que uma pequena quantidade de genes já seriam o suficiente para conseguirmos separar, de uma maneira satisfatória, os subtipos de LLA, baseados em seus níveis de expressão gênica. No entanto, durante o treinamento do modelo de Machine Learning, análises nos mostraram que talvez um número baixo de genes seriam insuficientes, principalmente devido à maior dificuldade de separação das amostras do subtipo BCR-ABL1.

Assim, aumentamos o tamanho do dataset e também fizemos refinamentos no algoritmo de ML, obtendo um resultado muito melhor, no que se refere à separação das amostras em diferentes clados dos dendrogramas apresentados mais à frente. Acreditamos que os resultados foram satisfatórios e que o algoritmo de ML usado apresenta grande potencial para este fim, podendo ser usado em datasets maiores e com maior número de amostras e subtipos.

# Ferramentas

Utilizamos o Neo4J para organizar os dados brutos que vieram dos bancos de dados em gráficos de redes e construir a matriz de distâncias. O banco de dados STRING forneceu as vias protéicas que os genes diferencialmente expressos estão inseridos. O software CyoScape foi necessário para analisar o grafo em rede gerado assim como para customizar seus componentes para melhor visualização. A biblioteca em Python `scikit-learn` permitiu obter os genes que mais ajudam a identificar o subtipo da doença, através de algoritmos de clusterização.

# Resultados e Discussão
## Genes Importantes para cada Subtipo Molecular

Nossas análises resultaram na identificação dos 5 mais importantes genes para a clusterização dos 4 subtipos. Nossos resultados mostram que não há nenhuma sobreposição entre os subtipos para os 5 genes de cada subtipo. Desta forma, na construção de nosso grafo para a realização da triagem de drogas _in silico_, consideramos os genes como definidores de um subtipo.

![](/project3-final/assets/images/image4.png)
<p align="center">Figura 4. 5 genes mais importantes para a clusterização dos 4 subtipos escolhidos.</p>

A partir do gráfico criado, foram calculadas as distâncias entre os genes alvos dos fármacos e os genes definidores do subtipo. Nosso grafo conseguiu incluir 17 dos 57 fármacos devido a restrição de genes alvos presentes na nossa análise. Dos 17 fármacos, 3 agiam mais diretamente nos genes de cada subtipo, obtendo a distância de 1. Cladribine obteve a distância de 1 para o subtipo _BCR-ABL1_ e _DUX4-IGH_. Imatinib obteve esse valor de distância para o subtipo _KMT2A_. Por último, Vincristina obteve a menor distância para o subtipo _BCR-ABL1_. O subtipo _ETV6-RUNX1_ não apresentou fármacos com valores de distância 1.

![](/project3-final/assets/images/table1.png)
<p align="center">Tabela 1. Matriz de distância entre os genes alvos dos fármacos e os genes mais importantes para cada subtipo.</p>

## Subtipos moleculares de mau prognóstico - *KMT2A* e *BCR-ABL1*
Para realização deste projeto, dois subtipos moleculares de mau prognóstico foram selecionados - KMT2A e BCR-ABL1. O primeiro subtipo é caracterizado pela incidência de 70-80% de rearranjos cromossômicos no gene KMT2A (_histone lysine [K]-Methyl Transferase 2A_) em leucemia linfoide aguda pediátrica, a qual leva a linhagem de células precursoras de linfócitos B à expressão de um imunofenótipo característico - antígeno CD19 e co-expressão de CD15, CD33 e CD68, conhecidos como marcadores mielóides (Lejman et al., 2021). Sua função biológica reside na transferência de grupos metil à histonas presentes na cromatina, mediando a sua estrutura e, consequentemente, regulando a ativação da transcrição gênica por mecanismos epigenéticos. A depender do gene ao qual o KMT2A está rearranjado, os pacientes acometidos podem apresentar distintos prognósticos, aos quais classes de medicamentos como inibidores de topoisomerase já são utilizados como alternativa quimioterápica.  
De forma similar, o segundo subtipo molecular escolhido, BCR-ABL1, é caracterizado pelo rearranjo cromossômico entre o gene ALB (_ABL Proto-Oncogene 1_, na sua porção q34, no cromossomo 9) e o gene BCR (_BCR Activator Of RhoGEF And GTPase, na_ região q11 do cromossomo 22). O gene ABL codifica uma proteína da classe das tirosina-quinases, a qual fosforila substratos proteicos e, consequentemente, atua na regulação de diferentes processos celulares relevantes no contexto oncogênico, como divisão e diferenciação celular. O gene BCR, de forma similar, também atua na fosforilação proteica, entretanto, a proteína codificada a partir dele pertence à classe das serina/treonina-quinases, cuja função é extremamente relevante no contexto oncogênico, visto que atua em processos como morte celular programada (apoptose), proliferação e diferenciação celular. Ao serem rearranjados, a proteína de fusão gerada atua na imortalização de células leucêmicas por regulação anormal das vias de sinalização às quais está envolvida. Assim, pacientes acometidos por LLA-B deste tipo molecular apresentam prognósticos piores, ainda que inibidores de tirosina-quinase estejam sendo utilizados como métodos de tratamento.  
No contexto da medicina personalizada, a busca por estratégias terapêuticas alternativas que visam a melhora do paciente em sua particularidade tem sido alvo de investigações científicas. Com isso, neste projeto, pudemos identificar os genes mais relevantes em grau de importância para estes subtipos moleculares através da união dos dados de transcriptoma do hospital St. Judes e das vias de sinalização mais alteradas encontradas na literatura. Assim, ao unir estes dados com a lista de fármacos proveniente do Hospital Boldrini, foi possível realizar uma triagem de drogas _in silico,_ a qual contribui para a predição de alvos moleculares alternativos para os fármacos já existentes em fase de uso clínico ou pré-clínico.  

### Genes de maior importância para o subtipo KMT2A

Diante das análises computacionais realizadas, ao comparar este subtipo aos outros três utilizados nesta investigação, identificamos cinco genes de maior importância para a clusterização das amostras de KMT2A, a qual teve 100% de acurácia, indicando o bom funcionamento do nosso modelo para este subtipo:  
- SHANK3 (_SH3 And Multiple Ankyrin Repeat Domains 3_);  
- LAMP5 (_Lysosomal Associated Membrane Protein Family Member 5_);  
- ZNF24TR (_ZNF24 Transcription Regulator_);  
- FHIT (_Fragile Histidine Triad Diadenosine Triphosphatase_);  
- HOXA9 (_Homeobox A9_).  

Mais do que identificar os genes individualmente, a interpretação biológica mais pertinente para este projeto é dos genes em conjunto, para que seja possível determinar quais fármacos podem atuar, se não nestes diretamente, nas vias em que estão inseridos. Para este subtipo em específico, segundo a imagem abaixo (Figura 2), é possível concluir que os níveis de expressão gênica de _SHANK3, ZNF24TR_ e _FHIT_ em geral apresentam os menores desvios-padrão da média dos níveis de expressão destes genes em todas as amostras analisadas, indicando que, para este subtipo, encontram-se negativamente regulados. Em oposição a isso, os genes _LAMP5_ e _HOXA9_ encontram-se, majoritariamente, com os maiores desvios-padrão da média dos níveis de expressão, indicando que encontram-se positivamente regulados. De todas as amostras analisadas para esse subtipo, uma delas apresenta o gene _ZNF24TR_ com nível de expressão médio e os genes _SHANK3_ e _FHIT_ positivamente regulados, o que fez com que esta fosse clusterizada próxima do grupo principal, mas externo a ele.

![](/project3-final/assets/images/image5.png)
<p align="center">Figura 5. Heatmap da expressão gênica dos 5 genes mais importantes para a clusterização de KMT2A considerando a sua variação em relação a média da expressão entre os 4 subtipos.</p>

Ademais, outras duas amostras apresentaram expressão diferencial quando comparadas com as demais amostras do subtipo, visto que possuem os genes _SHANK3_ e _ZNF24TR_ negativamente regulados ou próximos à média de expressão entre todos os subtipos, o gene _FHIT_ positivamente regulado, o gene _LAMP5_ positivamente regulado e o gene _HOXA9_ com regulação negativa, fator o qual os clusterizou próximos um do outro, mas distantes do cluster principal de KMT2A. Tal identificação é importante no contexto da medicina personalizada, pois foi possível ver que, mesmo dentro de um subtipo, os pacientes possuem alterações genéticas distintas, o que pode fazer com que os fármacos possam ser empregados de maneira diferencial entre eles. Esta talvez seja uma evidência de que, em geral, os pacientes apresentam alterações similares, mas é a análise individual de cada transcriptoma que permite a determinação de um tratamento personalizado e não mais apenas a consideração do subtipo molecular.  
Por fim, no contexto de funções biológicas, embora possam ter padrões de expressão compartilhados, os genes encontrados apresentam funções bastante distintas. O _SHANK3_, por exemplo, atua nas vias de transdução de sinal mediadas por proteínas G-acopladas. Esta via é responsável por captar sinais do meio extracelular e traduzi-los em sinais intracelulares para diferentes vias de sinalização, as quais são inclusive importantes no contexto oncogênico por regularem proliferação, sobrevivência, migração, diferenciação, degradação da matriz celular e angiogênese (Liu _et al_., 2021). Ao encontrar-se menos regulado, as células neoplásicas podem, por exemplo, não responder adequadamente a um sinal externo de diferenciação ou de proliferação, o que faz com que adquiram fenótipos de escape de ciclo celular e indiferenciação.  
O gene _ZNF24TR_, por sua vez, é conhecido por atuar como um regulador transcricional, além de atuar na via hematopoiética, fator relevante no contexto da LLA. Essa molécula atua como repressora, por exemplo, do gene _PDGFR-β_ que atua como acionador de vias de proliferação celular, migração e sobrevivência (Li _et al._, 2010). Por comportar-se como um supressor de tumor, estando negativamente regulado, a repressão de _PDGFR-β_ não pode ser feita, com isso as vias citadas acima são ativadas. De forma similar, o gene _FHIT_ também atua como supressor tumoral ao regular a via de apoptose, portanto, ao estar regulado negativamente, possibilita às células leucêmicas a sua imortalização (Waters _et al._, 2014).  
Por fim, os genes positivamente regulados, como _LAMP5_ e _HOXA9_, atuam impactando no controle do crescimento celular e na expansão de células tronco hematopoiéticas, respectivamente. Segundo a literatura (Gracia _et al_, 2022; Collins _et al_., 2016), ambos estão envolvidos com processos leucemogênicos por elevarem o crescimento celular leucêmico e por manterem as células em estado precursor em sua linhagem hematopoiética. Ao observar os resultados e identificar o aumento da regulação destes, é possível concluir que a leucemogênese encontra-se intensamente estimulada nos portadores desse subtipo.  
Para estes genes, no contexto de regulação identificado e a partir de suas distâncias relativas no grafo aos genes de interesse, os fármacos que podem apresentar uma estratégia terapêutica alternativa são: os inibidores de tirosina-quinases (terminados em "-inib") e moduladores epigenéticos (terminados em "-stat"). Segundo o nosso modelo, moduladores epigenéticos de proteínas HDAC, cuja função é remover grupos acetil das histonas controlando a transcrição gênica por meio do aumento da condensação ou não da cromatina e facilitando assim o acesso da maquinaria de transcrição ao DNA, são os fármacos que impactam em grande medida este subtipo, visto que é ocasionado por uma translocação em um gene regulatório do mesmo processo de condensação da cromatina. Este achado condiz com a literatura encontrada para pacientes portadores de LLA KMT2A e, o mais interessante, é que os fármacos utilizados em conjunto com estes inibidores não são os inibidores de tirosina-quinase, mas sim inibidores de topoisomerase, como Irinotecan. Assim, os fármacos encontrados pelo nosso modelo podem ser explorados em fases pré-clínicas em conjunto com os já utilizados, o que abre janelas de oportunidade para um tratamento personalizado e adequado para este subtipo.  

### Genes de maior importância para o subtipo BCR-ABL1

Similarmente ao que foi feito para o subtipo KMT2A, foram identificados os cinco genes de maior importância para a clusterização das amostras de BCR-ABL1, a qual teve 83,3% de acurácia, indicando que o modelo funcionou para este subtipo, entretanto com uma clusterização mais esparsa das amostras:  
- GBP5 (_Guanylate Binding Protein 5)_;
- STX3 (_Syntaxin 3_);  
- DUSP6 (_Dual Specificity Phosphatase 6_);  
- S100A13 (_S100 Calcium Binding Protein A13_);  
- TUBA4A (_Tubulin Alpha 4a_).

Assim como para os outros subtipos, os genes foram analisados e interpretados biologicamente em conjunto e, segundo a Figura 3, é possível identificar um grupo de amostras que é clusterizada de forma similar, em que todos os genes em questão apresentam os maiores desvios-padrão da média dos níveis de expressão, indicando que encontram-se positivamente regulados. Entretanto, assim como foi possível observar com o subtipo KMT2A e de forma ainda mais acentuada, um conjunto de amostras apresentou expressão diferencial quando comparado com as amostras clusterizadas juntas para esse subtipo, fator o qual indica que, além de existirem alterações genéticas distintas para cada paciente, neste subtipo elas são ainda mais diversificadas, o que aumenta a necessidade do uso da medicina personalizada nesse contexto. Mais do que isso, foi possível observar claramente, utilizando como exemplo os níveis de expressão do gene _GBP5_, que mesmo dentro das amostras que compartilham um cluster, existem aquelas que apresentam maior nível de expressão quando comparadas a outras, evidenciando ainda mais essa diversificação.  

![](/project3-final/assets/images/image6.png)
<p align="center">Figura 6. Heatmap da expressão gênica dos 5 genes mais importantes para a clusterização de BCR-ABL1 considerando a sua variação em relação a média da expressão entre os 4 subtipos.</p>

Entretanto, no que diz respeito às amostras não clusterizadas e à expressão dos genes em questão, não é possível predizer um padrão único que seja compartilhado entre elas, mas é cabível citar os genes que apresentam maior variação de expressão entre os indivíduos. Em relação ao gene _S100A13_, observa-se que apenas algumas amostras apresentam menores desvios-padrão da média dos níveis de expressão deste em relação a outras amostras, indicando que estão negativamente regulados e, portanto, foram clusterizadas mais próximas umas das outras. O mesmo ocorre para os genes _GBP5, STX3, DUSP_ e _TUBA4A_, em que encontram-se em diferentes amostras com o nível de expressão na média (_GBP5_) e negativamente regulados (_STX3, DUSP_ e _TUBA4A_).  
Por fim, no que diz respeito às funções biológicas exercidas por esses genes, tem-se que o gene S100A13 atua na regulação do ciclo, a diferenciação celular e a apoptose por apresentar, em sua estrutura, dois braços EF que apresentam domínios de ligação a cálcio, e embora tenha sido pouco estudado para LLA, em LMA (Leucemia Mieloide Aguda) apresenta funções importantes no que diz respeito a leucemogênese e manutenção do fenótipo leucêmico, por estimularem inflamação e serem quimioatratores de outras células, modulando o estroma e o microambiente celular (Brener _et al._, 2018). Por estar positivamente regulado, suas atividades são intensificadas em portadores deste subtipo.  
Para o gene _GBP5_, o qual realiza a conversão de GTP em GDP por meio de hidrólise em seu produto gênico, a up-regulação impacta diretamente vias de transdução de sinal, a biossíntese proteica e a movimentação de vesículas intracelulares. Entretanto, no caso de diferentes leucemias, sua função leva a um bom prognóstico, visto que interage diretamente com proteínas da via celular apoptótica e atua então induzindo esse processo (Luo _et al._, 2021). Por estar up-regulado e associar-se com checkpoints do sistema imunológico (Fan _et al._, 2023), este gene pode indicar uma possibilidade de a imunoterapia apresentar melhores resultados para pacientes acometidos por este subtipo.  
Relativo ao gene _STX3_, que codifica uma proteína de orientação apical na membrana das células epiteliais, é importante evidenciar sua função no transporte vesicular e da exocitose. No que diz respeito à oncogênese, essa proteína atua sobre a via de sinalização PTEN-PI3K-Akt-mTOR (Chen _et al._, 2021), promovendo a estagnação do ciclo celular (Giovannone _et al.,_ 2018). Assim, tem-se que este gene up-regulado somado ao _GBP5_ indicam um prognóstico mais favorável aos que possuem essa regulação. Por sua vez, quanto ao gene _DUSP6_, sua proteína pertence à família proteica das quinases ativadas por mitógenos (MAPKs), as quais são reguladoras essenciais de processos celulares como diferenciação e proliferação. Segundo a literatura (Ahmad _et al._, 2018), essa proteína a depender do câncer, pode atuar tanto como oncogene quanto como um supressor de tumor - em carcinoma mieloide agudo, por exemplo, apresenta uma função pró-oncogênica, o que nos leva a inferir um comportamento similar para LLA ainda mais acentuado pela sua alta expressão.  
Por fim, o gene _TUBA4A_ atua na estruturação de microtúbulos. No que diz respeito à oncogênese, pouco se sabe sobre sua atuação, entretanto a literatura indica que seu mau funcionamento pode levar à geração de proteínas com estruturas de dobramento alteradas (Ganne _et al._, 2023), além de impactar suas funções básicas como a manutenção da forma e movimentação celular, o transporte intracelular de organelas e também a separação dos cromossomos ao longo do ciclo celular. Tendo isso em vista, sua alta regulação pode estar associada com o aumento da ciclagem celular, bastante comum quando se trata de oncogênese.  
Com isso em vista para estes genes, no contexto de regulação identificado, os fármacos que podem apresentar uma estratégia terapêutica alternativa, medidos pelas menores distâncias relativas nos grafos aos genes de interesse, são: Cladribine e Vincristina. Alguns, como a Vincristina, já são comumente utilizados na clínica e mostram que o modelo proposto pelo projeto funcionou adequadamente, visto que é um inibidor de microtúbulo e, portanto, associa-se ao _TUBA4A._ Já a Cladribina, por ser uma molécula química antimetabólica análoga de nucleotídeo, pode ser um futuro alvo a ser explorado, visto que ainda não é utilizada na clínica, especialmente para esse subtipo em LLA, embora já seja utilizada como quimioterápico em LMA. Por fim, fármacos das classes dos inibidores epigenéticos e inibidores de tirosina-quinase (Terminados em "-stat" e "inib", respectivamente) ainda podem futuramente contribuir para a melhora e o refinamento do tratamento quimioterápico deste subtipo, visto que atuam nas vias aos quais os genes mais relevantes encontram-se associados, como proliferação celular, diferenciação celular e apoptose - entretanto, é importante dizer que serão necessários testes clínicos adequados para verificar o uso em conjunto destas moléculas e sua toxicidade.

## Subtipos Moleculares de bom prognóstico - *DUX4-IGH* e *ETV6-RUNX1*

Em relação aos subtipos moleculares considerados como indicadores de bom prognóstico, selecionamos pacientes dos subtipos _DUX4-IGH_ e _ETV6-RUNX1_. Presente em cerca de 5% dos casos de LLA-B, a fusão do gene _DUX4_ no locus do gene _IGH_ leva a perda de função da proteína codificada pelo gene _ERG_ e causa a super-expressão de _DUX4_. Geralmente presente em crianças mais velhas e em adolescentes, esse subtipo apresenta um prognóstico favorável mesmo com as altas frequências de deleções no gene _IKZF1_, associadas a uma menor resposta a corticóides. Por sua vez, o subtipo _ETV6-RUNX1_ é a fusão gênica mais comum em LLA-B pediátrica. A translocação t(12;21)(p13;q22) está presente em cerca de 1 a cada 4 pacientes, e é pensada ser um evento de fusão que ainda ocorre no útero, porém a transformação das células precursoras de linfócitos B em blastos leucêmicos depende ainda da presença de mais alterações moleculares em vias de diferenciação e ciclo celular para ocorrer. Com base nos estudos feitos acerca do prognóstico desse subtipo, a fusão _ETV6-IGH1_ é considerada um fator independente para reduzir a intensidade da terapia em decorrência do seu bom prognóstico.

### Genes mais importantes para DUX4-IGH

![](/project3-final/assets/images/image7.png)
<p align="center">Figura 7. Heatmap da expressão gênica dos 5 genes mais importantes para a clusterização de DUX4-IGH1 considerando a sua variação em relação a média da expressão entre os 4 subtipos.</p>

A clusterização de _DUX4-IGH_, a qual obteve 97% de acurácia, foi capaz de unir a maioria dos pacientes desse subtipo em um único cluster, com poucos casos fora do agrupamento. O padrão de 5 genes que permite o cluster deste subtipo é caracterizado pela tendência de uma maior expressão de _PTPRM_, _CAPN3_, _CHST2_ acompanhada pela menor transcrição de _NTSE_ e _DIPK1C_ (Figura 7). O gene _DIPK1C_ codifica uma proteína da família FAM69 e está presente na membrana do retículo endoplasmático. Sua função ainda não é completamente compreendida, mas já há evidência de uma correlação positiva entre sua expressão e positividade da Doença Residual Mínima (DRM) (Zinngrebe _et. al._, 2019; Huang _et. al._, 2021). Já _NTSE,_ ou CD73, faz parte da via de diferenciação de linfócitos e sua alta expressão em amostras de medula óssea de pacientes com LLA foi associada a uma pior taxa de sobrevivência. Sua participação na progressão de diversos tipos de câncer o torna um possível alvo futuro para novas terapias (da Silva Nunes _et. al._, 2022; Jiang _et. al._, 2018; Gao _et. al._, 2014). Portanto, a baixa expressão desses genes em DUX4-IGH pode estar relacionada com seu prognóstico favorável.

A maior expressão de _CHST2_, uma sulfotransferase participante no processo de migração de linfócitos para sítios de inflamação, em subtipos de LLA com deleção em _ERG_ já foi observada em diferentes estudos, apesar de sua função no desenvolvimento e progressão de cânceres ainda ser desconhecida (Zhang _et. al.,_ 2023; Tanaka _et. al._, 2018). _CAPN3_ codifica uma calpaína, uma protease intracelular que possui diversos substratos com diferentes funções fisiológicas, apesar de sua função ainda não ser completamente elucidada. A expressão dessa família de genes pode variar entre ações pró- e anti-tumorais. Mutações nesse gene foram associadas a Distrofia muscular de cinturas tipo 2A, mas sua expressão foi encontrada em tecidos não musculares, incluindo em células de melanoma. Acredita-se que uma das variantes de _CAPN3_ age induzindo morte celular pelo acúmulo de p53, e sua menor expressão é observada em melanomas mais agressivos e invasivos (Shapovalov, I., Harper, D., & Greer, P. A., 2022; Niapou _et. al._, 2012, Moretti _et. al.,_ 2012) . _PTPRM_ faz parte da família de tirosinas fosfatases (PTP) que fazem parte de diversas vias de sinalização incluindo ciclo celular, diferenciação e transformação oncogênica. Acredita-se que essa família tenha um efeito de inibição em tumores e há evidências de que genes codificadores dessas proteínas possuem seus promotores metilados em amostras de LLA. Ademais, _PTPRM_ age na via de sinalização de _STAT3_, a qual é geralmente alterada em LLA (Stevenson _et. al._, 2014; Zhao _et. al._, 2021).

Dentre as drogas com menor distância relativa para estes genes em nosso grafo, temos Cladribine (antimetabólito análogo de purina). A Cladribine está em testes clínicos para LLA. O mecanismo de ação da Cladribine envolve a conversão da Cladribine em cladribine trifosfato, uma molécula que compete com a adenina trifosfato na síntese do DNA. Um dos alvos desse fármaco é a enzima codificada pelo gene PNP, que catalisa a quebra de moléculas para a produção de purinas livres. A proteína codificada pelo gene _NTSE_ tem como produto da sua atividade adenosina. A adenosina é um nucleosídeo que compete com a Cladribine pela enzima PNP. Portanto, com a baixa expressão de _NTSE_ no subtipo _DUX4-IGH_, não há uma alta produção de adenosina pela proteína codificada por esse gene e como consequência é possível que haja uma menor competição com a Cladribine pela PNP. Assim, nossa triagem foi capaz de identificar uma possível droga para ser usada no subtipo _DUX4-IGH_. Devido a ação de _PTPRM_ na via JAK/STAT, inibidores dessas proteínas como Fedratinib e Ruxolitinib, podem apresentar um efeito reduzido em _DUX4-IGH_ já que a proteína codificada por esse gene já atua reduzindo a atividade desta via.

![](/project3-final/assets/images/image8.png)
<p align="center">Figura 8. Recorte do gráfico mostrando a conexão entre o gene alvo da Cladribine e o gene NT5E, importante para a clusterização do subtipo DUX4-IGH.</p>

### Genes mais importantes para ETV6-RUNX1

![](/project3-final/assets/images/image9.png)
<p align="center">Figura 9. Heatmap da expressão gênica dos 5 genes mais importantes para a clusterização de ETV6-RUNX1 considerando a sua variação em relação a média da expressão entre os 4 subtipos.</p>

Em relação a _ETV6-RUNX1_, a clusterização obteve 100% de acurácia e os 5 genes mais importantes para esse subtipo foram capazes de clusterizar a maioria dos casos com essa fusão gênica a partir de um padrão de maior expressão em relação aos outros paciente, com poucas exceções a essa tendência (Figura 9). ENSG00000286393, ENSG00000218672 e ENSG00000260370 são genes codificadores de RNAs longos não codificantes (lncRNAs), cujas funções ainda não são conhecidas e sua relação com leucemia ainda não foi estudada. Os lncRNAs participam em diversas vias moleculares incluindo regulação epigenética, ciclo celular e apoptose, e já foram relacionados a progressão e prognóstico de diversos tipos de câncer. Há evidência da relação entre leucemia e lncRNAs e estes são considerados biomarcadores promissores podendo também se tornar alvos terapêuticos ou indicadores de prognóstico. Para _ETV6-RUNX1_, a presença desses três lncRNAs pode indicar a importância de fatores regulatórios não proteicos para esse subtipo e a possibilidade de novas estratégias de tratamento mais específicas (Gao _et. al._, 2020; Garzon _et. al._, 2014; Fernando _et. al.,_ 2015).

O gene _BIRC7_, que codifica a proteína antiapoptótica Livin, teve sua alta expressão associada a diferentes tumores sólidos e aparenta influenciar a resposta à quimioterapia. Segundo um estudo que buscou associar sua expressão com as taxas de sobrevivência de pacientes com ALL, a alta expressão de _BIRC7_ está associada a fatores de bom prognóstico e há uma resposta inicial à quimioterapia e a menores taxas de mortalidade (Wu _et. al._, 2005; Shojaie, 2016; Ibrahim _et. al._, 2014). Já o gene _TNS1_ codificada da tensina 1, a qual faz parte da adesão focal e a ligação da célula à matriz extracelular, interagindo com filamentos de actina também envolvidos com vias de sinalização celular. A inibição desta proteína utilizando prazosin aumentou a apoptose em linhagens celulares de linfomas, contudo, não há ainda um consenso se esta proteína age de forma pró- ou anti-tumoral (Sun _et. al._, 2020; Wang _et. al._, 2022).

Nenhuma droga apresentou distâncias curtas em relação aos genes mais importantes para esse subtipo. Entretanto, inibidores da via _BCL-2_, como Venetoclax, podem apresentar algum efeito nesse subtipo devido à maior expressão de _BIRC7_, já que a expressão desses dois genes parecem afetar vias semelhantes. Da mesma forma, inibidores de Beta-integrina podem também apresentar efeitos com a maior expressão de _TSN1_, apesar de seu efeito ainda não estar elucidado na LLA.

# Conclusão

Nossos resultados apontam que nosso modelo obteve sucesso em triar as drogas selecionadas de forma que obtivemos as mais próximas dos genes mais importantes para a clusterização dos subtipos, a qual foi possível devido a um padrão de expressão encontrado nos pacientes com cada variação molecular. Ademais, os genes encontrados para a classificação dos subtipos são potenciais alvos para a elaboração de um tratamento especializado, buscando a melhor opção para cada paciente e assim tentando evitar recaídas ou o desenvolvimento de resistência à quimioterapia. Nossa metodologia permite que o modelo seja facilmente expandido para outros subtipos e outros fármacos de interesse, possibilitando uma busca mais ampla para novos alvos farmacológicos para LLA.

# Trabalhos Futuros

Os próximos passos incluiriam aproveitar o modelo feito e nossa metodologia e expandir para outros subtipos com a adição de outros fármacos, aumentando a complexidade de nosso grafo e auxiliando na busca de melhores opções de tratamento para os diferentes subtipos da LLA.

# Referências  
- Ahmad MK, Abdollah NA, Shafie NH, Yusof NM, Razak SRA. Dual-specificity phosphatase 6 (DUSP6): a review of its molecular characteristics and clinical relevance in cancer. Cancer Biol Med. 2018 Feb;15(1):14-28. doi: 10.20892/j.issn.2095-3941.2017.0107. PMID: 29545965; PMCID: PMC5842331.

- Annesley, C. E., & Brown, P. (2015). Novel agents for the treatment of childhood acute leukemia. In _Therapeutic Advances in Hematology_ (Vol. 6, Issue 2). <https://doi.org/10.1177/2040620714565963>  

- Borst, P. (1991). Genetic mechanisms of drug resistance: A review. In _Acta Oncologica_ (Vol. 30, Issue 1). <https://doi.org/10.3109/02841869109091819>  

- Brenner AK, Bruserud Ø. S100 Proteins in Acute Myeloid Leukemia. Neoplasia. 2018 Dec;20(12):1175-1186. doi: 10.1016/j.neo.2018.09.007. Epub 2018 Oct 23. PMID: 30366122; PMCID: PMC6215056.  

- Chen Y, Shen L, Chen B, Han X, Yu Y, Yuan X, Zhong L. The predictive prognostic values of _CBFA2T3_, _STX3_, _DENR_, _EGLN1_, _FUT4_, and _PCDH7_ in lung cancer. Ann Transl Med. 2021 May;9(10):843. doi: 10.21037/atm-21-1392. PMID: 34164477; PMCID: PMC8184469.

- Cordo’, V., van der Zwet, J. C. G., Canté-Barrett, K., Pieters, R., & Meijerink, J. P. P. (2021). T-cell Acute Lymphoblastic Leukemia: A Roadmap to Targeted Therapies. Blood Cancer Discovery, 2(1), 19–31. <https://doi.org/10.1158/2643-3230.BCD-20-0093>  

- Collins CT, Hess JL. Role of HOXA9 in leukemia: dysregulation, cofactors and essential targets. Oncogene. 2016 Mar 3;35(9):1090-8. doi: 10.1038/onc.2015.174. Epub 2015 Jun 1. PMID: 26028034; PMCID: PMC4666810.  

- Letai, A. (2017). Functional precision cancer medicine—moving beyond pure genomics. Nature Medicine, 23(9), 1028–1035. <https://doi.org/10.1038/nm.4389>  

- Onciu, M. (2009). Acute Lymphoblastic Leukemia. Hematology/Oncology Clinics of North America, 23(4), 655–674. <https://doi.org/10.1016/j.hoc.2009.04.009>  

- Barabási, AL., Gulbahce, N. & Loscalzo, J. Network medicine: a network-based approach to human disease. Nat Rev Genet 12, 56–68 (2011). <https://doi.org/10.1038/nrg2918>  

- Fan H, Shi Y, Wang H, Li Y, Mei J, Xu J, Liu C. GBP5 Identifies Immuno-Hot Tumors and Predicts the Therapeutic Response to Immunotherapy in NSCLC. Int J Gen Med. 2023 May 10;16:1757-1769. doi: 10.2147/IJGM.S408900. PMID: 37193249; PMCID: PMC10183185.  

- Karrman, K., & Johansson, B. (2017). Pediatric T‐cell acute lymphoblastic leukemia. Genes, Chromosomes and Cancer , 56 (2), 89 116. <https://doi.org/10.1002/gcc.22416>  

- Lejman M, Chałupnik A, Chilimoniuk Z, Dobosz M. Genetic Biomarkers and Their Clinical Implications in B-Cell Acute Lymphoblastic Leukemia in Children. Int J Mol Sci. 2022 Mar 2;23(5):2755. doi: 10.3390/ijms23052755. PMID: 35269896; PMCID: PMC8911213.  

- Lejman, M., Chałupnik, A., Chilimoniuk, Z., & Dobosz, M. (2022). Genetic Biomarkers and Their Clinical Implications in B-Cell Acute Lymphoblastic Leukemia in Children. In _International Journal of Molecular Sciences_ (Vol. 23, Issue 5). <https://doi.org/10.3390/ijms23052755>

- Lejman, M., Kuśmierczuk, K., Bednarz, K., Ostapińska, K., & Zawitkowska, J. (2021). Targeted therapy in the treatment of pediatric acute lymphoblastic leukemia—therapy and toxicity mechanisms. In _International Journal of Molecular Sciences_ (Vol. 22, Issue 18). <https://doi.org/10.3390/ijms22189827>  

- Liu N, Wang Y, Li T, Feng X. G-Protein Coupled Receptors (GPCRs): Signaling Pathways, Characterization, and Functions in Insect Physiology and Toxicology. Int J Mol Sci. 2021 May 17;22(10):5260. doi: 10.3390/ijms22105260. PMID: 34067660; PMCID: PMC8156084.  

- Li J, Chen X, Liu Y, Ding L, Qiu L, Hu Z, Zhang J. The transcriptional repression of platelet-derived growth factor receptor-beta by the zinc finger transcription factor ZNF24. Biochem Biophys Res Commun. 2010 Jun 25;397(2):318-22. doi: 10.1016/j.bbrc.2010.05.110. Epub 2010 May 26. PMID: 20510677.  

- da Silva Nunes, V. B., Dias, C. K., De Bastiani, M. A., Farias, M. G., Spagnol, F., Alegretti, A. P., Daudt, L. E., Michalowski, M. B., Battastini, A. M. O., Paz, A. A., & Figueiró, F. (2022). NT5E gene and CD38 protein as potential prognostic biomarkers for childhood B-acute lymphoblastic leukemia. Purinergic Signalling, 18(2), 211–222. <https://doi.org/10.1007/s11302-022-09841-x>  

- Fernando, T. R., Rodriguez-Malave, N. I., Waters, E. V., Yan, W., Casero, D., Basso, G., Pigazzi, M., & Rao, D. S. (2015). LncRNA Expression Discriminates Karyotype and Predicts Survival in B-Lymphoblastic Leukemia. Molecular Cancer Research, 13(5), 839–851. <https://doi.org/10.1158/1541-7786.MCR-15-0006-T>

- Ganne A, Balasubramaniam M, Ayyadevara H, Kiaei L, Shmookler Reis RJ, Varughese KI, Kiaei M. In silico analysis of TUBA4A mutations in Amyotrophic Lateral Sclerosis to define mechanisms of microtubule disintegration. Sci Rep. 2023 Feb 6;13(1):2096. doi: 10.1038/s41598-023-28381-x. PMID: 36747013; PMCID: PMC9902468.  

- Gao, J., Wang, F., Wu, P., Chen, Y., & Jia, Y. (2020). Aberrant LncRNA Expression in Leukemia. Journal of Cancer, 11(14), 4284–4296. <https://doi.org/10.7150/jca.42093>  

- Gao, Z., Dong, K., & Zhang, H. (2014). The Roles of CD73 in Cancer. BioMed Research International, 2014, 1–9. <https://doi.org/10.1155/2014/460654>  

- Garzon, R., Volinia, S., Papaioannou, D., Nicolet, D., Kohlschmidt, J., Yan, P. S., Mrózek, K., Bucci, D., Carroll, A. J., Baer, M. R., Wetzler, M., Carter, T. H., Powell, B. L., Kolitz, J. E., Moore, J. O., Eisfeld, A.-K., Blachly, J. S., Blum, W., Caligiuri, M. A., … Bloomfield, C. D. (2014). Expression and prognostic impact of lncRNAs in acute myeloid leukemia. Proceedings of the National Academy of Sciences, 111(52), 18679–18684. <https://doi.org/10.1073/pnas.1422050112>  

- Gracia-Maldonado G, Clark J, Burwinkel M, Greenslade B, Wunderlich M, Salomonis N, Leone D, Gatti E, Pierre P, Kumar AR, Lee LH. LAMP-5 is an essential inflammatory-signaling regulator and novel immunotherapy target for mixed lineage leukemia-rearranged acute leukemia. Haematologica. 2022 Apr 1;107(4):803-815. doi: 10.3324/haematol.2020.257451. PMID: 33910331; PMCID: PMC8968879.  

- Giovannone AJ, Winterstein C, Bhattaram P, Reales E, Low SH, Baggs JE, Xu M, Lalli MA, Hogenesch JB, Weimbs T. Soluble syntaxin 3 functions as a transcriptional regulator. J Biol Chem. 2018 Apr 13;293(15):5478-5491. doi: 10.1074/jbc.RA117.000874. Epub 2018 Feb 23. PMID: 29475951; PMCID: PMC5900775.  

- Holmfeldt, L., Wei, L., Diaz-Flores, E., Walsh, M., Zhang, J., Ding, L., Payne-Turner, D., Churchman, M., Andersson, A., Chen, S. C., Mccastlain, K., Becksfort, J., Ma, J., Wu, G., Patel, S. N., Heatley, S. L., Phillips, L. A., Song, G., Easton, J., ... Mullighan, C. G. (2013). The genomic landscape of hypodiploid acute lymphoblastic leukemia. _Nature Genetics_, _45_(3). <https://doi.org/10.1038/ng.2532>

- Huang, Q., Zhong, J., Gao, H., Li, K., & Liang, H. (2021). Subgrouping by gene expression profiles to improve relapse risk prediction in paediatric B‐precursor acute lymphoblastic leukaemia. Cancer Medicine, 10(11), 3782–3793. <https://doi.org/10.1002/cam4.3842>  

- Hunger, S. P., & Mullighan, C. G. (2015). Acute Lymphoblastic Leukemia in Children. _New England Journal of Medicine_, _373_(16), 1541–1552. <https://doi.org/10.1056/NEJMra1400972>  

- Ibrahim, L., Aladle, D., Mansour, A., Hammad, A., Al Wakeel, A. A., & Abd El-Hameed, S. A. (2014). Expression and prognostic significance of livin/BIRC7 in childhood acute lymphoblastic leukemia. Medical Oncology, 31(5), 941. <https://doi.org/10.1007/s12032-014-0941-4>  

- Inaba, H., & Mullighan, C. G. (2020). Pediatric acute lymphoblastic leukemia. In _Haematologica_ (Vol. 105, Issue 11, pp. 2524–2539). Ferrata Storti Foundation. <https://doi.org/10.3324/haematol.2020.247031>  

- Jayaweera, S. P. E., Wanigasinghe Kanakanamge, S. P., Rajalingam, D., & Silva, G. N. (2021). Carfilzomib: A Promising Proteasome Inhibitor for the Treatment of Relapsed and Refractory Multiple Myeloma. In _Frontiers in Oncology_ (Vol. 11). <https://doi.org/10.3389/fonc.2021.740796>  

- Jiang, T., Xu, X., Qiao, M., Li, X., Zhao, C., Zhou, F., Gao, G., Wu, F., Chen, X., Su, C., Ren, S., Zhai, C., & Zhou, C. (2018). Comprehensive evaluation of NT5E/CD73 expression and its prognostic significance in distinct types of cancers. BMC Cancer, 18(1), 267. <https://doi.org/10.1186/s12885-018-4073-7>  

- Lee, J. W., & Cho, B. (2017). Prognostic factors and treatment of pediatric acute lymphoblastic leukemia. In _Korean Journal of Pediatrics_ (Vol. 60, Issue 5). <https://doi.org/10.3345/kjp.2017.60.5.129>  

- Luo, Y., Jin, H., Kim, J.H. _et al._ Guanylate-binding proteins induce apoptosis of leukemia cells by regulating MCL-1 and BAK. _Oncogenesis_ 10, 54 (2021). <https://doi.org/10.1038/s41389-021-00341-y>

- Marke, R., Havinga, J., Cloos, J., Demkes, M., Poelmans, G., Yuniati, L., Van Ingen Schenau, D., Sonneveld, E., Waanders, E., Pieters, R., Kuiper, R. P., Hoogerbrugge, P. M., Kaspers, G. J. L., Van Leeuwen, F. N., & Scheijen, B. (2016). Tumor suppressor IKZF1 mediates glucocorticoid resistance in B-cell precursor acute lymphoblastic leukemia. In _Leukemia_ (Vol. 30, Issue 7). <https://doi.org/10.1038/leu.2015.359>  

- Moretti, D., Del Bello, B., Allavena, G., & Maellaro, E. (2014). Calpains and cancer: Friends or enemies? Archives of Biochemistry and Biophysics, 564, 26–36. <https://doi.org/10.1016/j.abb.2014.09.018>  

- Mullighan, C. G., Su, X., Zhang, J., Radtke, I., Phillips, L. A. A., Miller, C. B., Ma, J., Liu, W., Cheng, C., Schulman, B. A., Harvey, R. C., Chen, I.-M., Clifford, R. J., Carroll, W. L., Reaman, G., Bowman, W. P., Devidas, M., Gerhard, D. S., Yang, W., ... Downing, J. R. (2009). Deletion of IKZF1 and Prognosis in Acute Lymphoblastic Leukemia . _New England Journal of Medicine_, _360_(5). <https://doi.org/10.1056/nejmoa0808253>  

- Niapour, M., Farr, C., Minden, M., & Berger, S. A. (2012). Elevated calpain activity in acute myelogenous leukemia correlates with decreased calpastatin expression. Blood Cancer Journal, 2(1), e51–e51. <https://doi.org/10.1038/bcj.2011.50>  

- Pieters, R., Kaspers, G. J. L., Van Wering, E. R., Huismans, D. R., Loonen, A. M., Hählen, K., & Veerman, A. J. P. (1993). Cellular drug resistance profiles that might explain the prognostic value of immunophenotype and age in childhood acute lymphoblastic leukemia. _Leukemia_, _7_(3).

- Pui, C. H., Chessells, J. M., Camitta, B., Baruchel, A., Biondi, A., Boyett, J. M., Carroll, A., Eden, O. B., Evans, W. E., Gadner, H., Harbott, J., Harms, D. O., Harrison, C. J., Harrison, P. L., Heerema, N., Janka-Schaub, G., Kamps, W., Masera, G., Pullen, J., ... Schrappe, M. (2003). Clinical heterogeneity in childhood acute lymphoblastic leukemia with 11q23 rearrangements. _Leukemia_, _17_(4). <https://doi.org/10.1038/sj.leu.2402883>

- Pui, C. H., Gaynon, P. S., Boyett, J. M., Chessells, J. M., Baruchel, A., Kamps, W., Silverman, L. B., Biondi, A., Harms, D. O., Vilmer, E., Schrappe, M., & Camitta, B. (2002). Outcome of treatment in childhood acute lymphoblastic leukaemia with rearrangements of the 11q23 chromosomal region. _Lancet_, _359_(9321). <https://doi.org/10.1016/S0140-6736(02)08782-2>  

- Ramakers-Van Woerden, N. L., Pieters, R., Loonen, A. H., Hubeek, I., Van Drunen, E., Bema Beverloo, H., Slater, R. M., Harbott, J., Seyfarth, J., Van Wering, E. R., Hahlen, K., Schmiegelow, K., Janka-Schaub, G. E., & Veerman, A. J. P. (2000). TEL/AML1 gene fusion is related to in vitro drug sensitivity for L- asparaginase in childhood acute lymphoblastic leukemia. _Blood_, _96_(3).  

- Roberts, K. G., Li, Y., Payne-Turner, D., Harvey, R. C., Yang, Y.-L., Pei, D., McCastlain, K., Ding, L., Lu, C., Song, G., Ma, J., Becksfort, J., Rusch, M., Chen, S.-C., Easton, J., Cheng, J., Boggs, K., Santiago-Morales, N., Iacobucci, I., ... Mullighan, C. G. (2014). Targetable Kinase-Activating Lesions in Ph-like Acute Lymphoblastic Leukemia. _New England Journal of Medicine_, _371_(11).<https://doi.org/10.1056/nejmoa1403088>

- Shapovalov, I., Harper, D., & Greer, P. A. (2022). Calpain as a therapeutic target in cancer. Expert Opinion on Therapeutic Targets, 26(3), 217–231. <https://doi.org/10.1080/14728222.2022.2047178>  

- Shojaie, N., & Ghaffari, S. M. (2016). Simultaneous Analysis of Wnt and NF-κB Signaling Pathways in Doxorubicin Sensitive and Methotrexate Resistant PLC/ PRF/5 Cells. Cell Journal, 17(4), 730–739. <https://doi.org/10.22074/cellj.2016.3845>  

- Song, J., Zhao, D., Sun, G., Yang, J., Lv, Z., & Jiao, B. (2021). PTPRM methylation induced by FN1 promotes the development of glioblastoma by activating STAT3 signalling. Pharmaceutical Biology, 59(1), 902–909. <https://doi.org/10.1080/13880209.2021.1944220>  

- Stevenson, W. S., Best, O. G., Przybylla, A., Chen, Q., Singh, N., Koleth, M., Pierce, S., Kennedy, T., Tong, W., Kuang, S.-Q., & Garcia-Manero, G. (2014). DNA methylation of membrane-bound tyrosine phosphatase genes in acute lymphoblastic leukaemia. Leukemia, 28(4), 787–793. <https://doi.org/10.1038/leu.2013.270>  

- Sun, X., Yang, S., & Song, W. (2020). Prazosin inhibits the proliferation and survival of acute myeloid leukaemia cells through down-regulating TNS1. Biomedicine & Pharmacotherapy, 124, 109731. <https://doi.org/10.1016/j.biopha.2019.109731>  

- Tanaka, Y., Kawazu, M., Yasuda, T., Tamura, M., Hayakawa, F., Kojima, S., Ueno, T., Kiyoi, H., Naoe, T., & Mano, H. (2018). Transcriptional activities of DUX4 fusions in B-cell acute lymphoblastic leukemia. Haematologica, 103(11), e522–e526. <https://doi.org/10.3324/haematol.2017.183152>  

- Waters CE, Saldivar JC, Hosseini SA, Huebner K. The FHIT gene product: tumor suppressor and genome "caretaker". Cell Mol Life Sci. 2014 Dec;71(23):4577-87. doi: 10.1007/s00018-014-1722-0. Epub 2014 Oct 5. PMID: 25283145; PMCID: PMC4233150.  

- Wang, Z., Ye, J., Dong, F., Cao, L., Wang, M., & Sun, G. (2022). TNS1: Emerging Insights into Its Domain Function, Biological Roles, and Tumors. Biology, 11(11), 1571. <https://doi.org/10.3390/biology11111571>  

- Wu, H., Ma, Y., Zhu, Y., Shen, Y., Gu, C., Ye, Z., & Lin, H. (2006). Expression of BIRC7 protein and mRNA in non-Hodgkin’s lymphoma. Leukemia & Lymphoma, 47(6), 1110–1116. <https://doi.org/10.1080/10428190500472271>  

- Whitehead, V. M., Payment, C., Cooley, L., Lauer, S. J., Mahoney, D. H., Shuster, J. J., Vuchich, M. J., Bernstein, M. L., Look, A. T., Pullen, D., & Camitta, B. (2001). The association of the TEL-AML1 chromosomal translocation with the accumulation of methotrexate polyglutamates in lymphoblasts and with ploidy in childhood B-progenitor cell acute lymphoblastic leukemia: A Pediatric Oncology Group study. _Leukemia_, _15_(7). <https://doi.org/10.1038/sj.leu.2402165>  

- Zhang, D., Zhang, Y., Zou, X., Li, M., Zhang, H., Du, Y., Wang, J., Peng, C., Dong, C., & Hou, Z. (2023). CHST2-mediated sulfation of MECA79 antigens is critical for breast cancer cell migration and metastasis. Cell Death & Disease, 14(4), 288. <https://doi.org/10.1038/s41419-023-05797-x>  

- Zinngrebe, J., Schlichtig, F., Kraus, J. M., Meyer, M., Boldrin, E., Kestler, H. A., Meyer, L., Fischer‐Posovszky, P., & Debatin, K. (2020). Biomarker profile for prediction of response to SMAC mimetic monotherapy in pediatric precursor B‐cell acute lymphoblastic leukemia. International Journal of Cancer, 146(11), 3219–3231. <https://doi.org/10.1002/ijc.32799>  

### Links de GeneCard
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=KMT2A>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=SHANK3>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=LAMP5>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=ZNF24TR>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=FHIT>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=HOXA9>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=ABL1>  
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=BCR>  
[https://www.genecards.org/cgi-bin/carddisp.pl?gene=GBP5](https://www.genecards.org/cgi-bin/carddisp.pl?gene=GBP5&keywords=GBP5)  
[https://www.genecards.org/cgi-bin/carddisp.pl?gene=STX3](https://www.genecards.org/cgi-bin/carddisp.pl?gene=STX3&keywords=STX3)  
[https://www.genecards.org/cgi-bin/carddisp.pl?gene=DUSP6](https://www.genecards.org/cgi-bin/carddisp.pl?gene=DUSP6&keywords=DUSP6)  
[https://www.genecards.org/cgi-bin/carddisp.pl?gene=S100A13](https://www.genecards.org/cgi-bin/carddisp.pl?gene=S100A13&keywords=S100A13)  
[https://www.genecards.org/cgi-bin/carddisp.pl?gene=TUBA4A](https://www.genecards.org/cgi-bin/carddisp.pl?gene=TUBA4A&keywords=TUBA4A)
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=CAPN3>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=NT5E&keywords=NT5E>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=PTPRM&keywords=PTPRM>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=DIPK1C&keywords=DIPK1C>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=CHST2&keywords=CHST2>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=ENSG00000286393&keywords=ENSG00000286393>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=TNS1&keywords=TNS1>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=LINC03010&keywords=ENSG00000218672>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=BIRC7&keywords=BIRC7>
<https://www.genecards.org/cgi-bin/carddisp.pl?gene=ENSG00000260370&keywords=ENSG00000260370>
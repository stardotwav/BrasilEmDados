# **O Brasil em Dados | Covid, Vacinação, Economia e Política**

Para o trabalho prático da disciplina de Introdução à Ciência dos Dados será desenvolvido um processamento dos dados sobre a pandemia do covid-19 no Brasil, além disso, os dados serão comparados a questões como a vacinação, situação socioeconômica e a questões políticas atuais no Brasil. A base de dados base será a disponibilizada no site do Governo sobre o Covid [[1]](https://covid.saude.gov.br/), sendo que além dele, para realizar a extração dos dados sobre a informações da vacinação no Brasil será usando o site, também do Governo, no caso do Ministério da Saúde, a extensão DEMAS [[2]](https://qsprod.saude.gov.br/extensions/DEMAS_C19Vacina/DEMAS_C19Vacina.html), as informações sobre o PIB dos estados [[3]](https://www.ibge.gov.br/explica/pib.php)), e por fim, falaremos sobre a relação entre os apoiadores do atual presidente e as demais informações [[4]](https://especiais.gazetadopovo.com.br/eleicoes/2018/resultados/votacao-candidatos-presidente-brasil/).

<br>

**TAREFAS REALIZADAS**

[🟣 QUESTÕES A SEREM VALIDADAS](https://github.com/Estelamb/BrasilEmDados#-questões-a-serem-validadas) 

[🔵 PREPARAÇÃO DOS DADOS](https://github.com/Estelamb/BrasilEmDados#-preparação-dos-dados) 

[⚪ ANÁLISE E EXTRAÇÃO DE CONHECIMENTO](https://github.com/EstelambBrasilEmDados#-análise-e-extração-de-conhecimento)

[🟡 ANÁLISE PREDITIVA](https://github.com/Estelamb/BrasilEmDados#-an%C3%A1lise-preditiva)

[🔴 APRESENTAÇÃO](https://github.com/Estelamb/BrasilEmDados#-apresenta%C3%A7%C3%A3o)

[🟢 ORGANIZAÇÃO DO REPOSITÓRIO](https://github.com/Estelamb/BrasilEmDados#-organização-do-repositório)

[🟠 AUTORES](https://github.com/Estelamb/BrasilEmDados#-autores)

<br>

## **🟣 QUESTÕES A SEREM VALIDADAS**

A fim de facilitar aquilo que será avaliado no trabalho foram desenvolvidas algumas questões para auxiliar, divididas nas categorias citadas anteriormente, que irão se conectar ao tema geral.

### **🔢 Casos e Mortes por Covid**
1. Amostragem dos casos de covid por estado.
2. Qual estado tem o maior número de casos acumulados de covid?
3. Qual estado apresentou o maior número de casos novos de covid em um determinado dia?
4. Qual estado tem a maior taxa de infectados por covid?
5. Qual o estado que teve a maior taxa de mortalidade? (a taxa de mortalidade consiste no número de óbitos dividido pelo número de casos)
6. Qual a maior taxa de crescimento de casos de covid em cada estado? Em que período isso ocorreu?
7. Qual a maior taxa de crescimento de óbitos de covid em cada estado? Em que período isso ocorreu?

### **📈 Taxa de Vacinação**
8. Amostragem dos dados de vacinação por estado.
9. Qual o estado com maior taxa de vacinação?
10. Qual a região com maior taxa de vacinação?
11. Existe uma relação entre a taxa de vacinação e a diminuição de casos em cada estado?
12. Existe uma relação entre a taxa de vacinação e a diminuição de casos em cada região?

### **💰 Economia**
13. Amostragem de situação socioeconômica por estado, através do PIB.
14. Os estados com menor PIB, tiveram alguma relação com o aumento de casos de covid?
15. Os estados com menor PIB, tiveram alguma relação com o taxa de mortes por covid?
16. Os estados com menor PIB, tiveram alguma relação com a taxa de vacinação de covid?

### **💼 Política**
17. Amostragem de votos durante a última eleição a favor do atual presidente.
18. O apoio ao presidente tem alguma relação com os estados com maior taxa de casos de covid?
19. O apoio ao presidente tem alguma relação com os estados com maior taxa de óbitos por covid?
20. O apoio ao presidente tem alguma relação com os estados com maior taxa de vacinação?

<br>

## **🔵 PREPARAÇÃO DOS DADOS**
 
Após a definição do conjunto de dados utilizados pelo grupo, se faz presente a preparação dos dados em ambiente para análise dos mesmos. 
Com esta etapa buscamos entender os atributos dos objetos, a tipagem dos atributos, domínio, tratar e identificar ruídos ou a falta de informações sensíveis.
 
### 🔢 **Covid**
O conjunto de dados relacionado a Covid 19, estava  dividido em módulos, assim foi realizada sua junção em somente um dataFrame. A estrutura obtida apresente os seguintes atributos: regiao, estado, municipio, coduf, codmun, codRegiaoSaude, nomeRegiaoSaude, data, semanaEpi, populacaoTCU2019, casosAcumulado, casosNovos, obitosAcumulado, obitosNovos, Recuperadosnovos, emAcompanhamentoNovos, interior/metropolitana. Todos os atributos são do tipo Object. 

#### **Informação de Atributos**
1. regiao - Nomes das regiões
2. estado - Nomes dos estados
3. municipio - Nomes dos municípios
4. coduf - Código identificador da Unidade Federativa, código de cada estado
5. codmun - Código identificador do município
6. codRegiaoSaude - Código identificador do sistema de saúda da região
7. nomeRegiaoSaude - Nome do sistema de sáude da região
8. data - Datas de marcação de casos
9. semanaEpi - Identificação da semana de epidemia 
10. populacaoTCU2019 - População TCU
11. casosAcumulado - Número de casos acumulados
12. casosNovos - Número de novos casos
13. obitosAcumulado - Número com o total de obtos acumulados
14. obitosNovos - Número com o registro de novos obtos
15. Recuperadosnovos - Número com o registro de pacientes recuperados
16. emAcompanhamentoNovos - Número de pacientes em acompanhamento
17. interior/metropolitana - Marcação da zona sendo interior o metropolitana

A verificação inicial foi realizada com o atributo data, nosso objetivo visou a identificação do período inicial e final da coleta de dados, para assim ter a referência correta do tempo, ou seja, data inicial e final. O resultado obtido foram as datas: 25 de fevereiro de 2020(25/02/2020) e 22 de agosto de 2021.  Com isso, foi possível identificar um total de 545 dias e fazer verificações com municípios. 

No decorre da análise se deparamos com uma grande quantidade de atributos presente no dataframe. Assim, foi decidido realizar uma redução do tamanho com a remoção dos seguintes atributos: coduf, codmun, codRegiaoSaude, nomeRegiaoSaude, Recuperadosnovos, emAcompanhamentoNovos e interior/metropolitana. Essas colunas não são relevantes para as informações que queremos levantar, assim se fez necessário as suas remoções. 

Em relação a retirada de ruídos, em prévia visualização das informações que são relevantes ao estudo, não apresentaram erros prejudiciais à análise. Desse modo, a priori não foi realizada remoção de ruídos.

### 📈 **Vacinação**
Os dados presentes para realizar a análise da vacinação, são separados em dois conjuntos. O primeiro conjunto contém informações gerais sobre a campanha de vacinação realizada como: Município, Cód. IBGE, UF, Região, Fabricante, Doses Aplicadas, Dose 1, Dose 2. No segundo conjunto temos das datas referentes a vacinação com ênfase nas datas realizadas. 

#### **Informação de Atributo**
1. Município -  Nomes dos municípios
2. Cód. IBGE - Número com o códifo do IBGE por município
3. UF - Nome da Unidade Federativa, nome do estado
4. Região - Nomes das regiões
5. Fabricante - Nomes das empressas fabrícantes das vacinas
6. Doses Aplicadas - Número com a quantidade de doses aplicadas(Dose 1 + Dose 2)
7. Dose 1 - Número com a quantidade da aplicação da primeira dose
8. Dose 2 - Número com a quantidade da aplicação da segunda dose

Filtragem em ruídos, se fez necessário somente no segundo conjunto. Foi identificado datas nulas, sendo as mesmas marcadas com '-', assim foram retiradas.

Em relação aos atributos, se fez necessário a remoção dos seguintes: Cód. IBGE, Dose 1, Dose 2. Com foi supracitado, buscamos a redução do dataframe. Além disso, realizar em manter somente atributos relevantes para a análise. 

### 💰💼 **Economia e Política**
Visto que as informações de PIB e dos votos recebidos ao atual presidente na última eleição (no ano de 2018) serão utilizadas apenas como base de comparação com os demais conjuntos de dados, vistos anteriormente, não foi necessário realizar nenhuma limpeza dos dados, bastando apenas deixar os mesmos registrados no arquivo [DadosEleicoesePIB.ipynb](https://github.com/Estelamb/BrasilEmDados/blob/main/DadosEleicoesePIB.ipynb)

No arquivo que contém as informações podemos verificar os respectivos valores de PIB de cada estado brasileiro, além da porcentagem de votos que o atual presidente (Jair Bolsonaro) recebeu em cada estado brasileiro durante a eleição.

<br>

## ⚪ **ANÁLISE E EXTRAÇÃO DE CONHECIMENTO**
Como uma das partes finais do projeto, temos que foram gerados gráficos, tabelas, além de diversas análises para responder as questões levantadas na primeira sessão, sendo que as mesmas estão presentes no arquivo: [AnaliseExtracaoConhecimento.ipynb](https://github.com/Estelamb/BrasilEmDados/blob/main/AnaliseExtracaoConhecimento.ipynb)

<br>

## 🟡 **ANÁLISE PREDITIVA**
Para a última etapa do trabalho foram feitos dois tipos de análises preditivas, uma que demonstra o agrupamento dos dados, mostrando sua correlação, e o outro com categorização. Ambas as análises preditivas estão no final do arquivo: [AnaliseExtracaoConhecimento.ipynb](https://github.com/Estelamb/BrasilEmDados/blob/main/AnaliseExtracaoConhecimento.ipynb).

<br>

#### AGRUPAMENTO DE DADOS
Para fazermos os agrupamentos, foram usadas as bases de dados de vacinação e os casos e mortes por covid, sendo os mesmos agrupados pelas regiões do Brasil. Para as análises, usamos de regressões lineares, para cada pessoa vacinada impacta de acordo com o coeficiente estimado no número de óbitos. A partir disso foi possível notar que em todas as regiões, os valores do coeficiente estimado e o R² sairam extremamente baixos, sendo isto justificado pela pequena parcela da população vacinada, além do fato, de que as vacinas são efetivas à longo prazo.

#### CATEGORIZAÇÃO
Já na categorização foram usados os dados da vacinação relacionados com o PIB e a População de cada região. No primeiro caso, o aprendizado de máquina não supervisionado foi utilizado de forma a analisar a relação entre a Taxa de Vacinados e o PIB, porém, ele não chegou a um agrupamento similar ao real, sendo isso principalmente justificado por termos outliers, como o estado de São Paulo, que ficou categorizado como uma região única. No segundo caso, o aprendizado de máquina não supervisionado foi utilizado de forma a analisar a relação entre o Número de Habitantes e o PIB, que assim como no caso anterior não foi possível chegar próxima do agrupamento real, repetindo o caso citado sobre o estado de São Paulo.

<br>

## 🔴 **APRESENTAÇÃO**
Foi feita uma apresentação após a análise e extração dos conhecimentos dos dados selecionados. Essa apresentação pode ser vista na plataforma do Youtube, em formato de vídeo, ou então os slides usados para a mesma. Os links para ambos os casos é: [Vídeo](https://youtu.be/OC7nNA0ZJoo) e [Slides](https://github.com/Estelamb/BrasilEmDados/blob/main/BrasilEmDados.pdf)

<br>

## 🟢 **ORGANIZAÇÃO DO REPOSITÓRIO**
No repositório teremos a inserção do Jupyter Notebook utilizado para a validação das informações do trabalho, dessa forma, na pasta base teremos o arquivo .ipynb, e uma pasta com os arquivos do tipo, por exemplo .csv, utilizados durante o processamento do trabalho.

Além disso, teremos o arquivo `requirements.txt` utilizado para a instalação do ambiente virtual do trabalho, bastando usar os comandos abaixo, considerando que [Virtualenv](https://gist.github.com/Geoyi/d9fab4f609e9f75941946be45000632b) do Python já está instalado na máquina.

```
python3 -m venv trabalhoPraticoBrasilemDados
trabalhoPraticoBrasilemDados/bin/pip3 install --upgrade pip
trabalhoPraticoBrasilemDados/bin/pip3 install -r requirements.txt
clear
echo "Pacotes instalados:"
trabalhoPraticoBrasilemDados/bin/pip3 freeze

```

<br>

Após instalado o ambiente virtual utilizado, basta executar o mesmo, e executar o Jupyter Notebook, como mostrado abaixo.

```
source trabalhoPraticoBrasilemDados/bin/activate
```

```
jupyter-notebook
```
<br>

## 🟠 **AUTORES**

**Estela Miranda** - [Estelamb](https://github.com/Estelamb)

**João Marcos Ramos** - [raitocan](https://github.com/raitocan)

**Roniel Barbosa** - [RonielNunes](https://github.com/RonielNunes)

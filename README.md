# **O BRASIL EM DADOS | COVID, VACINAS, PIB E A POLITÍCA BRASILEIRA**

Para o trabalho prático da disciplina de Introdução à Ciência dos Dados será desenvolvido um processamento dos dados sobre a pandemia do covid-19 no Brasil, além disso, os dados serão comparados a questões como a vacinação, situação socioeconômica e a questões políticas atuais no Brasil. A base de dados base será a disponibilizada no site do Governo sobre o Covid [[1]](https://covid.saude.gov.br/), sendo que além dele, para realizar a extração dos dados sobre a informações da vacinação no Brasil será usando o site, também do Governo, o Open Data SUS [[2]](https://opendatasus.saude.gov.br/dataset/covid-19-vacinacao), as informações sobre o PIB dos estados [[3]](https://www.ibge.gov.br/estatisticas/economicas/contas-nacionais/9088-produto-interno-bruto-dos-municipios.html?=&t=resultados), e por fim, falaremos sobre a relação entre os apoiadores do atual presidente e as demais informações [[4]](https://especiais.gazetadopovo.com.br/eleicoes/2018/resultados/votacao-candidatos-presidente-brasil/).
Além disso, uma informação importante que será utilizada durante o desenvolvimento do trabalho é os repositórios do GitHub, em que o link para o repositório utilizado pelo grupo está marcado em [[5]](https://github.com/Estelamb/BrasilEmDados ), sendo que o mesmo já foi compartilhado com o professor da disciplina.

<br>

## **QUESTÕES A SEREM VALIDADAS**

A fim de facilitar aquilo que será avaliado no trabalho foram desenvolvidas algumas questões para auxiliar, divididas nas categorias citadas anteriormente, que irão se conectar ao tema geral.

<br>

### **CASOS**

1. Amostragem dos casos de covid por estado.
2. Qual estado tem o maior número de casos de covid?
3. Qual estado tem a maior taxa de mortos por covid?
4. Qual estado tem a maior taxa de recuperação de covid?
5. Qual o estado que teve a maior taxa de crescimento de casos de covid?
6. Qual o estado que teve a maior taxa de crescimento de óbitos por covid?
7. Qual o estado que teve a maior taxa de mortalidade? (a taxa de mortalidade consiste no número de óbitos dividido pelo número de casos)

<br>

### **TAXA DE VACINAÇÃO**

8. Amostragem dos dados de vacinação por estado.
9. Qual o estado com maior taxa de vacinação?
10. Qual a região com maior taxa de vacinação?
11. Existe uma relação entre a taxa de vacinação e a diminuição de casos em cada estado?
12. Existe uma relação entre a taxa de vacinação e a diminuição de casos em cada região?

<br>

### **SITUAÇÃO SOCIOECONÔMICA**

13. Amostragem de situação socioeconômica por estado, através do PIB.
14. Os estados com menor PIB, tiveram alguma relação com o aumento de casos de covid?
15. Os estados com menor PIB, tiveram alguma relação com o número de recuperados de casos de covid?
16. Os estados com menor PIB, tiveram alguma relação com a taxa de vacinação de casos de covid?

<br>

### **SITUAÇÃO POLÍTICA**

17. Amostragem de votos durante a última eleição a favor do atual presidente.
18. O apoio ao presidente tem alguma relação com as regiões com maior taxa de casos de covid?
19. O apoio ao presidente tem alguma relação com as regiões com maior taxa de vacinação?
20. O apoio ao presidente tem alguma relação com o PIB das regiões?

<br>

## **ORGANIZAÇÃO DO REPOSITÓRIO**
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
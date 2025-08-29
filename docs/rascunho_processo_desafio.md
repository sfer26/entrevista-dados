[repositorio_desafio-dados](https://github.com/sfer26/entrevista-dados)

# README:
# 🚀 Desafio Técnico – Analista de Dados & Desenvolvedor LLM

Este repositório contém o desafio técnico proposto para avaliação das habilidades em **Engenharia de Dados, Machine Learning e Desenvolvimento com LLMs**.
O desafio está dividido em **duas etapas principais**, envolvendo análise de dados, visualização e aplicação de modelos de aprendizado de máquina.

---

## 📂 Estrutura do Projeto

* **/data** → Contém amostras de dados das coleções do GCP (`ShoppingCart` e `ShoppingCart_v2`).
* **/notebooks** → Jupyter Notebooks com análises exploratórias, pré-processamento e modelos preditivos.
* **/src** → Código fonte da aplicação, incluindo scripts de tratamento de dados, visualização e integração.
* **/docs** → Documentação de apoio e diagramas do fluxo de trabalho.

---

## 🎯 Descrição do Desafio

### 1️⃣ Parte 1 – Visualização de Carrinhos Abandonados

Os dados estão disponíveis no projeto **entrevista** no **Google Cloud Platform (GCP)**, contendo as coleções:

* **ShoppingCart**
* **ShoppingCart\_v2**

Esses dados representam eventos de **carrinhos abandonados** em um sistema de vendas de assinaturas de cursos.

#### Objetivo:

* Construir **visualizações interativas** (Dash, Streamlit ou outra ferramenta similar).
* Permitir **cruzamentos de informações relevantes** para:
  * Suporte à **tomada de decisão** da área de Vendas.
  * Definir **estratégias de Marketing** para reduzir a taxa de abandono.
* A interface deve ser **intuitiva**, com fluxo de navegação claro e insights acionáveis.

---

### 2️⃣ Parte 2 – Modelo de Recuperação de Vendas

Usando a biblioteca **scikit-learn**, monte um modelo preditivo para **campanhas de recuperação de clientes**.

#### Objetivo:

* Criar **amostras preditivas** para identificar clientes com maior probabilidade de conversão.
* Testar algoritmos de **aprendizado de máquina**, por exemplo:
  1. Redes Neurais (MLPClassifier).
  2. Regressão Logística.
  3. Random Forest.
* Medir a **taxa estimada de recuperação de vendas** sobre clientes perdidos.
* Gerar relatório comparativo entre os modelos testados.

	---

## 🛠️ Tecnologias Recomendadas

* **Python 3.10+**
* **Bibliotecas**:

  * `pandas`, `numpy` → tratamento de dados
  * `matplotlib`, `seaborn`, `plotly` → visualizações
  * `scikit-learn` → machine learning
  * `dash` ou `streamlit` → interface interativa
* **GCP Firestore** → origem dos dados

---

## 📊 Entregáveis

1. **Dashboard interativo** para análise de carrinhos abandonados.
2. **Modelo preditivo** documentado em Jupyter Notebook.
3. Relatório de métricas (precisão, recall, F1-score, AUC).
4. README bem documentado explicando decisões, hipóteses e limitações.

---

## 📌 Critérios de Avaliação

* Clareza e organização do código.
* Capacidade de **extrair insights úteis** dos dados.
* Correta utilização de **modelos preditivos**.
* Documentação clara e objetiva.
* Criatividade em propor soluções que **reduzam abandono** e **aumentem conversões**.

---

## ▶️ Como Executar

1. Clone este repositório:

   ```bash
   git clone https://github.com/seu-usuario/desafio-entrevista.git
   cd desafio-entrevista
   ```

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux/Mac
   venv\Scripts\activate      # Windows
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Execute a aplicação:

   ```bash
   streamlit run src/app.py
   ```

   ou

   ```bash
   python src/dashboard.py
   ```

---

## 📬 Contato

Em caso de dúvidas sobre este desafio, entre em contato pelo e-mail: **[desenvolvimento@soulcode.com](mailto:desenvolvimento@soulcode.com)**

----

## Links uteis
[sklearn medium artigo](https://medium.com/@habbema/introdu%C3%A7%C3%A3o-ao-scikit-learn-f00b7201dbf7)
[sklearn artigo asimov](https://hub.asimov.academy/blog/scikit-learn-o-que-e-por-que-usar-e-como-instalar/)
[regressao logistica - asimov](https://hub.asimov.academy/blog/entendendo-a-regressao-logistica/)
[arvores de decisao_python - asimov](https://hub.asimov.academy/blog/arvores-de-decisao-em-python-estrutura-e-aplicacoes/)
[metricas preditivas - data science](https://mariofilho.com/precisao-recall-e-f1-score-em-machine-learning/)

---
# Planejamento de Ataque

#### **Fase 0: Preparação do Ambiente e Acesso aos Dados**

-> Pipeline de ETL

- [x] **Tarefa 0.1: Fork e Clone do Repositório.**
    - **Ação:** Primeiro, faça um **Fork** do repositório no GitHub para a sua conta. Depois, clone _o seu fork_ para o ambiente onde vai trabalhar (seja localmente ou direto no Colab com `!git clone ...`). Isso garante que você tenha sua própria versão para trabalhar.
        
- [x] **Tarefa 0.2: Configuração do Ambiente Virtual.**
        
- [x] **Tarefa 0.3: Autenticação e Conexão com o GCP no Colab.**
    - **Ação:** Esta é a tarefa **mais crítica** desta fase -> código para autenticar conta do Google e permitir que o Colab acesse os dados do Firestore no projeto `entrevista`.

#### **Fase 1: Análise Exploratória e Dashboard (Parte 1 do Desafio)**

O foco aqui é entender os dados de carrinhos abandonados e apresentar os achados de forma visual e interativa.

- [x] **Tarefa 1.1: ETL - Extração e Transformação.**
    
    - **Ação:** Crie um script ou células no notebook para:
        
        1. ~~**Extrair** os dados das coleções `ShoppingCart` e `ShoppingCart_v2` do Firestore.~~
        2. ~~**Carregar** esses dados em DataFrames do Pandas.~~
        3. **Limpar e Transformar:** Unir as duas fontes se necessário, tratar dados faltantes, converter tipos de dados (especialmente datas!), e talvez criar novas colunas (ex: dia da semana, hora do abandono).
            
- **[ 📝 ] Tarefa 1.2: Análise Exploratória de Dados (EDA).**
    
    - **Ação:** Antes de construir o dashboard; O objetivo é encontrar os **insights** que serão mostrados no dashboard.
    - **Perguntas a responder:**
        - Quais produtos ou cursos são mais abandonados?
        - Qual o valor médio dos carrinhos abandonados?
        - Existe um horário de pico de abandonos? E um dia da semana?
        - Há alguma relação entre o método de pagamento escolhido e o abandono?
        - Qual etapa do funil de compra tem mais abandonos?

  - [x] Tarefa 1.3: Construção do Dashboard.**        
> Dar enfase para o uso de LOOKER, porque foi a ferramenta citada na entrevista pelo recrutador -> usar um modelo de exemplo   

#### **Fase 2: Modelo Preditivo (Parte 2 do Desafio)**

- **[ 📝 ] Tarefa 2.1: Engenharia de Features e Definição do Target.**
    - **Ação:** Prepare um novo DataFrame específico para o modelo.      
        1. **Definir o `target` (y):** Crie a variável-alvo dados que mostrem quais dos "clientes perdidos" **realmente voltaram a comprar** após uma campanha. A coluna será algo como `converteu_recuperacao` (com 0 ou 1).
        2. **Selecionar as `features` (X):** colunas que ajudarão a prever o `target`. Use os insights da EDA!             
- **[ 📝 ] Tarefa 2.2: Treinamento e Avaliação do Modelo 1 (Random Forest).**
    - **Ação:** Siga o nosso plano: comece com um, e faça-o bem.
        1. Divide os dados 
        2. Instancia e treina o `RandomForestClassifier` com `.fit()`.
        3. Fazer as previsões no conjunto de teste com `.predict()`.
        4. **analisar** o `classification_report` e a `confusion_matrix`. O que os números significam para o negócio?
            
- **[ 📝 ] Tarefa 2.3 (Opcional): Treinamento do Modelo 2 (Regressão Logística).**
    
    - **Ação:** Se o passo 2.2 correu bem e há tempo, copio o processo e apenas troco o modelo. Compara os resultados. Qual é melhor em Precisão? E em Recall?
        

#### **Fase 3: Documentação e Entrega**

Empacotar tudo para a entrega.

- **[ 📝 ] Tarefa 3.1: Limpeza e Comentários no Notebook.**
    
    - **Ação:** Notebook limpo, com células na ordem correta, comentários explicando o que fiz, e as conclusões de cada etapa.
        
- **[ 📝 ] Tarefa 3.2: Atualização do README.**
        
- **[ 📝 ] Tarefa 3.3: Preparar o Relatório Comparativo.**
       

---
### **Plano de Ataque para o Prazo**

- **Quarta:** Foco total na **Fase 0**. Conseguir ler os dados do Firestore de dentro do Colab é a sua maior prioridade e pode ter alguns detalhes técnicos.
    
- **Quinta:** Mergulhar na **Fase 1**. Fazer toda a limpeza, análise exploratória e construir a primeira versão do dashboard. É um dia cheio, mas focado.
    
- **Sexta-feira:** Foco na **Fase 2 e 3**. Como os dados já estarão limpos, a parte de modelagem será mais direta. Deixe as últimas horas para polir a documentação e o README.

---
## Organização do caderno colab 
### CADERNO 1: `01_ETL_e_Analise_Exploratoria.ipynb`
-> 1 PARTE: CONEXÃO E CARGA DOS DADOS (ETL)
(O código aqui será a base para um script em /src)

->  PARTE 2: ANÁLISE EXPLORATÓRIA (EDA)
(Esta seção será o coração do seu "01_Analise_Exploratoria.ipynb")

-> PARTE 3: PREPARAÇÃO PARA O DASHBOARD
(O código aqui vai gerar os dados que o Looker vai usar)

### CADERNO 2:  `02_Modelo_Preditivo.ipynb`
-> PARTE 4: ENGENHARIA DE FEATURES PARA O MODELO
(Esta seção será o começo do seu "02_Modelo_Preditivo.ipynb")
-> PARTE 5: TREINAMENTO E AVALIAÇÃO DO MODELO
(Continuação do "02_Modelo_Preditivo.ipynb")
(células com o treino do RandomForest, LogisticRegression e a avaliação)

---
# Conexão com firestore e extração dos dados

> tive erro com a conexão do firestore (gcp) e colab
> confundi os diretorios

-> Achava que era:
```Markdown
📁 entrevista (coleção)
  └── 📄 shoppingCart (documento)
      └── 📁 shoppingCart (subcoleção)
          ├── 📄 000475912411
          ├── 📄 001043589133
          └── 📄 outros...
```

-> E era:

``` Markdown
📁 shoppingCart (coleção na RAIZ)
├── 📄 000475912411
├── 📄 001043589133  
├── 📄 001372999061
└── 📄 outros...

📁 shoppingCartV2 (outra coleção na RAIZ)
├── 📄 outros documentos...
```

> Para evitar erros: 
```python
#Cole isso sempre que não souber a estrutura
collections = list(db.collections()) print("Coleções na raiz:", [col.id for col in collections])
```

-> Lógica do Firestore:
``` python
# COLEÇÃO direta na raiz:
db.collection('nome_colecao')

# SUBCOLEÇÃO (dentro de um documento):
db.collection('colecao_pai').document('doc_pai').collection('subcolecao')
```

>[!example] Firestore tem uma hierarquia específica: 
>`database → coleções → documentos → subcoleções → documentos...`
>Estava procurando em `database → entrevista/shoppingCart/shoppingCart` quando na verdade era `database → shoppingCart`

#### Script da extração dos dados do firestore
``` python
# EXTRAÇÃO DE DADOS DO FIRESTORE
from google.cloud import firestore
import pandas as pd

# Configurações do projeto
project_id = 'entrevistas-470214'
database_id = 'entrevista'
db = firestore.Client(project=project_id, database=database_id)  
print("✅ Conexão estabelecida com Firestore") 

# EXTRAÇÃO shoppingCart
print("\nEXTRAINDO DADOS DE 'shoppingCart'...")
dados_shopping_cart = []
cont_v1 = 0 

for doc in db.collection('shoppingCart').stream():
cont_v1 += 1
doc_data = doc.to_dict()
doc_data['purchase_id'] = doc.id
dados_shopping_cart.append(doc_data)

if cont_v1 % 100 == 0:
print(f" Processados: {cont_v1} documentos...")  
print(f"✅ shoppingCart: {cont_v1} documentos extraídos") 

# EXTRAÇÃO shoppingCartV2
print("\nEXTRAINDO DADOS DE 'shoppingCartV2'...")
dados_shopping_cart_v2 = []
cont_v2 = 0

for doc in db.collection('shoppingCartV2').stream():
cont_v2 += 1
doc_data = doc.to_dict()
doc_data['purchase_id'] = doc.id
dados_shopping_cart_v2.append(doc_data)
 
if contador_v2 % 100 == 0:
print(f" Processados: {cont_v2} documentos...") 
print(f"✅ shoppingCartV2: {cont_v2} documentos extraídos")
  
# VERIFICAÇÃO
print("\n" + "="*60)
print("RESUMO DA EXTRAÇÃO:")
print(f"shoppingCart: {len(dados_shopping_cart)} documentos")
print(f"shoppingCartV2: {len(dados_shopping_cart_v2)} documentos")
print(f"Total extraído: {len(dados_shopping_cart) + len(dados_shopping_cart_v2)} documentos")
  
# TESTE: Verificar estrutura dos primeiros documentos
print("\nVERIFICAÇÃO DE ESTRUTURA:")
if dados_shopping_cart:
print(f"Colunas shoppingCart: {list(dados_shopping_cart[0].keys())}")
else:
print("shoppingCart vazio")  

if dados_shopping_cart_v2:
print(f"Colunas shoppingCartV2: {list(dados_shopping_cart_v2[0].keys())}")
else:
print("shoppingCartV2 vazio") 

print("\n✅EXTRAÇÃO CONCLUÍDA!")
print("Variáveis disponíveis:")
print(" - dados_shopping_cart (lista de dicts)")
print(" - dados_shopping_cart_v2 (lista de dicts)")
```


#### Script de criação de Dataframes para começar a explorar os dados pra tratamento e limpeza

``` python
# CRIAÇÃO DE DATAFRAMES
import pandas as pd
print("CRIANDO DE DATAFRAMES")
print("="*60) 

# DATAFRAME 1: shoppingCart
df_shopping_cart = pd.DataFrame(dados_shopping_cart)  

# Adicionar coluna identificadora da origem do dado
if not df_shopping_cart.empty:
df_shopping_cart['collection_source'] = 'shoppingCart'  
print(f"✅ df_shopping_cart criado: {df_shopping_cart.shape}")

# DATAFRAME 2: shoppingCartV2
df_shopping_cart_v2 = pd.DataFrame(dados_shopping_cart_v2) 
# Adicionar coluna identificadora
if not df_shopping_cart_v2.empty:
df_shopping_cart_v2['collection_source'] = 'shoppingCartV2' 
print(f"✅ df_shopping_cart_v2 criado: {df_shopping_cart_v2.shape}")
  
# DATAFRAME Unificado
# Combinar os dois DataFrames
df_shopping_cart_unificado = pd.concat([
df_shopping_cart,
df_shopping_cart_v2
], ignore_index=True)
 

print(f"✅ df_shopping_cart_unificado criado: {df_shopping_cart_unificado.shape}")

```

##### Criação da Coluna Identificadora (collection_source)

Antes de unificar os dois DataFrames (df_shopping_cart e df_shopping_cart_v2), uma coluna chamada collection_source foi adicionada a cada um deles. O valor desta coluna é uma string que identifica a coleção de origem de cada registro ('shoppingCart' ou 'shoppingCartV2').

Esta etapa é crucial por três motivos principais:
- Rastreabilidade (Data Provenance): Após a união dos DataFrames, a informação sobre de qual fonte cada linha veio seria permanentemente perdida. Esta coluna age como uma "etiqueta", garantindo que, mesmo no DataFrame final unificado, possamos rastrear a origem de cada registro.
- Análise Comparativa:  A coluna se torna uma ferramenta poderosa para segmentar e comparar os dois conjuntos de dados. Com ela, posso facilmente responder perguntas como: "A taxa de abandono é diferente entre os dados da V1 e da V2?" ou "O preço médio dos produtos varia entre as duas fontes?".
- Depuração (Debugging): Se encontrarinconsistências, erros ou valores inesperados em um subconjunto dos dados unificados, esta coluna permite isolar rapidamente a fonte original do problema (V1 ou V2), facilitando a investigação e a correção.

---
# Limpeza e tratamento

### Validar hipotese que V2 seja as vendas convertidas
-> não tem nada a ver, os dois df possuem abandono de carrinho
-> são apenas 'versões' diferentes
-> usar df_unificado já que as diferenças não vão interferir na EDA
	
``` Markdown
ANÁLISE DE COLUNAS:
- Colunas comuns: 18
- Colunas apenas em shoppingCart: 0
- Colunas apenas em shoppingCartV2: 2
- Exclusivas de shoppingCartV2: ['brand', 'ticket_id']
```

> tratar 'brand' e 'ticket_id' para o que vier nulo da V1 não atrapalhe
> brand será mantido, pode ter insights legais ao relacionar com price
> ticket_id: dropar -> não tem relevância. Melhor dropar já que tem diferença do df_shopping_cart para V2, só vai acumular serviço para tratar os nulos que vierem do primeiro df

### Limpar e selecionar colunas uteis
#### Remoção: cpf, email, phoneNumber, id, webhook, customer_id, subscription_id, shoppingCartHubspotId
- Decisão:
``` python
# Lista de colunas para dropar
colunas_para_remover = ['ticket_id', 'cpf', 'email', 'phoneNumber', 'id',
'webhook', 'customer_id', 'subscription_id', 'shoppingCartHubspotId']
```

``` Markdown
Colunas removidas com sucesso!
Colunas restantes no DataFrame 'df_limpo':
['lastName', 'firstName', 'price', 'paymentMethod', 'purchaseStatus', 'planName', 'createdAt', 'integrationStatus', 'purchase_id', 'collection_source', 'brand']
```

> ==MANTER 'purchase_id' como identificador único==
#### Renomear colunas
- Snake-case
- Português
- Descritivo mas conciso
``` python
# Renomear colunas mantidas
novos_nomes = {
'lastName': 'sobrenome',
'firstName': 'nome',
'price': 'preco',
'paymentMethod': 'metodo_pagamento',
'purchaseStatus': 'status_compra',
'planName': 'plano',
'createdAt': 'data_criacao',
'integrationStatus': 'status_integracao',
'purchase_id': 'id_compra',
'collection_source': 'origem_dados',
'brand': 'marca'
}
```
### Tratar valores nulos/brancos (missing values)
- brand e ticket_id: Para os registros que vieram da V1, esses valores são nulos. Posso preenchê-los com um valor que indique isso
		- brand: N/A
		- ~~ticket_id~~: 0 -> *coluna dropada*
		-- paymentMethod, planName: Não Informado
	- price: alguns estão vazios -> erro ? VERIFICAR se tem relação com algum status -> prencher com 0 (talvez)
		- Erro de sistema → mediana/média 
		- Abandono precoce → valor especial (-1) 
		- Produto gratuito → realmente 0

```
'marca': 'Nao_Informado',
'metodo_pagamento': 'Nao_Selecionado',
'plano': 'Nao_Definido'
```

#### Investigação de nulos da coluna 'price'
-> relacionando com status_compra

```
Preços nulos: 8108
Distribuição de status com preço nulo:
status_compra
Abandoned    5716
Success      2392
Name: count, dtype: int64

# nao tem a ver com o status da compra -> os nulos acontecem tanto em carrinhos abandonados quanto os convertidos em pedidos
```

-> origem:
```
Missing por origem:
origem_dados
shoppingCart      4054
shoppingCartV2    4054
Name: count, dtype: int64
```
	# também não diz muita coisa. os nulos são iguais em cada origem

-> temporal ? (algum período de tempo)

``` Markdown
data_criacao
2023-03    8108
Name: count, dtype: int64

MARÇO! Todos os nulos são do período de 2023-03. Pode ser um erro técnico\nUsar mediana do período adjascente\nTratar data antes de fazer o tratamento de nulos de 'price'
```

DECISÃO: Mediana do período adjascente
``` python
# Mediana dos adjacentes
# converter para str e verificar se o mês está na lista
# verifica se o preço não é nulo
# combinar os filtros com '&'
# seleciona e calcula a mediana desses valores
mediana_contexto = df_limpo[
(df_limpo['data_criacao'].dt.strftime('%Y-%m').isin(['2023-02', '2023-04'])) &
(df_limpo['preco'].notna())
]['preco'].median()
```

	- depois foi só imputar em março o valor da mediana:
	  Preços imputados com: R$ 682.80
	Missing values restantes: 0

#### Por que usar mediana na substituição de valores nulos do preço?
1. **Mais conservadora** - não vai distorcer suas análises
2. **Padrão na indústria** para dados financeiros/preços
3. **Robusta** - funciona bem independente da distribuição
4. **Defensável** - sempre é uma escolha segura

> [!question] Quando considerar média???
 Se tiver certeza que: 
> 1. Distribuição é aproximadamente normal
>2. Poucos outliers
>3. Distribuição é aproximadamente normal
>4. Poucos outliers
>5. Quer preservar a "informação" dos valores extremos
>
-> Exemplo: se produtos premium são importantes para análise
 Mas mesmo assim, pode usar média truncada (remove extremos) 



---
### Eng. de Feature (novas colunas, reestruturação)
- Data: coluna 'createdAt'
		- organizar mes, dia_semana, hora

#### 1. Features Temporais

- **Novas Colunas:** `ano`, `mes`, `dia`, `dia_semana`, `hora`, `periodo_dia`.
- **Descrição:** Estas colunas quebram a data e hora exata da criação do carrinho (`data_criacao`) em componentes mais fáceis de analisar e agrupar.
- **Lógica de Criação:**
    - As colunas `ano`, `mes`, `dia`, `dia_semana` e `hora` foram extraídas diretamente da coluna `data_criacao` usando as funções de data e hora do Pandas (`.dt`).
    - A coluna `periodo_dia` foi criada para agregar as 24 horas em quatro categorias mais simples: Madrugada (0h-5h), Manhã (6h-11h), Tarde (12h-17h) e Noite (18h-23h).
- **Objetivo Analítico:** Identificar padrões de comportamento baseados no tempo. Permite responder perguntas como: "A taxa de abandono é maior em algum `dia_semana` específico?" ou "O `periodo_dia` influencia a decisão de compra?"
#### 2. Feature de Preço Categórico
- **Nova Coluna:** `faixa_preco`.
- **Descrição:** Segmenta os produtos em quatro categorias de preço, transformando uma variável numérica contínua em uma categórica.
- **Lógica de Criação:** A coluna `preco` foi discretizada usando a função `pd.cut` do Pandas, com as seguintes faixas: `baixo` (até 500), `medio` (501-650), `alto` (651-750) e `premium` (acima de 750).
- **Objetivo Analítico:** Simplificar a análise de preço e criar segmentos de valor. Permite investigar: "Clientes que compram produtos na faixa 'Premium' abandonam mais o carrinho?" ou "Qual a faixa de preço mais popular?".
#### 3. Features de Regra de Negócio
- **Novas Colunas:** `tipo_plano`, `converteu`.
- **Descrição:** Criação de indicadores binários que refletem lógicas importantes para o negócio, simplificando análises complexas.
- **Lógica de Criação:**
    - `tipo_plano`: Classifica os planos em 'Simples' ou 'Combo'. A regra, inferida dos dados, define como 'Combo' qualquer plano que contenha "Assinatura M" em seu nome, indicando a junção de mais de um produto.
    - `converteu`: É uma flag booleana (`True`/`False`) que indica se a venda foi bem-sucedida. Foi criada a partir da coluna `status_compra`, recebendo `True` quando o status é 'Success'.
- **Objetivo Analítico:** Criar variáveis-chave para o dashboard. A coluna `converteu` é a nossa **variável alvo** principal, permitindo calcular taxas de conversão de forma direta para qualquer segmento. A coluna `tipo_plano` permite comparar a performance de diferentes ofertas de produto.
    

---
### EDA
[correlacao em python](https://medium.com/@joaopedro.thereziano/an%C3%A1lise-de-correla%C3%A7%C3%A3o-utilizando-python-30bcf29423c3)


![[Pasted image 20250828212026.png]]

### Primeiros insights: HORAS E DIAS
#### 1. O Fenômeno das 14h: A "Hora de Ouro"

- **Observação:** Às 14h, você tem o **maior volume de vendas E a maior taxa de conversão**. O ticket médio nesse horário é bom, mas não é o mais alto do dia.
- **Interpretação:** Este é, sem dúvida, o seu horário mais importante. É quando o maior número de clientes está ativo e, ao mesmo tempo, mais propenso a comprar. A combinação de alto tráfego com alta intenção de compra faz deste o motor do seu faturamento diário.
- **Hipótese (Persona):** Pode ser o pico do "horário de almoço" ou "pós-almoço", onde as pessoas usam uma pausa no trabalho para finalizar compras. Por ser um horário de massa, os produtos comprados podem ser os mais populares e de valor mediano, o que explica por que o ticket médio não é o mais alto.
- **Ação Estratégica:** **Máxima agressividade aqui.** Campanhas de marketing, e-mails e notificações push devem ser concentradas para chegar aos clientes um pouco antes e durante este horário. Garanta que o site esteja com performance máxima e o estoque dos produtos principais esteja abastecido.
#### 2. Os Compradores Noturnos (22h - 23h): Eficiência e Volume
- **Observação:** Este período tem a **segunda maior onda de vendas** e uma **taxa de conversão altíssima**, rivalizando com o pico das 14h.
- **Interpretação:** Este é outro bloco de horário extremamente valioso. São clientes que provavelmente estão comprando de casa, com calma, após o dia de trabalho e outras obrigações.
- **Hipótese (Persona):** O comprador "relaxando no sofá". Eles estão navegando com calma, talvez no celular ou tablet. São decididos e sabem o que querem, o que explica a alta conversão.
- **Ação Estratégica:** Campanhas de remarketing são excelentes para este horário. Lembre o cliente daquele produto que ele viu mais cedo. Ofertas "só hoje à noite" podem criar um senso de urgência e impulsionar ainda mais as vendas.
#### 3. A Anomalia da Madrugada (aprox. 4h - 6h): Poucos, mas Valiosos
- **Observação:** O volume de vendas e a taxa de conversão são **extremamente baixos**. No entanto, o **maior pico de Ticket Médio do dia acontece às 6h da manhã**.
- **Interpretação:** Esta é a análise mais interessante! Os pouquíssimos clientes que compram neste horário não estão navegando por acaso. Eles estão fazendo compras de **alto valor**, de forma planejada e decidida.
- **Hipótese (Persona):** Podem ser dois perfis:
    1. **Comprador B2B (Empresas):** Alguém começando o dia de trabalho e comprando um item de alto valor necessário para a empresa.
    2. **Comprador Decidido:** Alguém que já pesquisou, tomou a decisão e está apenas executando a compra de um item caro (um eletrônico, um pacote de viagem) em um momento de tranquilidade, sem distrações.
- **Ação Estratégica:** Não invista em marketing de massa aqui. Em vez disso, investigue **QUAIS** produtos são vendidos nesses horários. Isso pode te dar insights sobre seus itens de luxo ou de maior valor. Garanta que a experiência de compra para esses itens seja impecável.
#### 4. O Período da Manhã (9h - 12h): A Calmaria e a Preparação
- **Observação:** O volume de vendas e a taxa de conversão são modestos, e o ticket médio tem uma queda, principalmente às 9h e 12h.
- **Interpretação:** Este parece ser um período de "descoberta" e "pesquisa". As pessoas estão navegando, adicionando itens ao carrinho, comparando preços, mas não estão prontas para finalizar a compra.
- **Hipótese (Persona):** O "planejador". A pessoa está no trabalho, vê algo que gosta, mas deixa para decidir e comprar na hora do almoço (o que explica o pico das 14h).
- **Ação Estratégica:** O foco aqui não é a conversão imediata. Use este período para campanhas de engajamento: mostre novidades, guias de como usar um produto, reviews. O objetivo é "aquecer" o cliente para que ele converta mais tarde, nos horários de pico.
### Sumário Estratégico
- **Otimize para os Picos (14h, 22-23h):** Concentre 80% do seu esforço de marketing e operações para garantir que tudo funcione perfeitamente nestes horários.
- **Investigue a Anomalia (4-6h):** Descubra o que está sendo vendido de madrugada. Isso pode revelar um nicho de mercado de alto valor que você não conhecia.
- **Nutra os Clientes da Manhã (9-12h):** Use conteúdo e engajamento para preparar os clientes para a compra que eles farão mais tarde.
- **Agende Manutenções (5-9h):** Use o período de menor atividade para qualquer atualização técnica, minimizando o impacto.
---
### Insights VENDAS E CARRINHOS ABANDONADOS
#### Insight 1: O Tamanho do Problema (O Ponto de Partida)

- **Gráfico Principal:** O Gráfico de Pizza ("Distribuição Percentual do Status das Compras").
    
- **Insight para a Diretoria/Gestão:** A primeira e mais impactante informação é a proporção. Para cada **25.7%** de compras aprovadas, temos **62.9%** de carrinhos abandonados. Estamos convertendo apenas uma fração do nosso potencial. O problema do abandono é o principal "ladrão de receita" da empresa e precisa de atenção imediata.
    
- **No Dashboard:** Este gráfico deve ser o destaque na página inicial. Ele justifica a importância de todo o resto da análise.
    
#### Insight 2: ONDE estamos perdendo mais dinheiro?

- **Gráficos:** O "Top Planos por Faturamento" (a versão limpa, sem o "nao_definido").
    
- **Insight para a área de VENDAS:** A perda de receita não é distribuída igualmente. Ela está massivamente concentrada na **"Assinatura Tech Social ou Aluno"** (R$556 mil em carrinhos abandonados). A equipe de Vendas pode usar isso para focar em entender as objeções específicas deste plano. O processo de venda dele é claro? As vantagens são bem comunicadas? O potencial de ganho rápido está em otimizar a venda deste plano.
    

#### Insight 3: POR QUÊ os clientes desistem? (As Hipóteses)

Aqui usamos os gráficos que cruzam informações para cria
- **Gráfico 1:** "Taxa de Abandono por Tipo de Plano" (Simples vs. Combo).
    
    - **Insight para MARKETING:** Planos **'Simples' são abandonados com mais frequência** que 'Combos'. Isso sugere que, ao comprar um item avulso, o cliente sente mais incerteza ("_Será que é só isso que eu preciso?_") ou percebe menos valor.
        
    - **Estratégia Acionável:** Na página do carrinho de um plano 'Simples', **oferecer o 'Combo' como um upgrade de melhor custo-benefício**. Isso pode reduzir a hesitação e aumentar o ticket médio.
        
- **Gráfico 2:** "Taxa de Conversão por Faixa de Preço".
    
    - **Insight para MARKETING e VENDAS:** A conversão **cai drasticamente na faixa de preço 'média'**. Isso é o "Vale da Incerteza": o produto não é barato para ser um impulso, nem caro para ter um valor percebido altíssimo. É onde o cliente mais pensa.
        
    - **Estratégia Acionável:** Para os produtos de faixa de preço 'média', a página de checkout e o carrinho precisam ser reforçados com **provas sociais (reviews), selos de garantia, clareza sobre o valor entregue e talvez um chat de suporte proativo**. O objetivo é reduzir o atrito e a insegurança nesse segmento crítico.
        

#### Insight 4: QUANDO os clientes desistem?

- **Gráficos:** Dashboard original de análise horária (Volume de Vendas/Abandonos por Hora).
    
- **Insight para MARKETING:** O abandono acontece em padrões. Se o pico de abandonos em volume também é às 14h, isso abre uma oportunidade clara.
    
- **Estratégia Acionável:** Criar campanhas de **retargeting (e-mail ou anúncios) de alta urgência** para carrinhos abandonados nos horários de pico. Exemplo: "Esqueceu algo no carrinho? Volte em até 1 hora e finalize sua compra com 10% de desconto."

### **Página 2: Diagnóstico do Abandono (Onde & Por Quê?)**

**Narrativa:** "Ok, o problema é grande. Mas _onde_ exatamente estamos perdendo clientes e _por que_ eles desistem?" Esta é a página para os gerentes de Marketing e Vendas.

**Layout / Design:**


---

### **Página 3: Análise Detalhada (Deep Dive)**

**Narrativa:** "Me dê a lista de todos os carrinhos com uma característica específica." Esta é a página para a equipe de operação, para ações diretas.

**Layout / Design:**

- **Topo (Filtros Avançados):** Coloque filtros poderosos e visíveis para todas as principais dimensões: `status_compra`, `faixa_preco`, `tipo_plano`, `metodo_pagamento`, `dia_semana`, `hora`.
- **Corpo da Página (A Lista):** O elemento principal aqui é uma **Tabela**.
    - **Dados:** A tabela mostra os dados detalhados (`id_compra`, `plano`, `preco`, `data_criacao`, etc.).
    - **Interatividade:** A tabela é 100% filtrada pelos controles no topo da página. O usuário pode, por exemplo, filtrar por "Status: Abandoned", "Faixa de Preço: média" e "Dia: Segunda-feira" para ver a lista exata de carrinhos que se encaixam nesse perfil e talvez exportá-la para uma ação de marketing.
        
### Dicas Finais de Design e Narrativa:

- **Cores:** Use uma paleta consistente. Verde para sucesso/conversão, vermelho/laranja para abandono/falha, e uma cor neutra (azul ou cinza) para volume/contagem.
#### Opção 1: Paleta "Confiança e Inteligência" (O Padrão Tech)

Esta é a abordagem mais clássica e segura. Pense em marcas como IBM, Facebook, LinkedIn. Ela transmite seriedade e confiança.
- **Psicologia:** Azul inspira confiança, calma e inteligência. Cinza escuro denota profissionalismo e sofisticação.
- **Cores Principais:**
    - **Fundo:** Um cinza bem escuro (quase preto, # 1E1E1E) ou um branco/cinza muito claro.
    - **Cores Categóricas:** Uma escala de **azuis** e **turquesas**.
    - **Destaques:** Verde brilhante para números positivos e Laranja/Vermelho para números negativos.
- **Exemplo de Uso:** Um dashboard em "dark mode" com gráficos em tons de azul, o KPI de conversão em verde e a taxa de abandono em laranja.

----
### ==**O Roteiro do Dashboard: "A Jornada do Cliente que Perdemos"**

O objetivo é contar uma história em 3 atos (3 páginas/abas), guiando o usuário do problema geral até a solução acionável.

#### **Página 1: O Problema em Números (O Diagnóstico de 30 Segundos)**

**Narrativa:** "Qual é o tamanho real do nosso problema? Em 30 segundos, qualquer diretor precisa entender a oportunidade que estamos perdendo."

**Layout e Design:**

- **Título Principal (no topo):** Use o seu título, é perfeito: "**O Maior Concorrente da Empresa Somos Nós Mesmos**"
    
- **Linha de KPIs Principais (Scorecards):**
    
    - **KPI 1 (Destaque):** `Taxa de Abandono: 62.9%` (use a cor de alerta, laranja ou vermelho).
        
    - **KPI 2:** `Receita Perdida: R$ 914.286` (também em cor de alerta).
        
    - **KPI 3:** `Receita Realizada: R$ 556.728` (em cor positiva, verde).
        
    - **KPI 4:** `Total de Carrinhos: 14.475` (em cor neutra, azul ou cinza).
        
- **Gráfico Central:** Um **Gráfico de Anel (Donut Chart)** mostrando a "Distribuição de Status de Compra". Destaque a fatia de `Abandoned` com uma cor forte.
    
- **Gráfico de Contexto (Linha do Tempo):** Um **Gráfico de Linha** simples mostrando o total de `Carrinhos Criados` vs. `Carrinhos Abandonados` ao longo dos meses. Isso mostra se o problema está piorando.
    
- **Caixa de Texto (O Chamado):** No canto, seu texto de contexto: _"Este dashboard revela os padrões por trás do abandono de carrinho... transformando dados em estratégias acionáveis."_
    
#### **Página 2: O Diagnóstico (Onde, Quando e Por Quê?)**

**Narrativa:** "Ok, o problema é grande. Agora, vamos encontrar os pontos de maior 'vazamento' e entender os motivos."

**Layout e Design (a grade 2x2):**

- **Quadrante 1 (QUANDO):** O **Gráfico de Linha da Taxa de Conversão por Hora**.
    - **Título:** "A 'Hora de Ouro': O pico de conversão acontece às 14h"

- **Quadrante 2 (ONDE):** O **Gráfico de Barras Horizontais do Faturamento Perdido por Plano**. 
    - **Título:** "Onde o Dinheiro Vaza? 'Assinatura Tech Social' lidera as perdas

- **Quadrante 3 (POR QUÊ - Preço e Produto):** **Dois gráficos de barras menores, lado a lado**.   
    - Taxa de Conversão por `Faixa de Preço`.
    - Taxa de Abandono por `Tipo de Plano` (Simples vs. Combo).

- **Quadrante 4 (POR QUÊ - Pagamento):** O **Gráfico de Barras Empilhadas 100%** de Status por `Método de Pagamento`.
    - **Título:** "Onde a Experiência Quebra? O Atrito no Pagamento"
    - **Caixa de Texto de Insight ao lado deste gráfico:**
        > **"Método de Pagamento Obsoleto:** O gráfico revela que o **Boleto** possui a maior proporção de carrinhos abandonados. A hipótese é que a complexidade e o tempo de espera do método fazem o cliente "esfriar" e desistir da compra, sendo um dos principais vilões da nossa conversão."

#### **Página 3: O Plano de Ação (Como Resolver?)**

**Narrativa:** "Analisar não é o suficiente. Com base nos dados, aqui estão as ações recomendadas para recuperar a receita perdida." Esta página é para a ação.

**Layout e Design (um plano estratégico, não apenas gráficos):**

- **Título Principal:** "Da Análise à Ação: Um Plano para Reduzir o Abandono em 20%"
    
- **Coluna 1: Quick Wins (Resultados Rápidos)**
    
    - Use **Caixas de Texto com Ícones** para cada ação.
        
    - ✅ **Ação 1 (Produto):** "Promover Upgrade de 'Simples' para 'Combo' no carrinho." **Insight:** Combos abandonam 11% a menos.
        
    - ✅ **Ação 2 (Preço):** "Reforçar provas sociais (reviews, garantias) na faixa de preço 'Média'." **Insight:** É a faixa com a menor taxa de conversão (19%).
        
    - ✅ **Ação 3 (Marketing):** "Criar campanha de retargeting de urgência focada no pico das 14h." **Insight:** É o horário de maior volume e eficiência.
	- ✅ **Ação 4 (Pagamento):** "**Realizar teste A/B removendo a opção 'Boleto'** para o plano 'Tech Social' e promovendo o PIX."

- _Insight: Boleto é o método com a maior taxa de abandono._

### Opção 1: Paleta "Confiança e Inteligência" (O Padrão Tech)

Esta é a abordagem mais clássica e segura. Pense em marcas como IBM, Facebook, LinkedIn. Ela transmite seriedade e confiança.

- **Psicologia:** Azul inspira confiança, calma e inteligência. Cinza escuro denota profissionalismo e sofisticação.
    
- **Cores Principais:**
    - **Fundo:** Um cinza bem escuro (quase preto, # 1E1E1E) ou um branco/cinza muito claro.
    - **Cores Categóricas:** Uma escala de **azuis** e **turquesas**.
    - **Destaques:** Verde brilhante para números positivos e Laranja/Vermelho para números negativos.
- **Exemplo de Uso:** Um dashboard em "dark mode" com gráficos em tons de azul, o KPI de conversão em verde e a taxa de abandono em laranja.
### Opção 2: Paleta "Inovação e Criatividade" (A Moderna)

Esta paleta é mais vibrante e passa uma imagem de uma empresa moderna, criativa e energética. Pense em marcas que querem se destacar.

- **Psicologia:** Roxo está associado à criatividade e sabedoria. Teal (verde-azulado) representa inovação. Laranja traz energia.
- **Cores Principais:**
    - **Fundo:** Cinza médio ou branco.
    - **Cores Categóricas:** Uma combinação de **Roxo**, **Teal** e **Laranja**.
    - **Destaques:** Verde para sucesso, Vermelho para falha.
- **Exemplo de Uso:** Gráficos de barra com cada categoria (ex: tipo de plano) em uma dessas cores. Fica visualmente bem dinâmico.
### Opção 3: Paleta "Crescimento e Conhecimento" (A Inspiradora)

Esta paleta usa cores que remetem a crescimento, natureza e iluminação. É ótima para uma marca com um propósito educacional forte.

- **Psicologia:** Verde representa crescimento e sucesso. Amarelo/Dourado remete a conhecimento, valor e otimismo.
- **Cores Principais:**
    - **Fundo:** Branco ou um tom "creme" bem suave.
    - **Cores Categóricas:** Uma escala de **verdes** e **cinzas**.
    - **Destaques:** Um **amarelo/dourado** para destacar os KPIs mais importantes e um vermelho para alertas.
- **Exemplo de Uso:** Um dashboard com visual "clean", onde os gráficos de crescimento são em verde e os números principais brilham em dourado.

---

### Regras de Ouro (Mais Importante que a Paleta)

Independentemente da paleta que você escolher, siga estas regras para o dashboard ficar claro e acionável:

1. **Use Cores Semânticas:** Reserve cores específicas para significados específicos. Isso é crucial.
    
    - 🟢 **Verde:** Sempre para coisas boas (Conversão, Sucesso, Aumento de Vendas).
        
    - 🔴 **Vermelho / Laranja:** Sempre para coisas ruins (Abandono, Falha, Queda nas Vendas).
        
    - 🔵 **Azul / Cinza:** Para dados informativos e neutros (Volume, Contagem Total).
        
2. **Menos é Mais:** Não use 10 cores diferentes. Escolha de 3 a 5 cores principais e use variações de tons. Um dashboard limpo é mais profissional.
    
3. **Pense em Acessibilidade:** Evite colocar vermelho e verde lado a lado para representar "bom" vs. "ruim", pois pessoas com daltonismo podem não diferenciá-los. Use também ícones (seta para cima ▲, seta para baixo ▼) ou títulos claros para reforçar a mensagem.
    

**Dica Bônus:** Use uma ferramenta como o **Coolors.co** para te ajudar a gerar paletas harmoniosas. Você pode "travar" uma cor (ex: um verde que você gostou) e ele gera outras que combinam.
- **Títulos:** Cada título de gráfico deve ser uma **afirmação** ou uma **pergunta**, como sugeri acima. Isso é muito mais poderoso do que títulos genéricos como "Status vs. Pagamento".

---
# modelos preditivos

[[Modelos preditivos]]

### Tabela Comparativa Rápida

|Característica|Regressão Logística|Random Forest|Rede Neural (MLP)|
|---|---|---|---|
|**Analogia**|O Estatístico Cauteloso|O Comitê de Especialistas|O Cérebro Artificial|
|**Complexidade**|Baixa|Média|Alta|
|**Velocidade**|Muito Rápida|Média / Lenta|Lenta / Muito Lenta|
|**Interpretabilidade**|**Excelente**|Boa (Importância das Features)|**Muito Baixa**|
|**Poder de Predição**|Bom para padrões simples|**Excelente** para padrões gerais|**Potencialmente o maior**, para padrões complexos|
|**Necessidade de Preparar Dados**|Baixa|Baixa|**Alta (Obrigatório)**|

> a estratégia de começar com o **Random Forest** (para buscar alta performance) ou com a **Regressão Logística** (para ter um resultado rápido e interpretável) continua sendo a mais segura e eficiente para o prazo.

---
# Começando trabalho preditivo

## Alerta Importante: Vazamento de Dados (Data Leakage)

Antes de escrever o código, um ponto crucial: para prever se um cliente converteu, não podemos usar colunas que já contenham essa resposta.
    Colunas a serem EXCLUÍDAS das features:
        sobrenome, nome, id_compra, data_criacao: São identificadores, não características do comportamento.
        status_compra, abandonou: São praticamente a mesma informação que converteu. Usá-las seria "trapacear", e o modelo não aprenderia nada útil para prever novos clientes.
        taxa_conversao_hora, taxa_conversao_dia: Estas colunas foram calculadas usando agregações de dados que incluem o resultado da conversão. Usá-las também causaria vazamento de dados.

---
1. **Etapa 1: Preparação dos Dados (Limpeza e Seleção)**: Vamos carregar o conjunto de dados e separar as colunas que você identificou como _features_ da coluna alvo, a variável `converteu`. Isso garantirá que o modelo use apenas as informações apropriadas para a predição.
2. **Etapa 2: Pré-processamento e Engenharia de Atributos**: Nesta etapa, lidaremos com as variáveis categóricas (como 'metodo_pagamento', 'faixa_preco', e 'tipo_plano'), transformando-as em um formato numérico que o modelo possa entender, provavelmente usando a técnica de _One-Hot Encoding_.
3. **Etapa 3: Modelagem Preditiva**: Selecionaremos um algoritmo de aprendizado de máquina e treinaremos o modelo com base nas _features_ pré-processadas e na variável alvo.
4. **Etapa 4: Avaliação do Modelo**: Analisaremos o desempenho do modelo usando métricas relevantes para problemas de classificação, como precisão, recall e a matriz de confusão.
    
df depois do _One-Hot Encoding_.
![[Pasted image 20250829181126.png]]
>**One-Hot Encoding** é uma técnica que transforma dados categóricos (texto) em um formato numérico que os algoritmos de aprendizado de máquina podem processar.
> As features `metodo_pagamento`, `faixa_preco` e `tipo_plano` contêm textos como 'cartao', 'nao_selecionado', 'alto', 'simples', etc. Para um modelo matemático, não existe uma ordem ou hierarquia nesses textos. O modelo não sabe que 'cartao' é diferente de 'nao_selecionado'. Se você tentasse converter essas palavras para números diretamente (tipo 'cartao' = 1, 'boleto' = 2), o modelo poderia entender que 'boleto' é "maior" que 'cartao', o que seria um erro.
> Cada linha recebe um `1` na coluna que corresponde à sua categoria e um `0` nas outras. Isso garante que o modelo interprete cada categoria como uma característica independente, sem assumir nenhuma relação de ordem.

## Separar Features (X) e Alvo (y)

-> X: Todas as colunas de características (features).
-> y: A coluna que quero que o modelo aprenda a prever.

## Começar com random forest
O **Random Forest** é um algoritmo de aprendizado de máquina muito poderoso e geralmente é uma excelente escolha para começar. Ele funciona como uma "floresta de árvores de decisão". Em vez de usar apenas uma árvore para tomar a decisão, ele treina várias árvores diferentes e combina o resultado delas para fazer uma previsão final. Isso o torna menos propenso a erros e geralmente mais preciso.

A saída, `RandomForestClassifier(n_jobs=-1, random_state=42)`, não é um resultado ou uma pontuação. Ela é apenas uma confirmação de que o treinamento foi concluído com sucesso, e o objeto `rf_model` agora contém um modelo "pronto para uso" com os parâmetros que você definiu.

> [!NOTE]
> é como um estudante que acabou de terminar de estudar para uma prova:
> - O comando `rf_model.fit(X_treino, y_treino)` é o estudante lendo o livro didático (`X_treino`) e o gabarito (`y_treino`).
> - A saída significa que o estudante terminou de estudar. Ele não está mais vazio, ele "aprendeu" e está pronto para o teste.
> 

``` Markdown

Acurácia: 0.78
Relatório de Classificação:
precision    recall  f1-score   support
False       0.79      0.96      0.87      3227
True       0.68      0.26      0.38      1116


accuracy                            0.78      4343
macro avg       0.74      0.61      0.62      4343
weighted avg    0.76   0.78         0.74      4343


Matriz de Confusão:
[[3093  134]
[[826  290]]
```


3093 (Verdadeiros Negativos): O modelo disse que não iria converter e o cliente realmente não converteu. (Previsão correta!)
134 (Falsos Positivos): O modelo disse que iria converter, mas o cliente não converteu. (Falso alarme)
826 (Falsos Negativos): O modelo disse que não iria converter, mas o cliente realmente converteu. (falha! O modelo perdeu essas 826 oportunidades.)
290 (Verdadeiros Positivos): O modelo disse que iria converter e o cliente realmente converteu. (Previsão correta!)

### **O Relatório de Classificação: Entendendo os Resultados**

O relatório usa os números da matriz para calcular métricas mais fáceis de interpretar, dividindo-as por classe (`False` = não converteu, `True` = converteu).

- **Acurácia (0.78):** De forma geral, o modelo acertou 78% das previsões. Parece bom, mas a acurácia pode enganar, pois a maioria dos seus clientes não converte (`3227` vs `1116`), então o modelo acerta muito ao prever "não converteu".
- **Precision (Precisão):**
    - `Precision` para a classe `True` (0.68): De todos os clientes que o modelo **previu** que iriam converter, apenas **68% realmente converteram**. Isso significa que, se você usasse o modelo para fazer uma campanha, 32% dos contatos seriam desperdiçados.
- **Recall (Sensibilidade):**
    - `Recall` para a classe `True` (0.26): De todos os clientes que **realmente converteram**, o modelo só conseguiu encontrar **26% deles**. Isso é a métrica mais importante para o seu objetivo de "recuperação de vendas". Um `Recall` baixo significa que o modelo está **deixando a maior parte das oportunidades passarem batido**.
### **Resumo da Análise**
O modelo **é bom em identificar quem não vai converter**, mas **não é muito bom em encontrar os clientes que realmente convertem**.
O `Recall` de 0.26 para a classe `True` (conversão) mostra que o modelo está perdendo a maioria das oportunidades. Isso é normal para o primeiro modelo. Agora que você tem essa linha de base, o próximo passo é tentar melhorá-la

- Definir uma grade de hiperparâmetros a serem testados.
- Usar o `GridSearchCV` para encontrar a combinação que maximiza o `recall`, já que esta é a métrica mais importante para o seu objetivo de recuperar clientes.
- Imprimir a melhor combinação de parâmetros e a pontuação obtida.

Parâmetros usados pra os ajustes:
- **`n_estimators`**: É o número de árvores de decisão que o modelo Random Forest irá construir. Pense em cada árvore como um "especialista" em prever a conversão. Quanto mais árvores, mais "opiniões" o modelo considera para tomar a decisão final, o que geralmente aumenta a precisão. No seu caso, o valor ideal foi **150**.
    
- **`max_depth`**: É a profundidade máxima que cada árvore pode ter. Controlar a profundidade é crucial para evitar o **overfitting**, que é quando o modelo aprende os dados de treino tão bem que não consegue generalizar para dados novos. O `GridSearchCV` determinou que a profundidade ideal é **10**.
    
> Então, o novo modelo será um `RandomForestClassifier` com 150 árvores, e cada uma delas terá no máximo 10 níveis de profundidade. Isso garante que o modelo seja robusto, eficiente e tenha a melhor chance de prever com sucesso os clientes que podem ser recuperados!

O que o resultado da Matriz de Confusão nos diz é:
- **`[[2263, 0], [737, 0]]`**
- **2263 Verdadeiros Negativos**: O modelo acertou todos os clientes que não converteram.
- **0 Falsos Positivos**: O modelo não previu nenhum cliente que converteria e que na verdade não converteu.
- **737 Falsos Negativos**: O modelo previu que todos esses clientes não iriam converter, mas eles **realmente converteram**. Este é o número total de clientes que converteram no seu conjunto de teste, e o modelo errou todos.
- **0 Verdadeiros Positivos**: O modelo não acertou nenhum cliente que converteu.

## Usando Regressão logística

```
Treinando o modelo de Regressão Logística...

--- Avaliação do Modelo de Regressão Logística ---
Relatório de Classificação:
               precision    recall  f1-score   support

       False       0.75      0.49      0.59      2263
        True       0.24      0.50      0.33       737

    accuracy                           0.49      3000
   macro avg       0.50      0.50      0.46      3000
weighted avg       0.63      0.49      0.53      3000

Matriz de Confusão:
 [[1112 1151]
 [ 366  371]]
```
Acurácia mais baixa que o randomforest , mas:
- **Matriz de Confusão:**
    - **Verdadeiros Positivos (371):** O modelo previu que 371 clientes iriam converter e acertou! Isso é uma enorme melhoria em relação ao modelo anterior, que acertou 0.
    - **Falsos Negativos (366):** O modelo errou ao dizer que 366 clientes não iriam converter, quando na verdade, eles converteram. O número ainda é alto, mas é bem menor que os 737 erros do Random Forest.
- **Recall para a classe 'True' (0.50):**
    - Este é o ponto principal. O modelo de Regressão Logística conseguiu identificar **50% de todos os clientes que realmente converteram**. Isso é um resultado muito mais útil para o seu objetivo de "recuperar vendas" do que o `recall` de 0% do modelo anterior.
**Precision para a classe 'True' (0.24):**
- O `precision` é baixo, o que significa que o modelo gerou muitos falsos positivos. De todos os clientes que ele sugeriu para a campanha, apenas 24% realmente converteram. Isso indica que a sua equipe teria que lidar com muitos "alarmes falsos."

> O de Regressão Logística tem um desempenho geral ruim, mas é **muito mais útil** para o objetivo de encontrar clientes perdidos. Ele é capaz de encontrar as oportunidades de venda (alto `recall`), mas com um custo de muitos "alarmes falsos" (baixo `precision`).


## **Relatório de Desempenho dos Modelos**

 **Random Forest (Inicial):** 
 - `Recall` para `converteu`: **0%**
 **Conclusão:** Modelo **não serve** para o objetivo de recuperação de vendas.

- **Random Forest (Otimizado):**
	- `Recall` para `converteu`: **0%**
    - **Conclusão:** Otimização não resolveu o problema de base.
        
- **Regressão Logística (com peso de classe):**
    - `Recall` para `converteu`: **50%**
    - **Conclusão:** Modelo **capaz de identificar metade** dos clientes que converteram.
        
> A Regressão Logística, mesmo com uma acurácia geral mais baixa, é o **modelo vencedor** para o projeto, pois ele entrega a capacidade de identificar leads de alto valor que seriam perdidos de outra forma.

### **Taxa Estimada de Recuperação de Vendas**
Com um `recall` de 50%, a **taxa estimada de recuperação de vendas** do seu modelo é de **50%**. Isso significa que, se você usar este modelo para identificar e abordar clientes que abandonaram o carrinho, pode recuperar até 50% dessas vendas perdidas.

### **Criando Amostras Preditivas**
O passo final é criar a lista de clientes que você vai entregar para a equipe de vendas. Podemos filtrar o seu conjunto de teste para mostrar apenas os clientes que o modelo previu que iriam converter.

----
### **Análise Preditiva para Recuperação de Vendas: Relatório de Conclusão**

#### **1. Introdução e Objetivo**

Este projeto teve como objetivo principal desenvolver um modelo de análise preditiva para identificar clientes que, após abandonarem o carrinho de compras, possuem alta probabilidade de converter em uma venda. O foco da análise foi maximizar a **taxa de recuperação de vendas** por meio da identificação de leads qualificados.

#### **2. Metodologia**

O processo seguiu uma metodologia padrão de ciência de dados, garantindo a robustez e a confiabilidade dos resultados:

- **Preparação dos Dados:** Foram selecionadas features relevantes para a predição, como `preco`, `metodo_pagamento`, `hora` e `tipo_plano`. Colunas que poderiam causar vazamento de dados, como `status_compra` e `taxa_conversao`, foram removidas. Variáveis categóricas foram transformadas em formato numérico usando a técnica **One-Hot Encoding**.
- **Divisão e Treinamento:** O conjunto de dados foi dividido em 70% para treinamento e 30% para teste, garantindo que o desempenho do modelo fosse avaliado em dados não utilizados durante o aprendizado.
- **Modelagem Preditiva:** Foram testados dois algoritmos de aprendizado de máquina: **Random Forest** e **Regressão Logística**.
- **Avaliação:** A performance dos modelos foi avaliada com foco na métrica **Recall**, que mede a capacidade do modelo de identificar corretamente as oportunidades de venda.

#### **3. Análise e Resultados dos Modelos**

|Modelo Testado|Acurácia Geral|Recall (para Conversão)|Vantagem|Desvantagem|
|---|---|---|---|---|
|**Random Forest**|78%|**0%**|Alta acurácia geral.|**Não identificou nenhuma oportunidade de venda.**|
|**Regressão Logística**|49%|**50%**|**Identificou metade das oportunidades de venda.**|Acurácia geral mais baixa.|

Apesar de o modelo de **Random Forest** ter apresentado uma **acurácia** superior (78%), sua performance para o objetivo do projeto foi nula, com um **Recall de 0%**. Isso significa que o modelo não conseguiu identificar corretamente nenhum cliente que, de fato, converteu, tornando-o ineficaz para a recuperação de vendas.

O modelo de **Regressão Logística**, por outro lado, demonstrou ser o mais adequado. Embora sua acurácia geral seja de 49%, ele conseguiu um **Recall de 50%**, o que indica que é capaz de encontrar metade de todos os clientes que converteram em vendas, mesmo que o modelo tenha gerado alguns "alarmes falsos" (Falsos Positivos).

#### **4. Conclusão e Recomendação Final**

Para o objetivo de **recuperação de vendas**, o modelo de **Regressão Logística** é a escolha ideal. Sua capacidade de identificar 50% das oportunidades perdidas representa um retorno tangível e direto para o negócio.
- **Taxa Estimada de Recuperação de Vendas:** A taxa estimada de recuperação é de **50%** das vendas perdidas. 
- **Amostra Preditiva:** O modelo gerou uma amostra com 1.829 clientes que, com base nos dados, apresentam alta probabilidade de conversão.

A recomendação é que essa amostra preditiva seja usada para direcionar os esforços de uma equipe de vendas ou de marketing, que pode focar seus recursos em clientes com maior probabilidade de retorno, otimizando o processo de recuperação de vendas.

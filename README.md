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

  * Redes Neurais (MLPClassifier).
  * Regressão Logística.
  * Random Forest.
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


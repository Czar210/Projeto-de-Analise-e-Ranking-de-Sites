# Projeto de Análise e Ranking de Sites de Skincare

Este projeto realiza uma análise aprofundada de conteúdo de diversos sites sobre cuidados com a pele (skincare). Utilizando técnicas de Processamento de Linguagem Natural (PLN) e web scraping, o sistema coleta, processa e avalia o texto dos sites para gerar um ranking de relevância e realizar uma análise de sentimentos. Os resultados são apresentados em dashboards interativos.

## 📜 Visão Geral

O objetivo principal é criar um sistema automatizado capaz de:
1.  Extrair conteúdo textual de uma lista de URLs de sites de skincare.
2.  Processar e limpar o texto para análise.
3.  Identificar as palavras-chave e termos mais frequentes e relevantes.
4.  Avaliar o sentimento geral do conteúdo de cada site.
5.  Rankear os sites com base em um algoritmo de pontuação customizado que mede a relevância e a profundidade do conteúdo.
6.  Visualizar todos os resultados em dashboards interativos.

---

## ✨ Funcionalidades

O projeto é dividido nos seguintes módulos principais:

### 1. Web Scraping e Processamento de Texto
- **Coleta de Dados:** Utiliza as bibliotecas `requests` e `BeautifulSoup` para extrair conteúdo textual (parágrafos, links, títulos) de uma lista predefinida de sites.
- **Limpeza e Tokenização:** O texto extraído é normalizado (remoção de tags HTML, conversão para minúsculas) e tokenizado usando `NLTK`.
- **Remoção de Stopwords:** Palavras comuns e termos irrelevantes (preposições, artigos, etc.) são removidos com base em uma lista customizada de stopwords em português.

### 2. Análise de Frequência e N-Grams
- **Palavras-Chave:** Identifica as palavras mais frequentes no corpus de texto coletado.
- **Bigramas e Trigramas:** Encontra os termos compostos mais relevantes (ex: "pele sensível", "ácido hialurônico") para entender os principais conceitos discutidos.
- **Nuvem de Palavras:** Gera uma visualização gráfica dos termos mais proeminentes.

### 3. Análise de Sentimentos
- **Léxico Customizado:** Utiliza um léxico de sentimentos construído manualmente, com palavras e expressões positivas e negativas específicas do domínio de skincare.
- **Cálculo de Score:** Cada site recebe uma pontuação de sentimento (positiva, negativa ou neutra) com base na frequência e na polaridade das palavras encontradas.

### 4. Sistema de Ranking Avançado
O núcleo do projeto é um algoritmo de pontuação que avalia e rankeia os sites com base em quatro pilares:
- **Score Temático:** A densidade de palavras-chave predefinidas (palavras-semente) no texto.
- **Score de Relevância:** A importância de palavras raras e específicas, calculada com uma abordagem similar ao TF-IDF.
- **Score Bruto:** Uma pontuação geral baseada no volume e no peso de todas as palavras relevantes.
- **Peso Médio:** A média ponderada das palavras em um site, indicando a qualidade geral do vocabulário.

Uma **Nota Final** de 0 a 10 é calculada combinando esses quatro pilares de forma ponderada.

### 5. Dashboards Interativos
- **Visualização de Dados:** Utiliza `Plotly` e `Dash` para criar dashboards interativos que exibem:
    - O ranking final dos sites.
    - A decomposição da nota de cada site em seus componentes (Tema, Relevância, Score, etc.).
    - Gráficos de frequência de palavras e n-grams.
    - A nuvem de palavras.
    - O ranking da análise de sentimentos.

---

## 💻 Tecnologias Utilizadas

- **Linguagem:** Python
- **Análise de Dados e PLN:**
    - `pandas`: Manipulação e estruturação de dados.
    - `nltk`: Toolkit para processamento de linguagem natural (tokenização, stopwords, n-grams).
    - `pyspark`: Utilizado em uma das etapas para processamento de dados distribuído.
- **Web Scraping:**
    - `requests`: Para realizar requisições HTTP.
    - `BeautifulSoup4`: Para extrair dados de arquivos HTML.
- **Visualização e Dashboards:**
    - `plotly`: Para a criação de gráficos interativos.
    - `dash`: Para a construção dos dashboards web.
    - `wordcloud`: Para a geração da nuvem de palavras.

---

## 🚀 Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/Czar210/Skin_Care
    cd Skin_Care
    ```

2.  **Instale as dependências:**
    Recomenda-se criar um ambiente virtual.
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: venv\Scripts\activate
    ```
    Instale as bibliotecas a partir do notebook (ou crie um arquivo `requirements.txt`).
    ```bash
    pip install pyspark nltk dash wordcloud pandas requests beautifulsoup4 dash_core_components dash_html_components
    ```

3.  **Baixe os recursos do NLTK:**
    Execute o seguinte comando em um terminal Python para baixar os pacotes necessários:
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    ```

4.  **Execute o Notebook:**
    Abra e execute o arquivo `Skincare_final.ipynb` em um ambiente Jupyter (Jupyter Notebook, JupyterLab ou Google Colab).

5.  **Acesse os Dashboards:**
    Ao final da execução, o notebook irá gerar links para os dashboards. Copie e cole os links no seu navegador para visualizar os resultados de forma interativa.

---

## 📊 Resultados

A execução do notebook produzirá:
- **Saídas no Console:** Relatórios detalhados com a frequência de palavras, termos compostos (n-grams) e o ranking final dos sites com suas respectivas notas.
- **Dashboards Web:**
    - **Dashboard de Frequência:** Exibe a nuvem de palavras e os gráficos com as palavras, bigramas e trigramas mais comuns.
    - **Dashboard de Ranking:** Apresenta o ranking final dos sites e um gráfico detalhado que mostra a contribuição de cada componente (tema, relevância, etc.) para a nota final.
    - **Dashboard de Sentimentos:** Mostra a classificação de cada site com base no sentimento do seu conteúdo.
 
## ✨ Feito por

Uma equipa fantástica que tornou este projeto possível:

- @Czar210
- @devdebdeb
- @enzotakida
- @Subaruberu

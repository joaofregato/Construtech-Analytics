# Construtech Analytics 🏗️📊
**Projeto autoral que integra Google Cloud, Databricks e Power BI para automatizar o fluxo de indicadores de uma construtora, unificando dados operacionais e dashboards executivos inteligentes.**

---

## 💡 Contexto

Trabalhando com indicadores da construção civil, percebi que boa parte das empresas ainda depende de planilhas Excel descentralizadas e atualizações manuais.
Esse projeto nasceu da necessidade de **automatizar todo o fluxo de dados corporativos**, garantindo que informações de cronograma, produtividade, qualidade, sustentabilidade e satisfação do cliente sejam atualizadas **diariamente e de forma confiável**.

O **Construtech Analytics** é o resultado dessa proposta: um **pipeline de dados moderno**, desenvolvido no **Databricks** e conectado ao **Google Drive** e **Power BI**, com tratamento automatizado e armazenamento otimizado em **tabelas Delta**.

*(Os dados utilizados neste projeto são **fictícios** e simulam operações reais da construtora onde trabalho atualmente.)*


---

## 🎯 Objetivos

* Construir um **pipeline automatizado** de atualização de dados (ETL completo) a partir de planilhas armazenadas no Google Drive.
* Demonstrar integração entre **Google Drive → Databricks → Power BI**.
* Tratar e preparar dados de diferentes planilhas e abas da empresa.
* Gerar **dashboards interativos** com indicadores estratégicos para gestão de obras.

---

## 🛠️ Linguagens & Ferramentas

* **Python (Pandas, Google API Client)** → extração e tratamento dos dados.
* **Delta Tables (Databricks)** → armazenamento otimizado e atualização incremental.
* **Databricks** → orquestração e armazenamento dos dados tratados.
* **Google Cloud Service Account** → autenticação segura e acesso aos arquivos.
* **Power BI** → modelagem, criação de KPIs e dashboards.
* **DAX** → calculos e métricas via Power BI.
* **SQL** → manipulação de dados via Databricks.

---

## 📂 Fontes de Dados

As fontes originais são **planilhas Excel** armazenadas no **Google Drive** da empresa, divididas em múltiplas abas (por exemplo, *Produtividade*, *Retrabalho*, *Avanço de Obra*, *Cliente*, *Sustentabilidade*).
Essas planilhas são sincronizadas diariamente com o Databricks via **Jobs agendados**.

---

## 🔄 Fluxo do Projeto

### 1. **Extração (Google Drive → Databricks)**

* Integração via **Google Cloud Service Account**.
* Uso das bibliotecas `googleapiclient` e `google-auth` para autenticação e download dos arquivos Excel.
* O script identifica a planilha e aba desejada e realiza a leitura via **Pandas**.

### 2. **Transformação (ETL no Databricks)**

* Tratamento de valores nulos, padronização de datas e tipos de dados.
* Normalização automática de colunas com detecção de *datetime*.
* Unificação de abas e planilhas (*union all*) em um dataframe consolidado.
* Conversão para formato **Parquet/Delta** (A etapa de transformação em Parquet neste contexto está sendo utilizado apenas como uma boa prática de pipeline de dados e pode ser excluída).

### 3. **Carregamento (Delta Table → Power BI)**

* Criação de tabelas catalogadas no Databricks para consumo pelo Power BI.
* Conexão direta via **Databricks Connector** no Power BI.
* Atualizações automáticas programadas no Power BI Service.

### 4. **Visualização (Dashboards no Power BI)**

Foram criadas múltiplas páginas de dashboards com KPIs e análises:

## 🧱 Dashboards

### 📊 Dashboard Executivo → visão geral com principais indicadores.

![Dashboard Executivo]([https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/dashboard%20executivo.png])

### 🏗️ Avanço de Obra → monitoramento de cronograma e progresso físico.

![Avanço de Obra](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/avan%C3%A7o%20de%20obra.png)

### ⚙️ Produtividade → análise do IGP e eficiência das equipes.

![Produtividade](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/produtividade.png)

### 🔁 Retrabalho → controle de serviços reprovados e taxas de retrabalho.

![Retrabalho](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/retrabalho.png)

### ✨ Cliente → monitoramento de satisfação de cliente.

![Cliente](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/cliente.png)

### ♻️ Sustentabilidade → consumo de recursos, geração de resíduos e impacto ambiental.

![Sustentabilidade](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/cliente.png)

### 🔍 Ferramenta de filtro retrátil (UX/UI)

![Filtro](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/filtro%20retr%C3%A1til.png)

## ⭐ Modelagem de dados
![Modelagem de dados](https://github.com/joaofregato/Construtech-Analytics/blob/main/imagens/modelo.png)

---

## 📁 Estrutura do Repositório

```plaintext
/ConstrutechAnalytics
│── /databricks         # Scripts Python e notebooks (ETL + automação)
│── /power bi           # Dashboard (.pbix)
│── /images             # Screenshots dos dashboards
│── README.md           # Documentação do projeto
```

---

## 🚀 Como Executar

1. Configure uma conta de serviço no **Google Cloud Platform (GCP)**.
2. Salve o JSON de credenciais e aponte o caminho no script Python.
3. Execute o notebook no **Databricks**.
4. Configure um **Job** para execução diária.
5. Conecte o **Power BI** ao Databricks e carregue as tabelas Delta.

---

## 💡 Principais Aprendizados

* Integração segura entre **GCP** e **Databricks**.
* Automação de ETL com agendamento de Jobs.
* Tratamento de dados multi-aba e multi-planilha com **Pandas/Python**.
* Modelagem de dados, storytelling visual e estratégico no **Power BI**.
* Monitoramento e gestão estrátégica e performática de uma construtora.

---

## 📈 Resultados

* **Redução de 95% da intervenção manual** na atualização de indicadores.
* Dados padronizados e disponíveis no Power BI em **menos de 10 minutos após o preenchimento** das planilhas.
* Dashboards executivos com **atualização automática diária** e rastreabilidade total da origem dos dados.
* Insights para apoio de decisões estratégicas.

---

## 👷‍♂️ Autor

**João Fregato**
[LinkedIn](https://www.linkedin.com/in/joaofregato) | [GitHub](https://github.com/joaofregato)

# Construtech Analytics 🏗️📊
Projeto autoral que integra Google Cloud, Databricks e Power BI para automatizar o fluxo de indicadores de uma construtora, unificando dados operacionais e dashboards executivos inteligentes.

📌 Visão Geral do Projeto

O Construtech Analytics é um projeto de análise de dados desenvolvido para demonstrar como é possível integrar ferramentas modernas de engenharia de dados e BI em um fluxo automatizado, conectando planilhas operacionais no Google Drive ao Power BI por meio do Databricks e do Google Cloud Platform (GCP).

O objetivo é gerar insights estratégicos para construtoras, com dashboards que monitoram produtividade, retrabalho, avanço físico, satisfação do cliente e indicadores de sustentabilidade.

(Os dados utilizados neste projeto são fictícios e simulam operações reais da construtora onde trabalho.)

🎯 Objetivos

Construir um pipeline automatizado de atualização de dados (ETL completo).

Demonstrar integração entre Google Drive → Databricks → Power BI.

Tratar e preparar dados de diferentes planilhas da empresa.

Criar dashboards executivos com indicadores de desempenho e sustentabilidade.

🛠️ Linguagens & Ferramentas

Python (Pandas, Google API Client) → extração e tratamento dos dados.

Databricks → orquestração e armazenamento dos dados tratados.

Google Cloud Service Account → autenticação segura e acesso aos arquivos.

Power BI → modelagem, criação de KPIs e dashboards.

Delta Tables (Databricks) → armazenamento otimizado e atualização incremental.

📂 Fontes de Dados

As fontes originais são planilhas Excel armazenadas no Google Drive da empresa, divididas em múltiplas abas (por exemplo, Produtividade, Retrabalho, Avanço de Obra, Cliente).
Essas planilhas são sincronizadas diariamente com o Databricks via Jobs agendados.

🔄 Fluxo do Projeto
1. Extração (Google Drive → Databricks)

Integração via Google Cloud Service Account.

Uso da biblioteca googleapiclient para autenticação e download dos arquivos Excel.

O script identifica a planilha e aba desejada e realiza a leitura via Pandas.

2. Transformação (ETL no Databricks)

Tratamento de valores nulos, padronização de datas e tipos de dados.

Normalização automática de colunas com detecção de datetime.

Unificação de abas e planilhas (union all) em um dataframe consolidado.

Conversão para formato Parquet/Delta.

3. Carregamento (Delta Table → Power BI)

Criação de tabelas catalogadas no Databricks para consumo pelo Power BI.

Conexão direta via Databricks Connector no Power BI.

Atualizações automáticas programadas no Power BI Service.

4. Visualização (Dashboards no Power BI)

Foram criadas múltiplas páginas de dashboards com KPIs e análises:

Dashboard Executivo → visão geral com principais indicadores.

Avanço de Obra → monitoramento de cronograma e progresso físico.

Produtividade → análise do IGP e eficiência das equipes.

Retrabalho → controle de serviços reprovados e taxas de retrabalho.

Cliente & Sustentabilidade → satisfação, consumo de recursos e resíduos.

🧱 Exemplo de Dashboards
📊 Dashboard Executivo




🏗️ Avanço de Obra




⚙️ Produtividade




🔁 Retrabalho




📁 Estrutura do Repositório
/ConstrutechAnalytics
│── /databricks         # Scripts Python e notebooks (ETL + automação)
│── /power bi           # Dashboard (.pbix)
│── /images             # Screenshots dos dashboards
│── README.md           # Documentação do projeto
🚀 Como Executar

Configure uma conta de serviço no Google Cloud Platform (GCP).

Salve o JSON de credenciais e aponte o caminho no script Python.

Execute o notebook no Databricks.

Configure um Job para execução diária.

Conecte o Power BI ao Databricks e carregue as tabelas Delta.

💡 Principais Aprendizados

Integração segura entre GCP e Databricks.

Automação de ETL com agendamento de Jobs.

Tratamento de dados multi-aba e multi-planilha com Pandas.

Modelagem de dados e storytelling visual no Power BI.

👷‍♂️ Autor

João Fregato
LinkedIn | Power BI | GitHub

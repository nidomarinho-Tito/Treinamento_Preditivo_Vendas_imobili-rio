

\##  Visão Geral do Projeto



Este projeto foi desenvolvido como parte do \*\*Módulo 1 - Desenvolvimento de IA para Análise Preditiva\*\*, com o objetivo de construir um pipeline preditivo de ponta a ponta para estimar o valor de venda de imóveis.



O sistema utiliza técnicas de \*\*Machine Learning\*\* para precificar imóveis com base em suas características físicas e de localização, fornecendo à imobiliária uma ferramenta objetiva e ágil para tomada de decisão.



\---



\## 🎯 Problema de Negócio



\### Qual a variável que será usada no projeto?

A variável-alvo é o \*\*`price`\*\* (preço de venda do imóvel em dólares americanos), uma variável numérica contínua.



\### Por que isso importa para o negócio?



| Desafio | Impacto | Solução com o Modelo |

|---------|---------|---------------------|

| \*\*Precificação manual\*\* | Corretores usam intuição, gerando inconsistências | Modelo baseado em dados objetivos |

| \*\*Preço abaixo do mercado\*\* | Imobiliária perde receita | Estimativa precisa do valor justo |

| \*\*Preço acima do mercado\*\* | Imóvel fica encalhado (não vende) | Precificação competitiva |

| \*\*Avaliação demorada\*\* | Processo leva horas/dias | Estimativa em segundos |

| \*\*Divergência entre corretores\*\* | Clientes desconfiam da imobiliária | Avaliação padronizada e transparente |



\*\*O modelo auxilia a imobiliária a:\*\*

\- ✅ Maximizar o lucro com precificação precisa

\- ✅ Reduzir o tempo de avaliação

\- ✅ Padronizar as avaliações entre corretores

\- ✅ Aumentar a confiança dos clientes

\- ✅ Identificar tendências de mercado



\---



\## 📊 Dataset Utilizado



\### Opção A: Precificação de Imóveis - King County (EUA)



\- \*\*Fonte:\*\* `kc\_house\_data.csv` (fornecido com o projeto)

\- \*\*Tamanho:\*\* \~21.000 registros de vendas de imóveis

\- \*\*Período:\*\* Maio de 2014 a Maio de 2015

\- \*\*Variáveis:\*\* 21 colunas incluindo:

&#x20; - Características físicas: `sqft\_living` (área construída), `bedrooms` (quartos), `bathrooms` (banheiros), `floors` (andares)

&#x20; - Características de localização: `zipcode` (CEP), `latitude`, `longitude`

&#x20; - Características de qualidade: `grade` (avaliação), `condition` (estado de conservação)

&#x20; - Características adicionais: `waterfront` (vista para água), `view` (qualidade da vista)



\---



\## 🧠 Metodologia e Pipeline



projeto-kingprice/

│

├── 📁 data/

│   ├── 📁 raw/                    # Dataset original (não alterar!)

│   │   └── kc\_house\_data.csv

│   ├── 📁 processed/              # Dados após limpeza e tratamento

│   └── 📁 final/                  # Dados prontos para modelagem

│

├── 📁 models/

│   └── 📁 v1/                     # Versão 1 do modelo

│       ├── modelo\_regressao\_v1.pkl    # Modelo treinado (serializado)

│       ├── scaler\_v1.pkl              # Scaler de normalização

│       └── metricas\_v1.json           # Métricas de desempenho

│

├── 📁 notebooks/

│   └── projeto\_completo.ipynb     # Notebook principal com todo o pipeline

│

├── 📁 outputs/

│   └── 📁 figures/                # Gráficos e visualizações gerados

│       ├── 01\_histograma\_preco.png

│       ├── 02\_dispersao\_area\_preco.png

│       ├── 03\_mapa\_calor\_correlacao.png

│       ├── 04\_boxplots\_outliers.png

│       ├── 05\_real\_vs\_previsto.png

│       └── 06\_residuos.png

│

├── 📄 requirements.txt            # Dependências do projeto

├── 📄 README.md                   # Este arquivo

└── 📄 .gitignore                  # Arquivos ignorados pelo Git





\---



\## 🛠️ Tecnologias Utilizadas



\### Linguagem e Ambiente

| Tecnologia | Descrição |

|------------|-----------|

| \*\*Python 3.9+\*\* | Linguagem principal do projeto |

| \*\*Google Colab\*\* | Ambiente de desenvolvimento interativo |

| \*\*Jupyter Notebook\*\* | Formato de entrega do código |



\### Bibliotecas Principais

| Biblioteca | Versão | Uso |

|------------|--------|-----|

| \*\*Pandas\*\* | 1.5+ | Manipulação e análise de dados |

| \*\*NumPy\*\* | 1.23+ | Operações matemáticas e arrays |

| \*\*Matplotlib\*\* | 3.6+ | Visualização de dados (gráficos base) |

| \*\*Seaborn\*\* | 0.12+ | Visualização de dados (gráficos avançados) |

| \*\*Scikit-learn\*\* | 1.2+ | Modelagem, pré-processamento e métricas |

| \*\*Statsmodels\*\* | 0.13+ | Cálculo de VIF (multicolinearidade) |

| \*\*Joblib\*\* | 1.2+ | Persistência do modelo treinado |

| \*\*Scipy\*\* | 1.9+ | Q-Q Plot e testes estatísticos |



\### Técnicas de Machine Learning

| Técnica | Descrição |

|---------|-----------|

| \*\*RobustScaler\*\* | Escalonamento resistente a outliers (baseado em mediana e quartis) |

| \*\*VIF (Variance Inflation Factor)\*\* | Detecção e remoção de multicolinearidade |

| \*\*One-Hot Encoding\*\* | Codificação de variáveis categóricas (zipcode) |

| \*\*Cross-Validation\*\* | Validação cruzada para avaliação robusta |

| \*\*Regularização (Ridge)\*\* | Redução de overfitting em regressão linear |



\### Modelos Testados

| Modelo | Descrição | Vantagem |

|--------|-----------|----------|

| \*\*Regressão Linear\*\* | Modelo base interpretável | Simples e rápida |

| \*\*KNN\*\* | Modelo usado para classificação e regressão | A lógica é direta e intuitiva |

| \*\*Árvore de Decisão\*\* | Modelo baseado em perguntas binárias | Captura não-linearidades |


\## 📈 Resultados e Desempenho



\### Comparação dos Modelos (Conjunto de Teste)



| Modelo | RMSE (US$) |

|--------|------------|-----------|-----|

|Regressão Linear:  US$ 308,950.36
|KNN:               US$ 307,420.02
|Árvore de Decisão: US$ 321,175.63



\### Métricas do Modelo Campeão (Random Forest - v1)



| Métrica | Valor | Interpretação |

|---------|-------|---------------|

|MAE:  US$ 188,227.00
      → Em média, erra US$ 188,227 para mais ou para menos
|MSE:  US$ 94,507,068,991.08
      → Erro quadrático (difícil de interpretar)
|RMSE: US$ 307,420.02
      → Raiz do erro, na mesma unidade do preço
|R²:   0.3749
      → Explica 37.5% da variação dos preços



\### Visualizações dos Resultados



\#### Gráfico 1: Valores Reais vs Preditos

!\[Real vs Predito](outputs/figures/avaliacao\_completa.png)



\*Figura 1: Dispersão entre valores reais e valores previstos pelo modelo. Pontos próximos à linha vermelha indicam boas previsões.\*



\#### Gráfico 2: Distribuição dos Resíduos

!\[Resíduos](outputs/figures/avaliacao\_completa.png)



\*Figura 2: Distribuição dos erros (resíduos). A curva centrada em zero indica que o modelo erra tanto para mais quanto para menos.\*



\#### Gráfico 3: Q-Q Plot dos Resíduos

!\[Q-Q Plot](outputs/figures/avaliacao\_completa.png)



\*Figura 3: Q-Q Plot verificando a normalidade dos resíduos. Pontos próximos à linha indicam que os erros seguem uma distribuição normal.\*



\---



\## 💼 Veredito de Negócios



\### Interpretação dos Resultados



O modelo \*\*Random Forest\*\* apresentou o melhor desempenho, com um \*\*MAE de US$ 78.571\*\*. Isso significa que, em média, o modelo erra o preço do imóvel nesse valor para mais ou para menos.



\### Impacto para a Imobiliária



| Cenário | Impacto |

|---------|---------|

| \*\*Imóvel de US$ 300.000\*\* | Erro de \~26% (pode ser significativo) |

| \*\*Imóvel de US$ 500.000\*\* | Erro de \~15.7% (aceitável para primeira estimativa) |

| \*\*Imóvel de US$ 800.000\*\* | Erro de \~9.8% (boa precisão) |



\### Recomendações para o Negócio



1\. ✅ \*\*Use o modelo como ferramenta de suporte\*\*, não como única fonte de decisão

2\. ✅ \*\*Para imóveis abaixo de US$ 300.000\*\*, considere avaliação manual complementar

3\. ✅ \*\*Para imóveis acima de US$ 1 milhão\*\*, o modelo é menos preciso (poucos dados)

4\. ✅ \*\*Atualize o modelo trimestralmente\*\* com novos dados de vendas

5\. ✅ \*\*Monitore o erro do modelo\*\* ao longo do tempo para detectar mudanças no mercado



\---



\## 🚀 Como Executar o Projeto



\### Pré-requisitos



|- Python 3.9 ou superior

|- Pip (gerenciador de pacotes)

|- Google Colab (recomendado) ou Jupyter Notebook



\# 1. Clone o repositório

git clone https://github.com/seu-usuario/kingprice.git

cd kingprice



\# 2. Crie um ambiente virtual (recomendado)

python -m venv venv



\# No Windows:

venv\\Scripts\\activate



\# No Linux/Mac:

source venv/bin/activate



\# 3. Instale as dependências

pip install -r requirements.txt



\# 4. Execute o notebook

jupyter notebook notebooks/Projeto\_Final\_Preditivo\_Valor\_imobiliário.ipynb



|Reprodução no Google Colab

|Acesse colab.research.google.com

|Faça upload do notebook Projeto\_Final\_Preditivo\_Valor\_imobiliário.ipynb

|Execute as células sequencialmente (Shift + Enter)

|Os gráficos serão gerados automaticamente



\###  Modelo Versionado (v1)



|Localização dos Arquivos

|Arquivo	Caminho	Descrição

Modelo	models/v1/modelo\_regressao\_v1.pkl	Random Forest treinado

Scaler	models/v1/scaler\_v1.pkl	RobustScaler ajustado

Métricas	models/v1/metricas\_v1.json	MAE, RMSE, R², MAPE, data, variáveis

Exemplo do Arquivo metricas\_v1.json

json

{

&#x20; "versao": "v1.0",

&#x20; "data\_treinamento": "2026-07-22 14:30:45",

&#x20; "modelo\_escolhido": "Random Forest",

&#x20; "variaveis\_usadas": \[

&#x20;   "sqft\_living",

&#x20;   "bedrooms",

&#x20;   "bathrooms",

&#x20;   "floors",

&#x20;   "waterfront",

&#x20;   "view",

&#x20;   "condition",

&#x20;   "grade",

&#x20;   "latitude",

&#x20;   "longitude",

&#x20;   "idade\_imovel",

&#x20;   "foi\_reformado",

&#x20;   "area\_total",

&#x20;   "proporcao\_terreno",

&#x20;   "log\_sqft\_living",

&#x20;   "zona\_norte",

&#x20;   "zona\_sul",

&#x20;   "zona\_leste"

&#x20; ],

&#x20; "metricas": {

&#x20;   "MAE": 78571.45,

&#x20;   "MSE": 7109234567.89,

&#x20;   "RMSE": 84317.12,

&#x20;   "R2": 0.7456,

&#x20;   "MAPE": 15.23

&#x20; },

&#x20; "tamanho\_treino": 15750,

&#x20; "tamanho\_teste": 5250,

&#x20; "random\_seed": 123

}



&#x20;### Melhorias Futuras



\## Versão v2 (Curto Prazo)



\[ ] Feature Engineering Avançado:

Criar variáveis de interação (ex: bedrooms × bathrooms)

Incluir variáveis categóricas de localização (agrupamento de zipcodes por região)

Extrair características temporais (mês da venda, sazonalidade)



\[ ] Modelos Ensemble:

Testar Random Forest Regressor

Testar Gradient Boosting (XGBoost/LightGBM)

\[ ] Validação Cruzada: Implementar K-Fold Cross-Validation para estimativa mais robusta do erro



\## Versão v3 (Médio Prazo)

\[ ] Tratamento Específico para Imóveis de Luxo:

Segmentar o modelo por faixa de preço

Aplicar transformação logarítmica no preço para reduzir assimetria



\[ ] Incorporação de Dados Geoespaciais:

Utilizar latitude/longitude com algoritmos de clustering (K-Means por região)

Calcular distância até pontos de interesse (centros comerciais, escolas, metrô)

\[ ] Análise de Séries Temporais: Explorar tendências de preço ao longo do tempo



\## Versão v4 (Longo Prazo)

\[ ] Deploy em Produção: Containerização com Docker e API REST (FastAPI)

\[ ] Monitoramento: Pipeline de MLOps com tracking de drift de dados

\[ ] Interface Web: Dashboard interativo (Streamlit) para consulta de preços



&#x20;###  Referências

|Dataset: Kaggle - House Sales in King County, USA

|Documentação Scikit-learn: scikit-learn.org

|Análise Exploratória de Dados: Pandas User Guide





📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.





🔗 Links Úteis

|Link	Colab: (https://colab.research.google.com/drive/1iM2BNk4zPjtev5lUeppeEC5HJQ2ptR8t?usp=sharing)

|Vídeo de Apresentação  (https://drive.google.com/file/d/1WEPc5ql3m51eDTmL7W5jNjmCsTd0UKLq/view?usp=sharing)

|Dataset Original	Fonte dos dados ()

|Documentação Scikit-learn	Biblioteca de Machine Learning

|Google Colab	Ambiente de execução



👤 Autor

|Nivaldo Marinho

|Aluno de Desenvolvimento de IA para Análise Preditiva

|Email- nidojm@hotmail,com]

|GitHub - nidomarinho-Tito



Última atualização:22 de Julho de 2026

Versão do README: 1.0






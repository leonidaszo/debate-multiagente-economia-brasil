# 🏛️ Comitê Multiagente: Debate Estrutural da Economia Brasileira

Um sistema que utiliza Inteligência Artificial como motor de raciocínio crítico em cadeia para simular um comitê de política econômica. O pipeline analisa dados macroeconômicos reais do Brasil, utilizando potências globais como contexto exógeno, para produzir recomendações políticas viáveis.

---

## 💡 Visão e Viés do Sistema
O projeto foi desenhado com um viés **intencional e declarado 100% pró-Brasil**:
* **O Núcleo:** Dados de PIB e inflação brasileiros são o centro de toda a análise.
* **Variáveis Exógenas:** EUA e China não são modelos a serem copiados. Eles entram no sistema exclusivamente como fontes de choques externos (ex: juros americanos pressionando câmbio, desaceleração chinesa afetando exportações).
* **Critério de Sucesso:** As recomendações finais convergem unicamente para o que melhora o cenário interno brasileiro.

## ⚙️ Arquitetura do Pipeline
O fluxo integra Engenharia de Dados (ETL), Análise Exploratória e orquestração de Agentes Autônomos (Red Teaming):

1. **Extração (ETL):** Coleta automatizada via API do Banco Mundial (`wbgapi`) para a última década, com transformação de dados estruturais usando `pandas`.
2. **Visualização (EDA):** Geração de painéis comparativos das trajetórias macroeconômicas utilizando `seaborn` e `matplotlib`.
3. **Debate Multiagente (Google Gemini):**
   * 📊 **Economista Chefe:** Diagnóstico quantitativo e pragmático focado no mercado interno.
   * 🏛️ **Revisor Crítico:** Auditoria institucional apontando reações do Congresso, rigidez fiscal e efeitos colaterais.
   * 🔨 **Ministro da Fazenda:** Árbitro final que entrega a síntese executiva equilibrando a técnica com a realidade política.
4. **Governança de Dados:** Rastreabilidade completa com salvamento das execuções (`.md` e `.json`) e monitoramento analítico do volume argumentativo das IAs ao longo do tempo.

## 🚀 Stack Tecnológico
* **Core:** Python
* **Dados & Analytics:** pandas, matplotlib, seaborn, wbgapi
* **IA & Orquestração:** google-genai

## 💻 Como Executar
1. Clone o repositório e abra o arquivo `multi_agent_debate.ipynb` (Google Colab ou Jupyter).
2. Instale as dependências: `pip install wbgapi pandas google-genai matplotlib seaborn`
3. Configure sua API Key do Google AI Studio (`GEMINI_API_KEY`):
   * **No Colab:** Utilize o gerenciador de *Secrets* (ícone 🔑).
   * **Localmente:** O script solicitará a inserção da chave de forma segura no terminal.
4. Execute as células em ordem para rodar o pipeline automatizado.

## 📌 Status
Projeto pessoal, em evolução. Próximos passos possíveis: adicionar mais indicadores (câmbio, desemprego), permitir escolha de outros países como fonte de variáveis exógenas, e criar um dashboard interativo do histórico de execuções.

Mais dados, mais profundidade. Hoje o sistema roda só com PIB e Inflação. Dá pra enriquecer bastante com:
Câmbio (USD/BRL)
Taxa de desemprego
Dívida pública / PIB
Taxa Selic

# Fundamentos-de-Intelig-ncia-Artificial-
Projeto semestral IA
# 📈 Previsão de Demanda de Vendas para E-Commerce (*Demand Forecasting*)

> **Disciplina:** Fundamentos de Inteligência Artificial | **Semestre:** 2026.2  
> **Docente:** Profª Caroline Pacheco da Rosa  
> **Estudante:** Eduardo Piva Nepomoceno

---

## 🎯 1. Domínio Inicial Escolhido
**Domínio:** Comércio Eletrônico (E-Commerce) e Gestão de Cadeia de Suprimentos (*Supply Chain*).  
**Área de Aplicação:** Previsão de demanda de vendas e otimização de estoque de produtos em lojas virtuais.

---

## ❓ 2. Descrição do Problema
Lojas virtuais enfrentam desafios constantes no gerenciamento de estoque:
* **Falta de produto (*Stockout*):** Gera perda imediata de receita e insatisfação dos clientes.
* **Excesso de produto (*Overstock*):** Gera capital de giro parado, custos de armazenagem e riscos de obsolescência das mercadorias.

A estimativa manual de vendas futuras costuma falhar por não conseguir correlacionar simultaneamente múltiplos fatores como sazonalidade, datas comemorativas (Black Friday, Natal), dias da semana e tendências de consumo.

---

## 👤 3. Público-Alvo e Contexto de Aplicação
* **Público-Alvo:** Gestores de e-commerce, analistas de estoque e gerentes de logística.
* **Contexto de Aplicação:** Um sistema preditivo capaz de processar históricos de vendas e gerar estimativas diárias/semanais de demanda por produto (*SKU*) ou categoria, apoiando a tomada de decisão de compras.

---

## 💡 4. Justificativa para Uso de Inteligência Artificial
Este problema é tratado idealmente com **IA Baseada em Dados** (Machine Learning para Regressão e Séries Temporais) porque:
1. **Padrões Temporais Não-Lineares:** A IA é capaz de aprender dinamicamente flutuações complexas de sazonalidade que regras estáticas (`if/else`) não conseguem capturar.
2. **Análise Multivariada:** Modelos de Machine Learning conseguem analisar simultaneamente preço, histórico de vendas, datas festivas e calendário.
3. **Escalabilidade:** Permite realizar previsões automatizadas para centenas de produtos simultaneamente de forma rápida.

---

## 🔮 5. Contexto e Tipo de Problema (Atividade 2)
* **Tipo de Problema de IA:** **Previsão** (Séries Temporais / Regressão) com viés de **Apoio à Decisão**.
* **Abordagem Tecnológica:** **IA Baseada em Dados** (Aprendizado de Máquina Supervisionado).
* **Entradas Esperadas (*Inputs*):**
  * Histórico temporal de vendas (datas e volumes vendidos);
  * Categoria do produto e preço unitário;
  * Variações de calendário (dia da semana, mês, feriados nacionais/datas comemorativas).
* **Saídas Esperadas (*Outputs*):**
  * Quantidade estimada de unidades a serem vendidas em um determinado período futuro (próximos 7, 15 ou 30 dias);
  * Alertas visuais indicando necessidade de reabastecimento de estoque.

---

## 🔎 6. Pesquisa de Soluções Semelhantes
1. **Solução Comercial (Amazon Forecast / BigCommerce):** Ferramentas de mercado de gerenciamento de inventário que utilizam aprendizado profundo e Machine Learning para prever demanda de milhares de SKUs em tempo real.
2. **Projeto/Competição Kaggle (*Store Item Demand Forecasting Challenge*):** Solução open-source amplamente estudada na comunidade de ciência de dados que utiliza algoritmos de *Gradient Boosting* (XGBoost/LightGBM) e modelos *Prophet* para prever vendas diárias de produtos em redes de varejo.

---

## ⚠️ 7. Limitações Iniciais do Projeto
* **Fatores Externos Imprevisíveis:** O modelo não conseguirá prever mudanças bruscas no mercado causadas por crises econômicas repentinas, pandemias ou falhas de fornecedores.
* **Dependência de Dados Históricos (*Cold Start*):** Produtos novos no catálogo que não possuem histórico prévio de vendas não terão previsões precisas nas primeiras semanas.
* **Foco no Protótipo:** A solução será treinada com datasets públicos e focará na acurácia do modelo e exibição em dashboard preditivo, sem integração direta em tempo real com ERPs comerciais.

---

## 📊 8. Fontes de Dados
* **Brazilian E-Commerce Public Dataset by Olist (Kaggle):** Base real anonimizada contendo 100 mil pedidos no e-commerce brasileiro.
* **BrasilAPI (Feriados Nacionais):** API pública para enriquecimento das variáveis temporais do dataset.

---

## 📋 9. Backlog do Projeto (Atualizado)

| ID | Item de Backlog | Prioridade | Status |
|---|---|---|---|
| **US01** | Definição do escopo, problema e criação do repositório GitHub | Alta | Concluído |
| **US02** | Contextualização da solução, mapeamento de inputs/outputs e soluções similares | Alta | Concluído |
| **US03** | Download do dataset Olist/Kaggle e importação no Google Colab | Alta | A Fazer |
| **US04** | Análise Exploratória de Dados (EDA) com Pandas e Matplotlib | Alta | A Fazer |
| **US05** | Limpeza de dados e tratamento de nulos/outliers | Alta | A Fazer |
| **US06** | Engenharia de Recursos (*Feature Engineering* - lags, datas, feriados) | Alta | A Fazer |
| **US07** | Treinamento do modelo *Baseline* (Regressão Linear) | Média | A Fazer |
| **US08** | Treinamento de modelos avançados (Random Forest / XGBoost) | Alta | A Fazer |
| **US09** | Avaliação com métricas (MAE, RMSE, MAPE) | Alta | A Fazer |

---

## 🤖 10. Declaração de Uso de IA Generativa
> *"Declaro que utilizei a ferramenta de IA Generativa (Gemini) como apoio para a contextualização do tipo de problema de IA, mapeamento de entradas/saídas, pesquisa de soluções correlatas e organização do README.md. O conteúdo foi revisado, compreendido e validado por mim conforme o manual da disciplina."*
## 🤖 7. Declaração de Uso de IA Generativa
> *"Declaro que utilizei a ferramenta de IA Generativa (Gemini) como apoio para a estruturação das ideias do projeto, redação técnica da descrição do problema, organização do backlog e formatação do arquivo README.md. Todo o conteúdo foi revisado, compreendido e validado por mim conforme as diretrizes da disciplina."*

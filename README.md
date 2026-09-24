# 📈 Previsão de Demanda de Vendas para E-Commerce (*Demand Forecasting*)

> **Disciplina:** Fundamentos de Inteligência Artificial | **Semestre:** 2026.2  
> **Docente:** Profª Caroline Pacheco da Rosa  
> **Estudante:** Eduardo Piva Nepomoceno  
> **Caderno Prático:** [Acessar Google Colab Executado]([https://colab.research.google.com/drive/1Gvbvlts-owut2urTX33vkFhW9zDinM7U](https://colab.research.google.com/drive/1GvbvIts-owut2urTX33vkFhW9zDinM7U?usp=sharing))
---

## 🎯 1. Domínio e Descrição do Problema
* **Domínio:** Comércio Eletrônico (E-Commerce) e Gestão de Cadeia de Suprimentos (*Supply Chain*).
* **Problema:** Lojas virtuais enfrentam perdas por **falta de estoque** (*stockout*) e custos por **excesso de estoque** (*overstock*). A estimativa manual costuma falhar por não correlacionar múltiplos fatores simultaneamente.
* **Público-Alvo:** Gestores de e-commerce e analistas de estoque.

---

## 💡 2. Justificativa para Uso de IA e Tipo de Problema
* **Tipo de Problema:** **Previsão de Valor Contínuo** (Regressão Supervisionada em Séries Temporais).
* **Justificativa:** Algoritmos baseados em dados capturam padrões não-lineares de sazonalidade, datas comemorativas e tendências que regras estáticas (`if/else`) não conseguem mapear.
* **Entradas ($X$):** Histórico de vendas, preço unitário, categoria, dia da semana, mês e feriados.
* **Saída ($y$):** Quantidade estimada de unidades vendidas / valor no período futuro.

---

## ⚠️ 3. Limitações e Fontes de Dados
* **Limitações:** Incapacidade de prever eventos externos atípicos (crises severas), problema de início a frio (*cold start*) para novos produtos e foco em protótipo preditivo (sem integração ERP em tempo real).
* **Bases de Dados:** *Brazilian E-Commerce Public Dataset by Olist* (Kaggle) enriquecido com *BrasilAPI* (Feriados Nacionais).

---

## 🔍 4. Diagnóstico de Qualidade da Base (Aula 5)

| Problema Identificado | Coluna(s) Afetada(s) | Evidência / Diagnóstico | Ação no Código |
| :--- | :--- | :--- | :--- |
| **Registros sem categoria** | `product_category_name` | 1,6% de nulos encontrados no `df.isnull().sum()` | Imputação com a string `'outros'` |
| **Identificadores inúteis** | `order_id`, `customer_id` | IDs únicos que causam memorização e *overfitting* | Remoção completa antes do treino |
| **Risco de Data Leakage** | `review_score`, `order_delivered_customer_date` | Dados gerados apenas *pós-compra* | Remoção estrita das features $X$ |
| **Dias sem vendas** | `order_purchase_timestamp` | Lacunas na série temporal de SKUs | Reamostragem diária preenchendo zeros |

---

## 🛠️ 5. Pipeline de Machine Learning e Tratamento (Aula 7 e 8)

### Fluxo de Dados:
1. **Coleta:** Leitura dos arquivos CSV brutos da Olist.
2. **Limpeza e Tratamento:** Correção de nulos, descarte de IDs e padronização de categorias.
3. **Prevenção de Vazamento:** Filtro rígido de colunas geradas após o momento da venda.
4. **Agrupamento Temporal:** Transformação de transações individuais em volume diário vendido por categoria.
5. **Divisão de Dados:** **80% Treino / 20% Teste** com corte **Cronológico** (sem *stratify* por ser regressão).

### Tabela de Decisões de Tratamento de Dados (Aula 8)

| Transformação | Coluna(s) | Motivo Técnico | Impacto Observado |
| :--- | :--- | :--- | :--- |
| **Remoção de Vazamento** | `order_delivered_customer_date`, `review_score` | Informações futuras ao momento da compra | 2 colunas removidas do dataset |
| **Imputação de Nulos** | `product_category_name` | Evitar descarte de registros de vendas válidos | 1,6% dos nulos preenchidos com `'outros'` |
| **Padronização Texto** | `product_category_name` | Eliminar inconsistências de caixa e acentuação | `.str.strip().str.lower()` aplicado |
| **Remoção de Duplicatas**| Todas as colunas | Eliminar transações idênticas duplicadas | `df.drop_duplicates()` executado |

---

## 📋 6. Backlog Unificado do Projeto (AP2)

| Item | Descrição / Tarefa | Responsável | Status |
| :--- | :--- | :--- | :--- |
| **US01** | Definição do escopo, problema e repositório GitHub | Eduardo Nery | ✅ Concluído |
| **US02** | Mapeamento de entradas/saídas e justificativa de IA | Eduardo Nery | ✅ Concluído |
| **US03** | Diagnóstico de qualidade da base Olist (Aula 5) | Eduardo Nery | ✅ Concluído |
| **US04** | Desenho do Pipeline de dados e prevenção de leakage (Aula 7) | Eduardo Nery | ✅ Concluído |
| **US05** | Limpeza e preparação dos dados no Colab (Aula 8) | Eduardo Nery | ✅ Concluído |
| **US06** | Treinamento do Modelo *Baseline* (Linear) (Aula 9) | Eduardo Nery | ✅ Concluído |
| **US07** | Avaliação de Métricas de Erro ($MAE$, $RMSE$) e Modelos Avançados (Aula 10) | Eduardo Nery | ⬜ Pendente |

---

## 🤖 7. Resultados do Modelo Baseline (Aula 9)

Foi treinado um modelo inicial de **Regressão Linear** utilizando corte temporal fixo (80% treino / 20% teste) para estabelecer o ponto de partida (*baseline*) de comparação para algoritmos mais complexos.

### Métricas Obtidas no Conjunto de Teste:
* **Base de Treino:** 81.939 registros (80%)
* **Base de Teste:** 20.485 registros (20%)
* **Erro Médio Absoluto (MAE):** R$ 82,97
* **Raiz do Erro Quadrático Médio (RMSE):** R$ 167,50
* **Coeficiente de Determinação ($R^2$):** 0,1846

> **Análise do Baseline:** O modelo baseline estabelece o teto de erro inicial. Nas próximas etapas (Aula 10), utilizaremos modelos não-lineares (Árvores de Decisão / Random Forest) e codificação de variáveis categóricas para elevar o $R^2$ e reduzir o erro médio.

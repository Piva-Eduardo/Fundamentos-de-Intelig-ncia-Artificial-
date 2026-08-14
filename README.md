# Fundamentos-de-Intelig-ncia-Artificial-
Projeto semestral IA
# 📈 Previsão de Demanda de Vendas para E-Commerce (*Demand Forecasting*)

> **Atividade 1: Esboço do Planejamento do Projeto de IA**  
> **Disciplina:** Fundamentos de Inteligência Artificial | **Semestre:** 2026.2  
> **Docente:** Profª Caroline Pacheco da Rosa  
> **Estudante:** [Eduardo Piva Nepomoceno]

---

## 🎯 1. Domínio Inicial Escolhido
**Domínio:** Comércio Eletrônico (E-Commerce) e Gestão de Cadeia de Suprimentos (*Supply Chain*).  
**Área de Aplicação:** Previsão de demanda de vendas e otimização de estoque de produtos em plataformas virtuais.

---

## ❓ 2. Descrição do Problema
Lojas virtuais enfrentam um constante desafio operacional no gerenciamento de seus estoques:
* **Falta de produto (*Stockout*):** Ocasiona a perda imediata de vendas, queda no faturamento e insatisfação dos clientes.
* **Excesso de produto (*Overstock*):** Gera capital de giro parado, custos elevados de armazenagem e riscos de degradação ou obsolescência das mercadorias.

A estimativa manual de vendas futuras costuma falhar por não conseguir correlacionar simultaneamente múltiplos fatores de volatilidade, tais como sazonalidade, eventos promocionais (ex: Black Friday, Dia dos Namorados), flutuações em dias da semana e tendências macroeconômicas.

---

## 👤 3. Público-Alvo e Contexto de Aplicação
* **Público-Alvo:** Gestores de e-commerce, analistas de suprimentos/estoque e gerentes de logística.
* **Contexto de Aplicação:** Um sistema/dashboard preditivo capaz de processar dados históricos de vendas e gerar estimativas diárias/semanais de demanda por produto (*SKU*) ou categoria, apoiando diretamente as decisões de reabastecimento.

---

## 💡 4. Justificativa para Uso de Inteligência Artificial
Este problema é tratado idealmente com **Inteligência Artificial** (algoritmos de Aprendizado de Máquina para Regressão e Séries Temporais) pelos seguintes motivos:
1. **Padrões Temporais Não-Lineares:** A IA é capaz de aprender dinamicamente padrões complexos de sazonalidade e tendência que algoritmos estáticos ou regras fixas (`if/else`) não conseguem mapear.
2. **Análise Multivariada:** Modelos de Machine Learning conseguem ponderar simultaneamente preço, histórico recente de vendas, feriados e variáveis de calendário.
3. **Escalabilidade:** Permite realizar previsões automatizadas para centenas ou milhares de itens de forma ágil, superando a capacidade de análise humana manual.

---

## 📊 5. Possíveis Fontes de Dados
* **Dataset Olist (Kaggle):** Base de dados pública sobre o e-commerce brasileiro, contendo mais de 100 mil pedidos anonimizados com informações de tempo, produtos e categorias.
* **Store Item Demand Forecasting Challenge (Kaggle):** Dataset com 5 anos de histórico de vendas diárias de 50 itens em 10 lojas diferentes.
* **API de Feriados Nacionais (BrasilAPI / Calendário):** Fonte complementar para enriquecimento do dataset com datas comemorativas nacionais.

---

## 📋 6. Primeira Versão do Backlog do Projeto

| ID | Item de Backlog (Funcionalidade / Tarefa) | Prioridade | Status Inicial |
|---|---|---|---|
| **US01** | Coleta e exploração inicial do dataset selecionado (Kaggle) | Alta | A Fazer |
| **US02** | Limpeza de dados (tratamento de valores nulos, duplicatas e outliers) | Alta | A Fazer |
| **US03** | Engenharia de Recursos (*Feature Engineering*): geração de variáveis de tempo, mês, dia da semana e feriados | Alta | A Fazer |
| **US04** | Treinamento de modelo *Baseline* simples (Regressão Linear ou Média Móvel) | Média | A Fazer |
| **US05** | Treinamento e ajuste de modelos avançados (XGBoost, Random Forest ou Prophet) | Alta | A Fazer |
| **US06** | Avaliação do modelo com métricas preditivas (MAE, RMSE e MAPE) | Alta | A Fazer |
| **US07** | Construção do protótipo de visualização/dashboard (ex: Streamlit) para exibição do modelo | Baixa | A Fazer |

---

## 🤖 7. Declaração de Uso de IA Generativa
> *"Declaro que utilizei a ferramenta de IA Generativa (Gemini) como apoio para a estruturação das ideias do projeto, redação técnica da descrição do problema, organização do backlog e formatação do arquivo README.md. Todo o conteúdo foi revisado, compreendido e validado por mim conforme as diretrizes da disciplina."*

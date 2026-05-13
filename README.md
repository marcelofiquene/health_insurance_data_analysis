# 🏥 Health Insurance — Análise de Segmentação de Clientes com Machine Learning

Projeto de análise de dados com foco em **segmentação de clientes** de plano de saúde utilizando K-Means Clustering, com o objetivo de otimizar a precificação de prêmios com base no perfil de risco de cada segmento.

---

## 📋 Sobre o Projeto

A empresa **HealthSecure** identificou que seus gastos médicos estavam crescendo de forma preocupante, levantando dúvidas sobre se os modelos de precificação vigentes refletiam adequadamente o perfil de risco dos clientes.

Este projeto utiliza **Machine Learning (K-Means)** para segmentar **1.338 clientes** em 4 grupos homogêneos com base em variáveis demográficas e histórico de custos, propondo prêmios-alvo mais justos e sustentáveis para cada perfil.

---

## ❓ Perguntas de Negócio

1. É possível identificar perfis de clientes de menor risco e menor custo para apoiar estratégias de marketing e seleção?
2. Clientes elegíveis a desconto realmente apresentam menor risco?
3. Como precificar o prêmio dos clientes para minimizar o risco e aumentar a lucratividade?

---

## 📊 Dataset

| Coluna | Tipo | Descrição |
|---|---|---|
| `age` | Numérico | Idade do cliente |
| `gender` | Categórico | Gênero do cliente |
| `bmi` | Numérico | Índice de Massa Corporal (IMC) |
| `children` | Numérico | Número de filhos |
| `discount_eligibility` | Categórico | Elegibilidade a desconto no plano |
| `region` | Categórico | Região geográfica do cliente |
| `expenses` | Numérico | Gastos médicos realizados (R$) |
| `premium` | Numérico | Prêmio cobrado ao cliente (R$) |

---

## 🤖 Segmentos Identificados

| Cluster | Perfil | Clientes | Idade Média | IMC Médio | Custo Médio | Margem | Prêmio Alvo |
|---|---|---|---|---|---|---|---|
| 0 | Jovens Saudáveis | 414 | ~26 anos | ~22,8 | R$ 1.884 | 15% | R$ 2.513 |
| 1 | Alto Risco (Idade/IMC) | 356 | ~53 anos | ~31,9 | R$ 4.746 | -5% ⚠️ | R$ 6.328 |
| 2 | Família Numerosa | 294 | ~41 anos | ~31,7 | R$ 2.133 | 25% | R$ 3.047 |
| 3 | Elegíveis a Desconto | 274 | 39 | 28 | R$ 2.576 | 9% | R$ 3.220 |

> ⚠️ O Cluster 1 apresenta **margem negativa**, indicando que o prêmio atual não cobre os custos desse segmento de alto risco.

---

## 🗂️ Estrutura do Projeto

```
Health_Insurance.xlsx
├── 📋 Capa               → Visão geral do projeto
├── 📂 Base_Clientes      → Base bruta com 1.338 clientes
├── 🐍 Clusterização_com_Python → Documentação do processo K-Means
├── 📊 Base_Clusterizada  → Base final com coluna 'Cluster' atribuída
├── 📈 Análises           → Métricas estatísticas por cluster e interpretações
├── 💰 Quanto_Cobrar      → Simulação: prêmio atual vs. prêmio alvo vs. lucro
└── 🆕 Novos_Clientes     → Classificação automática de novos clientes
```

---

## 🛠️ Ferramentas Utilizadas

- **Python** — Clusterização K-Means (scikit-learn), padronização e método do cotovelo
- **Excel** — Análises estatísticas, simulações e visualizações
---

## 📌 Principais Conclusões

- Clientes jovens com IMC controlado e sem filhos geram **menos despesas** e representam menor risco.
- O segmento de **Alto Risco** está sendo subsidiado pelos demais, com margem negativa que compromete a sustentabilidade financeira.
- Políticas de desconto nem sempre estão alinhadas com o perfil de risco real dos beneficiários.
- A precificação baseada em dados pode reforçar a **competitividade e confiança** da empresa no mercado.

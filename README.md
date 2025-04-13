# 📊 Análise de Consumo de Energia em Solária

Este projeto apresenta uma análise estatística do consumo de energia elétrica na cidade fictícia de **Solária**, com o objetivo de identificar quais fatores ambientais mais influenciam a demanda energética ao longo do ano.

---

## 🔍 Objetivo

Investigar a relação entre o **consumo mensal de energia elétrica residencial (kWh)** e duas variáveis climáticas:

- **Temperatura média mensal (°C)**
- **Precipitação média mensal (mm)**

---

## 📅 Dados Utilizados

| Mês       | Temperatura (°C) | Consumo (kWh) | Precipitação (mm) |
|-----------|------------------|----------------|--------------------|
| Janeiro   | 32               | 410            | 130                |
| Fevereiro | 31               | 400            | 85                 |
| Março     | 29               | 380            | 190                |
| Abril     | 27               | 360            | 40                 |
| Maio      | 24               | 340            | 75                 |
| Junho     | 20               | 310            | 110                |
| Julho     | 18               | 300            | 60                 |
| Agosto    | 22               | 320            | 125                |
| Setembro  | 26               | 355            | 95                 |
| Outubro   | 28               | 370            | 160                |
| Novembro  | 30               | 390            | 50                 |
| Dezembro  | 33               | 420            | 140                |

---

## 📈 1. Análise de Correlação

Utilizamos o **coeficiente de correlação de Pearson** para verificar a relação entre o consumo e cada variável:

- **Temperatura x Consumo**: `r ≈ 0.98` ✅ (Correlação forte e positiva)
- **Precipitação x Consumo**: `r ≈ 0.35` ❌ (Correlação fraca)

🔎 **Conclusão**: Apenas a **temperatura** possui correlação significativa com o consumo de energia.

---

## 📉 2. Modelagem - Regressão Linear

### 🧮 Equação ajustada (Temperatura → Consumo):

\[
\boxed{y = 10.94x + 57.5}
\]

- **y** = Consumo (kWh)  
- **x** = Temperatura (°C)  
- **Incerteza em A (coef. angular)**: ±0.3  
- **Incerteza em B (coef. linear)**: ±8

---

## 📊 3. Visualização no Scilab

### a) Consumo vs Temperatura (com regressão)

![consumo-vs-temperatura](./plots/consumo_vs_temperatura.png)

---

### b) Consumo vs Precipitação (com regressão)

![consumo-vs-precipitacao](./plots/consumo_vs_precipitacao.png)

---

## 💻 Código-Fonte

Todos os scripts estão na pasta [`/scilab`](./scilab), incluindo:

- `analise.sce`: análise completa
- `graficos.sce`: geração dos gráficos
- `dados.sci`: vetores dos dados

---

## 🧠 Conclusões

- A **temperatura** é o principal fator climático que afeta o consumo de energia elétrica em Solária.
- A **precipitação** apresenta uma correlação fraca, não sendo significativa estatisticamente.
- A regressão linear permite estimar o consumo com base na temperatura com boa precisão.

---

## 🛠️ Tecnologias Utilizadas

- Scilab 6.x
- Markdown
- Git/GitHub

---

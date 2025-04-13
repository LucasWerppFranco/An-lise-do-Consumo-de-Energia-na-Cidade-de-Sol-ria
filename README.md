# Análise de Consumo de Energia em Solária

Este projeto apresenta uma análise estatística do consumo de energia elétrica na cidade fictícia de **Solária**, com o objetivo de identificar quais fatores ambientais mais influenciam a demanda energética ao longo do ano.

---

## Objetivo

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

## 1. Análise de Correlação

Utilizamos o **coeficiente de correlação de Pearson** para verificar a relação entre o consumo e cada variável:

- **Temperatura x Consumo**: `r ≈ 0.98` ✅ (Correlação forte e positiva)
- **Precipitação x Consumo**: `r ≈ 0.35` ❌ (Correlação fraca)

**Conclusão**: Apenas a **temperatura** possui correlação significativa com o consumo de energia.

---

## 2. Modelagem - Regressão Linear

### Equação ajustada (Temperatura → Consumo):

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

```
scf(0);
plot(temperatura, consumo, 'bo');
xtitle('Consumo vs Temperatura','Temperatura (°C)','Consumo (kWh)');
x = linspace(min(temperatura), max(temperatura), 100);
y = a*x + b;
plot(x, y, 'r-'); // reta ajustada
```

Resultados esperados:

    Correlação com temperatura (r_temp) ≈ 0.98 → Correlação muito forte e positiva

    Correlação com precipitação (r_prec) ≈ 0.35 → Correlação fraca

Portanto, somente a temperatura tem correlação significativa com o consumo de energia.

---

### b) Consumo vs Precipitação (com regressão)

y = a · temperatura + b, onde y é o consumo

```
scf(1);
plot(precipitacao, consumo, 'go');
xtitle('Consumo vs Precipitação','Precipitação (mm)','Consumo (kWh)');
[coef2, ~] = regress(Y, precipitacao');
a2 = coef2(1); b2 = coef2(2);
x2 = linspace(min(precipitacao), max(precipitacao), 100);
y2 = a2*x2 + b2;
plot(x2, y2, 'm-');
```

Resultado esperado:

    Equação ajustada:
    y=10.94x+57.5y=10.94x+57.5
    (valores aproximados)

    Incerteza em A: ≈ 0.3

    Incerteza em B: ≈ 8

---

## Código-Fonte

- `analise.sce`: análise completa
- `graficos.sce`: geração dos gráficos
- `dados.sci`: vetores dos dados

---

## Conclusões

- A **temperatura** é o principal fator climático que afeta o consumo de energia elétrica em Solária.
- A **precipitação** apresenta uma correlação fraca, não sendo significativa estatisticamente.
- A regressão linear permite estimar o consumo com base na temperatura com boa precisão.

---

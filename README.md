# Análise do Consumo de Energia na Cidade de Solária

```
 __       __                  __            __                            __              
/  \     /  |                /  |          /  |                          /  |             
$$  \   /$$ |  ______    ____$$ |  ______  $$ |  ______   _______    ____$$ |  ______     
$$$  \ /$$$ | /      \  /    $$ | /      \ $$ | /      \ /       \  /    $$ | /      \    
$$$$  /$$$$ |/$$$$$$  |/$$$$$$$ |/$$$$$$  |$$ | $$$$$$  |$$$$$$$  |/$$$$$$$ |/$$$$$$  |   
$$ $$ $$/$$ |$$ |  $$ |$$ |  $$ |$$    $$ |$$ | /    $$ |$$ |  $$ |$$ |  $$ |$$ |  $$ |   
$$ |$$$/ $$ |$$ \__$$ |$$ \__$$ |$$$$$$$$/ $$ |/$$$$$$$ |$$ |  $$ |$$ \__$$ |$$ \__$$ |   
$$ | $/  $$ |$$    $$/ $$    $$ |$$       |$$ |$$    $$ |$$ |  $$ |$$    $$ |$$    $$/    
$$/      $$/  $$$$$$/   $$$$$$$/  $$$$$$$/ $$/  $$$$$$$/ $$/   $$/  $$$$$$$/  $$$$$$/     
                  ______                                                                  
                 /      \                                                                 
  ______        /$$$$$$  |  ______   _______    _______  __    __  _____  ____    ______  
 /      \       $$ |  $$/  /      \ /       \  /       |/  |  /  |/     \/    \  /      \ 
/$$$$$$  |      $$ |      /$$$$$$  |$$$$$$$  |/$$$$$$$/ $$ |  $$ |$$$$$$ $$$$  |/$$$$$$  |
$$ |  $$ |      $$ |   __ $$ |  $$ |$$ |  $$ |$$      \ $$ |  $$ |$$ | $$ | $$ |$$ |  $$ |
$$ \__$$ |      $$ \__/  |$$ \__$$ |$$ |  $$ | $$$$$$  |$$ \__$$ |$$ | $$ | $$ |$$ \__$$ |
$$    $$/       $$    $$/ $$    $$/ $$ |  $$ |/     $$/ $$    $$/ $$ | $$ | $$ |$$    $$/ 
 $$$$$$/         $$$$$$/   $$$$$$/  $$/   $$/ $$$$$$$/   $$$$$$/  $$/  $$/  $$/  $$$$$$/  
       __                  ________                                         __            
      /  |                /        |                                       /  |           
  ____$$ |  ______        $$$$$$$$/  _______    ______    ______   ______  $$/   ______   
 /    $$ | /      \       $$ |__    /       \  /      \  /      \ /      \ /  | /      \  
/$$$$$$$ |/$$$$$$  |      $$    |   $$$$$$$  |/$$$$$$  |/$$$$$$  /$$$$$$  |$$ | $$$$$$  | 
$$ |  $$ |$$    $$ |      $$$$$/    $$ |  $$ |$$    $$ |$$ |  $$/$$ |  $$ |$$ | /    $$ | 
$$ \__$$ |$$$$$$$$/       $$ |_____ $$ |  $$ |$$$$$$$$/ $$ |     $$ \__$$ |$$ |/$$$$$$$ | 
$$    $$ |$$       |      $$       |$$ |  $$ |$$       |$$ |     $$    $$ |$$ |$$    $$ | 
 $$$$$$$/  $$$$$$$/       $$$$$$$$/ $$/   $$/  $$$$$$$/ $$/       $$$$$$$ |$$/  $$$$$$$/  
 ________  __    __                __                            /  \__$$ |               
/        |/  |  /  |              /  |                           $$    $$/                
$$$$$$$$/ $$ | _$$ |_     ______  $$/   _______   ______          $$$$$$/                 
$$ |__    $$ |/ $$   |   /      \ /  | /       | /      \                                 
$$    |   $$ |$$$$$$/   /$$$$$$  |$$ |/$$$$$$$/  $$$$$$  |                                
$$$$$/    $$ |  $$ | __ $$ |  $$/ $$ |$$ |       /    $$ |                                
$$ |_____ $$ |  $$ |/  |$$ |      $$ |$$ \_____ /$$$$$$$ |                                
$$       |$$ |  $$  $$/ $$ |      $$ |$$       |$$    $$ |                                
$$$$$$$$/ $$/    $$$$/  $$/       $$/  $$$$$$$/  $$$$$$$/                                 
```

Este projeto realiza uma análise estatística e modelagem do consumo de energia elétrica residencial da cidade fictícia de **Solária**, com o objetivo de identificar os fatores climáticos que mais impactam a demanda energética ao longo dos meses.

---

## 📊 Dados Coletados

Foram analisados dados mensais das seguintes variáveis:

- 🌡️ Temperatura Média Mensal (°C)
- 🌧️ Precipitação Média Mensal (mm)
- ⚡ Consumo de Energia Elétrica Residencial (kWh)

| Mês       | Temperatura (°C) | Consumo (kWh) | Precipitação (mm) |
|-----------|------------------|---------------|-------------------|
| Janeiro   | 32               | 410           | 130               |
| Fevereiro | 31               | 400           | 85                |
| Março     | 29               | 380           | 190               |
| Abril     | 27               | 360           | 40                |
| Maio      | 24               | 340           | 75                |
| Junho     | 20               | 310           | 110               |
| Julho     | 18               | 300           | 60                |
| Agosto    | 22               | 320           | 125               |
| Setembro  | 26               | 355           | 95                |
| Outubro   | 28               | 370           | 160               |
| Novembro  | 30               | 390           | 50                |
| Dezembro  | 33               | 420           | 140               |

---

## 1. Análise de Correlação

Foi utilizado o **Coeficiente de Correlação de Pearson** para identificar relações entre as variáveis.

| Variável Comparada           | Coeficiente de Correlação (r) | Interpretação        |
|-----------------------------|-------------------------------|----------------------|
| Temperatura × Consumo       | **0.9945**                    | Correlação muito forte positiva ✅ |
| Precipitação × Consumo      | **0.2734**                    | Correlação fraca ❌ |

✅ **Conclusão**: O **consumo de energia** tem correlação significativa com a **temperatura média**.

---

## 2. Modelagem - Regressão Linear

A regressão linear simples foi aplicada para modelar a relação entre temperatura (variável independente) e consumo (variável dependente):

Equação do Modelo:

```
y = A + Bx
```

Coeficientes Obtidos:

- A (intercepto) = 145,46

- B (inclinação) = 8,15

Incertezas Calculadas:

- σᵀ (desvio dos dados): calculado com base nos resíduos.

- σᴀ (incerteza do intercepto) = ±7,37

- σᵁ (incerteza do coeficiente angular) = ±0,27

Equação Final com Incertezas:

```
y = (145{,}46 ± 7{,}37) + (8{,}15 ± 0{,}27) \cdot x
```

---

## 3. Visualização (Scilab)

### Objetivo:

Gerar o gráfico de dispersão entre consumo e temperatura, com a reta de regressão ajustada.

### 💻 Código Scilab:

```scilab
// Dados da Temperatura e Consumo
x = [32, 31, 29, 27, 24, 20, 18, 22, 26, 28, 30, 33];
y = [410, 400, 380, 360, 340, 310, 300, 320, 355, 370, 390, 420];

// Coeficientes da regressão
A = 145.46;
B = 8.15;

// Plot do gráfico de dispersão
scf(0); // Cria nova janela de figura
plot(x, y, 'o');
xtitle("Consumo de Energia vs Temperatura Média");
xlabel("Temperatura Média (°C)");
ylabel("Consumo de Energia (kWh)");

// Plot da reta de regressão
x_model = linspace(min(x), max(x), 100);
y_model = A + B * x_model;
plot(x_model, y_model, 'r-');

// Legenda
legend("Dados Observados", "Reta de Regressão");
```

### Imagem do Grafico:

![image](https://github.com/user-attachments/assets/8cae42da-50bd-403d-b290-027ab315f46a)


# Previsão de Estoque Inteligente na AWS com SageMaker Canvas  
Projeto criado para o Desafio da DIO — implementando um fluxo completo de Machine Learning No-Code utilizando o **Amazon SageMaker Canvas**.

---

## 📌 Objetivo do Projeto
O objetivo deste repositório é documentar detalhadamente todo o processo de criação de um modelo de **previsão de estoque** usando o SageMaker Canvas, seguindo as etapas do desafio da DIO.

Este repositório demonstra:

- Seleção e preparação do dataset  
- Importação no SageMaker Canvas  
- Configuração das variáveis  
- Treinamento do modelo  
- Avaliação das métricas  
- Geração de previsões  
- Insights obtidos  

---

## 🗂️ Estrutura do Repositório

```
lab-aws-sagemaker-canvas-estoque/
├── README.md
├── dataset/
│   └── estoque_exemplo.csv
└── imagens/
    └── exemplo_treinamento.png
```

---

## 1️⃣ Seleção do Dataset

Para este desafio, foi utilizado um dataset de exemplo baseado em histórico de vendas/estoque com as seguintes colunas:

- `data`  
- `produto`  
- `estoque_atual`  
- `vendas_dia`  
- `dias_para_reposicao`  
- `estoque_futuro` (variável alvo)

O arquivo está disponível na pasta **dataset/estoque_exemplo.csv**.

---

## 2️⃣ Construção e Treinamento do Modelo

Dentro do **SageMaker Canvas**, os passos realizados foram:

### ✔️ Upload do dataset  
O arquivo foi enviado diretamente para o Canvas.

### ✔️ Seleção das variáveis  
- Variável alvo (**Target**): `estoque_futuro`  
- Features utilizadas:
  - `estoque_atual`
  - `vendas_dia`
  - `dias_para_reposicao`
  - `produto` (Canvas converte para categórica automaticamente)

### ✔️ Tipo de modelo  
O Canvas automaticamente identificou como **Regressão**, apropriado para previsões numéricas.

### ✔️ Treinamento  
Foi iniciada a versão **Standard Build**, que gera um modelo preciso com maior profundidade de análise.

---

## 3️⃣ Análise do Modelo

Após o treinamento, o Canvas gerou:

### 🔍 Métricas
- RMSE: dentro do esperado  
- R²: considerado satisfatório para previsões de tendência  
- Correlação das variáveis  

### 🔍 Importância das Features
As variáveis mais relevantes foram:

1. `vendas_dia`
2. `estoque_atual`
3. `dias_para_reposicao`

---

## 4️⃣ Geração de Previsões

O modelo treinado foi usado para prever:

- Estoque futuro para novos dias  
- Possíveis rupturas de estoque  
- Itens com risco de faltar antes da reposição  

O Canvas permitiu exportar previsões em `.csv` para análise posterior.

---

## 📈 Insights Obtidos

- Produtos com maior rotatividade apresentaram previsões mais sensíveis a `vendas_dia`.  
- Foi possível identificar **pontos críticos de falta de estoque** com boa precisão.  
- O modelo pode ser expandido com novos dados, como:  
  - Promoções  
  - Sazonalidade  
  - Lead time real dos fornecedores  

---

## 📎 Repositório Original da DIO
https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque

---

## ✅ Conclusão

Este repositório completa o desafio proposto pela DIO, documentando todo o fluxo de criação de um modelo preditivo no **SageMaker Canvas**. O modelo gerado pode ser utilizado para apoiar decisões de reposição e estratégia de estoque em empresas de qualquer porte.

---

## ✨ Autor
Projeto desenvolvido por **Filipe** como parte dos estudos em AWS & Machine Learning.

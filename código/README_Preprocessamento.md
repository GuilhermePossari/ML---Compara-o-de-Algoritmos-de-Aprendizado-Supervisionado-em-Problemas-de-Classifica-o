# Trabalho de Aprendizado de Máquina - Parte B (Pré-processamento)

## 📋 Resumo do Trabalho Realizado

Este documento descreve o trabalho de **pré-processamento e análise exploratória** para o projeto de comparação de algoritmos de classificação em doenças cardíacas.

## 🗂️ Arquivos Entregues

### 1. **Notebook Principal**
- **Arquivo**: `preprocessamento_doencas_cardiacas.ipynb`
- **Descrição**: Jupyter Notebook completo com toda a análise exploratória e pré-processamento
- **Status**: ✅ Testado e funcionando perfeitamente

### 2. **Dados Pré-processados**
- **X_train.csv**: Features do conjunto de treino (734 amostras, 11 variáveis)
- **X_test.csv**: Features do conjunto de teste (184 amostras, 11 variáveis)
- **y_train.csv**: Target do conjunto de treino (734 amostras)
- **y_test.csv**: Target do conjunto de teste (184 amostras)

## 📊 Dataset Utilizado

- **Fonte**: Heart Disease Dataset (heart.csv) - Versão atualizada e expandida
- **Amostras**: 918 pacientes (3x mais que o UCI original)
- **Features**: 11 variáveis (idade, sexo, pressão arterial, colesterol, tipo de dor no peito, etc.)
- **Target**: Presença/ausência de doença cardíaca (binário: 0 = ausente, 1 = presente)
- **Balanceamento**: Dataset bem balanceado (55.3% com doença, 44.7% sem doença)
- **Qualidade**: Zero valores ausentes, dados limpos e consistentes

## 🔧 Pré-processamento Realizado

### ✅ **1. Tratamento de Valores Ausentes**
- **Antes**: 0 valores ausentes
- **Após**: 0 valores ausentes
- **Método**: Dataset já limpo (grande vantagem do heart.csv)

### ✅ **2. Codificação de Variáveis Categóricas**
- **Variáveis codificadas**: Sex (M/F → 1/0), ChestPainType (ATA/NAP/ASY/TA → 0/1/2/3), RestingECG, ExerciseAngina, ST_Slope
- **Método**: Label Encoding para variáveis ordinais

### ✅ **2. Tratamento de Outliers**
- **Variáveis tratadas**: `trestbps`, `chol`, `thalach`
- **Outliers removidos**: 15 total
- **Método**: Capping usando IQR (1.5 * IQR)

### ✅ **3. Normalização**
- **Variáveis normalizadas**: `age`, `trestbps`, `chol`, `thalach`, `oldpeak`
- **Método**: StandardScaler (média = 0, desvio padrão = 1)
- **Variáveis categóricas**: Mantidas como estão (já codificadas numericamente)

### ✅ **4. Divisão dos Dados**
- **Método**: Divisão estratificada 80/20
- **Treino**: 734 amostras (406 sem doença, 328 com doença)
- **Teste**: 184 amostras (102 sem doença, 82 com doença)
- **Random State**: 42 (para reprodutibilidade)

## 📈 Análise Exploratória Incluída

- ✅ Estatísticas descritivas completas
- ✅ Distribuição das variáveis (histogramas)
- ✅ Detecção de outliers (boxplots)
- ✅ Matriz de correlação
- ✅ Análise de variáveis categóricas vs target
- ✅ Visualizações antes/depois da normalização

## 🚀 Como Usar os Arquivos

### **Para o Henry (Pesquisa & Redação)**:
- Use o notebook como referência para escrever a metodologia
- As análises exploratórias estão documentadas com interpretações
- Dataset está caracterizado e justificado

### **Para o Possas (Modelagem & Resultados)**:
- Carregue os arquivos CSV diretamente:
```python
import pandas as pd

X_train = pd.read_csv('X_train.csv')
X_test = pd.read_csv('X_test.csv')
y_train = pd.read_csv('y_train.csv').iloc[:, 0]  # Primeira coluna
y_test = pd.read_csv('y_test.csv').iloc[:, 0]    # Primeira coluna
```
- Dados já estão prontos para algoritmos de ML
- Não precisa repetir pré-processamento

## 🔍 Validação Realizada

✅ **Todas as bibliotecas funcionando**  
✅ **Dataset carregado com sucesso**  
✅ **Pré-processamento sem erros**  
✅ **Arquivos CSV gerados corretamente**  
✅ **Dados balanceados e consistentes**  

## 📋 Próximos Passos

1. **Maeda**: Usar análises para escrever introdução e metodologia
2. **Possas**: Implementar algoritmos de classificação (mínimo 2)
3. **Todos**: Revisar e integrar as partes do trabalho final

## 🎯 Algoritmos Sugeridos para Implementação

- K-Nearest Neighbors (KNN)
- Random Forest
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- Naive Bayes

# 🚀 INSTRUÇÕES RÁPIDAS - USO DOS ARQUIVOS

## Para o Henry (Metodologia):
📖 **Use o notebook** `preprocessamento_doencas_cardiacas.ipynb` como referência para:
- Descrição do dataset (918 amostras, 11 features)
- Justificativa da escolha (Heart Disease Dataset atualizado - maior volume de dados)
- Metodologia de pré-processamento aplicada
- Métricas de balanceamento das classes

## Para o Possari (Algoritmos):
💻 **Código para carregar os dados prontos**:

```python
import pandas as pd
import numpy as np
from sklearn.metrics import accuracy_score, classification_report

# Carregar dados pré-processados
X_train = pd.read_csv('X_train.csv')
X_test = pd.read_csv('X_test.csv')
y_train = pd.read_csv('y_train.csv').iloc[:, 0]
y_test = pd.read_csv('y_test.csv').iloc[:, 0]

# Exemplo de uso com algoritmo
from sklearn.ensemble import RandomForestClassifier

# Treinar modelo
model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)

# Fazer predições
y_pred = model.predict(X_test)

# Avaliar
accuracy = accuracy_score(y_test, y_pred)
print(f"Acurácia: {accuracy:.3f}")
print(classification_report(y_test, y_pred))
```

## ✅ Checklist de Entrega:
- [ ] `preprocessamento_doencas_cardiacas.ipynb` ← Notebook completo
- [ ] `X_train.csv` ← Features de treino
- [ ] `X_test.csv` ← Features de teste  
- [ ] `y_train.csv` ← Target de treino
- [ ] `y_test.csv` ← Target de teste
- [ ] `README_Preprocessamento.md` ← Este arquivo

**Dados já estão limpos, normalizados e prontos para uso! 🎉**
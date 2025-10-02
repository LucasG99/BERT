# 🤖 Detecção de Bots em Tweets com BERT/DistilBERT

Este projeto implementa um pipeline de **NLP (Processamento de Linguagem Natural)** para detectar bots em postagens de redes sociais, utilizando modelos pré-treinados da família BERT.

---

## 📂 Estrutura do repositório
- `notebook.ipynb` → Notebook completo com pré-processamento, treino, avaliação e explicações.  
- `model_export_complete.keras` → Modelo salvo em formato Keras v3 (arquitetura + pesos).  
- `README.md` → Este arquivo.  

---

## 🚀 Metodologia
1. **Exploração dos dados**  
   - Balanceamento das classes  
   - Definição de `max_length` para tokenização  

2. **Tokenização com DistilBERT**  
   - Padding e truncamento para tamanho fixo  
   - Criação de datasets via `tf.data.Dataset`  

3. **Modelagem**  
   - Uso de `TFDistilBertModel` congelado  
   - Camada densa final para classificação binária  

4. **Treinamento**  
   - Poucas épocas (viável em Colab)  
   - Callback `EarlyStopping`  
   - Avaliação com métricas de acurácia, AUC, F1, além de gráficos  

5. **Comparação com baseline**  
   - TF-IDF + Regressão Logística  

---

## 📊 Resultados
- **Acurácia**: ~50%  
- **AUC**: ~0.51  
- O modelo não superou significativamente o baseline, mas mostrou a viabilidade do pipeline.  
- Thresholds alternativos (F1 e Youden) foram testados para analisar trade-offs entre precisão e recall.  
- Gráficos de **loss, acurácia, matriz de confusão e relatórios de classificação** estão disponíveis no notebook.  

---

## 🔮 Melhorias futuras
- Fine-tuning completo do DistilBERT ou modelos mais recentes (RoBERTa, BERTimbau).  
- Treino com mais épocas e dados adicionais.  
- Inclusão de **features não textuais** (ex: metadados do usuário, frequência de postagens).  
- Técnicas de balanceamento de classes e regularização.  

---

## 💾 Como carregar o modelo salvo
```python
from tensorflow.keras.models import load_model

## Como carregar e usar o modelo salvo

O modelo treinado foi exportado em formato **Keras 3 (`.keras`)**, que já inclui arquitetura + pesos.  
Isso significa que você pode abrir e usar o modelo sem precisar reconfigurar nada.

### Carregar o modelo
```python
from keras.models import load_model

# Baixar o arquivo do GitHub (exemplo via wget)
!wget https://github.com/LucasG99/BERT/raw/main/model_export_complete.keras

# Carregar o modelo
model = load_model("model_export_complete.keras", compile=False)

model = load_model("model_export_complete.keras", compile=False)
model.summary()

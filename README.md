# 🤖 Twitter Bot Detection com TinyBERT

Este projeto tem como objetivo treinar uma rede neural baseada em **TinyBERT** utilizando **Keras** para detectar contas automatizadas (bots) no Twitter.  
A implementação foi feita no **Google Colab** com base no dataset **Twitter Bot Detection** disponível no Kaggle.

---

## 📂 Estrutura do Projeto

- `bot_detection_data.csv` → Dataset utilizado (tweets e rótulo indicando se é bot ou humano).  
- `notebook.ipynb` → Notebook com todo o pipeline (pré-processamento, treino, avaliação e gráficos).  
- `TinyBERT_trained.zip` → Modelo TinyBERT treinado e salvo, pronto para reutilização.  
- `README.md` → Este arquivo de documentação.  

---

## ⚙️ Tecnologias Utilizadas

- **Python 3**  
- [TensorFlow](https://www.tensorflow.org/)  
- [Transformers (Hugging Face)](https://huggingface.co/transformers/)  
- **Pandas / Numpy / Scikit-learn**  
- **Matplotlib / Seaborn**  

---

## 🚀 Como Rodar o Projeto

1. Clone este repositório:
   ```bash
   git clone https://github.com/seuusuario/twitter-bot-detection.git
   cd twitter-bot-detection

Abra o notebook no Google Colab ou em ambiente local.
Certifique-se de ter GPU habilitada, se possível.

Instale as dependências:

pip install tensorflow transformers scikit-learn matplotlib seaborn pandas

Execute o notebook passo a passo.

📊 Resultados

Acurácia no conjunto de teste: ~0.50

Matriz de Confusão: o modelo classificou todas as amostras como "Humano", não identificando bots.

Curva ROC e AUC: ~0.51, indicando desempenho próximo ao acaso.

Curvas de Perda: estáveis em torno de 0.693, mostrando que o modelo não aprendeu padrões relevantes.

Exemplos de Gráficos

Matriz de Confusão
Mostrou que o modelo não conseguiu separar as classes.

Curva ROC
Linha próxima da diagonal, AUC ≈ 0.51.

Curva de Perda
Estagnada, sem indícios de aprendizado.

📌 Lições Aprendidas

Durante o desenvolvimento deste projeto, percebi que:

Trabalhar com modelos da família BERT exige muito mais do que apenas rodar código pronto: é necessário ajuste fino, balanceamento de classes e maior tempo de treino.

Nem sempre usar um modelo de ponta garante bons resultados se o dataset ou a configuração não forem adequados.

Resultados ruins também têm valor: eles mostram limitações e apontam os próximos passos para evolução do projeto.

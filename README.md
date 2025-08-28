# Projeto: Transfer Learning em Python (Colab)

## Objetivo
O objetivo deste projeto é aplicar a técnica de **Transfer Learning** utilizando **redes neurais profundas** com o framework **TensorFlow/Keras**.  
O modelo base utilizado foi o **MobileNetV2**, pré-treinado no dataset **ImageNet**, e adaptado para classificar imagens em **duas classes**.  

O exemplo implementado utiliza o dataset **Cats vs Dogs** do TensorFlow Datasets (TFDS), mas pode ser facilmente adaptado para qualquer conjunto de imagens de duas classes (por exemplo, fotos pessoais, objetos do dia a dia, etc).

---

## Metodologia
1. **Aquisição de dados**  
   - Opção A: uso do dataset público **Cats vs Dogs** (TFDS).  
   - Opção B: dataset customizado, organizado em duas pastas (uma por classe).  

2. **Pré-processamento**  
   - Redimensionamento das imagens para `224x224`.  
   - Normalização dos valores de pixel (`0-1`).  
   - Divisão em treino, validação e teste.  
   - Aplicação de **data augmentation** (flip horizontal, rotação, zoom).  

3. **Modelo de Transfer Learning**  
   - Base: **MobileNetV2** (`include_top=False`, pesos do ImageNet).  
   - Camadas adicionais:  
     - Global Average Pooling  
     - Dropout (regularização)  
     - Dense final com ativação *softmax*  

4. **Treinamento**  
   - **Fase 1:** congelamento da base pré-treinada.  
   - **Fase 2:** fine-tuning das últimas camadas da MobileNetV2.  
   - Otimização com Adam e taxa de aprendizado ajustada em cada fase.  

5. **Avaliação**  
   - Métricas: **accuracy**, **loss**.  
   - **Matriz de confusão** e **classification report** (precision, recall, F1).  

6. **Exportação do modelo**  
   - Formatos: `.keras`, `SavedModel` e `.tflite` (para dispositivos móveis).  

---

## Resultados
- O modelo apresentou **alta acurácia** no dataset de validação e teste.  
- Data augmentation e fine-tuning contribuíram para reduzir overfitting e melhorar a capacidade de generalização.  
- A matriz de confusão mostrou boa distinção entre as classes (gatos vs cães).  

*(Obs.: Os valores exatos de acurácia e métricas podem variar dependendo da execução no Colab e do dataset utilizado.)*

---

## Conclusão
O uso de **Transfer Learning** se mostrou eficiente para resolver um problema de classificação binária de imagens, mesmo com um número limitado de dados.  
A abordagem permite **reaproveitar conhecimento de redes pré-treinadas**, reduzindo o tempo de treinamento e a necessidade de hardware muito potente.  

Este projeto pode ser adaptado facilmente para outros domínios (como classificação de objetos pessoais, identificação de pessoas em fotos, etc), bastando trocar o dataset.  

---

## Estrutura do Repositório
```
transfer-learning-project/
├── Transfer_Learning_Cats_vs_Dogs.ipynb   # Notebook Colab
├── README.md                              # Documentação do projeto
└── (opcional) /samples                    # Exemplos de imagens
```

---

## Como executar no Colab
1. Faça upload do notebook `Transfer_Learning_Cats_vs_Dogs.ipynb` no Google Colab.  
2. Rode as células em ordem.  
3. Escolha na seção **1A (TFDS)** ou **1B (Drive)** a origem dos dados.  
4. O modelo será treinado, avaliado e exportado nos formatos indicados.  

---

## Referências
- [Cats vs Dogs (TFDS)](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs)  
- [Dataset Microsoft Research](https://www.microsoft.com/en-us/download/details.aspx?id=54765)  
- [Exemplo Transfer Learning (ml4a)](https://colab.research.google.com/github/kylemath/ml4a-guides/blob/master/notebooks/transfer-learning.ipynb)  
- [Documentação TensorFlow](https://www.tensorflow.org/)  

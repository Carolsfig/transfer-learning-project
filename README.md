# Projeto: Transfer Learning (Python + Colab)

Este projeto demonstra **Transfer Learning** com TensorFlow/Keras aplicando **MobileNetV2** em imagens de **duas classes**.
O exemplo padrão usa o dataset **Cats vs Dogs** via **TensorFlow Datasets (TFDS)**, mas você pode facilmente trocar por **seu próprio dataset** (duas classes).

## Como usar (no Colab)

1. Faça o upload do notebook `Transfer_Learning_Cats_vs_Dogs.ipynb` para o Google Colab.
2. Execute as células em ordem.
3. Na seção **1A**, rode com o TFDS (mais simples) **ou**:
   - Na seção **1B**, monte seu Google Drive e aponte `DATA_DIR` para a pasta com duas subpastas (uma por classe).
4. O notebook treina em duas fases (congelada + fine-tuning), plota curvas e exporta o modelo (Keras, SavedModel e TFLite).

## Estrutura sugerida do repositório

```
transfer-learning-project/
├── Transfer_Learning_Cats_vs_Dogs.ipynb
├── README.md
└── (opcional) /samples
```

## Subindo para o GitHub (linha de comando)

```bash
git init
git add Transfer_Learning_Cats_vs_Dogs.ipynb README.md
git commit -m "Transfer Learning project (Cats vs Dogs / custom)"
git branch -M main
git remote add origin https://github.com/<SEU_USUARIO>/<SEU_REPO>.git
git push -u origin main
```

> Se você usa GitHub Desktop ou a UI do GitHub, basta arrastar/soltar os arquivos e confirmar o commit.

## Adaptação para outras bases (duas classes)

- Utilize a seção **1B** do notebook, com `image_dataset_from_directory`.
- Mantenha a organização: `dataset/classA/...` e `dataset/classB/...`.
- Ajuste hiperparâmetros (`learning_rate`, `epochs`, `fine_tune_at`) se necessário.
- Você pode trocar a base pré-treinada (e.g., `EfficientNetB0`, `ResNet50`).

## Referências
- Cats vs Dogs (TFDS): https://www.tensorflow.org/datasets/catalog/cats_vs_dogs  
- Download (Microsoft Research): https://www.microsoft.com/en-us/download/details.aspx?id=54765  
- Exemplo (ml4a): https://colab.research.google.com/github/kylemath/ml4a-guides/blob/master/notebooks/transfer-learning.ipynb
```


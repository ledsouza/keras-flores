## Classificação de Flores Iris com Keras 💐

![Static Badge](https://img.shields.io/badge/Status-Finalizado-green)

## Descrição

Este projeto demonstra a construção de um modelo de Machine Learning utilizando a biblioteca Keras para classificar as espécies de flores Iris (Setosa, Versicolor e Virginica) com base em suas características. O modelo utilizado é uma Rede Neural Multi-Layer Perceptron (MLP).

## Tecnologias Utilizadas

- Python
- Keras
- TensorFlow (como backend do Keras)
- Scikit-learn (para carregar o dataset e pré-processamento)
- Matplotlib e Seaborn (para visualização dos dados)
- Pandas (para manipulação de dados)
- Plotly (para visualização interativa)

## Descrição Detalhada do Projeto

### Dataset

O projeto utiliza o famoso dataset Iris, que contém 150 amostras de flores Iris, divididas igualmente em três espécies: Setosa, Versicolor e Virginica. Cada amostra possui quatro características:

- Comprimento da sépala (cm)
- Largura da sépala (cm)
- Comprimento da pétala (cm)
- Largura da pétala (cm)

### Pré-processamento de Dados

1. **Categorização:** A variável alvo (espécie da flor) é convertida para uma representação categórica one-hot encoding utilizando `keras.utils.to_categorical`.
2. **Normalização:** As características são normalizadas para o intervalo [0, 1] utilizando o `MinMaxScaler` do Scikit-learn.
3. **Separação de Conjunto:** O dataset é dividido em conjuntos de treino (80%) e teste (20%) utilizando o `train_test_split` do Scikit-learn. A estratificação é utilizada para garantir a mesma proporção de classes em ambos os conjuntos.

### Modelo MLP

O modelo MLP é construído utilizando o `keras.Sequential`, que permite a criação de uma rede neural sequencial. O modelo possui as seguintes camadas:

1. **Camada de Entrada:** Define o formato de entrada com base nas características do dataset.
2. **Camada Oculta:** Uma camada densa com 512 neurônios e função de ativação ReLU. Os pesos são inicializados com `keras.initializers.RandomNormal`.
3. **Camada de Saída:** Uma camada densa com 3 neurônios (um para cada classe) e função de ativação Softmax.

### Treinamento

1. **Compilação:** O modelo é compilado utilizando:
    - Função de Perda: `categorical_crossentropy` (adequada para classificação multiclasse)
    - Otimizador: `rmsprop` (uma variante do gradiente descendente)
    - Métrica: `categorical_accuracy`
2. **Treinamento:** O modelo é treinado com os dados de treino por 100 épocas, utilizando 30% do conjunto de treino para validação.

### Avaliação

1. **Visualização do Aprendizado:** A perda e a acurácia durante o treinamento são plotadas para visualizar o aprendizado do modelo.
2. **Avaliação no Teste:** O modelo é avaliado no conjunto de teste utilizando o método `evaluate`.
3. **Predição:** Uma amostra de dados é utilizada para testar a predição do modelo.

## Resultados

O modelo MLP alcançou uma alta acurácia no conjunto de teste, demonstrando a capacidade da rede neural em aprender os padrões do dataset Iris e classificar as flores corretamente. A visualização do aprendizado mostra que o modelo não sofreu overfitting, já que a perda e a acurácia no conjunto de validação acompanharam o desempenho no conjunto de treino.

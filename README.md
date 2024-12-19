# Cálculo de Métricas de Avaliação de Aprendizado

## Descrição do Desafio
Neste projeto, vamos calcular as principais métricas para avaliação de modelos de classificação de dados, como acurácia, sensibilidade (recall), especificidade, precisão e F-score. Para que seja possível implementar estas funções, você deve utilizar os métodos e suas fórmulas correspondentes.

Para a leitura dos valores de VP, VN, FP e FN, será necessário escolher uma matriz de confusão para a base dos cálculos. Essa matriz você pode escolher de forma arbitrária, pois nosso objetivo é entender como funciona cada métrica.

### Tabela 1: Visão geral das métricas usadas para avaliar métodos de classificação. VP: verdadeiros positivos; FN: falsos negativos; FP: falsos positivos; VN: verdadeiros negativos; P: precisão; S: sensibilidade; N: total de elementos.

![Exemplo de Imagem](tabela.png)

## Implementação
O código abaixo realiza o cálculo das métricas mencionadas com base em uma matriz de confusão arbitrária.

```python
# Importar bibliotecas
import numpy as np

# Definir a matriz de confusão
VP = 50
VN = 100
FP = 5
FN = 10

# Função para calcular a acurácia
def calcular_acuracia(VP, VN, FP, FN):
    return (VP + VN) / (VP + VN + FP + FN)

# Função para calcular a sensibilidade (recall)
def calcular_sensibilidade(VP, FN):
    return VP / (VP + FN)

# Função para calcular a especificidade
def calcular_especificidade(VP, VN, FP, FN):
    return VN / (FP + VN)

# Função para calcular a precisão
def calcular_precisao(VP, FP):
    return VP / (VP + FP)

# Função para calcular o F-score
def calcular_f_score(precisao, sensibilidade):
    return 2 * (precisao * sensibilidade) / (precisao + sensibilidade)

# Calcular as métricas
acuracia = calcular_acuracia(VP, VN, FP, FN)
sensibilidade = calcular_sensibilidade(VP, FN)
especificidade = calcular_especificidade(VP, VN, FP, FN)
precisao = calcular_precisao(VP, FP)
f_score = calcular_f_score(precisao, sensibilidade)

# Exibir os resultados
print(f'Acurácia: {acuracia:.2f}')
print(f'Sensibilidade: {sensibilidade:.2f}')
print(f'Especificidade: {especificidade:.2f}')
print(f'Precisão: {precisao:.2f}')
print(f'F-score: {f_score:.2f}')


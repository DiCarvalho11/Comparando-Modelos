# Comparação de Modelos de Classificação

## Objetivo

- Comparar os seguintes modelos de classificação:
  * Árvore de Decisão com poda
  * K Vizinhos mais Próximos (KNN)
  * Regressão Logística
  * Floresta Aleatória
- Escolher o melhor modelo com base no desempenho em validação
- Avaliar o melhor modelo no conjunto de teste

## Etapas

1. **Carregar o dataset** 

2. **Separar os dados em treino, validação e teste** (60%, 20%, 20%)  

3. **Treinar os seguintes modelos:**

   a) **Árvore de Decisão com poda por complexidade**    
      - Para poda: use o método `cost_complexity_pruning_path`  
      - Varra diferentes valores de `ccp_alpha` e escolha o melhor na validação  

   b) **KNN (K-Nearest Neighbors)**   
      - Teste para `k = 3, 5, 10, 20`

   c) **Regressão Logística (sem ajustar hiperparâmetros)**    

   d) **Floresta Aleatória**  
      - Fixe `n_estimators=100`  
      - Teste combinações de `criterion = ['gini', 'entropy']` e `max_features = ['sqrt', 'log2', None]`

4. **Para cada modelo (usando apenas o conjunto de validação), calcule:**
   - Acurácia;
   - Precisão;
   - Recall;
   - F1-score.

5. **Monte uma tabela** com uma linha por modelo e colunas:  
   `'acuracia'`, `'precisao'`, `'recall'`, `'f1'`

6. **Escolha o melhor modelo com base nas métricas de validação.**  
   - Avalie esse único modelo no conjunto de teste.  

7. **Exiba as importâncias usando Floresta Aleatória:**  
   - Mostre um gráfico com as 20 variáveis mais importantes  

8. **Utilizando apenas as 5 covariadas mais importantes encontradas no item anterior, rode todos os modelos novamente e compare os melhores modelos encontrados usando todas as covariadas e os melhores modelos encontrados usando apenas as 5 mais importantes**

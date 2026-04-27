# IN1166-Aplicacoes-ML

Este repositório documenta a realização e implementação do projeto prático para apresentação na disciplina de **Aplicações de Machine Learning (IN1166)**.

## Sobre a Proposta do Projeto

O objetivo principal deste projeto propõe replicar e avaliar a metodologia de um artigo científico focado na **estimativa da Qualidade de Transmissão (QoT)** em redes de telecomunicações ópticas virtuais / simuladas. 

A variável alvo (*target*) focada é a **Relação Sinal-Ruído Óptica considerando ruído não-linear (`OSNRdB_NL`)**, que é uma métrica contínua vital para assegurar que a luz transmitida nos *spans* da fibra ótica chegue ao destino com estabilidade interpretável.

Para prever essa degradação física sem recorrer a fórmulas ou simuladores extremamente pesados, o cenário engloba um *pipeline* completo de Machine Learning focado em modelos de Regressão. No principal *notebook* do projeto (Experimento), testamos e desenhamos as seguintes arquiteturas para comparar ativamente os seus desempenhos:

1. **Support Vector Machine (SVR):** Treinada utilizando um *Radial Basis Function Kernel* robusto, excelente para traçar distâncias em mapeamentos paramétricos curvados e não lineares típicos de transmissões em redes ópticas.
2. **Redes Neurais Artificiais (ANN):** Constituída por múltiplas camadas densas (`ReLU` + `Sigmoidal`) projetadas no *framework TensorFlow/Keras* para convergir a previsão em frações de segundo aliada a um otimizador com regularização de pesos (*AdamW*).

## Estrutura
- **`data/`**: Contém a formatação e os ficheiros (ex. *opticalnetwork_dataset.csv*) utilizados como *input* das variáveis do sistema de simulações.
- **`experimento.ipynb`**: *Jupyter Notebook* central contendo análise exploratória de dados (EDA), seleção de *features*, limpeza da malha (*data leakage control*), código de treino independente, comparação visual empírica do Erro de Previsão na projeção geométrica dos resultados nos sets de *Test*.
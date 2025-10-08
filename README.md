# Flappy Bird com Inteligência Artificial 🐦

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-1d3c56?style=for-the-badge&logo=pygame&logoColor=white)
![NEAT](https://img.shields.io/badge/NEAT-AI-brightgreen?style=for-the-badge)

Este repositório contém o código-fonte de uma recriação do famoso jogo Flappy Bird, **desenvolvido com a turma de Back End do Programa Bolsa Futuro Digital (BFD) em Petrópolis.**

O projeto, construído em Python com a biblioteca Pygame, possui um modo de jogo tradicional e uma implementação de Inteligência Artificial que aprende a jogar sozinha usando o algoritmo genético **NEAT** (Neuroevolution of Augmenting Topologies).

O código foi aprimorado com correções e contribuições de **Felipe Maya**.

## ✨ Funcionalidades

-   **Modo de Jogo Clássico:** Jogue o Flappy Bird tradicionalmente, controlando o pássaro com a tecla `ESPAÇO`.
-   **Modo Inteligência Artificial:** Ative a IA para assistir a uma população de pássaros aprender, geração após geração, a desviar dos canos de forma autônoma.
-   **Física Realista:** Movimento de queda e pulo baseados em uma simulação de gravidade.
-   **Detecção de Colisão:** Implementação de máscaras de colisão (*masks*) para uma detecção precisa entre o pássaro e os obstáculos.
-   **Pontuação e Geração:** Acompanhe a pontuação no modo clássico e o número da geração atual no modo IA.

## 🛠️ Tecnologias Utilizadas

-   **[Python](https://www.python.org/)**: Linguagem de programação principal.
-   **[Pygame](https://www.pygame.org/news)**: Biblioteca utilizada para o desenvolvimento de jogos, responsável pelos gráficos, sons e controles.
-   **[NEAT-Python](https://neat-python.readthedocs.io/)**: Biblioteca que implementa o algoritmo NEAT para treinar a rede neural que controla os pássaros.

## 📁 Estrutura de Arquivos

Para que o jogo funcione corretamente, a estrutura de pastas deve ser a seguinte:

```
.
├── imgs/
│   ├── bird1.png
│   ├── bird2.png
│   ├── bird3.png
│   ├── pipe.png
│   ├── base.png
│   └── bg.png
├── config.txt
└── flappybird.py
```

-   **`imgs/`**: Pasta contendo todas as imagens (sprites) do jogo.
-   **`config.txt`**: Arquivo de configuração para o algoritmo NEAT, definindo os parâmetros da rede neural, população, mutações, etc.
-   **`flappybird.py`**: O código-fonte principal do jogo.

## 🚀 Como Executar

Siga os passos abaixo para rodar o projeto em sua máquina.

### 1. Pré-requisitos

-   Python 3.x instalado.
-   Git (opcional, para clonar o repositório).

### 2. Instalação

Primeiro, clone o repositório para a sua máquina local:
```bash
git clone [https://github.com/AugustoQueiroz13/Jogo-FlappyBirdPy.git](https://github.com/AugustoQueiroz13/Jogo-FlappyBirdPy.git)
cd Jogo-FlappyBirdPy
```

Em seguida, instale as dependências necessárias. É recomendado criar um ambiente virtual.
```bash
# Crie e ative um ambiente virtual (opcional, mas recomendado)
python -m venv venv
# No Windows:
venv\Scripts\activate
# No Linux/Mac:
source venv/bin/activate

# Instale as bibliotecas
pip install pygame neat-python
```

### 3. Escolhendo o Modo de Jogo

Para alternar entre o modo manual e o modo com Inteligência Artificial, você precisa editar uma variável no início do código.

#### **Para Jogar Manualmente (IA Desabilitada)**

1.  Abra o arquivo `flappybird.py` em um editor de texto.
2.  Encontre a seguinte linha no início do código:
    ```python
    ai_jogando = True 
    ```
3.  **Altere seu valor para `False`**:
    ```python
    ai_jogando = False
    ```
4.  Salve o arquivo e execute o script no seu terminal:
    ```bash
    python flappybird.py
    ```
5.  Use a tecla `ESPAÇO` para pular.

#### **Para Treinar a Inteligência Artificial**

1.  Abra o arquivo `flappybird.py`.
2.  Garanta que a variável `ai_jogando` esteja definida como `True`:
    ```python
    ai_jogando = True
    ```
3.  Salve o arquivo e execute o script:
    ```bash
    python flappybird.py
    ```
4.  Observe a IA aprender. O terminal exibirá as estatísticas de cada geração.

## 🧠 Como a IA Funciona?

A Inteligência Artificial utiliza o algoritmo **NEAT**, que simula a evolução biológica.
1.  **População Inicial:** Uma população de pássaros é criada, cada um com um "cérebro" (rede neural) aleatório.
2.  **Inputs:** Cada pássaro recebe informações sobre o ambiente, como sua própria altura e a distância para os próximos canos.
3.  **Output:** Com base nesses inputs, a rede neural decide se o pássaro deve pular ou não.
4.  **Fitness:** Os pássaros que sobrevivem por mais tempo e atravessam mais canos recebem uma pontuação de "fitness" maior.
5.  **Evolução:** Ao final de cada geração (quando todos os pássaros morrem), os pássaros com maior fitness são selecionados para "reproduzir", criando a próxima geração. Seus cérebros são combinados e sofrem pequenas mutações, permitindo que a população melhore a cada ciclo.

## ⭐ Créditos

-   **Desenvolvedores:** Turma de Back End do Programa Bolsa Futuro Digital (BFD) - Petrópolis.
-   **Professor:** Augusto Queiroz
-   **Correções e Contribuições:** do aluno Felipe Maya
  
Este projeto foi inspirado em diversos tutoriais da comunidade de desenvolvimento de jogos em Python.

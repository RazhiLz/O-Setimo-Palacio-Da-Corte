<img src="o palhaço.png" alt="Texto alternativo" width="300"/>



# 🃏 O Sétimo Palácio da Corte 🃏

Um jogo de cartas estratégico e emocionante!

## 📜 A História 📜

Em um reino distante, onde a magia e a intriga se entrelaçam, existe uma lenda sobre o Sétimo Palácio da Corte. Dizem que este palácio, escondido entre as brumas do tempo, guarda segredos ancestrais e um poder inimaginável. Apenas aqueles com astúcia, coragem e a sorte dos deuses podem desvendar seus mistérios.

A cada século, um torneio é realizado para selecionar os mais dignos de tentar a sorte no Sétimo Palácio. Os competidores, nobres e plebeus, enfrentam desafios que testam suas habilidades e sua capacidade de tomar decisões cruciais. O objetivo final é encontrar as três cartas Joker, símbolos do poder supremo, que lhes concederão o controle do palácio e seus segredos.

Mas a jornada não é fácil. O palácio é protegido por armadilhas mágicas e guardiões implacáveis. Além disso, a competição é acirrada, e os jogadores devem estar preparados para eliminar seus rivais e garantir sua própria sobrevivência.

A lenda diz que apenas um pode emergir vitorioso. Será você o escolhido para desvendar os segredos do Sétimo Palácio da Corte?

## 🎮 Como Jogar 🎮

1.  **Início:** O jogo começa com 5 jogadores e a fase de 20 cartas.
2.  **Objetivo:** Encontre 3 cartas Joker para vencer!
3.  **Jogando:**
    *   Clique nas cartas para revelá-las.
    *   Se encontrar um Joker, ele é adicionado à sua coleção.
    *   Se encontrar 7 cartas normais, você é eliminado!
    *   Reis e Rainhas dão a você outra chance de jogar.
4.  **Fases:**
    *   **Fase 1 (20 cartas):** Encontre os dois primeiros Jokers para avançar.
    *   **Fase 2 (8 cartas):** Apenas os jogadores com Jokers avançam. Encontre os dois Jokers restantes para avançar.
    *   **Fase 3 (4 cartas):** Encontre o último Joker para vencer!
5.  **Vitória:** Seja o primeiro a coletar 3 cartas Joker!

## 🏗️ Estrutura do Jogo 🏗️

O jogo é estruturado em componentes React, com a lógica principal gerenciada no componente `App.tsx`.

*   `App.tsx`: Componente principal que gerencia o estado do jogo e a lógica de transição entre as fases.

    *   **Estado do Jogo:** O componente utiliza `useState` para gerenciar o estado do jogo, incluindo:
        *   `phase`: A fase atual do jogo ('20cards', '8cards', etc.).
        *   `cards`: Um array de objetos `Card` que representam as cartas no tabuleiro.
        *   `players`: Um array de objetos `Player` que representam os jogadores no jogo.
        *   `currentPlayerIndex`: O índice do jogador atual no array `players`.
        *   `gameStarted`: Um booleano que indica se o jogo começou ou não.
    *   **Lógica de Inicialização:** A função `initializeGame` cria os jogadores, define a fase inicial, cria o baralho e define o jogador atual.
    *   **Lógica de Clique na Carta:** A função `handleCardClick` é o ponto central da lógica do jogo. Ela lida com o que acontece quando um jogador clica em uma carta:
        *   Revela a carta.
        *   Adiciona a carta ao jogador atual.
        *   Verifica se o jogador encontrou um Joker e atualiza o estado do jogo de acordo.
        *   Verifica se o jogador foi eliminado por ter muitas cartas normais.
        *   Avança para o próximo jogador (a menos que a carta seja um Rei ou Rainha).
    *   **Transições de Fase:** A lógica para avançar entre as fases é complexa e envolve a verificação de várias condições, como o número de Jokers encontrados e o número de jogadores restantes.
*   `GameBoard.tsx`: Componente que exibe o tabuleiro do jogo, as cartas e as informações dos jogadores.

    *   **Layout Responsivo:** O componente utiliza Tailwind CSS para criar um layout responsivo que se adapta a diferentes tamanhos de tela.
    *   **Exibição de Cartas:** O componente mapeia o array `cards` e renderiza um componente `Card` para cada carta.
    *   **Informações do Jogador:** O componente exibe informações sobre os jogadores, como seus nomes, número de cartas e se eles têm um Joker.
*   `Card.tsx`: Componente que representa uma única carta no jogo.

    *   **Animação de Flip:** O componente utiliza CSS transitions e transforms para criar uma animação de "flip" quando a carta é revelada.
    *   **Backface Visibility:** A propriedade `backface-visibility: hidden` é utilizada para esconder a parte de trás da carta quando ela está virada.
*   `types.ts`: Define os tipos de dados utilizados no jogo (Card, Player, GamePhase).

    *   **Tipagem Forte:** O uso de TypeScript permite que o código seja mais robusto e fácil de manter.
*   `utils/gameLogic.ts`: Contém funções utilitárias para criar o baralho, embaralhar as cartas e calcular as chances de vitória.

    *   **Criação do Baralho:** A função `createDeck` cria um baralho de cartas com base na fase atual do jogo.
    *   **Embaralhamento:** A função `shuffleArray` embaralha o baralho de cartas.
    *   **Cálculo de Chances de Vitória:** A função `calculateWinChance` calcula as chances de vitória com base na fase atual do jogo.

## 🛠️ Tecnologias Utilizadas 🛠️

*   React
*   TypeScript
*   Tailwind CSS
*   Vite
*   Lucide React (para ícones)

## 🚀 Como Executar o Projeto 🚀

1.  Clone o repositório
2.  Execute `npm install` para instalar as dependências
3.  Execute `npm run dev` para iniciar o servidor de desenvolvimento


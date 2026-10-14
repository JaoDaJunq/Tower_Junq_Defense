# Animações v1: João e Raposa

## Sequências

- `assets/animations/joao/idle/idle_01.webp` a `idle_06.webp`: ciclo de repouso em 6 quadros, com respiração e piscada. Cada quadro é um arquivo independente; canvas 192×288, alfa real e linha de base alinhada.
- `assets/animations/joao/attack/attack_01.webp` a `attack_08.webp`: antecipação, corte e retorno à guarda em 8 quadros independentes; canvas 192×288, alfa real e linha de base alinhada. O efeito de corte continua separado em `assets/slash.webp`.
- `assets/animations/raposa/walk/walk_01.webp` a `walk_06.webp`: ciclo de corrida em 6 quadros independentes; canvas 186×160, alfa real e base alinhada.

As poses foram produzidas com geração de imagem a partir dos sprites aprovados e normalizadas para o mesmo canvas, escala e pivô. São assets autorais gerados para este projeto, sem dependências de assets externos ou atribuição externa.

## Estado e QA

- Estado: integrado no protótipo.
- Prévia foi enviada quadro a quadro no chat durante a produção.
- Integridade alfa e dimensões de todos os arquivos foram verificadas localmente.
- A lógica alterna os quadros individuais em runtime sem atlas/spritesheet: idle a cada 180 ms, ataque ao longo de 560 ms e caminhada a cada 105 ms. Movimento no mapa continua sendo atualizado por tempo delta.
- A prévia em navegador e a leitura em tela móvel ainda precisam de conferência visual após publicar o commit.

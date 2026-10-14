# Fluxo de arte, assets e animação

Este documento define como produzir e integrar a arte do Tower Junq Defense. Ele existe para proteger os designs aprovados e evitar os problemas que já apareceram em outros jogos: spritesheet recortada errado, transparência falsa, variação de tamanho entre personagens, direção incoerente, membro que some entre frames e ataques sem arte própria.

## Direção visual aprovada: Mar de Origami

O conceito B foi escolhido pelo usuário em 14/10/2026. Esta aprovação fixa a direção geral do mundo e da arte, não os sprites finais nem todas as decisões de gameplay. Veja [a bíblia visual](art/ART_BIBLE.md).

- Mundo original formado por ilhas e ondas de papel dobrado, com linguagem visual inspirada em origami e referências japonesas.
- João aparece neste conceito como navegador de papel, com cabelo preto e uma mecha azul, óculos, capa azul/coral e um pincel de caligrafia. Este é um estudo conceitual, não o model sheet final.
- Primeiro inimigo conceitual: uma raia de origami feita de tinta preta.
- Direção de cor inicial: azul-cobalto, papel marfim, coral e tinta preta; os tons exatos podem ser refinados no model sheet.
- A rota de defesa pode usar dobras do mar e ilhas de papel; plataformas inspiradas em origami ainda precisam de validação de gameplay.
- A câmera, a proporção final da tela, os papéis dos personagens, a história e as animações ainda não foram aprovados.

A identidade não deve retornar automaticamente ao pixel art chibi, cenário urbano ou equipamento de outros jogos. Use o concept aprovado como ponto de partida e crie os personagens e mapas deste projeto para esta proposta.

Não copie personagens, sprites, UI, nomes, efeitos ou identidade de jogos comerciais usados como referência. Referências públicas servem para aprender estrutura e legibilidade. Registre origem, autor e licença de todo asset externo; “público” e “gratuito” não significam automaticamente reutilizável.

## Etapas com portões de aprovação

### 0. Brief visual e função de jogo

Antes da arte, registre para cada unidade:

- Nome e papel no combate.
- Referências aprovadas e traços que não podem mudar.
- Câmera, escala relativa, paleta e nível de detalhe.
- Se fica parada ou se move; orientação de idle e direções de ataque.
- Ataque básico, habilidade, projétil e leitura visual do alcance/impacto.
- Estados realmente necessários para o gameplay.

Se um dado ainda não existir, faça uma proposta curta e marque como pendente. Não invente que ela já foi aprovada.

### 1. Bíblia visual e model sheet

Defina o padrão compartilhado do elenco: proporção chibi, tamanho relativo, perspectiva, contorno, paleta, nível de pixel, iluminação, baseline e origem/pivô.

Apresente primeiro o design parado em vistas úteis para o jogo, com paleta e silhueta legíveis. Mostre separadamente versões alternativas quando houver escolha visual. Aguarde aprovação do modelo do personagem antes de produzir animações em lote.

### 2. Personagem piloto

Complete um personagem do início ao fim antes de expandir para o elenco:

1. Sprite base aprovado.
2. Idle curto.
3. Ataque básico com antecipação, ação e recuperação suficientes para o golpe ser legível.
4. Projétil/arma, telegráfico, impacto e VFX necessários, em artes separadas.
5. Habilidade especial.
6. Estados adicionais apenas se o jogo exigir, como dano ou derrota.

Uma unidade fixa não precisa de caminhada. Um inimigo que percorre caminhos precisa de orientação compatível com o movimento. Não espelhe automaticamente sprites assimétricos sem conferir arma, cabelo, roupa, marca e mão dominante.

### 3. Aprovação de cada animação

Para cada estado, entregue:

- Frames individuais numerados e uma prancha em ordem.
- Prévia animada em GIF ou vídeo curto.
- Indicação de duração/velocidade e se o loop é contínuo ou de execução única.
- Fundo transparente real nos PNGs finais.
- Uma descrição breve do que o movimento comunica.

Aprovação do modelo não aprova automaticamente uma animação. Confira os frames individualmente, especialmente braços, mãos, rosto, armas e silhueta em poses extremas.

### 4. Integração e teste dentro do jogo

Só integre assets aprovados. Teste na resolução/layout real e confirme:

- Escala aparente entre personagens e inimigos.
- Enquadramento completo, sem cortes em arma, cabelo, pés, efeitos ou sombra.
- Direção do corpo e do ataque em relação ao alvo.
- Leitura do ataque sobre diferentes fundos e em movimento.
- VFX separados, na posição correta, sem cobrir o personagem desnecessariamente.
- Funcionamento das animações no ritmo real do combate e no celular.

Se o frame parece bom isolado mas falha no jogo, volte ao asset ou à sua configuração e corrija antes de replicar o problema.

### 5. Produção em lote

Depois do piloto integrado e aprovado, replique o padrão para os outros personagens. Trabalhe por personagem e estado, mantendo uma matriz de progresso:

| Asset | Conceito | Frames | Prévia | Integrado | QA |
| --- | --- | --- | --- | --- | --- |
| Ex.: Jão / idle | pendente | pendente | pendente | pendente | pendente |

Nunca marque como aprovado algo que só foi gerado, sem conferência visual.

## Regras técnicas para arquivos

### Células e recorte

- Use canvas/célula de dimensões fixas dentro da mesma animação.
- Preserve margem transparente em volta da silhueta e não deixe conteúdo vazar para a célula vizinha.
- Mantenha pivô e linha de base consistentes. Para personagem em pé, use os pés como referência de alinhamento.
- Compare altura e largura do conteúdo visível, ignorando padding transparente. Elenco equivalente deve ter escala aparente consistente.
- A dimensão final da célula deve ser definida com um teste na tela do jogo. Não reduza a arte antes de validar legibilidade.

### Transparência e separação

- PNG final deve usar canal alfa real; não inclua padrão quadriculado como pixels.
- Mantenha personagem, arma destacável, projétil, impacto, telegráfico e VFX em arquivos separados quando precisarem de controle independente.
- Não substitua assets desenhados por formas/linhas de código como solução final. Formas de debug podem existir enquanto explicitamente temporárias.

### Organização e nomes

Adapte os diretórios ao projeto, sem misturar fontes com arquivos de build. Sugestão:

```text
assets/
  source/characters/<id>/<id>.aseprite
  source/effects/<id>/<id>.aseprite
  game/characters/<id>/<animation>/
  game/effects/<id>/
docs/art/
  ART_BIBLE.md
  ASSET_MANIFEST.md
```

Use nomes previsíveis em minúsculas, por exemplo:

```text
jao_idle_down_01.png
jao_attack_down_01.png
jao_special_lightning_01.png
jao_projectile_lightning_01.png
jao_impact_lightning_01.png
```

Mantenha o arquivo editável de origem (por exemplo, `.aseprite`), PNGs exportados e JSON/metadata do atlas. Registre no manifesto nome, status (proposto/aprovado/integrado), autor/origem, URL, licença e atribuição exigida.

## Checklist de QA obrigatório

Antes de considerar o asset pronto:

- [ ] Design corresponde ao modelo e às referências aprovadas.
- [ ] Transparência alfa foi verificada; não há fundo falso.
- [ ] Todos os frames têm canvas/célula e pivô consistentes.
- [ ] Nenhuma parte da silhueta foi cortada ou vazou para outra célula.
- [ ] Altura visível, pés e escala estão alinhados com o elenco.
- [ ] Rosto, corpo, arma e direção de movimento são coerentes.
- [ ] Nenhum membro ou equipamento desaparece sem intenção entre frames.
- [ ] Prévia foi assistida em velocidade normal e quadro a quadro.
- [ ] O efeito do ataque é uma arte própria e aparece separado quando necessário.
- [ ] Asset foi testado dentro do jogo, em tamanho real e no layout mobile.
- [ ] Origem e licença estão registradas; atribuição foi incluída quando exigida.
- [ ] Build/export carrega os arquivos finais, não uma cópia antiga ou placeholder.

## Regra de comunicação

Ao falar de assets e animações, informe claramente em qual etapa cada item está: proposta, aguardando aprovação, aprovado, em produção, integrado ou validado. Nunca chame concept de asset jogável, nem integração de validação visual. Se uma limitação impedir algum teste, diga exatamente qual verificação ficou pendente.

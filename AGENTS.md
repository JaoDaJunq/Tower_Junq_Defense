# Instruções do projeto

## Arte, sprites e animações

Antes de criar, editar, recomendar para integração ou implementar qualquer arte, sprite, animação, efeito visual, personagem ou mapa:

1. Leia [o fluxo de arte, assets e animação](docs/ART_ASSET_ANIMATION_PIPELINE.md).
2. Confira as decisões e assets já aprovados no histórico do projeto. Uma aprovação é permanente para aquele design; não substitua o asset aprovado por recoloração, filtro, placeholder ou versão semelhante.
3. Siga as etapas de aprovação e QA descritas no documento. Não avance de conceito para produção em lote sem validar o piloto visualmente, salvo quando o usuário autorizar explicitamente essa etapa.
4. Mantenha personagem, arma, projétil, impacto e efeitos como assets separados quando forem elementos diferentes. Arte final deve vir de arquivos de imagem; desenho via código serve apenas para debug e protótipo temporário.
5. Entregue arquivos prontos para integração, com nomes claros, origem/licença registrada quando aplicável e prévias que permitam conferir cada frame.

## Regras inegociáveis

- Preserve a identidade aprovada: silhueta, proporções, roupa, cores, acessórios, equipamento e lado de uso de armas.
- Use transparência alfa real nos assets finais. Um quadriculado desenhado não é transparência.
- Use quadros/células de dimensão consistente, pivô e linha de base alinhados, margem suficiente e silhueta inteira dentro do recorte.
- Normalize pela altura visível do personagem, não apenas pela dimensão do canvas. Personagens do mesmo elenco devem manter escala aparente coerente.
- Confira a direção do rosto, corpo, arma e deslocamento. Não publique animação em que personagem olha para um lado e se move para outro.
- Não una VFX ao personagem se o efeito deve ser independente. Não entregue atlas sem verificar recortes e animação.
- Não use um asset porque ele é público ou gratuito sem confirmar a licença e registrar os termos.
- A aprovação de um concept sheet não significa aprovação automática de todos os frames ou da integração final.

## Critério de conclusão

Uma tarefa de arte só está concluída após: revisão do arquivo em tamanho original, conferência quadro a quadro, prévia animada, checagem de transparência/recorte/alinhamento e teste visual dentro do jogo. Registre limitações que ainda não puderam ser verificadas.

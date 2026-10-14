# Protótipo jogável v1: Jardim da Lua

## Escopo

A primeira versão transforma em protótipo jogável o concept aprovado do Jardim da Lua, com João ronin como torre e a raposa de origami como inimigo. O mapa possui rota única, plataformas de posicionamento, ondas, selos, vidas e pausa/aceleração.

## Como jogar

1. Escolha o cartão **Ronin João**.
2. Toque em uma das plataformas de origami para posicionar uma torre. Cada torre custa 100 selos.
3. Posicione mais torres se desejar.
4. Inicie a onda. João escolhe automaticamente o inimigo mais avançado dentro do alcance e ataca com katana.
5. Raposas que chegam ao portal reduzem as vidas. Raposas derrotadas concedem selos.
6. Use pausa e velocidade 1×/1,5×/2× para controlar o teste.

## Implementado

- Mapa Jardim da Lua com arte ambiental própria.
- João e raposa como imagens raster independentes; PNG/WebP conserva canal alfa real nos personagens e VFX.
- Rota de gameplay, plataformas clicáveis, alcance da torre e telemetria básica.
- Ondas com dificuldade crescente, recompensa, vidas, pausa, aceleração e reinício.
- Corte de katana como asset separado.

## Estado e limites desta versão

É um primeiro protótipo visual e funcional, ainda sujeito a ajuste de leitura, equilíbrio, escala de tela e direção dos sprites. O João usa uma pose estática durante o golpe; a imagem do corte comunica o ataque. A raposa desliza pela rota sem ciclo de caminhada. Os alvos, custos, dano, vida e velocidades são valores temporários para teste.

Os concepts de **Atol das Dobras + Raia de Tinta**, **Bosque de Bambu de Papel + Besouro de Carapaça** e **Porto dos Torii + Lampião Errante** permanecem preservados como opções para fases futuras.

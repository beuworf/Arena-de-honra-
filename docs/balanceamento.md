# Balanceamento: classes contra inimigos e chefes

Teste automático feito com um robô que joga sozinho cada build. O robô anda
até o inimigo, alterna golpes e habilidades, mantém distância nas classes de
longe, esquiva de metade dos ataques e bebe poção abaixo de 35 de vida. Ele
**não** bloqueia, não aparara, não pega itens do chão nem combina habilidades
de forma esperta. Por isso, os números servem para **comparar classes entre
si**, não para medir o jogo de uma pessoa boa.

- **Chefe / Grande / Grupo:** tempo, em segundos de jogo, para matar 1 chefe
  do nível 1 (140 de vida), 1 inimigo grande (14 de vida) e um grupo de 8
  comuns. O jogador não morre nesse teste. "—" quer dizer que não conseguiu em
  120 s.
- **Sobrevive / Abates / Nível:** média de 3 partidas normais, do zero até
  morrer (limite de 600 s).

| Build | Chefe | Grande | Grupo de 8 | Sobrevive | Abates | Nível |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Espada e Escudo | 59 s | 4,2 s | 3,9 s | 100 s | 50 | 1 |
| Espada Longa | **19 s** | 2,1 s | 7,2 s | 125 s | 76 | 1 |
| Dois Machados | 61 s | 4,4 s | 2,2 s | 74 s | 45 | 1 |
| Arco | 26 s | 2,7 s | 4,9 s | 105 s | 96 | 1 |
| Lança + Urso | 41 s | 2,0 s | 3,1 s | 89 s | 55 | 1 |
| Adagas | 25 s | 2,6 s | 2,2 s | **256 s** | **289** | 1 |
| Mago (Fogo) | 63 s | 3,7 s | 4,6 s | 90 s | 44 | 1 |
| Mago (Gelo) | **—** | 12,1 s | **18,6 s** | **69 s** | **18** | 1 |
| Mago (Sombra) | **—** | **120 s** | 4,2 s | 158 s | 49 | 1 |
| Mago (Ilusão) | 41 s | 10,5 s | 7,7 s | 92 s | 74 | 1 |
| Paladino | 31 s | 5,8 s | 2,1 s | 139 s | 126 | 1 |
| Pugilista | **74 s** | **11,3 s** | 4,6 s | 110 s | 51 | 1 |
| Necromante | 47 s | 3,2 s | 6,3 s | 103 s | 55 | 1 |

## Dano recebido por tipo de inimigo (média por partida)

O **arqueiro inimigo** é a maior fonte de dano em quase todas as builds, em
geral 40% a 60% de todo o dano recebido. O chefe quase não machuca.

Os números completos estão em `docs/balanceamento.json`. Para rodar de novo:
`node tools/balanceamento.js`, que precisa de Playwright e de uma cópia
`lab.html` com os ganchos de teste.

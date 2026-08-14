# Auto-38zero

Automação em UiPath para o jogo [38-0 — Jogo de Draft do Brasileirão](https://38-0.com.br/) ("A
Campanha Perfeita"), um jogo de draft/simulação de futebol.

## O que faz

O projeto tem dois workflows (`entry-points.json`):

- **`Montar Time.xaml`** — abre o jogo no Chrome, navega até "Brasileirão" > "Pontos Corridos",
  percorre as opções de competição, escolhe o modo "Clássico"/"Estrelas ⭐" e monta o time
  automaticamente sorteando os jogadores ("Rolar o sorteio").
- **`Simular.xaml`** — inicia o campeonato com o time montado, avança automaticamente pelas
  simulações ("Direto ao fim", "Pular mesmo assim") e, ao final de cada partida, verifica o
  resultado (campeão ou eliminado) e repete a revanche com o mesmo time.

## Requisitos

- [UiPath Studio](https://www.uipath.com/product/studio) (schema versão 4.0 / Studio 26.0+).
- Dependências do projeto (restauradas automaticamente pelo Studio via `project.json`):
  - `UiPath.System.Activities` `25.10.3`
  - `UiPath.UIAutomation.Activities` `25.10.13`
- Google Chrome instalado (os workflows usam `Use Browser Chrome`).

## Como executar

1. Abra o projeto (`project.json`) no UiPath Studio.
2. Rode `Montar Time.xaml` para montar o time no jogo.
3. Rode `Simular.xaml` para simular o campeonato com o time montado.

Os workflows dependem da interface visual do jogo (seletores de UI Automation); mudanças no
layout do site podem exigir reajuste dos seletores no Studio.

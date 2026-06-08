# Mission Control AI — Artemis Deep Scan

Sistema em Python para simular o monitoramento básico de uma missão espacial experimental.

O programa analisa ciclos de telemetria da missão, calcula riscos, classifica o estado operacional e gera um relatório final no terminal.

## Missão

**Nome da missão:** Artemis Deep Scan  

## Integrantes

- Caio César Portela França - RM: 573127
- Gustavo Curis de Francisco - RM: 569704
- Tiago Pimentel Muniz - RM: 574148

## Objetivo

Monitorar uma missão simulada com base em cinco variáveis principais:

- Temperatura interna
- Comunicação com a base
- Sistema de energia
- Suporte de oxigênio
- Estabilidade operacional

A partir desses dados, o sistema identifica alertas, calcula pontuação de risco, classifica cada ciclo e apresenta recomendações automáticas.

## Estrutura dos dados

A matriz principal do sistema é `dados_missao`.

Cada linha representa um ciclo da missão.

Cada ciclo segue exatamente esta ordem:

```python
[temperatura, comunicacao, bateria, oxigenio, estabilidade]
```

Exemplo:

```python
[22, 95, 91, 98, 93]
```

Significado:

- Temperatura: 22 °C
- Comunicação: 95%
- Bateria: 91%
- Oxigênio: 98%
- Estabilidade: 93%

## Regras de classificação

Cada variável é classificada como:

- `NORMAL`
- `ATENÇÃO`
- `CRÍTICO`

Pontuação:

| Classificação | Pontos |
|---|---:|
| NORMAL | 0 |
| ATENÇÃO | 1 |
| CRÍTICO | 2 |

Como cada ciclo possui 5 variáveis, a pontuação máxima por ciclo é 10.

## Classificação do ciclo

| Pontuação | Classificação |
|---:|---|
| 0 a 2 | MISSÃO ESTÁVEL |
| 3 a 5 | MISSÃO EM ATENÇÃO |
| 6 a 10 | MISSÃO CRÍTICA |

## Funcionalidades

O sistema realiza:

- análise de temperatura;
- análise de comunicação;
- análise de bateria;
- análise de oxigênio;
- análise de estabilidade;
- cálculo de risco por ciclo;
- classificação automática de cada ciclo;
- geração de recomendações;
- análise da tendência da missão;
- identificação da área mais afetada;
- relatório final no terminal.

## Como executar

No terminal, rode:

```bash
python mission_control.py
```

## Arquivos do projeto

```text
mission-control-ai/
├── README.md
└── mission_control.py
```

## Saída esperada

O programa exibe no terminal:

- dados analisados por ciclo;
- status de cada variável;
- pontuação de risco;
- classificação do ciclo;
- recomendação automática;
- relatório final da missão.

## Observação

Os dados utilizados são simulados e servem para representar o funcionamento de um sistema básico de monitoramento de missão espacial.


# Template de Análise de Incidente

Este template auxilia na documentação estruturada de uma análise de
tráfego voltada à investigação de um possível incidente. Ele complementa o
[template de laboratório](lab-template.md) e segue a
[metodologia de análise de tráfego](../docs/network-analysis-methodology.md)
deste repositório.

> **Importante**: distinga sempre entre **fato observado**, **hipótese**,
> **inferência** e **conclusão confirmada** (ver seção específica ao final
> deste template). Não apresente hipóteses como se fossem conclusões.

## Contexto

Descreva o contexto geral: por que esta análise está sendo realizada, qual
o cenário do laboratório e qual o gatilho (real ou simulado) que motivou a
investigação.

## Escopo

Defina os limites da análise:

- Quais hosts, redes ou intervalos de tempo estão dentro do escopo.
- O que está explicitamente fora do escopo desta análise.

## Origem da captura

- Local/ambiente de captura:
- Interface de rede utilizada:
- Ferramenta utilizada (Wireshark, TShark, tcpdump etc.):
- Autorização/contexto de laboratório:

## Data e horário

- Data da captura:
- Horário de início:
- Horário de término:
- Fuso horário considerado:

## Hosts envolvidos

| Host/IP (anonimizado) | Papel | Observações |
|---|---|---|
| `<host-lab-01>` | | |
| `<host-lab-02>` | | |

## Linha do tempo

| Horário | Evento observado |
|---|---|
| `HH:MM:SS` | Descrição do evento (fato observado) |
| `HH:MM:SS` | Descrição do evento (fato observado) |

## Protocolos envolvidos

Liste os protocolos relevantes identificados durante a análise (ex.: TCP,
DNS, HTTP) e o papel de cada um no cenário investigado.

## Indicadores observados

Liste os indicadores técnicos identificados (ex.: portas incomuns,
retransmissões elevadas, respostas DNS com erro, conexões para hosts não
usuais), classificando cada um conforme a seção
[Fato, hipótese, inferência e conclusão](#fato-hipótese-inferência-e-conclusão-confirmada).

## Evidências

Referencie os pacotes, frames, timestamps e screenshots (anonimizados) que
sustentam cada indicador observado.

## Hipóteses

Descreva as hipóteses formuladas a partir dos indicadores observados,
deixando claro que ainda não foram confirmadas.

## Limitações

Descreva as limitações da análise (ex.: captura incompleta, ausência de
logs de outros sistemas, impossibilidade de inspecionar tráfego
criptografado).

## Conclusão

Apresente a conclusão da análise, indicando claramente o nível de
confiança (confirmada, parcialmente confirmada, inconclusiva).

## Recomendações

Liste recomendações práticas decorrentes da análise (ex.: ajustes de
configuração, necessidade de captura adicional, pontos de atenção para
monitoramento futuro).

## Fato, hipótese, inferência e conclusão confirmada

Para manter o rigor técnico da documentação, utilize sempre a
classificação abaixo:

- **Fato observado**: algo diretamente visível nos pacotes capturados
  (ex.: "o pacote 42 contém uma flag RST").
- **Hipótese**: uma possível explicação para um fato observado, ainda não
  verificada (ex.: "é possível que esse RST indique uma porta fechada no
  destino").
- **Inferência**: uma dedução baseada em múltiplos fatos observados, com
  razoável grau de confiança, mas ainda sujeita a revisão (ex.: "o padrão
  de RSTs sugere uma varredura de portas").
- **Conclusão confirmada**: uma afirmação sustentada por evidências
  suficientes e verificáveis dentro do escopo da análise (ex.: "os pacotes
  de 1 a 50 confirmam uma varredura sequencial de portas no host X").

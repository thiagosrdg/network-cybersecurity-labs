# Lab 01: ICMP Analysis

## Status

Planned

## Objetivo

Capturar e analisar tráfego ICMP gerado pelo comando `ping`, identificando
mensagens Echo Request e Echo Reply, e observando campos como endereços
IP, TTL, tipo e código ICMP. Também busca observar possíveis sinais de
perda de pacotes, latência elevada ou comportamento anormal na
comunicação.

## Conceitos abordados

- Protocolo ICMP (Internet Control Message Protocol).
- Mensagens Echo Request (tipo 8) e Echo Reply (tipo 0).
- Mensagens de erro ICMP (ex.: Destination Unreachable — tipo 3, Time
  Exceeded — tipo 11).
- Campo TTL (Time to Live) do cabeçalho IP.
- Relação entre `ping` e o protocolo ICMP.
- Filtros de captura e exibição específicos para ICMP.

## Ambiente

- Sistema operacional: `<preencher>`
- Versão do Wireshark: `<preencher>`
- Interface de rede: `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Cenário

`<Descrever o cenário utilizado para gerar o tráfego ICMP, por exemplo,
execução de ping entre dois hosts em uma rede de laboratório isolada.>`

## Procedimento

`<Descrever, passo a passo, como a captura foi realizada e como o comando
ping foi executado durante o laboratório.>`

## Filtros utilizados

### Capture filters

```text
icmp
```

### Display filters

```text
icmp
icmp.type == 8
icmp.type == 0
```

## Análise dos pacotes

`<Documentar aqui os pacotes relevantes observados durante a execução real
do laboratório: sequência de Echo Request/Reply, valores de TTL,
identificação (ICMP id/sequence) e tempos de resposta.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de captura correspondentes em captures/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável, após a execução do laboratório — por exemplo,
perda de pacotes incomum, TTLs inconsistentes ou respostas de hosts não
esperados.>`

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório.>`

## Conclusão

`<Preencher após a execução do laboratório.>`

## Referências

- [RFC 792 — Internet Control Message Protocol](https://www.rfc-editor.org/rfc/rfc792)
- [Documentação oficial do Wireshark](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)

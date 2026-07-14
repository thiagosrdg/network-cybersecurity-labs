# Lab 05: Suspicious Traffic Analysis

## Status

Planned

## Objetivo

Aplicar uma metodologia inicial de investigação de tráfego para
identificar conexões incomuns, observando portas, hosts, frequência de
comunicação, retransmissões e padrões anormais. O laboratório busca
documentar hipóteses de forma responsável, sem afirmar conclusões sem
evidências suficientes.

## Conceitos abordados

- Metodologia de investigação de tráfego (ver
  [docs/network-analysis-methodology.md](../../docs/network-analysis-methodology.md)).
- Diferença entre fato observado, hipótese, inferência e conclusão
  confirmada (ver
  [templates/incident-analysis-template.md](../../templates/incident-analysis-template.md)).
- Indicadores técnicos de possível comportamento suspeito (portas
  incomuns, RSTs frequentes, retransmissões, respostas DNS com erro).
- Limitações da análise baseada apenas em captura de pacotes.

## Ambiente

- Sistema operacional: `<preencher>`
- Versão do Wireshark: `<preencher>`
- Interface de rede: `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Cenário

`<Descrever o cenário utilizado para gerar ou obter o tráfego analisado,
deixando explícito que se trata de um ambiente de laboratório controlado
e/ou de tráfego sintético gerado para fins de estudo.>`

## Procedimento

`<Descrever, passo a passo, como a captura foi realizada e como a
investigação foi conduzida, incluindo a ordem de aplicação dos filtros.>`

## Filtros utilizados

### Capture filters

```text
Adicionar filtros de captura aqui, caso utilizados.
```

### Display filters

```text
tcp.flags.reset == 1
tcp.analysis.retransmission
dns.flags.rcode != 0
tcp.port == 4444
tcp.port == 8080
frame.len > 1500
```

## Análise dos pacotes

`<Documentar aqui os pacotes relevantes observados durante a execução real
do laboratório, aplicando a metodologia de análise progressiva descrita em
docs/network-analysis-methodology.md.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de captura correspondentes em captures/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório, classificando cada descoberta
como fato observado, hipótese, inferência ou conclusão confirmada.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável, após a execução do laboratório.>`

> **Observação importante**: o uso de uma porta específica (ex.: 4444 ou
> 8080) **não comprova**, isoladamente, atividade maliciosa. Portas
> incomuns são apenas um ponto de partida para investigação — todo
> indicador deve ser analisado dentro do contexto completo da comunicação
> (hosts envolvidos, volume de tráfego, protocolo real utilizado,
> frequência e demais evidências).

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório.>`

## Conclusão

`<Preencher após a execução do laboratório, deixando claro o nível de
confiança nas conclusões apresentadas.>`

## Referências

- [Documentação oficial do Wireshark](https://www.wireshark.org/docs/)
- [docs/network-analysis-methodology.md](../../docs/network-analysis-methodology.md)
- [templates/incident-analysis-template.md](../../templates/incident-analysis-template.md)

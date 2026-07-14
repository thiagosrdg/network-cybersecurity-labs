# Lab 03: TCP Three-Way Handshake

## Status

Planned

## Objetivo

Analisar o estabelecimento de conexões TCP, identificando as etapas do
*three-way handshake* (SYN, SYN-ACK e ACK), os números de sequência e
confirmação envolvidos, e observando possíveis retransmissões, resets ou
falhas de conexão.

## Conceitos abordados

- Protocolo TCP (Transmission Control Protocol).
- *Three-way handshake* (SYN, SYN-ACK, ACK).
- Números de sequência (`seq`) e confirmação (`ack`).
- Flags TCP (SYN, ACK, RST, FIN).
- Retransmissões e análise de erros (`tcp.analysis.*`).
- Encerramento de conexão (gracioso via FIN, abrupto via RST).

## Ambiente

- Sistema operacional: `<preencher>`
- Versão do Wireshark: `<preencher>`
- Interface de rede: `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Cenário

`<Descrever o cenário utilizado para gerar o tráfego TCP, por exemplo,
conexões estabelecidas entre um cliente e um servidor de laboratório em
uma porta específica.>`

## Procedimento

`<Descrever, passo a passo, como a captura foi realizada e como as
conexões TCP foram geradas durante o laboratório.>`

## Filtros utilizados

### Capture filters

```text
tcp
```

### Display filters

```text
tcp
tcp.flags.syn == 1
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.syn == 1 && tcp.flags.ack == 1
tcp.flags.reset == 1
tcp.analysis.retransmission
```

## Análise dos pacotes

`<Documentar aqui os pacotes relevantes observados durante a execução real
do laboratório: sequência completa do handshake, números de seq/ack em
cada etapa e eventuais falhas identificadas.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de captura correspondentes em captures/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável, após a execução do laboratório — por exemplo,
volume elevado de pacotes SYN sem conclusão do handshake (possível
half-open scan) ou RSTs incomuns.>`

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório.>`

## Conclusão

`<Preencher após a execução do laboratório.>`

## Referências

- [RFC 9293 — Transmission Control Protocol (TCP)](https://www.rfc-editor.org/rfc/rfc9293)
- [Documentação oficial do Wireshark](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)

# Lab 02: DNS Analysis

## Status

Planned

## Objetivo

Analisar consultas e respostas DNS capturadas em ambiente de laboratório,
identificando os nomes consultados, os tipos de registro envolvidos e os
códigos de resposta. O laboratório busca observar tanto o comportamento
normal de resolução de nomes quanto possíveis anomalias.

## Conceitos abordados

- Protocolo DNS (Domain Name System).
- Estrutura de consultas (queries) e respostas (responses).
- Tipos de registro (A, AAAA, CNAME, MX, entre outros).
- Códigos de resposta DNS (`rcode`), incluindo `NOERROR` e `NXDOMAIN`.
- Diferença entre resolução recursiva e iterativa (conceitual).
- Filtros de captura e exibição específicos para DNS.

## Ambiente

- Sistema operacional: `<preencher>`
- Versão do Wireshark: `<preencher>`
- Interface de rede: `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Cenário

`<Descrever o cenário utilizado para gerar o tráfego DNS, por exemplo,
resolução de nomes a partir de um host de laboratório contra um resolver
DNS controlado.>`

## Procedimento

`<Descrever, passo a passo, como a captura foi realizada e quais consultas
DNS foram geradas durante o laboratório.>`

## Filtros utilizados

### Capture filters

```text
port 53
```

### Display filters

```text
dns
dns.flags.response == 0
dns.flags.response == 1
dns.qry.name
dns.flags.rcode != 0
```

## Análise dos pacotes

`<Documentar aqui os pacotes relevantes observados durante a execução real
do laboratório: nomes consultados, tipos de registro, tempos de resposta e
eventuais códigos de erro retornados.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de captura correspondentes em captures/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável, após a execução do laboratório — por exemplo,
consultas para domínios incomuns, volume elevado de respostas `NXDOMAIN`
ou padrões de consulta atípicos.>`

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório.>`

## Conclusão

`<Preencher após a execução do laboratório.>`

## Referências

- [RFC 1035 — Domain Names, Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035)
- [Documentação oficial do Wireshark](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)

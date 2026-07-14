# Lab 01: Host Discovery and Port Scanning

## Status

Planned

## Objetivo

Realizar a descoberta de hosts ativos em uma rede de laboratório e
executar uma varredura básica de portas TCP, identificando portas
abertas, fechadas e filtradas, e compreendendo a diferença entre os
principais tipos de scan.

## Conceitos abordados

- Host discovery (`-sn`).
- TCP connect scan (`-sT`) vs. SYN scan (`-sS`).
- Estados de porta: `open`, `closed`, `filtered`.
- Interpretação básica da saída do Nmap.
- Relação entre um SYN scan e o *three-way handshake* do TCP (ver também
  o track [wireshark](../../../wireshark/labs/03-tcp-three-way-handshake/README.md)).

## Ambiente

- Sistema operacional (host de scanning): `<preencher>`
- Versão do Nmap: `<preencher>`
- Alvo(s) do scan (ambiente próprio/autorizado): `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Autorização

`<Confirmar explicitamente que o alvo do scan é um ambiente próprio ou
possui autorização documentada, conforme
docs/scanning-safety-and-ethics.md.>`

## Cenário

`<Descrever o cenário utilizado, por exemplo, uma rede de laboratório
isolada com uma ou mais máquinas virtuais próprias como alvo.>`

## Procedimento

`<Descrever, passo a passo, como o laboratório foi executado.>`

## Comandos utilizados

```text
nmap -sn 192.168.1.0/24
nmap -sT 192.168.1.10
nmap -p- 192.168.1.10
```

## Análise dos resultados

`<Documentar aqui os resultados relevantes observados durante a execução
real do laboratório: hosts descobertos, portas identificadas e seus
estados.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de saída correspondentes em outputs/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável — por exemplo, serviços inesperados em portas
não usuais.>`

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório.>`

## Conclusão

`<Preencher após a execução do laboratório.>`

## Referências

- [Documentação oficial do Nmap](https://nmap.org/book/man.html)
- [nmap/docs/scanning-safety-and-ethics.md](../../docs/scanning-safety-and-ethics.md)
- [nmap/resources/useful-commands.md](../../resources/useful-commands.md)

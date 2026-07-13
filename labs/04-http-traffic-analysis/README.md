# Lab 04: HTTP Traffic Analysis

## Status

Planned

## Objetivo

Analisar requisições e respostas HTTP capturadas em um ambiente
controlado, identificando métodos, códigos de status, cabeçalhos e
conteúdo transmitido. O laboratório também busca demonstrar, na prática,
os riscos do tráfego HTTP sem criptografia.

## Conceitos abordados

- Protocolo HTTP (Hypertext Transfer Protocol).
- Métodos HTTP (GET, POST, entre outros).
- Códigos de status HTTP (2xx, 3xx, 4xx, 5xx).
- Cabeçalhos HTTP relevantes (`Host`, `User-Agent`, `Content-Type`,
  `Authorization`, `Cookie`).
- Riscos de transmissão de dados em texto claro.
- Diferença entre HTTP e HTTPS/TLS (conceitual).

## Ambiente

- Sistema operacional: `<preencher>`
- Versão do Wireshark: `<preencher>`
- Interface de rede: `<preencher>`
- Topologia: `<preencher>`
- Máquinas virtuais: `<preencher>`
- Ferramentas auxiliares: `<preencher>`

## Cenário

`<Descrever o cenário utilizado para gerar o tráfego HTTP, por exemplo,
requisições feitas a um servidor web de laboratório com conteúdo e
credenciais fictícias.>`

## Procedimento

`<Descrever, passo a passo, como a captura foi realizada e quais
requisições HTTP foram geradas durante o laboratório.>`

## Filtros utilizados

### Capture filters

```text
tcp port 80
```

### Display filters

```text
http
http.request
http.response
http.request.method == "GET"
http.request.method == "POST"
http.response.code >= 400
```

## Análise dos pacotes

`<Documentar aqui os pacotes relevantes observados durante a execução real
do laboratório: requisições e respostas relevantes, métodos utilizados,
códigos de status e cabeçalhos observados.>`

## Evidências

`<Adicionar screenshots anonimizadas em screenshots/ e referenciar os
arquivos de captura correspondentes em captures/ quando o laboratório for
executado.>`

## Principais descobertas

`<Preencher após a execução do laboratório.>`

## Indicadores de comportamento suspeito

`<Preencher, se aplicável, após a execução do laboratório.>`

## Mitigações ou recomendações

`<Preencher, se aplicável, após a execução do laboratório — por exemplo,
recomendação de uso de HTTPS/TLS para qualquer tráfego que envolva dados
sensíveis.>`

## Conclusão

`<Preencher após a execução do laboratório.>`

## Referências

- [RFC 9110 — HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110)
- [Documentação oficial do Wireshark](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)

---

> ⚠️ **Aviso**: este laboratório deve ser realizado exclusivamente em
> ambiente controlado, utilizando credenciais e dados fictícios.
> **Credenciais, cookies e tokens reais nunca devem ser publicados** em
> capturas, screenshots ou nesta documentação. Veja
> [docs/packet-capture-safety.md](../../docs/packet-capture-safety.md).

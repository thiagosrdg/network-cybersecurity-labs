# Capture Filters vs Display Filters

O Wireshark utiliza dois tipos distintos de filtros, com sintaxes e
finalidades diferentes. Entender essa diferença é essencial antes de
iniciar qualquer laboratório.

## Diferença conceitual

| Aspecto | Capture Filter | Display Filter |
|---|---|---|
| Quando é aplicado | Antes/durante a captura | Depois da captura, sobre os pacotes já capturados |
| O que faz | Decide **quais pacotes são capturados** | Decide **quais pacotes já capturados são exibidos** |
| Sintaxe | Baseada em BPF (Berkeley Packet Filter) | Sintaxe própria do Wireshark (mais rica e granular) |
| Pode ser alterado depois? | Não — pacotes descartados na captura não podem ser recuperados | Sim — pode ser reaplicado quantas vezes for necessário |
| Onde é configurado | Nas opções de captura, antes de iniciar | Na barra de filtros, a qualquer momento |

Em resumo: **capture filters reduzem o volume de dados capturados**,
enquanto **display filters ajudam a navegar e investigar** os dados já
capturados. Em laboratórios de análise, é comum capturar de forma mais
ampla e refinar a investigação com display filters (ver
[wireshark-display-filters.md](wireshark-display-filters.md)).

## Sintaxe de capture filters (BPF)

Exemplos comuns:

```text
host 192.168.1.10
net 192.168.1.0/24
port 53
tcp port 443
udp port 53
icmp
src host 192.168.1.10
dst host 192.168.1.20
```

### Explicação rápida

- `host 192.168.1.10` — captura todo o tráfego de/para o host informado.
- `net 192.168.1.0/24` — captura todo o tráfego dentro da rede informada.
- `port 53` — captura tráfego (TCP ou UDP) na porta 53 (DNS).
- `tcp port 443` — captura apenas tráfego TCP na porta 443 (HTTPS).
- `udp port 53` — captura apenas tráfego UDP na porta 53 (DNS).
- `icmp` — captura apenas tráfego ICMP.
- `src host 192.168.1.10` — captura tráfego cuja origem seja o host
  informado.
- `dst host 192.168.1.20` — captura tráfego cujo destino seja o host
  informado.

## Boas práticas

- Utilize capture filters quando o volume de tráfego esperado for grande e
  o foco da análise já for conhecido (ex.: capturar apenas tráfego DNS).
- Evite capture filters excessivamente restritivos em laboratórios
  exploratórios — pacotes descartados na captura são perdidos
  definitivamente.
- Para investigações amplas ou exploratórias, prefira capturar sem filtro
  (ou com um filtro mínimo) e refinar a análise com display filters.
- Documente sempre qual capture filter (se houver) foi utilizado, para
  garantir a reprodutibilidade do laboratório.

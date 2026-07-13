# Filtros Úteis

Lista prática de filtros de exibição organizados por protocolo e
finalidade, para consulta rápida durante os laboratórios. Para a
explicação completa de cada categoria, veja
[docs/wireshark-display-filters.md](../docs/wireshark-display-filters.md).

## Diagnóstico geral

```text
ip.addr == 192.168.1.10
tcp.port == 443
udp.port == 53
frame.len > 1500
frame contains "erro"
```

## ICMP — conectividade e latência

```text
icmp
icmp.type == 8
icmp.type == 0
icmp.type == 3
icmp.type == 11
```

## DNS — resolução de nomes

```text
dns
dns.flags.response == 0
dns.flags.response == 1
dns.qry.name == "exemplo.com"
dns.flags.rcode != 0
```

## TCP — controle de conexão

```text
tcp
tcp.flags.syn == 1
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.syn == 1 && tcp.flags.ack == 1
tcp.flags.reset == 1
tcp.flags.fin == 1
tcp.analysis.retransmission
tcp.analysis.duplicate_ack
tcp.analysis.zero_window
```

## HTTP — tráfego web não criptografado

```text
http
http.request
http.response
http.request.method == "GET"
http.request.method == "POST"
http.response.code >= 400
```

## Investigação de tráfego suspeito

```text
tcp.flags.reset == 1
tcp.analysis.retransmission
dns.flags.rcode != 0
tcp.port == 4444
tcp.port == 8080
frame.len > 1500
```

> Lembrete: portas incomuns, isoladamente, **não comprovam** atividade
> maliciosa. Todo indicador deve ser analisado dentro do contexto da
> comunicação observada (ver
> [Lab 05](../labs/05-suspicious-traffic-analysis/README.md)).

## Combinações úteis

```text
ip.addr == 192.168.1.10 && tcp.port == 443
http.request && ip.src == 192.168.1.30
dns.flags.response == 1 && dns.flags.rcode != 0
tcp.flags.syn == 1 && tcp.flags.ack == 0 && ip.dst == 192.168.1.20
```
